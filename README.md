# Turtlebot_PID

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

In a separate terminal:-
```
cd catkin_ws
source devel/setup.bash #just in case
roslaunch turtlebot_pid gotogoal.launch



catkin_make -DCATKIN_WHITELIST_PACKAGES="turtlebot_pid"  

rostopic pub /mobile_base/commands/reset_odometry std_gs/Empty  

roslaunch turtlebot_pid gotogoal.launch




