# RF Robot Sensors

***
### **Accelerometer**
[Part Link](https://www.digikey.ca/en/products/detail/dfrobot/SEN0373/13590881?s=N4IgTCBcDaIMoFEByAGAzAdjSAugXyA)
* #### Libraries
   * [DFRobot_BMX160 ](https://github.com/DFRobot/DFRobot_BMX160)
* #### Documents
   * [Datasheet + Setup Guide](https://wiki.dfrobot.com/BMX160_9_Axis_Sensor_Module_SKU_SEN0373)
* #### Hookup
   * The accelerometer uses an I2C port on the Base Shield which requires a VCC, GND, SCL, and SDA connection. Each pin should be connected to the corresponding pin of the same name on the Base Shield, with the other pins on the sensor left disconnected.<br><br>
   * Use Breadboard to attach wires from the respected sensor pin to the Base Shield. 
* #### Code
   * Run the following code to output the accelerometer x, y, and z acceleration values to the serial monitor. When laid flat on the table, the z-axis should read ~-9.81m/s2 and the other two values should read ~0. Example code provided by the library can also be used for further understanding of the accelerometer functions. 
   * [Accelerometer Test Code](https://github.com/IdeasClinicUWaterloo/W25_HealthTech_Innovation_Challenge_Guides/blob/main/Dashboard/Arduino_Code/Part_Testing/Accelerometer_test/Accelerometer_test.ino)

***
### **Colour Sensor**
* [Part Link](https://www.digikey.ca/en/products/detail/dfrobot/SEN0101/6588457?gclsrc=aw.ds&&utm_adgroup=&utm_source=google&utm_medium=cpc&utm_campaign=PMax%20Product_Low%20ROAS%20Categories&utm_term=&productid=6588457&utm_content=&utm_id=go_cmp-20291741422_adg-_ad-__dev-c_ext-_prd-6588457_sig-Cj0KCQiAs5i8BhDmARIsAGE4xHwkMFMRrdYxqIl3Mv8EGdNE3Zt0SoJy4V8yZpN3muggOEyRdVIUhYoaApFWEALw_wcB&gad_source=1&gclid=Cj0KCQiAs5i8BhDmARIsAGE4xHwkMFMRrdYxqIl3Mv8EGdNE3Zt0SoJy4V8yZpN3muggOEyRdVIUhYoaApFWEALw_wcB&gclsrc=aw.ds)
* #### Libraries
   * [DFRobot_TCS3200](https://github.com/Panjkrc/TCS3200_library) -Also available in Arduino IDE Library Manger
* #### Documents
   * [Hookup Guide](https://github.com/Panjkrc/TCS3200_library/blob/master/wiring_schematics.png)
   * [Datasheet](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/2107/SEN0101_Web.pdf)
* #### Hookup 
   * This sensor is very large, so you will likely need to use multiple bread boards to connect it. Feel free to remove one of the positive/negative strips on the side to stick two boards together. You will need to use jumper wires to connect to this sensor.
   * Connect the pin labeled VDD on the chip to the 5v port on the Arduino, and connect the GND on the chip to the GND on the Arduino.
   * The pins labeled s0 and s1 control the output scaling (changing the scaling variable in the code controls these outputs.) Connect s0 to the D0 port on the Arduino, and s1 to D1.
   * The pins labeled s2 and s3 control which colour the chip is measuring (either red, green, blue, or white.) Connect s2 to the D2 port on the Arduino, and S3 to the D3 port.
   * The pin labeled OUT on the chip is what the Arduino uses to get the output from the chip. Connect OUT to port D4 on the Arduino.
   * If you would like to turn the LEDs on to brighten the area you are trying to measure, connect the LED pin on the chip to the 5v port on the Arduino.
* #### Code
   * [Colour Sensor Test Code](https://github.com/IdeasClinicUWaterloo/W25_HealthTech_Innovation_Challenge_Guides/blob/main/Dashboard/Arduino_Code/Part_Testing/ColorSensor_test/ColorSensor_test.ino)

***
### **Pulse Oximeter**
   * There are two different Pulse Oximeters: one is green, and the other is purple. They have different part links and datasheets, but everything else, including the hookup and code, is the same.

* [Part Link: Green Sensor](https://www.digikey.ca/en/products/detail/analog-devices-inc-maxim-integrated/maxrefdes117/6165562)

* [Part Link: Purple Sensor](https://www.digikey.ca/en/products/detail/sunfounder/ST0244/22116824?s=N4IgTCBcDaILYEMAeBmADARjWABACwFMEAnAFx2IVIJzgHsATAVwBsCQBdAXyA)
* #### Libraries
   * [DFRobot_MAX30102 Arduino Library ](https://github.com/DFRobot/DFRobot_MAX30102) - Must download from Git. Not available through the IDE.
* #### Documents 
   * [Datasheet: Green Sensor](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/1222/MAXREFDES117_Web.pdf)
   * [Datasheet: Purple Sensor](https://www.analog.com/media/en/technical-documentation/data-sheets/max30102.pdf)
* #### Hookup: SAME FOR BOTH SENSORS!!
   * On the pulse-oximeter sensor, two sides of the sensor there is a single connection point (GND or VIN), and on the other two sides there are three connection points (each with INT, SCL, and SDA).
   * This sensor uses an I2C connection, so we need to use the GND and VIN (VCC), as well as one set of the SDA and SCL pins (from the same side). INT pins are NOT used.
   * Use Breadboard to attach wires from the respected sensor pin to the Base Shield. 
* #### Code: SAME FOR BOTH SENSORS!!
   * [Pulse-Oximeter Test Code](Arduino_Code/Part_Testing/PulseOximeter_test/PulseOximeter_test.ino?ref_type=heads)
   * This code uses the serial plotter instead of the serial monitor. The numbers will still be shown on the monitor but the data will be very hard to understand without being in a graph.

