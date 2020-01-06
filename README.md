# turtlebot_PID

```
roslaunch turtlebot_gazebo turtlebot_world.launch world_file:=/home/kulbir/catkin_ws/src/turtlebot_simulator/turtlebot_gazebo/worlds/empty.world  

catkin_make -DCATKIN_WHITELIST_PACKAGES="turtlebot_pid"  

rostopic pub /mobile_base/commands/reset_odometry std_gs/Empty  

roslaunch turtlebot_pid gotogoal.launch


```




