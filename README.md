# 1.0 Introduction

This repository contains the necessary files to adjust the baud rates and motor IDs for the Open Manipulator Dynamixel servos. The 2020 Cornell Tech robotics internship team adjusted these parameters and labeled the servos such that configuration is not necessary.

However, these files are included for future use, if required. 

# 2.0 Using the Repo

To program the servos, the [Arduino IDE] (https://emanual.robotis.com/docs/en/software/arduino_ide/) needs to be installed, along with the OpenCR Library for Arduino. The OpenCR board needs to be powered and connected to each servo that needs to be programmed. No other servos should be connected to the OpenCR or daisy chain connections in the Dynamixel servo to be programmed.

Next, [clone this repo](https://github.com/Cornell-Tech-Turtlebot/DINAMIXEL_OPEN_MANIPULATOR_CONFIGURATION) to a local directory. (i.e.: using command line: git clone https://github.com/Cornell-Tech-Turtlebot/DINAMIXEL_OPEN_MANIPULATOR_CONFIGURATION.git)

- The servo id parameter lets the OpenCR board know which servos are which in Dynamixel's daisy chain configuraion. You may change motor IDs by modifying these lines in the c_ID_Change.ino file: 

  #define DXL_ID  1<br>
  #define NEW_DXL_ID  15<br>

  This file assumes that the servo's baud rate is still as set at factory (57600). This line may be changed as necessary to get the right baud rate passed to the OpenCR board:

  #define BAUDRATE  57600

- You may change the baud rate by using the the d_BPS_Change.ino file and changing this line:  #define NEW_BAUDRATE 1000000. This file assumes that the Dynamixel servos are in their factory state (i.e. baud rate is 57600). This line specifies the servo ID for the servo being programmed: "#define DXL_ID 15". The Robotis Open Manipulator packages assume a baud rate of 1000000.
