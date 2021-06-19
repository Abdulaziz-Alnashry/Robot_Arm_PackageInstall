# Robot_Arm_PackageInstall
In this project I installed and initiated the Arduino package for robot arm and tested that it's working as expected in both Rviz and Gazebo via ROS. 
*** STEPS ***
First: Preparing ROS by creating a workspace using Catkin_make 
- Mine was mellodic so the command was as following:
 $ source /opt/ros/melodic/setup.bash

$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make

- And now after preparing the workspace, it's time to install the arm package into Src folder as following:

  $ cd ~/catkin_ws/src
	$ sudo apt install git
	$ git clone https://github.com/smart-methods/arduino_robot_arm 
  
- installing the dependencies now:

  $ cd ~/catkin_ws
	$ rosdep install --from-paths src --ignore-src -r -y
	$ sudo apt-get install ros-melodic-moveit
	$ sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
	$ sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
	$ sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control

- time to compile the package:

 $ catkin_make

*** Launching Rviz and controll the motors ***
 $ roslaunch robot_arm_pkg check_motors.launch
 (Screenshot uploaded)
 
 *** Movelt in Rviz ***
 $ roslaunch moveit_setup_assistant setup_assistant.launch
(Screenshot uploaded)

*** Gazebo ***
$ roslaunch moveit_pkg demo_gazebo.launch

 
