# Steps to Create Project

## Materials Overview
- Raspberry Pi 4,
- DHT11 sensor (for temperature and humidity),
- Capacitative Soil Moisture Sensor v. 1.2 (for soil moisture level).
- Jumper cables 3x

## Wiring
To connect the DTH11 sensor to the Raspberry Pi, follow this diagram:

![image](https://github.com/AyeshaUllah/UnixGreenhouse/assets/123969109/514b1aa4-6d48-4fc2-811e-362775913bf6)

Source: Pi My Life Up | https://pimylifeup.com/raspberry-pi-dht11-sensor/

Here is our Raspberry Pi connected to the DHT11 sensor:

![rpi](https://github.com/AyeshaUllah/UnixGreenhouse/assets/123969109/0c7721c5-6e23-4a0c-84ec-4bf786d446ee)

## Preparing the Raspberry Pi
Using Raspberry Pi OS, flash the MicroSD of the Raspberry Pi 4 with Debian Bookworm (64-bit).  

Open the terminal. Update and upgrade the Raspberry Pi's packages by typing the following commands.
```
sudo apt update
sudo apt upgrade -y
```

Install the required packages for this project (Python 3, its package manager pip, and the Python virtual environment module) with the following command:
```
sudo apt install python3 python3-pip python3-venv
```

## Creating the Python Virtual Environment
Since we will be writing a Python script and using a Python virtual environment to run the DHT11 sensor, its best to create a separate directory to store all the required files.
```
mkdir ~/dht11
cd ~/dht11
```

Create a Python virtual environment.
```
python3 -m venv env
```

Activate the environment.
```
source env/bin/activate
```

Install the Adafruit DHT Library.
```
python3 -m pip install adafruit-circuitpython-dht
```

## Creating the Python Script
Create a .py file in which you will write the code which will be used to run the DHT11 sensor.
```
nano dht11.py
```

Within this file, write the following code:
```
import time
import adafruit_dht
import board

dht_device = adafruit_dht.DHT11(board.D4)

try:
    temperature_c = dht_device.temperature
    humidity = dht_device.humidity
    timestamp = time.strftime('%Y-%m-%d %H:%M:%S')

    print('Time: {} Temp:{:.1f} C Humidity:{}%'.format(timestamp, temperature_c, humidity))

except RuntimeError as err:
    print(err.args[0])

    time.sleep(2.0)
```

## Running the Python script
To run the Python script, type the following command into the terminal:
```
python3 dht11.py
```

## Automate the Python script using crontab
In order to ensure the Python script runs automatically, use crontab. 

Type the following command to create an automated task that will run periodically using the cron daemon:
```
crontab -e
```

At the bottom of the page, type the following command to append the output of the script to a file. Each asterisk represents the minutes, days, months, or weeks respectively of when you want the script to run. For the purposes of this project, we set it to run every 2 minutes to check if it was working.
```
*/2 * * * * ~/dht11.py >> /path/to/output/file.csv 2>&1
```

For our purposes, we also had to include the path to the Python3 interpretor within the Python environment, so that the script could be interpreted and run: 

To get the path of your Python3 interpretor, type the command:
```
which python3
```

And include that path in the previous command, like so: 

```
*/2 * * * * /path/to/your/python/interpreter ~/dht11.py.py >> /path/to/output/file.csv 2>&1
```
## Expected Output
If you followed the steps properly, your output should look something like this:

![436335409_826176778844902_7246741191479867343_n](https://github.com/AyeshaUllah/UnixGreenhouse/assets/130682851/ced8a7cf-0c77-4539-8bd6-86b13d72ed21)
