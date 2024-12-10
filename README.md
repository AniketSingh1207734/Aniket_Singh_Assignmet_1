# Aniket_Singh_Assignmet_1
# Bot Description Package

This package contains the URDF and Xacro files for defining the robot's physical structure in the Gazebo simulation. The robot's geometry, links, joints, and sensors are described in these files.

## Table of Contents
- Overview
- Package Structure
- Prerequisites
- Installation
- How to Test
- Troubleshooting

## Overview
The `bot_description` package provides the URDF (Unified Robot Description Format) of the robot, which is used to visualize and simulate the robot in a Gazebo environment. The URDF can be written directly or generated using Xacro for better modularity and parameterization.

## Package Structure
bot_description/
├── urdf/
│   ├── robot.xacro         # Main Xacro file describing the robot
│   └── robot.urdf          # Generated URDF file (optional)
├── CMakeLists.txt
├── package.xml
└── ...

## Prerequisites
- ROS Noetic installed on Ubuntu 20.04
- `xacro` package for processing Xacro files
- Gazebo (integrated with ROS)

Ensure your workspace is set up and sourced properly:
```
source ~/Aniket_Singh_ws/devel/setup.bash
```
Installation 
Clone the bot_description package into your workspace's src/ folder:
```
cd ~/your_workspace_ws/src
git clone https://github.com/AniketSingh1207734/Aniket_Singh_Assignmet_1 bot_description
```
Build your workspace:
```
cd ~/Aniket_Singh_ws
catkin_make
```
# How to Test
Step 1: Visualize the Robot in RViz
To test if the robot description is correct, you can visualize the robot in RViz

Open RViz and add a robot model
```
roslaunch bot_description rviz.launch
```
other launch files

spawn.launch Spawn the Robot in Gazebo :
```
roslaunch bot_descrption spawn.launch
```
control.launch
```
roslaunch bot-description control.launch
```
![image](https://github.com/user-attachments/assets/6eaaf1b4-0978-40fc-9bf9-4e153f44fda7)

# Bot World Package

This package defines the Gazebo simulation environment for testing the robot. It includes a simple world with four walls surrounding the robot and cones placed at the corners.

## Table of Contents
- Overview
- Package Structure
- Prerequisites
- Installation
- How to Test
- Troubleshooting

## Overview
The `bot_world` package creates a Gazebo environment that simulates a bounded area with four walls and construction cones at the corners. The robot from the `bot_description` package is spawned in the center of this world.

## Package Structure
bot_world/
├── launch/
│   ├── spawn_robot.launch        # Launch file to start Gazebo and spawn the robot
├── worlds/
│   ├── simple_world.sdf          # SDF file describing the world with walls and cones
├── CMakeLists.txt
├── package.xml
└── ...

# How to Test
Step 1: Launch Gazebo World and Spawn the Robot
To test the world and robot spawning:

Ensure that both bot_description and bot_world packages are built.

Run the following command to launch Gazebo with the robot:

```
roslaunch bot_world spawn_robot.launch
```

Gazebo should open, and you should see:

A robot spawned at the origin of the world.
Four walls surrounding the robot.
Four construction cones placed at the corners of the walls.

![image](https://github.com/user-attachments/assets/a5ab1c72-9793-4a17-b339-ed09a745a274)


