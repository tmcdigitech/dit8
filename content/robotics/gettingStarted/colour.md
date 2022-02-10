---
title: Colour Sensor
weight: 8
---
*adapted from [PyBricks](https://docs.pybricks.com/en/stable/robotics.html)*
{{< figure src="https://pybricks.com/ev3-micropython/_images/sensor_ev3_color.png" title="Colour Sensor" >}}

A sensor lets an EV3 program measure and collect data about is surroundings. The Colour Sensor can detect colour and reflected light.

Three modes: **Colour**, **Reflected Light Intensity** and **Ambient Light**
Intensity
– **Color Mode**: Recognizes 7 colours (black, brown, blue, green, yellow, red, white) and No Color

– **Reflected Light**: Measures the intensity of the light reflected back from a lamp that emits a red light. (0=very dark and 100=very light)

– **Ambient Light**: Measures the strength of the light that enters the sensor from the environment. (0=very dark and 100=very light)

## Example Code
```python
#!/usr/bin/env pybricks-micropython
from pybricks.hubs import EV3Brick
from pybricks.ev3devices import Motor
from pybricks.parameters import Port
from pybricks.robotics import DriveBase
from pybricks.tools import wait
# Initialize the EV3 Brick.
ev3 = EV3Brick()
from pybricks.ev3devices import (Motor, TouchSensor, ColorSensor,
InfraredSensor, UltrasonicSensor, GyroSensor)

# Initialize the motors.
left_motor = Motor(Port.B)
right_motor = Motor(Port.C)

# Initialize the sensors.
line_sensor = ColorSensor(Port.S1)

# Initialize the drive base.
robot = DriveBase(left_motor, right_motor, wheel_diameter=55.5, axle_track=104)

# Go forward while reflected light is less than 10.
ev3.speaker.beep()
robot.drive(100,0)
while line_sensor.reflection() < 10:
    wait(10)
robot.stop()

```

