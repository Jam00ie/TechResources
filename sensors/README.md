# Sensors

This Folder contains all the sensors that are utilized with the Seed Grove Kit

# Sensor Setup

Use the resources under each sensor type to learn more about how the sensor works, what libraries are needed, and how to connect it to your arduino.
For the test codes provided for each sensor, open a blank Arduino IDE tab to copy and paste to code into.

***
### **Button/Touch Sensor**
* [Button Part Link](https://wiki.seeedstudio.com/Grove-Button/)
* [Touch Sensor Part Link](https://wiki.seeedstudio.com/Grove-Touch_Sensor/)
* #### Libraries
   * No additional libraries needed for these sensors.
* #### Documents
   * [Button Manual](https://robu.in/wp-content/uploads/2019/09/Grove-Button-User-Manual.pdf)
   * [Touch Sensor Manual](https://robu.in/wp-content/uploads/2019/09/Grove-Touch-Sensor.pdf)
* #### Hookup
   * Using one of the digital ports (D7) on the Base Shield, simply use the provided 4-prong connection wires to directly connect the sensor to the Base Shield, ensuring proper connections are made (GND to GND, VCC to VCC, etc.)
* #### Code
   * [Button/Touch Test Code](Arduino_Code/Part_Testing/ButtonAndTouchSensor_test/ButtonAndTouchSensor_test.ino?ref_type=heads)


***
### **Buzzer**
* [Part Link](https://wiki.seeedstudio.com/Grove-Buzzer/)
* #### Libraries
   * [Servo](https://docs.arduino.cc/libraries/servo/) - Also available in Ardiuno IDE Library Manger
* #### Documents
   * [Manual](https://www.mouser.com/datasheet/2/744/Seeed_107020000-1217511.pdf)
* #### Hookup
   * Using one of the digital ports (D8) on the Base Shield, simply use the provided 4-prong connection wires to directly connect the sensor to the Base Shield, ensuring proper connections are made (GND to GND, VCC to VCC, etc.)
* #### Code
   * [Buzzer Test Code](Arduino_Code/Part_Testing/Buzzer_test/Buzzer_test.ino?ref_type=heads)

***
### **LCD Display**
* [Part Link](https://wiki.seeedstudio.com/Grove-LCD_RGB_Backlight/)
* #### Libraries
   * [Grove LCD RGB Backlight](https://github.com/Seeed-Studio/Grove_LCD_RGB_Backlight) - Also available in Arduino IDE Library Manger
* #### Documents
   * [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/1081/104030001_Web.pdf)
* #### Hookup
   * The Grove LCD Display is not compatible with the Arduino R4 and will require pull-up resistors to function correctly. Use a breadboard to set up 4kΩ to 6kΩ  resistors in the configuration shown below.<br>
   ![Pullup Resistors](Images/Pullup_Resitors.png) <br>
   * The LCD Display uses I2C ports, so connect the VCC, GND, SDA, and SCL connection to the corresponding ports on the Base Shield.
* #### Code
   * [LCD Display Test Code](Arduino_Code/Part_Testing/LCD_test/LCD_test.ino?ref_type=heads)

***
### **LEDs** 
* [Part Link](https://www.digikey.ca/en/products/detail/sparkfun-electronics/COM-15206/10064425?s=N4IgTCBcDaIIwFYBsAOAtAYQPIFk2LAAYk0A5AERAF0BfIA)
* #### Libraries
   * [Adafruit_NeoPixel](https://reference.arduino.cc/reference/en/libraries/adafruit-neopixel/) - Also available in Ardiuno IDE Library Manger
* #### Documents
   * [Hookup Guide](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/1179/WS2812_Breakout_Hookup_Guide.pdf)
* #### Hookup
   * Use one of the 4-pin to male wires to connect any of the D ports on the Arduino. The D port you use should be the value of the LED_PIN constant defined in the second line of the LED test code.
   * Connect the black wire from the 4-pin to the black/blue wire on the LED strip (Ground)
   * Connect the red wire from the 4-pin to the red wire on the LED strip (5v)
   * Connect the yellow wire from the 4-pin to the yellow wire on the LED strip (data)
   * The white wire on the 4-pin should not connect to anything.
* #### Code
   * Running the code below with the correct pin setup should turn the LEDs in circuit with the arduino a light purple color. Change the “red”, “green”, and “blue” values and upload code to get different color outputs! 
   * [LED Test Code](Arduino_Code/Part_Testing/LED_test/LED_test.ino?ref_type=heads) <br><br>

***
### **Servo**
* [Part Link](https://wiki.seeedstudio.com/Grove-Servo/)
* #### Libraries
   * [Servo](https://docs.arduino.cc/libraries/servo/) - Also available in Ardiuno IDE Library Manger
* #### Documents
   * [Manual](https://www.manualslib.com/manual/1836691/Seeed-Grove-Servo-Series.html)
* #### Hookup
   * Using one of the digital ports (D5) on the Base Shield, simply use the provided 4-prong connection wires to directly connect the sensor to the Base Shield, ensuring proper connections are made (GND to GND, VCC to VCC, etc.)
* #### Code
   * [Servo Test Code](Arduino_Code/Part_Testing/Servo_test/Servo_test.ino?ref_type=heads)


***
### **Sound Sensor**
* [Part Link](https://wiki.seeedstudio.com/Grove-Sound_Sensor/)
* #### Libraries
   * No additional libraries needed for this sensor.
* #### Documents
   * [Datasheet](https://www.mouser.com/datasheet/2/744/Seeed_101020015-1217523.pdf?srsltid=AfmBOorwHlJCEQqf9S8z5mSSTPdVx3PrN5UK1Yeg_4D4VB85bLY0FuRT)
* #### Hookup
   * Using one of the analog ports (A0) on the Base Shield, simply use the provided 4-prong connection wires to directly connect the sensor to the Base Shield, ensuring proper connections are made (GND to GND, VCC to VCC, etc.)
* #### Code
   * [Sound Sensor Test Code](Arduino_Code/Part_Testing/SoundSensor_test/SoundSensor_test.ino?ref_type=heads)<br><br>


***
### **Temperature Sensor**
* [Part Link](https://www.digikey.ca/en/products/detail/seeed-technology-co-ltd/101020015/5482612?gclsrc=aw.ds&&utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Product_Low%20ROAS%20Categories&utm_term=&productid=5482612&utm_content=&utm_id=go_cmp-20291741422_adg-_ad-__dev-c_ext-_prd-5482612_sig-Cj0KCQiAs5i8BhDmARIsAGE4xHzTSHPixUNWPe_Sz5zNK9TpqalWp9gAVqcVxikBVv6sWPFyKczcFioaAkwVEALw_wcB&gad_source=1&gclid=Cj0KCQiAs5i8BhDmARIsAGE4xHzTSHPixUNWPe_Sz5zNK9TpqalWp9gAVqcVxikBVv6sWPFyKczcFioaAkwVEALw_wcB&gclsrc=aw.ds)
* #### Libraries
   * [DFRobot_MAX30102 Arduino Library ](https://github.com/DFRobot/DFRobot_MAX30102)
* #### Documents
   * [Datasheet](https://www.mouser.com/datasheet/2/744/Seeed_101020015-1217523.pdf?srsltid=AfmBOorwHlJCEQqf9S8z5mSSTPdVx3PrN5UK1Yeg_4D4VB85bLY0FuRT)
* #### Hookup
   * Using one of the analog ports (A0) on the Base Shield, simply use the provided 4-prong connection wires to directly connect the sensor to the Base Shield, ensuring proper connections are made (GND to GND, VCC to VCC, etc.)
* #### Code
   * [Temp Test Code](Arduino_Code/Part_Testing/TemperatureSensor_test/TemperatureSensor_test.ino?ref_type=heads)
 
***
### **Light Sensor**
* [Part Link](https://www.digikey.ca/en/products/detail/seeed-technology-co-ltd/101020173/6235093?s=N4IgTCBcDaIIwAZFiQdgMwgLoF8g)
* #### Libraries
    * [Grove Digital Light Sensor](https://github.com/Seeed-Studio/Grove_Digital_Light_Sensor)
* ### Documents
    * [Datasheet]([https://seeeddoc.github.io/Grove-Light_Sensor/](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/2518/101020173_Web.pdf))
* ### Hookup
    * Using one of the analog ports (A0) on the Base Shield, simply use the provided 4-prong connection wires to directly connect the sensor to the Base Shield, ensuring proper connections are made (GND to GND, VCC to VCC, etc.)
 * ### Code
    * [Light Sensor Test Code](https://github.com/Seeed-Studio/Sketchbook_Starter_Kit_V2.0/blob/master/Grove_Light_Sensor/Grove_Light_Sensor.ino)

***
### **Relay**
* [Part Link](https://www.digikey.ca/en/products/detail/seeed-technology-co-ltd/103020005/5487965)
* ### Libraries
    * No additional Libraries Required
* ### Documents
    *[Datasheet](https://seeeddoc.github.io/Grove-Relay/)
* ### Hook up
    * Using one of the digital ports (D8) on the Base Shield, simply use the provided 4-prong connection wires to directly connect the sensor to the Base Shield, ensuring proper connections are made (GND to GND, VCC to VCC, etc.)
* ### Code
    * [Relay Test Code](https://github.com/Seeed-Studio/Sketchbook_Starter_Kit_V2.0/blob/master/Grove_Relay/Grove_Relay.ino)

***
### Rotary Angle Sensor
* [Part Link](https://www.digikey.ca/en/products/detail/seeed-technology-co-ltd/101020017/5482577?s=N4IgTCBcDaIIwAZFgUg7CAugXyA)
* ### Libraries
    * No additional Libraries Required
* ### Documents
    *[Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/813/Grove_Rotoary_Angle_Sensor_Web.pdf)
* ### Hook up
    * Using one of the analog ports (A0) on the Base Shield, simply use the provided 4-prong connection wires to directly connect the sensor to the Base Shield, ensuring proper connections are made (GND to GND, VCC to VCC, etc.)
* ### Code
    * [Rotary Angle Sensor Test Code](https://github.com/Seeed-Studio/Sketchbook_Starter_Kit_V2.0/blob/master/Grove_Rotary_Angle_Sensor/Grove_Rotary_Angle_Sensor.ino)
