# ROS-LeapMotion-Windows
ros_leapmotion is a ROS package for the Leap Motion on Windows

## General informations

It is based on the Leap Motion SDK 4.0.0. Tested on windows 10 x64 with ROS Melodic and Leap Motion SDK 4.0.0+52173.

The ROS message associated to the Leap Motion contains the euclidian coordinates of the hand joints.


## How to use it

Download and install the Leap Motion SDK Orion 4.0.0. https://developer.leapmotion.com/releases (you need to creat a free account).

The CMakeList file and the system path might be modified to match your configuration :
- Line 139 : The root to the the LeapC.lib file must be specified. For exemple, if the package is in the workspace "C:\catkin_ws\", the root to the LeapC.lib is "C:/catkin_ws/src/ros_leapmotion/lib/x64/LeapC.lib". Use "x64" for a 64 bits system and "x86" for a 32 bits system.
- The root of the dll file must be added to the system path. For this exemple, add "C:\catkin_ws\src\ros_leapmotion\lib\x64" to the path (Once again, change "x64" to "x86" for a 32bits system).

Once the package is build, you can run the leapmotion node with :
```
rosrun ros_leapmotion leapmotion_node
```
The node "leapmotion_node" sends messages on the "leapmotion_raw" topic.
The content of the message can be found in the folder "ros_leapmotion/msg".

If you want to get more information from the leapmotion, you might want to modify the file "ros_leapmotion/src/sender.cpp". 
