--- 
title: "DigiDrums"
description: "Project Documentation for DigiDrums"
layout: default
---

# DigiDrums: A Cyber-Physical Drum Simulator

DigiDrum is a drum set simulator. I worked on this project with [Aislinn Ennis](https://www.linkedin.com/in/aislinn-ennis/) and [Leah Glasser](https://www.linkedin.com/in/leah-glasser-872248321/) in ECE 4760: Digital Systems Design Using Microcontrollers.

## High Level Overview

The user can hold a drumstick in either hand and can kick a footpedal, and when a drumstrike is detected, the corresponding noise is played from a set of speakers nearby. In this way, using the drumsticks and footpedal like as normal can feel like you are playing a real drumset even though there are no drums or hi-hats present.

<p align="center"> 
<iframe width="560" height="315" src="https://www.youtube.com/embed/fSZf4prnDR0" title="ECE 4160: Lab 8 Fast Drift" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen> </iframe> 
</p> 

The system uses a RP2040 microcontroller as the computational power. An IMU is placed on each drum stick in order to estimate the motion of the user’s hand, communicating with the RP2040 through an I2C bus. A DAC is also connected to the RP2040 and communicates via SPI, and audio recordings of a snare, a hi-hat, and a base drum are sent to the DAC via DMA. This output is then played on a set of speakers. 

For a more in-depth discussion and documentation of this project, please visit [this DigiDrum website](file:///Users/hilarioesparza/Desktop/ace68_hle37_lag289%202/ace68_hle37_lag289.html) that my labmates and I created.

## Personal Contribution

While my lab partners and I shared a lot of the work and spent many hours collaborating on the different aspects of the system, the part of the project that I spent the most time working on was definitely the strike detection logic.

