<img src="photosandvideos/Software Proposal.drawio.png">

*Fig. 22  Software Proposal*

Based on Fig. 17, our device begins by initializing the system. This includes setting the hardware registers, resetting all internal variables, and establishing communication with the ESP32 and sensors. Once finished, the next step in the code is to enable interrupts. After that is done, the software code acquires the I2C addresses for both the temperature and humidity sensors and then writes out a byte to initialize both sensors. If no byte is returned, the code keeps trying until a byte is received from both sensors. If the byte value is acquired, the software then check the write out by the sensors. If either the temperature is below 80F and the humidity sensor is below 60%rh, the code tells the motor to spin clockwise, closing the vent. If either value exceeds the 80F or 60%rh, the code instructs the motor to drive counterclockwise, opening the vent. Once humidity and temperature drop below these values, the microcontroller will activate the motor to move clockwise, resealing the vent. This loop is monitored via UART which is sent out to both puTTY and MQTT.

##Top 5 Changes

The first change our team would implement would be to use proper I2C interrupts. Using proper interrupts would allow the code to run as smoothly as possible when talking with the I2C sensors.

The second change our team would make is to have higher integration with both sensors. As the code is, the only checked value is the temperature, with humidity being only as a readout. Having both integrated to the code to cause function would be optimal.

The third change our team would integrate would be the use of #define. Using this function would allow us as a team to streamline the constant call of the hexadecimal addresses to just simple letter phrases. 

The fourth change our team would pursue would be the proper implementation of MQTT. Having MQTT implemented properly into our code would allow us as a team to observe the ESP32 as it gathers information from our microcontroller. This is necessary because it’s a requirement for the course. 

The fifth change our team would implement would be the more prolific use of comments. Using comments would better log on what each block of code is doing or to what is expected out of the code. In addition, comments could help us in debugging on where the code could possibly be failing. 

##Version 2.0

Given a second chance, our team would want to implement more efficient code that would be able to run proper I2C interrupts. We realized too far into the project, that they would be necessary to the calling out to the sensors. We would also have liked to add a better UART interrupts as well. Going through the testing it was hard how to figure out how to talk to the micro controller. For instance, the Pickkit 4 is not recognized as a COM so you would have to transfer data to the ESP32, but you would have to know code to get something in the terminal in the first place. So it would have been better to add a button or some sort of input first in the code stage, or a better way to implement the debug led. The SPI was easier to understand, but also still no response on that end. We would’ve loved to see some integration of all the subsystems, but we couldnt get in contact with them in the first place, the SPI or the I2C. We wish we could’ve figured out why just because we spent so long on it. The different peripherals was what threw us off at first but if we were told the differences in clock settings it would have been helpful for like FOSC/4 and FOSC.
