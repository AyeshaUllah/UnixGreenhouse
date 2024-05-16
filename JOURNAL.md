#Journals

##Journal 1
###23/04/2024
After receiving the feed, I checked the internet for the process and things to set up when implementing our original project and the recommendations given to us. 

###24/04/2024 
After we received the feedback regarding our project, we had a discussion and decided to follow the advice given to us. Instead of developing an automated watering system suitable
for use in a greenhouse or personal garden, we opted to install a system that sends a notification to the plant owner when their plants require watering.

###30/04/2024
One of my team members created a Git repository and personal branches. Link: https://github.com/AyeshaUllah/UnixGreenhouse.git

###01/05/2024
We went to the STEM Center and were able to see the Raspberry Pi and understand more about what we need to start installing and booting the
system. Due to a jam-packed schedule that we had during that day, we couldn't do much and decided to continue it tomorrow after our exam. As we handed the Raspberry Pi
to the marker technician, he suggested a lot of things and even offered a hand to help us set up the Raspberry Pi

##Journal 2
###02/05/2024
Raebaa and I visited the STEM Center after class to borrow a Raspberry Pi and work on it. 
We installed Raspberry Pi OS and flashed the SD card with the 32-bit OS. In the setup 
settings, we enabled SSH connection and connected to the school Wi-Fi network.
However, we could not do more since Raeeba is not feeling well

###03/05/2024
We couldn't access the STEM center, so we worked on the teacher's Raspberry Pi. We 
had trouble flashing the drive, so we used school computers instead. But we 
encountered more errors when installing the Raspberry Pi OS due to a diMerent package 
name. Our teacher helped us successfully flash the SD card with a 64-bit OS. We 
connected the Raspberry Pi to the monitor, keyboard, and mouse to work on it and 
explored the OS, running some update commands in the terminal

###06/05/2024
Raeeba had a meeting with the gardening coordinator and she shared the conversation 
they had

1. General plant questions
a. What kind of plants do the Vanier Gardens have?
    The gardens are separated into three diMerent gardens with diMerent kinds of 
    plants in them:
    • The first (“the food forest”) contains perennial plants (i.e., trees, nuts, apples, 
    blackberries, etc.);
    • The second contains vegetables boxes (i.e., squash, corn, lettuce, etc.);
    • The third (“the no-mow zone”) contains pollinating flowers, and grain.
b. How often does each plant need to be watered?
   It depends on the weather conditions, as well as the plant.
c. What are the main diMerences between caring for houseplants and caring 
  for outdoors plants, like the ones in the Vanier Gardens

With indoor plants, the watering is 100% up to the owner. The diMerence between 
pots (i.e., size, materials, etc.) must also be considered. If creating a monitoring 
system for indoor plants, it would be better to give each pot its own sensors to 
measure its conditions, while for outdoor plants, we could place a few sensors 
to measure the conditions of a whole plot of land. Bugs are also harder to deal 
with indoors
d. Do diMerent plants have diMerent “safe” temperature and humidity 
  ranges?
  Yes, they do vary per type of plant. He is not aware of the exact figures
2. UI questions
  a. Would it be more useful for you to have the numerical values, or would a 
    text indictor (i.e., good temperature, bad humidity) be better?
    Since he is not aware of the exact figures of what would constitute a “good” or 
    “bad” measurement, and since plants’ temperature and humidity ranges vary, 
    the latter option would not be possible to do. We would have to find the safe 
    ranges for each specific plant, which would make the project more complex. He 
    is fine with receiving numerical data instead.
b. Since plants’ watering times vary, would it be useful for you to receive an 
  email notification reminding you to water your plants?
  If the email contains information about the plant’s condition, it could be useful. 
  He would find it more useful to have all the information recorded in a 
  spreadsheet, though. Since the Gardens double as an educational place, having 
  these records could be useful for classes who could study, for example, the 
  effect of global warming on plant life. (Note: while a general email reminder to 
  water your plants may not be useful for outdoor plants, they could be useful for 
  indoor ones)
3. Features that would be useful to have/possible future enhancements.
  a. Apart from the sensors we were already planning on adding (temperature, 
    humidity and soil moisture), what other features would be useful to have?
    Ways to measure windspeed, the amount of rainfall and sunshine a plot of land 
    receives would be useful. For the temperature and humidity sensor, obtaining 
    the soil temperature and humidity would be more useful to have than the air 
    temperature and humidity.
    We discussed more about our plans for our project, and he gave us some advice 
    on where we could put the Raspberry Pi. He also said that for the purposes of the 
    Vanier Gardens, having a Wi-Fi connection over the school’s Wi-Fi would be 
    better than a data plan.
###08/05/2024
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
chatgpt since all the tutorials we followed were not working. however, we are still 
experiencing the same error. We decided to bring it to the class the next day instead since 
we had been working on it for a couple of hour already and we were still stuck with those 
errors

##Journal 3
###09/05/2024
We successfully connected the DHT11 to the Raspberry Pi and got it to work. However, when 
we tried to connect the Capacitive Soil Moisture Sensor, it didn't work. We consulted the 
Makerspace technician, who informed us that we would need an additional component to 
obtain data from the sensor as it had an analog output, which our Raspberry Pi did not 
support.

###10/05/2024
We attempted to use a GrovePi+ to connect to and receive data from the sensor. However, 
we encountered an issue with the declaration of the home directory in the library scripts we 
were using, preventing us from fully installing the library for our sensor

###13/05/2024
We've successfully redirected the output of the DHT11 to a CSV file as suggested by the 
gardening coordinator. We chose not to set up email notifications as it seemed unnecessary 
compared to the CSV file, which records temperature and humidity fluctuations. 
Additionally, we've automated the script to run using crontab, so manual script running is no 
longer necessary.
We attempted to connect the soil moisture sensor to the Raspberry Pi using an Arduino, but 
unfortunately, we were unsuccessful. We have documented our experience and the steps 
we took on our GitHub repository (https://github.com/AyeshaUllah/UnixGreenhouse) in the 
modifications section of our README.md file.
