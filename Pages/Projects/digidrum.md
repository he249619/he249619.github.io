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

For a more in-depth discussion and documentation of this project, please visit [this DigiDrum website](Images/DigiDrum/ace68_hle37_lag289.html) that my labmates and I created.

## Personal Contribution

While my lab partners and I shared a lot of the work and spent many hours collaborating on the different aspects of the system, the part of the project that I spent the most time working on was definitely the strike detection logic.

I spent a long time trying different methods of utilizing the IMU data in order to determine when the user had made a valid striking motion with the drumstick. What we at first thought would be a trivial acceleration magnitude check quickly became much more complicated. Through the course of experimentation, we found that when making a striking motion, the arm suddenly stopped after moving and unintentionally introduced oscillatory behavior. These oscillations would confuse our system about how many valid strikes the user made. 

Consequently, we had to abandon our first method of strike detection, which was simply looking at the magnitude of the acceleration of the drumstick. I then tried many other ways of pairing together both the accelerator’s and gyroscope’s data, looking at both their magnitude and sign, in an attempt to achieve a valid strike detection system. However, when trying to essentially create a heuristic that looked at the magnitude and/or sign of the data, I found that there were always cases where a false strike was considered valid and a valid strike was disregarded as false. For our system to work, it needed to be responsive to the user’s true striking motion and nothing else, in addition to not double counting a single striking motion.

It became frustrating because no matter what process I tried, the strike detection did not work well. However, when we graphed the IMU data, we could visually tell when a strike was valid or not, and this informed us that there must be a way for the microcontroller to do it as well. After talking with one of the TAs of our lab, I decided to try to implement a correlation filter and ring buffer.

A correlation filter works by isolating the most interesting or important aspects of a certain set of data, and then creating a weighted sum of those aspects. It is important to choose the weights carefully so that they average to 0. This means that when the incoming data is noisy or doesn’t have the desired characteristics, the sum of the important parts of the data will be close to 0, on average. However, when the data has the characteristics that resemble the desired output, this summation will become a large positive number. From there, a simple threshold could be created, and we were then able to compare any drumstick motion to the data of a valid strike, and if the data drumstick motion matched up well with the valid strike, our system could trigger the corresponding noise.

This system allowed for a significant increase in the correct detection rate, while also not detecting false strikes and not double counting a single striking motion.

To implement this filter, I created two ring buffers to store acceleration data, one for each drumstick. The ring buffers were simple arrays in C, and I used two separate integer variables to index the arrays. The variables index variables increment with every time step, eventually overflowing back to zero. However, this behavior was a feature for our product, not a bug. By making each array’s length to be an integer to the power of two, and by masking the index variables with the length of the arrays in binary with padded zeros as the most significant bits, these counters would always access some index within the range of the list. Furthermore, the index the counters would access always incremented to the next position in the array in between time steps, and it would loop back from the end of the array to the beginning.

This created a strike detection system that smoothly and accurately detected a valid striking motion and that didn’t create false detections.
