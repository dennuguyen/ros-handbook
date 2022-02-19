# Claw

This claw was donated from UCRG Team 1 for the Offworld Robotic's curriculum.

## Dependencies

`claw` package relies on [MimicJointPlugin](https://github.com/roboticsgroup/roboticsgroup_gazebo_plugins) so that two of the claws follows the joint angle of one of the actuated claws.

Installation:
1. `git clone https://github.com/roboticsgroup/roboticsgroup_gazebo_plugins.git` into `~/catkin_ws/src`
1. `catkin_make`

## Gazebo Script

Run this first to spawn the claw.

```
cd ~/catkin_ws
catkin_make
source devel/setup.bash
roslaunch claw_gazebo claw.launch
```

## Control Script

Run this to spawn the controllers so we can control the claw.

```
cd ~/catkin_ws
catkin_make
source devel/setup.bash
roslaunch claw_control claw.launch
```

## Publish Commands

Run this to control the claw joint.

```
rostopic pub /claw/command std_msgs/Float64 "data: -1.2"
```
