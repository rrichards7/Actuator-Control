# Linear Actuator Control with Arduino/LabVIEW

*Lead Architect: Ryan J. Richards*

Actuator Control LabVIEW Code

## Introduction/Methodology ##

PWM over relay


## MakerHub LINX ##

LINX is a library developed by MakerHub that allows programmers to interface with the RaspberryPi, Arduino and other microcontrollers on LabVIEW. LINX has been used extensively in this project to communicate with the ArduinoMEGA, which controls each subsystem. Download and other information can be found at:

[MakerHub LINX](http://sine.ni.com/nips/cds/view/p/lang/en/nid/212478)

## Hardware Setup ##

The actuator setup utilizes a motor shield [1] that attaches to the ArduinoMEGA. This shield is capable of controling two motors, however we will only need to control one. The motor shield has the following schematic:

![2](https://user-images.githubusercontent.com/23239868/28724241-5a6e9fe0-7387-11e7-81d2-7194e0f5a444.PNG)

*Setup instructions:*

(1) connect the **External Power Jack** to a power supply/battery with the appropriate voltage/current

(2) connect the **M1+** jack to the positive terminal of the actuator

(3) connect the **M1-** jack to the negative terminal of the actuator

(4) attach the **Motor Shield** to the ArduinoMEGA - ensuring that the setup matches the pictures below:

<img src="https://user-images.githubusercontent.com/23239868/28725167-a88e1aa4-738a-11e7-8b86-28be78fe1ba5.JPG" height="480" width="640">

<img src="https://user-images.githubusercontent.com/23239868/28725170-ad3fc318-738a-11e7-912f-3abe2e052944.JPG" height="480" width="640">

## LabVIEW Code ##

This LabVIEW code exemplifies the basic control system for the actuator using the motor shield. The code used in the SnowDrone main VI uses this setup but separates the configuration slightly to accomodate the message-based architecture.

![1](https://user-images.githubusercontent.com/23239868/28725418-5beff22a-738b-11e7-8d97-a1336910b6be.PNG)

*Setup and execution:*

(1) set the **PWM Channel** to **9**

(2) set the **IN1 Channel** to **8**

(3) set the **IN2 Channel** to **11**

(4) set the **Duty Cycle** to **1**

(5) set the **Serial Port** to the COM port of the ArduinoMEGA

(6) Run the VI and press either the **Extend** or **Retract** button - the actuator will then extend/retract accordingly

(7) Press the **Stop** button when done (rather than aborting execution - this ensures that the Arduino connection is closed)

![ezgif com-video-to-gif 1](https://user-images.githubusercontent.com/23239868/28726149-1250643a-738e-11e7-95fb-263cadb7c8f7.gif)
![3](https://user-images.githubusercontent.com/23239868/28726269-8f527d92-738e-11e7-90de-68a0fc8a6cfe.PNG)


## Mounting to Snowmobile ##

steering wheel vs underneath




## Future Considerations ##

new motor shield to support larger current pull



## Appendix ##

[1] [Motor shield information](http://wiki.seeedstudio.com/wiki/Motor_Shield_V1.0)
