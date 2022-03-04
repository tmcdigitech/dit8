---
title: Touch Sensor
weight: 6
---
*adapted from [PyBricks](https://docs.pybricks.com/en/stable/robotics.html)*
{{< figure src="https://pybricks.com/ev3-micropython/_images/sensor_ev3_touch.png" title="Touch Sensor" >}}

A sensor lets an EV3 program measure and collect data about is surroundings. The Touch Sensor can detect when the sensor’s red button
has been pressed or released.

# Example Code
{{< highlight python "lineNos=table,lineNoStart=1" >}}
#!/usr/bin/env pybricks-micropython
from pybricks.hubs import EV3Brick
from pybricks.ev3devices import Motor
from pybricks.parameters import Port, Stop
from pybricks.robotics import DriveBase
from pybricks.tools import wait
from pybricks.ev3devices import (Motor, TouchSensor, ColorSensor, InfraredSensor, UltrasonicSensor, GyroSensor)

# Initialize the EV3 Brick.
ev3 = EV3Brick()

# Initialize the motors.
left_motor = Motor(Port.B)
right_motor = Motor(Port.C)

# Initialize the drive base.
robot = DriveBase(left_motor, right_motor, wheel_diameter=55.5, axle_track=104)

# Initialize Touch Sensor
touch_sensor = TouchSensor(Port.S1)

# Drive forward until touch sensor is pressed
robot.drive(1000, 0)
while not touch_sensor.pressed():
    wait(1)
robot.stop()


