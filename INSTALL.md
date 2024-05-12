# Steps to Create Project
## Prepare the Raspberry Pi
Open the terminal. Update and upgrade the Raspberry Pi's packages by typing the following commands.
```
sudo apt update
sudo apt upgrade -y
```

Install the required packages for this project (Python 3, its package manager pip, and the Python virtual environment module) with the following command:
    sudo apt install python3 python3-pip python3-venv

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

Run the environment.
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

while True:
    try:
        temperature_c = dht_device.temperature
        temperature_f = temperature_c * (9 / 5) + 32

        humidity = dht_device.humidity

        print("Temp:{:.1f} C / {:.1f} F    Humidity: {}%".format(temperature_c, temperature_f, humidity))
    except RuntimeError as err:
        print(err.args[0])

    time.sleep(2.0)
```

## Running the Python script
To run the Python script, type the following command into the terminal:
```
python3 dht11.py
```
            
