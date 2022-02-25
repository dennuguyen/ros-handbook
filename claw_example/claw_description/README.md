# ROS Description Package

## Learning Outcomes

- Can export STL meshes from a CAD.
- Can create a robot model using STL meshes with a descriptive language i.e. urdf, xacro, sdf.
- Can write launch files for description packages.
- Can use RViz to display the robot_description.

## Exporting CAD as STL

Standard Triangle Language (STL) files are triangulated representations of a 3D CAD model.

When exporting a CAD as STL, consider what group of components do not need to be modelled separately. Typically, this group of components have fixed joints between themselves. Simplify where possible!

## Robot Description Languages

Robot description languages are used to *describe* the robot's links and joints so the robot model can be generated in RViz or Gazebo.

### URDF

Unified Robot Description Format (URDF) is an XML format to describe a robot model.

URDFs can only be used for a single robot, lacks friction, and is generally inflexible.

### Xacro

XML Macro (Xacro) lets you use macros which expand into larger or commonly used XML expressions.

Think of xacro as a superset of urdf, therefore prefer xacro file extension when possible.

### SDF

Simulation Description Format (SDF) is an XML format to describe robots, objects, environments (lighting, terrain, physics).

SDFs improve upon URDF's flaws:
- Cannot describe non-robot objects.
- Does not support closed-loop kinematics.
- Etc.

## ROS Launch Files for Description Packages

Launch files for description packages have a particular style.

- `description.launch.xml`: For loading the robot_description into the param server.
- `display.launch`: For displaying the robot_description in RViz.

## RViz

RViz is the program that visualises the ROS environment. RViz is customisable in its views but displaying the robot_description is the only priority.
