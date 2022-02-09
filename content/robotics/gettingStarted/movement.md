---
title: Movement
weight: 5
---

## Set up

```python
# Initialize the motors.
left_motor = Motor(Port.B)
right_motor = Motor(Port.C)
```

```python
# Initialize the drive base.
robot = DriveBase(left_motor, right_motor, wheel_diameter=55.5, axle_track=104)
```

## Driving for a given distance or by an angle
Use the following commands to drive a given distance, or turn by a given angle.
This is measured using the internal rotation sensors. Because wheels may slip while moving, the travelled distance and angle are only estimates. 

### `straight(distance)`
Drives straight for a given distance and then stops.
Parameters:
- `distance`, distance to travel in *millimetres*.

### `turn(angle)`
Turns in place by a given angle and then stops.
Parameters:
- `angle`, angle to turn in *degrees*.

### `drive(drive_speed, turn_rate)` 
Starts driving at the specified speed and turn rate. Both values are measured at the center point between the wheels of the robot. It keeps going until you use stop() or change course by using drive() again. For example, you can drive until a sensor is triggered and then stop or turn around. 

Parameters:
- drive_speed (speed: mm/s) – Speed of the robot.
- turn_rate (rotational speed: deg/s) – Turn rate of the robot.

```python
## Example Movement Code 

# Go forward and backwards for one metre.
robot.straight(1000)
robot.straight(-1000)

# Set the drive base speed and turn rate. It keeps going until you use stop()
robot.drive(100, 0)

# Turn clockwise by 360 degrees and back again. 
robot.turn(360)
robot.turn(-360)

# stop the motor
robot.stop()

# this stops any active movement and actively brakes the motor 
robot.stop(Stop.BRAKE)

# this stops any active movement and leaves the motors on coast
robot.stop(Stop.COAST)
```