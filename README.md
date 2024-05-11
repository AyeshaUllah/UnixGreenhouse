# UnixGreenhouse

------------------------------------------------------------------
Winter 2024 | Unix 420-321-VA 
------------------------------------------------------------------
PROJECT OVERVIEW:
In an era of technological domination and rapid urbanization, it’s important for us to always remember to make space for nature in our lives. A great way to do this is by keeping a garden, as, with the widespread use of pesticides in agriculture, many have already turned to keeping their own gardens in order to safely grow their own produce. Unfortunately, a large number of people forget, or don’t have time, to tend to their plants regularly, which results in said plants withering away, wasting the would-be gardener’s time and effort. Thus, our team would like to create a solution to help people monitor their plant(s)'s condition(s), so that people can easily know when their plants need attention, and so that more people can keep a touch of nature in their lives.

For our project, we have decided to create a plant monitoring system using a Raspberry Pi 4. Our project aims to help people keep track of their plant(s)'s condition(s) by collecting and storing information about various factors that could affect the plant(s), namely the temperature and humidity surrounding the plant(s), as well as the soil moisture level. We used a Raspberry Pi 4 as well as a DHT11 sensor to obtain the temperature and humidity values, and a Capacitative Soil Moisture Sensor v. 1.2 for the soil moisture level. 

One of our solutions that we had originally envisioned involved creating a plant watering system using a Raspberry Pi. The system would detect the moisture level of the plant’s soil. If dry, the system would proceed to water the plants for a specified period of time to ensure an adequate amount of water had been provided to the plant. If wet, the system would not water the plant. This is a simple solution; however we felt it did not fully ensure the plant(s)’s survival given its narrow scope of work. It also did not communicate much information regarding the plant(s)’s condition(s) to the owner. We planned to incorporate this system into our current solution, the more complete greenhouse system, however, doing so seemed to be too complex a task to complete within the time-frame we were given, as it involved woodworking. Thus, we decided to scrap the automated plant watering system, in favour of simply gathering data using sensors. 

(...)

Our final solution was influenced, in part, by a meeting we had with the Vanier gardening coordinator. In order to ensure we were creating a useful product, we arranged a meeting with him to ask questions that were relevant to our project. To see a transcript of our interview, please view the INTERVIEW file.

------------------------------------------------------------------
MATERIALS OVERVIEW:
1. Raspberry Pi 4,
2. DHT11 sensor (for temperature and humidity),
3. Capacitative Soil Moisture Sensor v. 1.2 (for soil moisture level).

(see INSTALL file for information on how to create the system.)
