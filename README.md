# turtlebot_PID

```
sudo apt-get install ros-kinetic-turtlebot*

cd catkin_ws/src

git clone https://github.com/turtlebot/turtlebot.git  
git clone https://github.com/turtlebot/turtlebot_msgs.git
git clone https://github.com/turtlebot/turtlebot_apps.git
git clone https://github.com/turtlebot/turtlebot_interactions.git
git clone https://github.com/turtlebot/turtlebot_simulator.git

cd ..
catkin_make

roslaunch turtlebot_gazebo turtlebot_world.launch world_file:=/home/kulbir/catkin_ws/src/turtlebot_simulator/turtlebot_gazebo/worlds/empty.world  

catkin_make -DCATKIN_WHITELIST_PACKAGES="turtlebot_pid"  

rostopic pub /mobile_base/commands/reset_odometry std_gs/Empty  

roslaunch turtlebot_pid gotogoal.launch


```




