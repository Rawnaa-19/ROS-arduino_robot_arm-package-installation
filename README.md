# ROS & arduino_robot_arm Package Installation
The following steps describe how I installed ROS on Ubuntu 18.04 and launched the robot arm .

## 1. Installing VirtualBox
<kbd>![image](https://github.com/Rawnaa-19/ROS-arduino_robot_arm-package-installation/assets/106926557/dfe93a6f-cb11-4e35-aba8-78c115e74ce0)</kbd>


## 2. Installing Ubuntu 18.04 into VirtualBox 
<kbd>![image](https://github.com/Rawnaa-19/ROS-arduino_robot_arm-package-installation/assets/106926557/cecb437d-d74d-42c6-85b7-ac80e41a8925)</kbd>


<kbd>![image](https://github.com/Rawnaa-19/ROS-arduino_robot_arm-package-installation/assets/106926557/5647f1d4-8239-4cc0-b16d-a1c59ad20d97)</kbd>

## 3. Installing ROS melodic
Installation of ROS melodic was done by running the following commands into the Ubuntu terminal
```
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
$ sudo apt update
$ sudo apt install ros-melodic-desktop-full
$ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
$ sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
$ sudo apt install python-rosdep
$ sudo rosdep init
$ rosdep update
```

## 4. Creating catkin workspace
```
$ source /opt/ros/noetic/setup.bash
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make
$ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
```

## 5. Installing arduino_robot_arm Package
```
$ cd ~/catkin_ws/src
$ sudo apt install git
$ git clone https://github.com/smart-methods/arduino_robot_arm 
$ cd ~/catkin_ws
$ rosdep install --from-paths src --ignore-src -r -y
$ sudo apt-get install ros-melodic-moveit
$ sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
$ sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
$ sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control
$ catkin_make
```

## 6. Launching the robot arm
```
$ roslaunch robot_arm_pkg check_motors.launch

```
</kbd>![image](https://github.com/Rawnaa-19/ROS-arduino_robot_arm-package-installation/assets/106926557/c6c8b34a-4555-452e-a2df-2d71e6f38af0)</kbd>

