---
layout: page
title: Mini Swarm Bot
description: Swarm of robots for warehouse management
tags:
- MultiAgent
- ROS
- Embedded System
- Control Theory
- Navigation Stack
- Computer Vision
- Robotics
date: "2021-08-01T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""
img: assets/img/projects/dotbot/featured.png
image:
  caption: Dot-Bot
  focal_point: Smart

links:
- icon: github
  icon_pack: fab
  name: Code and Details
  url: https://www.github.com/hex-plex/Dot-Bot
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---

This is fully ROS integrated robot, which can be used in various purposes our main use case was to test out multiagent algorithms. We used it to take part in the national level competition, FlipKart Grid 3.0 Robotics challenge 2021.

I have worked on building the platform and the integrating ROS with the following robot. The localization was done using a Apriltag_ros and a array of cameras. Also worked on implementing autonomously navigating in the environment and computing the optimal path while considering other robots in the arena.

The complete package including the controller and the planner can be found at [Dot-Bot](https://github.com/Robotics-Club-IIT-BHU/Dot-Bot).

## Robot control
 
The robots control architecture is a state-of-the-art implementation using a microprocessor and a microcontroller along with sensor fusion for position estimation with external cameras for deteciton of apriltags that denote the robot.

The exact control architecture is briefly given in the below image which later is elaborated in 3 bulletin points

![]({{relative_url}}/assets/img/projects/dotbot/dotbot_control.png)

- Communication: Communication between the robot and the remote PC is done through [Networking of multiple machines](http://wiki.ros.org/ROS/Tutorials/MultipleMachines). The communication between the microprocessor and the Microcontroller is done through UART at a baudrate of 2000000.
- Pose Estimation: Pose estimation is done through using Encoder and Imu fusion for odometry(i.e., odom to base frame). Then we use and external camera for ground truth (i.e., map to base frame).
- Controller: We have used a simple velocity based 3 wheel omni drive to control the robot. The omni drive node works at 100 hz on the raspberrypi and the micro controller controls individual motors to trace the given velocity this made it very easy to transfer from the simulation to real world.

The whole implementation of the control architecture can be found at [Swarm-bot-hardware](https://github.com/Robotics-Club-IIT-BHU/Swarm-Bot-Hardware).

## Simulation

We have setup the whole simulation for these robots as we have modelled the real robot. We have also added the 2DOF droppers that can be seen on top of each robot.

We have setup Rviz to visualize the robots both in simulation and hardware.
![]({{relative_url}}/assets/img/projects/dotbot/gazebo.png)
<p align="center">
<i>An demo of the robot in gazebo</i>
</p>

## Flipkart grid Challenge
The main task was to drop packages using the most optimal path, We had used [CBS](https://github.com/PathPlanning/Continuous-CBS) with minor changes to best suite our problem statement. We also used [Tracking PID](https://github.com/nobleo/tracking_pid) for tracing these trajectories and making it more general and robust to be used with other algorithms and systems.

![]({{relative_url}}/assets/img/projects/dotbot/arena.jpg)
<p align="center">
<i>Example of the arena in which it drops the package</i>
</p>

The robot is now a developmental platform for other multiagent research at Indian Institute of Technology, Varanasi
The robot is now about to have minor upgrades for it be used in a more real world use case by addition of lidars and better on board computation.


A preliminary result of the path planning algorithm with package dropping can be seen below.

<iframe src="https://drive.google.com/file/d/1NhuapFy1Y12LVFoKoIaRP3BYm-ReoEHW/preview" width="700" height="500"/>