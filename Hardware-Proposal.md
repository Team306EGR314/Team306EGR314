*Hardware Proposal*

<img src="photosandvideos/Team 306 Schematic.png">

Fig. 16  Hardware Proposal

Microcontroller ESP32, and Switching regulator (Top Right)
	This part of the schematic includes the switching regulator, and microcontrollers. The device will be powered by the regulator TPS564247DRLR, which will aslo supply power to the PIC18F15Q41 and ESP32. The PIC will be programmed using the microchip Snap. The ESP32 module is used for WIFI access, and will be programmed using UART.

Temperature Sensor (Top Left)
	Receiving power from the switching regulator, this will be programmed using I2C. This will collect data inside the module. The info received will be in Celsius or Farenheit. This data will be sent back to the PIC microcontroller.



Humidity Sensor (Left middle)
	Receiving power from the switching regulator, this will be programmed using I2C. This will also be measured inside the module. The data will be collected in percentage. This data will be sent back to the microcontroller.

Motor Driver (Bottom Portion)
	Receiving power from the switching regulator, this will be programmed using SPI, The motor will receive information from the PIC18F15Q41 from the sensors, this will tell the motor when and how to move. The motor ideally will open the hatch on the module when the humidity and temperature get too high. The idea is that when cold air rushes in, it will lower both criteras and then the motor will close the hatch.
