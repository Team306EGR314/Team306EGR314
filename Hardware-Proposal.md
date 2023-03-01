**Hardware Proposal**

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

<img src="photosandvideos/Team 306 Power Budget.png">

	The team decided for a 7.6V 2S Lipo battery as a readily available and rechargeable power source. This battery has a 4500mAh capacity with a potential discharge of 1/25th of an hour. To get maximum current draw from the battery, simply the 4500mAh capacity multiplied by 25 gives a maximum draw of 112.5 Amps. Within our budget we only had one powered rail at 3.3V for our components. To achieve our desired 3.3V, 7.6V will be regulated down through the TPS564247DRL. The current usage of this switching regulator is only 0.12mA. Within our 3.3 volt rail, all components added together were less than a quarter of the potential current output of the TPS564247DRL at roughly 1000mA. This is a more than comfortable buffer for that entire rail. Total current usage between all components adds up to 837.19mA which is miniscule compared to the max amperage draw of the battery. Total battery life utilizing a single battery is a respectable 5.3 hours, but we may add a second battery in parallel to double that to something much more practical for the end user.
