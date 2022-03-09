---
title: FTL help
weight: 2
---

{{< tabs "samples" >}}
{{< tab "Part 1" >}}
```python
from pybricks.hubs import EV3Brick 
from pybricks.ev3devices import Motor 
from pybricks.parameters import Port 
from pybricks.robotics import DriveBase 
from pybricks.tools import wait 
from pybricks.ev3devices import (Motor, TouchSensor, ColorSensor, InfraredSensor, UltrasonicSensor, GyroSensor) 

# Initialize the EV3 Brick. 
ev3 = EV3Brick() 

# Initialize the motors. 
left_motor = Motor(Port.B) 
right_motor = Motor(Port.C) 

# Initialize the Touch Sensor. 
# touch_sensor = TouchSensor(Port.S1) 

# Initialize the Colour Sensor. 
color_sensor = ColorSensor(Port.S3) 

# Initialize the ultrasonic sensor.  
# ultrasonic_sensor = UltrasonicSensor(Port.S4) 

# Initialize the drive base. 
robot = DriveBase(left_motor, right_motor, wheel_diameter=55.5, axle_track=104)

# Write your program here.
robot.drive(200, 0)
while color_sensor.reflection() < 10:
    wait(10)
robot.stop()
```
{{< /tab >}}

{{< tab "Part 2" >}}
```python
from pybricks.hubs import EV3Brick 
from pybricks.ev3devices import Motor 
from pybricks.parameters import Port 
from pybricks.robotics import DriveBase 
from pybricks.tools import wait 
from pybricks.ev3devices import (Motor, TouchSensor, ColorSensor, InfraredSensor, UltrasonicSensor, GyroSensor) 

# Initialize the EV3 Brick. 
ev3 = EV3Brick() 

# Initialize the motors. 
left_motor = Motor(Port.B) 
right_motor = Motor(Port.C) 

# Initialize the Touch Sensor. 
# touch_sensor = TouchSensor(Port.S1) 

# Initialize the Colour Sensor. 
color_sensor = ColorSensor(Port.S3) 

# Initialize the ultrasonic sensor.  
# ultrasonic_sensor = UltrasonicSensor(Port.S4) 

# Initialize the drive base. 
robot = DriveBase(left_motor, right_motor, wheel_diameter=55.5, axle_track=104)

# Write your program here.
robot.drive(50, 0)
while True:
    value = color_sensor.reflection()
    if value > 30:
        # too bright
        # on line
        # veer left
        robot.drive(50, -50)
    elif value < 10:
        # too dark
        # off line
        # veer right
        robot.drive(50, 50)
    else:
        # value is okay
        # drive straight
        robot.drive(50, 0)
    wait(10)
```
{{< /tabs >}}