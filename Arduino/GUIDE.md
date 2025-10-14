# Arduino Set up Guide
A step-by-step guide on how to install and prepare you're Arduino Environment

# Content:
1. [Arduino IDE Setup](#1-arduino-ide-setup)
    * [Arduino Board And Port Setup](#arduino-board-and-port-setup)
    * [Intalling Libraries](#installing-libraries)
2. [Communicating with the Arduino](#2-communicating-with-the-arduino)

## 1. Arduino IDE Setup

### Arduino Board and Port Setup
If you do not already have the Arduino IDE, you can download it [here](https://www.arduino.cc/en/software). We recommend downloading the first option - Arduino IDE 2.3.4.
Before you can begin coding, you should configure your Arduino IDE to the specific arduino you are using. In this case you will be using the "Arduino UNO R4 Minima".

1. Go to the bar at the top of the screen that reads "Select Board". 
2. Select the option "Select other board and port".
3. Search the board name "Arduino UNO R4 Minima", then select it.
4. Select the port which the arduino is connected to from the drop-down menu, then click "ok".<br>
**If the port you are using is not shown, select "show all ports".<br>
**If you don't know the port ID, go to your "Device Manager" to find the ID under "Ports".

### Installing Libraries
The required libraries for each sensor are listed in [Sensor Setup](#4-sensor-setup), use this [Link](https://docs.arduino.cc/software/ide-v1/tutorials/installing-libraries/) for more help installing libraries.
#### Method 1: Using the Arduino R4
Search for the Library name in the ‘library manager” in the Arduino IDE and install. <br>
![Library Manger](Images/Arduino_Library_Manager.png)
#### Method 2: Downloading Library Zip File
##### Steps:
1. Download the library from GitHub as a .zip file <br>
![Zip Library in GitHub](Images/Git_Zip_Library.png)

2. Once downloaded simply browse to the Arduino IDE and add the library as a zip file. 
<br>(Sketch -> Include Library -> Add .ZIP Library) <br>
![Include Library](Images/Include_Library.png)
3. Browse to File -> Examples and then find your library and click on the example to get some example code for how to use that library. <br> 
![Libray Examples](Images/Library_Examples.png)

### Running Code
To upload the code to the Arduino, ensure that the correct port is selected, and press the button with the arrow in the top left. This will send the code to the Arduino and it will loop forever. If you want to restart your code, you can click the reset button (labeled RST on the shield next to the green light) once. If you want to erase the code from the Arduino without uploading new code, you can click this reset button twice. If you ever find that the code is failing to upload despite the correct port being selected, it is generally a good idea to try erasing the old code.


## 2. Communicating with the Arduino
All communication is done via the Serial port. You can view the serial port using your Arduino IDE by going to tools -> serial monitor from the menu at the top. You can also open it up as a graph view by opening the serial plotter in the same menu. Whenever there is a Serial.print() or Serial.println() command in the Arduino code, that information should show up in your serial monitor. 

#### Baud Rate
Any test code that uses the serial port runs a setup function to initialize the code settings. Serial.begin() initializes the Serial Monitor baud rate. Whatever number is initialized in the Setup() function must match the baud rate value in the Serial Monitor. Most of the time, your IDE will change it automatically, but it is important to check if things are not working. 

#### Arduino Code
* As well, the Arduino can read and respond to information sent to it from the serial port. 
* [Code to respond to serial inputs wrapped with <>, ex. < message >](https://github.com/IdeasClinicUWaterloo/InnovationChallange_Guides/blob/main/Dashboard/Arduino_Code/Serial_Communication/SerialReader/SerialReader.ino)

#### Python Code
* Python can also send and recieve messages through the serial port using the [PySerial](https://pyserial.readthedocs.io/en/latest/) library
* To install this library, follow steps 2.1 and 2.2 [here](https://github.com/IdeasClinicUWaterloo/InnovationChallange_Guides/blob/main/Computer_Vision/GUIDE.md#21-download-python-version-37---312), and then run ```pip install pyserial```
* [Python code to communicate with Arduino](https://github.com/IdeasClinicUWaterloo/W25_HealthTech_Innovation_Challenge_Guides/blob/main/Dashboard/Python_Code/ArduinoToPython.py), to be used with an Arduino running the code above
* You will likely need to close the serial monitor in your Arduino IDE in order to run this code
