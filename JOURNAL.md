# Journals

These are a collection of the journals we wrote documenting the creation process of our project.

## Journal 1
### 23/04/2024
After receiving the feed, we checked the internet for the process and things to set up when implementing our original project and the recommendations given to us. 

### 24/04/2024 
After we received the feedback regarding our project, we had a discussion and decided to follow the advice given to us. Instead of developing an automated watering system suitable
for use in a greenhouse or personal garden, we opted to install a system that sends a notification to the plant owner when their plants require watering.

### 30/04/2024
Ayesha created a Git repository and personal branches. Link: https://github.com/AyeshaUllah/UnixGreenhouse.git

### 01/05/2024
We went to the STEM Center and were able to see the Raspberry Pi and understand more about what we need to start installing and booting the
system. Due to a jam-packed schedule that we had during that day, we couldn't do much and decided to continue it tomorrow after our exam. As we handed the Raspberry Pi
to the marker technician, he suggested a lot of things and even offered a hand to help us set up the Raspberry Pi

## Journal 2
### 02/05/2024
Raeeba and Janna visited the STEM Center after class to borrow a Raspberry Pi and work on it. 
We installed Raspberry Pi OS and flashed the SD card with the 32-bit OS. In the setup 
settings, we enabled SSH connection and connected to the school Wi-Fi network.
However, we could not do more since Raeeba is not feeling well

### 03/05/2024
We couldn't access the STEM center, so we worked on the teacher's Raspberry Pi. We 
had trouble flashing the drive, so we used school computers instead. But we 
encountered more errors when installing the Raspberry Pi OS due to a diMerent package 
name. Our teacher helped us successfully flash the SD card with a 64-bit OS. We 
connected the Raspberry Pi to the monitor, keyboard, and mouse to work on it and 
explored the OS, running some update commands in the terminal

### 06/05/2024
Raeeba had a meeting with the gardening coordinator and she shared the conversation 
they had. The transcript of their conversation can be found in the [INTERVIEW](INTERVIEW.md) file.
    
### 08/05/2024
We visited the STEM Center to borrow a Raspberry Pi and work on a project. The 
technician allowed us to take the Raspberry Pi until the end of the semester, which makes 
it easier for us to find time to work on the project. We also borrowed a monitor, keyboard, 
and mouse. We decided to re-flash the SD card with a 64-bit OS because it had more 
functionality and package availability compared to the 32-bit OS that was previously 
flashed. We changed the Wi-Fi connection to my data plan connection while adjusting 
the settings. After flashing the SD card, we connected the Raspberry Pi to the monitor, 
keyboard, and mouse. Then, we followed the Adafruit DHT11 Python Setup Guide. 
Unfortunately, this process didn't work as we received several errors, indicating that 
certain packages were not available and there was an issue with how the environment is
being managed or accessed. We attempted to follow other tutorials that used the same 
repository as the previous guide, but we still encountered the same errors. For the wiring, 
we found a diagram that helps us to connect the Raspberry Pi and the sensor but, we 
couldn’t do more since we are having trouble with the code. As a last resort, we consulted 
chatgpt since all the tutorials we followed were not working. However, we are still 
experiencing the same error. We decided to bring it to the class the next day instead since 
we had been working on it for a couple of hour already and we were still stuck with those 
errors

## Journal 3
### 09/05/2024
We successfully connected the DHT11 to the Raspberry Pi and got it to work. However, when 
we tried to connect the Capacitive Soil Moisture Sensor, it didn't work. We consulted the 
Makerspace technician, who informed us that we would need an additional component to 
obtain data from the sensor as it had an analog output, which our Raspberry Pi did not 
support.

### 10/05/2024
We attempted to use a GrovePi+ to connect to and receive data from the sensor. However, 
we encountered an issue with the declaration of the home directory in the library scripts we 
were using, preventing us from fully installing the library for our sensor

### 13/05/2024
We've successfully redirected the output of the DHT11 to a CSV file as suggested by the 
gardening coordinator. We chose not to set up email notifications as it seemed unnecessary 
compared to the CSV file, which records temperature and humidity fluctuations. 
Additionally, we've automated the script to run using crontab, so manual script running is no 
longer necessary.
We attempted to connect the soil moisture sensor to the Raspberry Pi using an Arduino, but 
unfortunately, we were unsuccessful. We have documented our experience and the steps 
we took on our GitHub repository (https://github.com/AyeshaUllah/UnixGreenhouse) in the 
modifications section of our README.md file.
