RVIZ Initiation

- Create a workspace for catkin based on the type you have mine is melodic

sudo apt-get install ros-melodic-catkin

- Within the catkin_ws directory there is a source file

mkdir -p ~/catkin_ws/src

- Name it as catkin work

cd ~/catkin_ws/

- To install the package type this command

catkin_make

- Get in the source folder by using this command

cd ~/catkin_ws/src

- Install the robotic arm package by using this command

git clone https://github.com/smart-methods/arduino_robot_arm.git

- Enter the catkin_ws folder

cd ~/catkin_ws

- Install the commands needed from ROS by using these commands below

rosdep install --from-paths src --ignore-src -r -y

sudo apt-get install ros-kinetic-moveit

sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui

sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control

- Get to the bashrc file and add the following text below

sudo nano ~/.bashrc

at the end of the (bashrc) file add the follwing line

(source /home/reemaalmurayshid/catkin_ws/devel/setup.bash)

then

ctrl + o

- Update the sources of bashrc using this command

source ~/.bashrc

- Launch the RVIZ using this command

roslaunch robot_arm_pkg check_motors.launch
