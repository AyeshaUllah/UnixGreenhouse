# UnixGreenhouse (Winter 2024 | Unix | 420-321-VA)

## Project Overview  

For our project, we have decided to create a plant monitoring system using a Raspberry Pi 4. Our project aims to help people keep track of their plant(s)'s condition(s) by collecting and storing information about various factors that could affect the plant(s), namely the temperature and humidity surrounding the plant(s). We used a Raspberry Pi 4 as well as a DHT11 sensor to obtain the temperature and humidity values. 

## Modifications 

Our final project ended being different from our original idea. Certain features were changed or replaced due to either being less useful than what we originally thought they would be, or simply because we didn't manage to implement them. 

### Other Solutions

One of our solutions that we had originally envisioned involved creating a plant watering system using a Raspberry Pi. The system would detect the moisture level of the plant’s soil. If dry, the system would proceed to water the plants for a specified period of time to ensure an adequate amount of water had been provided to the plant. If wet, the system would not water the plant. This is a simple solution; however we felt it did not fully ensure the plant(s)’s survival given its narrow scope of work. It also did not communicate much information regarding the plant(s)’s condition(s) to the owner. We planned to incorporate this system into our current solution, the more complete greenhouse system, however, doing so seemed to be too complex a task to complete within the time-frame we were given, as it involved woodworking. Thus, we decided to scrap the automated plant watering system, in favour of simply gathering data using sensors. 

### Soil Moisture Level

When deciding which factors to measure, we had originally decided to measure the soil moisture level of the plant, in addition to the temperature and humidity. Unfortunately, we were not able to get the Capacitative Soil Moisture Sensor v. 1.2 to work. 

Since the sensor outputs analog data which cannot be read by a Raspberry Pi due to the latter's lack of an ADC (Analog to Digital Converter) circuit, we had to use another device to receive the data. 

At first, we attempted to use a Grove Pi+ component. Using the component required using the [GrovePi library](https://github.com/DexterInd/GrovePi). However, after cloning the library, we found we could not use it, as the reference to the user in the library was "pi@raspberrypi". Our raspberry pi was named "garden@raspberrypi", so we received errors when trying to run the code, as the home directory referenced in the library scripts did not match with our home directory. Even after asking for help from the teacher who created a "pi" user on the Raspberry Pi so that we could match the library scripts, we continued to receive errors. This is possibly due to the fact that since we had no pi user upon running the scripts, a "pi" reference had already been created with its own permissions. Upon creating a new "pi" user, that user could have inherited the permissions of the already created "pi", which prevented us from using it. 

Since, we did not want to re-flash our SD card just so that we could rename our root user, we decided to try using an Arduino to connect and receive the data from the sensor. We installed the Arduino IDE on the Raspberry Pi, and wrote the following script for the Arduino:

```
const int soilPin = ACM0; 
const int threshold = 500;

void setup () {
Serial.begin(9600); 
}

void 100p() {
int soilValue = analogRead(soilPin); // Read soil moisture value
Serial. println(soilValue); // Send value to Raspberry Pi delay (1000); 
}
```

We also wrote the follwing code for the Python Script that would run on the Raspberry Pi:

```
import serial

ser = serial. Serial('/dev/ttyAcM0', 9600) # Open serial port (adjust port as need
ser. flush()

while True:
  if ser.in_waiting > 0:
     data = ser. readline() decode(). strip()
     print("Soil moisture:", data)
```

Unfortunately, this also did not work. We made sure to check the connection between the Arduino and the Raspberry Pi as well as the Capacitative Soil Moisture Sensor using the following command: 

```
ls /dev/tty*
```

We found that our Arduino was listed under /dev/ttyACM0. This path also appeared when we checked the available ports in the Arduino IDE. However, when we ran the python script, it would not output anything. 

Perhaps we wrote the scripts or did the wiring incorrectly, or there might have simply been a problem with the sensor itself, regardless, we decided to scrap the soil moisture measurement.

### Email Notification

In terms of storing the information, we wanted to send it to the owner, in the form of an email notification. We would send the owner an email periodically, at regular intervals, to remind them to water their plant. However, after talking to the Vanier gardening coordinator who told us it would be more useful to have the data stored in a spreadsheet, we decided to scrap the email, and store all the data in a file instead.

Our final solution was influenced, in part, by a meeting we had with the Vanier gardening coordinator. In order to ensure we were creating a useful product, we arranged a meeting with him to ask questions that were relevant to our project. To see a transcript of our interview, please view the [INTERVIEW](INTERVIEW.md) file.

### Automated Script

We also decided to make it so that the Raspberry Pi could receive and store the temperature and humidity data automatically. Our final project uses crontab to run our Python script every 2 minutes, and redirect its output to the CSV file. This eliminates the need for the owner to run the system manually.

## Materials Overview
1. Raspberry Pi 4,
2. DHT11 sensor (for temperature and humidity),
3. Jumper wires.

(see [INSTALL](INSTALL.md) file for information on how to create the system.) 
