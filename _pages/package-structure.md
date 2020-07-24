---
permalink: /package-structure
title: Teamcode Organization
---

### Subsystem Organization
One useful way to organize your code is with a subsystem organization — essentially, we are breaking down the robot into respective hardware classes. 
* For example, for a mecanum drive train, we have one OpMode. In this example, that is Drive.java. By separating hardware into classes like this, we can test each piece of hardware separately - for example, we can test the drivetrain even when the lift is not ready to test. 
  
![Our sample subsystem organization](subsystem.png)


As you can see here, in Drive.java, we are creating a MecanumDrive object, which is our subsystem. Now, we can make use of MecanumDrive.java’s methods, like init(), controller(), getLFrontPower(), getLFrontVelocity(), etc. We also have a similar Lift subsystem, which I later used to create a Lift object in Drive as well. 


Another useful class to have is a Constants.java class, containing constants that are useful for all classes. 

Subsystems allow for more consistency and greater efficiency, encouraging abstraction and code reuse. All op modes use the same consistent interface for interacting with the robot subsystems, and all of the logic for managing the systems is in one place. For example, if you are trying to make a new autonomous opmode program, with subsystem organization, you can easily call the subsystems in that program, instead of copying and pasting all your methods into each new program.


### Utility

### Roadrunner
