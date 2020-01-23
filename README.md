# Turtlebot2_PID
The aim of this project is to control the Turtlebot2 using PID. The user inputs the goal location and the turtlebot goes there using a PID controller.

---

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

