---
title: Starter code
weight: 100
---

This is a good base to use at the top of each of your projects.

{{< highlight python "linenos=table" >}}
#!/usr/bin/env pybricks-micropython 

from pybricks.hubs import EV3Brick 
from pybricks.ev3devices import Motor 
from pybricks.parameters import Port, Stop
from pybricks.robotics import DriveBase 
from pybricks.tools import wait 
from pybricks.ev3devices import (Motor, TouchSensor, ColorSensor, InfraredSensor, UltrasonicSensor, GyroSensor) 

# Initialize the EV3 Brick. 
ev3 = EV3Brick() 

""" 
Setting up motors and sensors
------------------

It is vital that you correctly tell the EV3
what sensors it will need and where they are connected.

Any sensors listed below MUST be present on the listed ports.
You can comment out one or more of these lines if you need
to temporarily ignore a sensor.
""" 

# Initialize the motors. 
left_motor = Motor(Port.B) 
right_motor = Motor(Port.C) 

# Initialize the sensors.
touch_sensor = TouchSensor(Port.S1) 
color_sensor = ColorSensor(Port.S3) 
ultrasonic_sensor = UltrasonicSensor(Port.S4) 

# Initialize the drive base. 
robot = DriveBase(left_motor, right_motor, wheel_diameter=55.5, axle_track=104)

# ------------------------
# Write your program here.
# ------------------------

{{< /highlight >}}
