# Turtlebot3_with_SLAM_Simulation_on_ROS
## Install ROS "Melodic"
Open the terminal and enter the below commands one at a time
```
$ sudo apt update
$ sudo apt upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh
$ chmod 755 ./install_ros_melodic.sh 
$ bash ./install_ros_melodic.sh
```

### Install Dependent ROS Packages
```
$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
  ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc \
  ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan \
  ros-melodic-rosserial-arduino ros-melodic-rosserial-python \
  ros-melodic-rosserial-server ros-melodic-rosserial-client \
  ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server \
  ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro \
  ros-melodic-compressed-image-transport ros-melodic-rqt* \
  ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers 
  ```

### Install TurtleBot3 Packages
```
$ sudo apt-get install ros-melodic-dynamixel-sdk
$ sudo apt-get install ros-melodic-turtlebot3-msgs
$ sudo apt-get install ros-melodic-turtlebot3
```

### Set TurtleBot3 Model Name
- In case of TurtleBot3 Burger
```
$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
```

- In case of TurtleBot3 Waffle Pi
```
$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc
```

### Launch Simulation World
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

### Run SLAM Node
open a new terminal
``` 
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```

### Run Teleoperation Node
open a new terminal
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
``` 

### Save Map
open a new terminal
```
$ rosrun map_server map_saver -f ~/map
```

![image](https://github.com/Rama-Alyoubi/Turtlebot3_with_SLAM_Simulation_on_ROS/assets/128150728/a083e4ee-15fd-4a2b-8b61-43804ab383f8)
![image](https://github.com/Rama-Alyoubi/Turtlebot3_with_SLAM_Simulation_on_ROS/assets/128150728/1e84f901-3aca-4c57-952f-a9a5f118b038)
![image](https://github.com/Rama-Alyoubi/Turtlebot3_with_SLAM_Simulation_on_ROS/assets/128150728/9141a435-2de7-4569-a4fc-a2f2aa734861)
