# Turtlebot_PID
The aim of this project is to control the Turtlebot2 using PID. The user inputs the goal location and the turtlebot goes there using a PID controller.

---

## Moving the Turtlebot
We can move the turtlebot by:-
1. Publishing to the concerned topics
2. Using teleop.launch which takes inputs from the user using the keyboard.

### By publishing to the topic /cmd_vel
1. To control the velocity of the robot, we publish to the topic **/cmd_vel**. 
2. Use the command **rostopic info /cmd_vel_mux/input/teleop** to see the type of message required to be sent to the topic, the publishers to the topic and the subscribers to the topic.
3. Use **rosmsg show geometry_msgs/Twist** to see the details of the message type.



To install Turtlebot 2:-
```
sudo apt-get install ros-kinetic-turtlebot*
```
To clone the associated packages in the Catkin workspace:-
```
cd catkin_ws/src

git clone https://github.com/turtlebot/turtlebot.git  
git clone https://github.com/turtlebot/turtlebot_msgs.git
git clone https://github.com/turtlebot/turtlebot_apps.git
git clone https://github.com/turtlebot/turtlebot_interactions.git
git clone https://github.com/turtlebot/turtlebot_simulator.git

cd ..
catkin_make
```
To run the simulation:-
```
cd catkin_ws
source devel/setup.bash #just in case

roslaunch turtlebot_gazebo turtlebot_world.launch world_file:=/home/kulbir/catkin_ws/src/turtlebot_simulator/turtlebot_gazebo/worlds/empty.world  
```

In a separate terminal:-
```
cd catkin_ws  
source devel/setup.bash #just in case 
```
Use the following command to source the setup file if you're using Z shell:- 
```
source devel/setup.zsh
```
To launch the file to make the turtlebot go to a particular position:-
```
roslaunch turtlebot_pid gotogoal.launch  
```

To launch the file to make the turtlebot go to a particular angle:-
```
roslaunch turtlebot_pid gotoangle.launch  
```

If you make any changes to the python file, then do catkin_make or:-
```
catkin_make -DCATKIN_WHITELIST_PACKAGES="turtlebot_pid"
```
To see the info:-
```
rostopic pub /mobile_base/commands/reset_odometry std_gs/Empty
```
## References:-
1. https://github.com/Zhanghq8/Turtlebot_PID_Controller (This uses Turtlebot2)
2. Robot Ignite Academy: Mastering with ROS: Turtlebot3

