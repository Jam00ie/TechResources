## Arduino Shield Connections
The Grove Base Shield V2 is an Arduino compatible board with Grove ports. This component fits directly on top of the Arduino UNO ports allowing for connections to be easily made to grove seeeduino modules (sensors) and multiple I2C connections. 
1. 4 Analog Ports: A0, A1, A2 and A3. 
2. 7 Digital Ports: D2, D3, D4, D5, D6, D7 and D8. 
3. 1 UART Port: UART. 
4. I2C Ports: 4 I2C ports. 
5. Power Switch: when using Arduino UNO with Base Shield v2, **please turn the switch to 5v position.** This voltage is required for the shield to function, and is not meant to be changed at any point. If you need 3.3v for an external device, use the 3.3v port on the right side of the board in the blue rails.
6. Reset Buton: reset the arduino board. 
7. PWR LED: The Green LED turns on when power on. 

Each of the white connection ports is labelled with that port’s required connections. Each white port should only be connected to one sensor/module.  

The blue connection ports on the sides of the shield are directly above the ports they connect to on the Arduino. Please note that the white connection ports with the same name as a blue connection port are connected. This means if you have one sensor in the white D7 and another in the blue D7, they will interfere.

When connecting modules to the arduino, ensure wires are connected to the correct locations such that GND on the sensor goes to GND on the shield, VCC to VCC, SDA to SDA, and so on. 

For analog and digital pins, there are 4 connection points but only 3 are needed. The pin number that is printed on the shield next to the port is the connection that should be used for data transmission. <br>  

![Arduino Shield Diagram](Images/Base_Shield.png)

To read about the sensors correlated to the Seed Grove kit, reference the [sensors folder] (https://github.com/IdeasClinicUWaterloo/Technologies-Utilized-for-Idea-s-Clinic-Challenges/blob/main/sensors/README.md)!
