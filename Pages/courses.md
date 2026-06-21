--- 
title: "Coursework"
description: "Project Documentation"
layout: default
---

# Class History

The following is a complete list of the STEM courses that I have taken. Some of them are linked to descriptions further down this page.

### Math

* MATH 1910: Calculus
* MATH 1920: Multivariable Calculus
* MATH 2930: Differential Equations
* MATH 2940: Linear Algebra

### Science

* CHEM 2090: Engineering General Chemistry
* PHYS 1110: Experimental Physics
* PHYS 1112: Mechanics and Heat
* PHYS 2213: Electromagnetism
* PHYS 2214: Oscillations, Waves, and Quantum
* PHYS 2216: Intro to Special Relativity
* EAS 3410: Atmospheric Thermodynamics and Hydrostatics

### Engineering

* ECE 2100: Circuits
* ECE 2300: Digital Logic
* ECE 2720: Data Science
* ECE 2400: Computer Systems Programming in C/C++
* ECE 3030: Electromagnetic Fields and Waves
* ECE 3250: Signals and Systems
* ECE 4060: Quantum Physics and Engineering
* ECE 3150: Microelectronics
* ECE 4370: Photonics
* ECE 4380: Electromagnetic Materials
* [BEE 3900: Bio-Robotics](#bee-3900:-bio-robots)
* ECE 4760: Digital Systems Design with Microcontrollers
* ECE 4770: Foundation of Robotics
* ECE 4160: Fast Robots
* SYSEN 5410: Cyber-Physical Systems
* SYSEN 5200: System Analysis, Behavior, and Optimization
* SYSEN 6680: Optimal Control and Decision Theory

# Class Descriptions

### ECE 4760: Digital Systems Design Using Microcontrollers

This was a fun lab-based class I took during my undergraduate career at Cornell. The class focused on four different labs, each using different peripherals and concepts to develop interesting systems using an RP2040. In the first lab, we developed a bird song synthesizer, the second lab worked on developing a digital Galton Board, and in the third lab we implemented a pitch PID controller for a drone motor. Out of those three, the PID controller was my favorite, and my lab group was able to get the pitch to be within a ~2% error from its desired value. For the final lab, we got to choose our own system to implement. We decided to create a virtual drum set machine called [DigiDrum](https://www.youtube.com/watch?v=fSZf4prnDR0). Unfortunately, no one in my lab group was particularly musically talented!

### [ECE 4160: Fast Robots](https://hilarioesparza.github.io/fastrobots-2026/)

This lab-based class focused on the hardware and software development and debugging process of a robotic car. We took the electrical guts out of a toy RC car, rebuilt it with our own system, and then programmed it to perform mapping, localization, Kalman filter aided position and orientation PID control, and cool stunts! My favorite part of the class was working on the inverted pendulum challenge in the last lab.

## Masters in Engineering

### SYSEN 5410: Cyber-Physical Systems

This class applied a systems level approach and understanding to technical concepts I had already been exposed to. We learned about TCP, UDP, and MQTT networking paradigms; signal processing and filtering; Kalman and Bayes filters; and a foundation in computer vision. I used what was learned in this lab to build a prototype robot arm, which I named [Armold](https://youtu.be/8_QH_XWPAGs). Armold was a 3DoF robotic arm built with four servo motors, and it had two separate modes of operation. In the first mode, a user could change the angle of each of the servo motors through a physical interface with an IMU and two joysticks. The second mode of operation, and the more exciting one, was to change the position of the end effector of Armold to move to the same position as an AprilTag was, as long as the AprilTag was within reach of the arm. I did this with a camera connected to my laptop, and then transformed the position of the AprilTag in the camera's frame of reference to the global frame of reference. From there, I used numerical inverse kinematics to calculate the necessary servo angles, and used a TCP connection between my laptop and a RP2350 to move the servos smoothly to the new angles. I plan to design a 3D printed arm for this project, instead of using popsicle sticks, so keep an eye out for that!

### SYSEN 6680: Optimal Control and Decision Theory

### BEE 3900: Bio-Robots




