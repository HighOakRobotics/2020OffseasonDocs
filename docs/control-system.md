---
permalink: /control-system
title: Understanding FTC Control System Hardware
---

### The FTC Control System

|---|
| Pt 1 | Pt 2 |
|-|-|
| REV Control System/Expansion Hub | Sensors (Color, Distance, Limit, Touch) |
| Battery | Camera |
| Motor/Encoder | Phone |
| Servo | Gamepad |
|---|

### FTC Control System Example - Skystone
![FTC Skystone Control System Setup](skystone_system.png)

### DC Motor
A direct current, or DC motor, converts electrical energy into mechanical energy. In robotics, we use DC motors to allow the robot to be battery-powered and for variation in speed. Two of the motors typically used in FTC are the REV Robotics Core Hex Motor and the REV Robotics HD Hex Motor. The Core Hex Motor has a 90-degree orientation, a female output shaft, and a build-in encoder. The HD Hex Motor features a gearbox and a mounted encoder.

### Encoder
Encoders are used to help accurately control movement by translating rotary or linear motion into a digital signal. They are essentially a sensor that measures motor movement, usually in the form of position or rotation. Encoders are attached to or integrated into drive motors and count the revolutions of the motor shaft either optically or magnetically. The DcMotor object has support for using encoder counts to control how long the motor will run when turned on.

### Motor with Encoder Control
Now that we know about motors and encoders, let’s look at some motors with encoder control.The NeveRest motors are gearmotors with an attached encoder. Typically, with a NeveRest Orbital 20 you get twice the speed but half the torque of a 40. 40s are often used for direct drive to 4" wheels whereas 20s would struggle (especially with a heavy robot) because they don't have enough torque to get the robot going fast enough. This is the cable designed for the encoder that is pre-attached to the NeveRest Series of motors and gearmotors. It has a connector on the opposite end to directly interface between the NeveRest encoder and the REV Expansion Hub.

### Servo
So what is a servo? A servomechanism, or servo for short, is an automatic device that uses error-sensing negative feedback to correct the action of a mechanism. It usually includes a built-in encoder or other position feedback mechanism to ensure the output is achieving the desired effect. Servos allow for very precise control of rotational speed, linear speed, and position. When coding a 180-degree servo, its position can go from 0 to 1 and can rotate 180 degrees, but a continuous rotation servo rotates until a stop command is issued.

### Sensors
Let’s move on to sensors. Here are 4 commonly used FTC sensors: color, touch, limit, and distance. 
* Color Sensor
  * A color sensor works by measuring the reflected color of an object, and it can also measure the distance from the sensor to other objects. 
* Touch Sensor
  * These signal code that something has happened when the button is pushed. Touch sensors are on a default high state, returning true when it is not pressed, and false when pressed. 
* Limit Switch
  * Limit switches signal when mechanical parts reach a certain point and the user wants them to stop, preventing mechanisms from moving too far past its limit—hence the name “limit switch”. This can help avoid any damage to your hardware. 
* Distance Sensor
  * This sensor determines the proximity of an object without having to have any physical contact with the other object.
  
### Camera/Vision
Let’s move on to vision. [Vuforia](https://developer.vuforia.com/downloads/sdk) is an augmented reality software development kit for mobile devices that enables the creation of augmented reality applications. This library uses computer vision technology to recognize and track planar images and simple 3D objects. The way it works is that it matches images caught from a camera to a pre-defined reference image. So a really important advantage of Vuforia is that it can analyze both images while searching for specific feature points. Unfortunately, one disadvantage of Vuforia is that it only processes a reference image once when searching for these feature points. Thus, if the image does not have enough feature points, it will likely not be detected well. So for flat markers like the skystone images in the 2019-2020 season, there are limitations to using Vuforia because in order to be recognized, flat markers need to have contrasting coloring, preferably with small details that will act as unique elements to be bound to. Open Source Computer Vision, or [OpenCV](https://sourceforge.net/projects/opencvlibrary/files/opencv-win/), is a library designed for computational efficiency and with a strong focus on real-time applications. During the 2019-2020 season, we used OpenCV for our autonomous code to locate the skystone upon initialization. What we liked about OpenCV is that OpenCV is highly customizable. It has plenty of algorithms, although some of them do require knowing some math topics like derivatives, vector algebra, applied math, and data types. Unlike Vuforia, OpenCV can work with big or very small and even damaged images. We’ll go more into depth with vision in Workshop 5.



