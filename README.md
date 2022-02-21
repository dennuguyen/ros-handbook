# ROS Packages

## Learning Outcomes

- Understand what a ROS package is and how it is built.
- Can write a package.xml.
- Can write a CMakeLists.txt.
- Know conventional structure for a control package.
- Know conventional structure for a description package.
- Know conventional structure for a gazebo package.
- Know conventional structure for a serial package.
- Understand how to manage packages.
- Understand how to use git for version controlling of packages.

## What is a package?

A [ROS package](http://wiki.ros.org/Packages) contains a robot functionality that is reusable. It is built using the CMake build system.

The following are typical steps to building a ROS package:
```
cd ~/catkin_ws           # Or wherever your catkin workspace is.
catkin_build             # Builds all the packages within src folder.
source devel/setup.bash  # Brings the packages/nodes into user namespace.
```

All packages have a `package.xml` and `CMakeLists.txt` file:
- The [package.xml](http://wiki.ros.org/catkin/package.xml) file specifies dependencies and customise the package. Read the following [package.xml template]() to understand how it is written.
- The [CMakeLists.txt](http://wiki.ros.org/catkin/CMakeLists.txt) file is the input to the CMake build system which specifies build instructions and install location. Read the following [CMakeLists.txt template]() to understand how it is written.


## Control Package

The control package contains *controllers* for actuated mechanisms. ROS provides in-built controllers such as:
- [Joint Position Controller](http://wiki.ros.org/robot_mechanism_controllers/JointPositionController).
- [Joint Velocity Controller](http://wiki.ros.org/robot_mechanism_controllers/JointVelocityController).

The typical folders a control package can have are:
- **config**: Specify controller parameters at start of run-time. These are utilised by launch files.
- **launch**: Launch selected controller(s).

## Description Package

The description package contains *descriptions* of the robot. This is essential to create a custom robot model that can be visualised or simulated.

The typical folders a description package can have are:
- **launch**: Load the robot description or display it in RViz.
- **meshes**: Meshes used for robot models (prefer STL format).
- **rviz**: Custom RViz window configuration.
- **urdf**: Description of robot models in URDF/Xacro/SDF.

## Gazebo Package

The gazebo package contains world files and objects to simulate the robot in a Gazebo world.

The typical folders a gazebo package can have are:
- **launch**: Launch selected Gazebo world.
- **models**: Objects that can be used within a world.
- **worlds**: World files that specify lighting, terrain, objects, etc.

## Teleop Package

The teleop package contains *source code* that allows a robot to be teleoperated from a physical device e.g. mouse, keyboard, game controller.

The typical folders a teleop package can have are:
- **include**: Include folder for C++ header files.
- **launch**: Launch node to enable teleoperation.
- **src**: Source folder for C++ source files.

## Navigation Package

The [navigation package](http://wiki.ros.org/navigation) allows autonomous navigation of a robot.

The typical folders a navigation package can have are:
- **launch**: 
- **maps**: 
- **param**: 
- **rviz**: 

## SLAM Package

The SLAM package provides simultaneous localisation and mapping capabilities.

The typical folders a SLAM package can have are:
- **bag**:
- **config**:
- **include**:
- **launch**:
- **rviz**:
- **src**:

## Manipulation Package

The manipulation package provides manipulation capabilities for an end effector.

The typical folders a manipulation package can have are:
- **launch**:

## Kinematics Package

The kinematics package contains forward and inverse kinematics for a robot arm.

The typical folders a kinematics package can have are:
- **launch**:

## Serial Package

The serial package encapsulates the functionality to [run ROS on multiple machines](http://wiki.ros.org/ROS/Tutorials/MultipleMachines). ROS provides [rosserial_python](http://wiki.ros.org/rosserial_python) which sets up publishers and subscribers over a network.

The typical folders a serial package can have are:
- **launch**: Launch the `rosserial_python` package.

## Package Management & Collaboration

Packages should have a hierarchy to avoid cyclic dependencies.

### ROS Packages & Git

The git repository should consist of a collection of packages targeting a particular robot platform.