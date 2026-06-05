# About Me

<div style="display: flex; align-items: center; gap: 20px;">
  <img src="Images/website_photo.png" alt="Me!" style="width: 186px; height: 178px"/>
  <div>
    My name is [Hilario (Lalo) Esparza](https://www.linkedin.com/in/hilario-esparza/), and I am an engineering student attending Cornell University. I recently graduated with my B.S. in Electrical and Computer Engineering from Cornell, and I am now completing my M.Eng. in Systems Engineering, with a focus on robotics. While I have many interests, I find robotics to be a wonderful blend of controls, state estimation, cyber-physical systems, and hardware and sofrware development and debugging. Particularly, I find swarm, bio-inspired, and field robotics to be very intruiging fields with loads of potential for the automotive, space, agriculture, and research industries.
  </div>
</div>

# Projects

This will be updated as I start and complete more projects!

## Course Work

### [ECE 4160: Fast Robots](https://hilarioesparza.github.io/fastrobots-2026/)

This lab-based class focused on the hardware and software development and debugging process of a robotic car. We took the electrical guts out of a toy RC car, rebuilt it with our own system, and then programmed it to perform mapping, localization, Kalman filter aided position and orientation PID control, and cool stunts! My favorite part of the class was working on the inverted pendulum challenge in the last lab.

### ECE 4760: Digital Systems Design Using Microcontrollers

This was another fun lab-based class I took during my undergraduate career at Cornell. The class focused on four different labs, each using different peripherals and concepts to develop interesting systems using an RP2040. In the first lab, we developed a bird song synthesizer, the second lab worked on developing a digital Galton Board, and in the third lab we implemented a pitch PID controller for a drone motor. Out of those three, the PID controller was my favorite, and my lab group was able to get the pitch to be within a ~2% error from its desired value. For the final lab, we got to choose our own system to implement. We decided to create a virtual drum set machine called [DigiDrum](https://www.youtube.com/watch?v=fSZf4prnDR0). Unfortunately, no one in my lab group was particularly musically talented!

### SYSEN 5410: Cyber-Physical Systems

This class complimented the above two classes very nicely, as it applied a systems level approach and understanding to similar technical challenges. We learned about TCP, UDP, and MQTT networking paradigms; signal processing and filtering; Kalman and Bayes filters; and a foundation in computer vision. I used what was learned in this lab to build a prototype robot arm, which I named [Armold](https://youtu.be/8_QH_XWPAGs). Armold was a 3DoF robotic arm built with four servo motors, and it had two separate modes of operation. In the first mode, a user could change the angle of each of the servo motors through a physical interface with an IMU and two joysticks. The second mode of operation, and the more exciting one, was to change the position of the end effector of Armold to move to the same position as an AprilTag was, as long as the AprilTag was within reach of the arm. I did this with a camera connected to my laptop, and then transformed the position of the AprilTag in the camera's frame of reference to the global frame of reference. From there, I used numerical inverse kinematics to calculate the necessary servo angles, and used a TCP connection between my laptop and a RP2350 to move the servos smoothly to the new angles. I plan to design a 3D printed arm for this project, instead of using popsicle sticks, so keep an eye out for that!
