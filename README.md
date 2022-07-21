# RVIZ + GAZEBO  + Arduino + Rosserial Arduino + Ros_lib + Arduino upload installation 

* Running RVIZ + Controlling the motors in sumulation + Move it in RVIZ + GAZEBO launch
RVIZ Initiation 

-	Create a workspace for catkin based on the type you have mine is melodic

•	sudo apt-get install ros-melodic-catkin

-	Within the catkin_ws directory there is a source file 

•	mkdir -p ~/catkin_ws/src

-	Name it as catkin work
•	cd ~/catkin_ws/

-	To install the package type this command 
•	catkin_make

-	Get in the source folder by using this command 
•	cd ~/catkin_ws/src

-	Install the robotic arm package by using this command
•	git clone https://github.com/smart-methods/arduino_robot_arm.git 

-	Enter the  catkin_ws folder 
•	cd ~/catkin_ws

-	Install the commands needed from ROS by using these commands below
•	rosdep install --from-paths src --ignore-src -r -y

•	sudo apt-get install ros-melodic-moveit

•	sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui

•	sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher

•	sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control

-	Get to the  bashrc file and add the following  text below
•	sudo nano ~/.bashrc

•	at the end of the (bashrc) file add the follwing line
•	(source /home/reemaalmurayshid/catkin_ws/devel/setup.bash)
•	then 
•	ctrl + o

-	Update the sources of bashrc using this command 
•	source ~/.bashrc

-	Launch the RVIZ using this command 
•	roslaunch robot_arm_pkg check_motors.launch


-------------------------------------------------------------------------------------------------------------------------
Install Arduino 
1.	Go to the main website :
 https://www.arduino.cc/en/software
2.	Choose your operating system I chose 64 bits Linux 
3.	Extract the zip file 
4.	Open in terminal 
5.	Type the command ./install.sh  to install Arduino 
6.	Check if the program is present 
7.	Open the Arduino program 
8.	You  will see a folder  called an Arduino once you open the program 
-------------------------------------------------------------------------------------------------------------------------
Install Rosserial  Arduino  by using these two command :
•	sudo apt-get install ros-melodic-rosserial-arduino
•	 sudo apt-get install ros-melodic-rosserial

-------------------------------------------------------------------------------------------------------------------------------
Install ros_lib 
•	$cd <sketchbook>/libraries
•	$rm-rf ros lib
•	$ rosrun rosserial _arduino make_libraries.py .


-----------------------------------------------------------------------------------------------------------------------------------
Uploade the Arduino code
- select the Arduino port to be used on Ubuntu system
- change the permissions (it might be ttyACM)
•	$ ls -l /dev |grep ttyUSB
•	$ sudo chmod -R 777 /dev/ttyUSB0
- upload the code from Arduino IDE
-----------------------------------------------------------------------------------------------------------------------------
Run Rviz
•	$ roslaunch robot_arm_pkg check_motors.launch
•	$ rosrun rosserial_python serial_node.py _port:=/dev/ttyUSB0 _baud:=115200
-----------------------------------------------------------------------------------------------------------------------------
Controlling the motors in simulation
•	$ roslaunch robot_arm_pkg check_motors.launch
•	$ roslaunch robot_arm_pkg check_motors_gazebo.launch
•	$ rosrun robot_arm_pkg joint_states_to_gazebo.py
•	You may need to change the permission
•	$ cd catkin/src/arduino_robot_arm/robot_arm_pkg/scripts
•	$ sudo chmod +x joint_states_to_gazebo.py 
--------------------------------------------------------------------------------------------------------------------------
Moveit in rviz 
•	$ roslaunch moveit_pkg demo.launch $

---------------------------------------------------------------------------------------------------------------------------
Gazebo launch 
•	$roslaunch moveit_pkg demo_gazebo.launch $

