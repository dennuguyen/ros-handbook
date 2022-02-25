# Specify build instructions for CMake.
cmake_minimum_required(VERSION 2.8.3)

# Name of the project make sure it is the same in package.xml.
project(claw_description)

# Find packages that are required by this project.
find_package(catkin REQUIRED)

# CMake macro to generate pkg-config and CMake files.
catkin_package()

find_package(roslaunch)

# For each subfolder, find any more installation rules.
foreach(dir launch meshes urdf)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)
