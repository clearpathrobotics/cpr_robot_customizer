# generic_robot
**CPR generic_robot ROS Package.**

## Overview
This ROS package provides an easy-to-use interface for adding sensors to your robot. The usage interface consists of environment variables which can be set to add sensors visually to your robot's model, as well as enable the launching of their respective drivers. The sensors supported in this package are commonly used by Clearpath Robotics to customize mobile robotic platforms.

## Prerequisites
Before using this package, it is assumed that:
1. You have a ROS robot.
2. You have a ROS workspace on your robot.
3. You have the physical sensors you wish to add to your robot and they are electromechanically integrated onto your robot. Note that this is optional if you only wish to visualize your robot's model and do not wish to launch the sensors' drivers.
4. You have a `.urdf.xacro` file that describes your robot's model. Note that this file needs to support the usage of xacro macros. [Here](http://wiki.ros.org/urdf/Tutorials/Using%20Xacro%20to%20Clean%20Up%20a%20URDF%20File) is a tutorial on how to add xacro support to a regular URDF file. You can refer to Clearpath Robotics' [Husky](https://github.com/husky/husky/blob/noetic-devel/husky_description/urdf/husky.urdf.xacro) robot as an example.
5. You have a `.launch` file that loads your `.urdf.xacro` file into the robot's model through the `robot_description` parameter. This file may also bring up other components of your robot (e.g. base platform, motor drivers, navigation software, etc.). You can refer to Clearpath Robotics' [Husky](https://github.com/husky/husky/blob/noetic-devel/husky_description/launch/description.launch) robot as an example.

## Usage
1. Clone this package into your robot's ROS workspace, install the required dependencies, and build the workspace in order to compile this package:
```
cd <PATH_TO_WORKSPACE>/src/
git clone https://github.com/jyang-cpr/generic_robot.git
cd ..
rosdep install --from-paths src --ignore-src --rosdistro=$ROS_DISTRO -r -y
catkin_make
source devel/setup.bash
```
2. In your robot's `.urdf.xacro` description file, add the line: `<xacro:include filename="$(find generic_robot)/urdf/accessories.urdf.xacro" />`. This will ensure that the sensors you want are added visually to your robot's model.
3. In your robot's `.launch` file, add the line: `<include file="$(find generic_robot)/launch/accessories.launch" />`. This will ensure that the drivers of the sensors you want are launched upon bringing up your robot.
4. In the `environment_variables` file located in the `/scripts` folder of this package, set the environment variables of the sensors you want added to your robot. Alternatively, you can set these environment variables in a different location that is sourced automatically, such as the `~/.bashrc` file on your robot. See below for a complete list of supported sensors and their corresponding environment variables. 
5. Source the file where the environment variables are set. If you set the environment variables in the `environment_variables` file: 
```
cd <PATH_TO_WORKSPACE>
source src/generic_robot/scripts/environment_variables
```
6. The next time your robot's `.launch` file is launched (e.g. upon booting), the desired sensors will be added your robot's model and their respective drivers will be run to extract their data into ROS.

## Supported Sensors and Environment Variables
