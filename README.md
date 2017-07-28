![eecs-header-mobile](https://user-images.githubusercontent.com/23239868/28728329-3dc1609e-7396-11e7-910b-6be87048d7d8.png)

# Linear Actuator Control with Arduino/LabVIEW #

*Lead Architect: Ryan J. Richards*

*The Pennsylvania State University - School of Electrical Engineering and Computer Science*

## Introduction/Methodology ##

The linear actuator is used to control the steering angle of the snowmobile. A motor shield (attached to the main ArduinoMEGA) serves as a programmable switch between the Arduino and the actuator. Although a relay would be the simplest way to control the actuator, the actuator must be constantly switched on/off and move in different directions. Switching a relay too often significantly lowers the lifespan of the device. However, by using a motor shield with the Arduino, **Pulse Width Modulation** (PWM) can be used - which can be constantly switched without worry *and* has the programmatical ability to reverse the polarity of the power supplied to the actuator (which gives makes it either *extend* or *retract*).


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

The final setup should look like this:

<img src="https://user-images.githubusercontent.com/23239868/28728949-9b4914b2-7398-11e7-8573-9b2260107602.JPG" height="480" width="640">

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

Mounting the actuator to the snowmobile is a very laborious task since there are very few mounting points on the snowmobile itself. 

The 2015 PSU SnowDrone team sought to mount the actuator on a metal apparatus (which attached to the seat of the snowmobile) and connect the actuator to the steering handle itself. However, the steering handle did not move in a linear motion which means that this is not an optimal mounting position. 

The 2017 PSU SnowDrone team sought to mount the actuator to the bottom of the snowmobile - one end connecting to the front sled steering connection itself while the other end connects to some fixed point on the snowmobile. This proved to be a hard but (semi) achievable task.

Propsed connection steps:

(1) connect the moveable end of the actuator to the right-sled steering base

<img src="https://user-images.githubusercontent.com/23239868/28729155-6f0f0ee6-7399-11e7-9977-90c3a2e7253a.JPG" height="480" width="640">

(2) connect the fixed end of the actuator to bolt openning on the base of the snowmobile

<img src="(https://user-images.githubusercontent.com/23239868/28729334-1faa4248-739a-11e7-972e-6ab14b889610.JPG" height="480" width="640">


## Future Considerations ##

new motor shield to support larger current pull



## Appendix ##

[1] [Motor shield information](http://wiki.seeedstudio.com/wiki/Motor_Shield_V1.0)
