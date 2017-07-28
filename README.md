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



## Mounting to Snowmobile ##




## Results ##



## Appendix ##

[1] [Motor shield information](http://wiki.seeedstudio.com/wiki/Motor_Shield_V1.0)
