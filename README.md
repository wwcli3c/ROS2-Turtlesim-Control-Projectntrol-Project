# ROS2-Turtlesim-Control-Projectntrol-Project

This project demonstrates how to work with the turtlesim package in ROS2. It includes basic commands, topic publishing, service calls, and controlling multiple turtles.

Requirements
Ubuntu 22.04

ROS2 (Humble)

Terminal

Basic understanding of Linux and ROS2 commands

How to Use
1. Start the turtlesim node

ros2 run turtlesim turtlesim_node
2. Open another terminal and start the teleop (keyboard control)


ros2 run turtlesim turtle_teleop_key
Use the arrow keys to move the turtle.

3. List all topics

ros2 topic list
4. Move the turtle manually (via topic)

ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0}, angular: {z: 1.8}}"

5. Move the turtle to a specific location (using service)

ros2 service call /turtle1/teleport_absolute turtlesim/srv/TeleportAbsolute "{x: 5.0, y: 5.0, theta: 1.57}"

6. Change background color

ros2 param set /turtlesim background_r 0
ros2 param set /turtlesim background_g 0
ros2 param set /turtlesim background_b 0
ros2 service call /clear std_srvs/srv/Empty

7. Spawn a second turtle

ros2 service call /spawn turtlesim/srv/Spawn "{x: 2.0, y: 2.0, theta: 0.0, name: 'turtle2'}"

8. Move the second turtle

ros2 topic pub /turtle2/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 1.5}, angular: {z: 0.5}}"

9. Kill a turtle

ros2 service call /kill turtlesim/srv/Kill "{name: 'turtle2'}"
File Structure (if using scripts)
