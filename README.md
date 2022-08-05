biotac_driver
==============

Overview
---------------------------------------------

Biotac low level driver and ROS nodes from UPenn's `biotac_stack` contained in the **Penn-haptics-bolt** repository (https://github.com/IanTheEngineer/Penn-haptics-bolt.git).

The following instructions are from the README.md file in the **Penn-haptics-bolt** respository. For more details also look at the UPenn Haptics group's wiki page: http://bolt-haptics.seas.upenn.edu/index.php/Main/HomePage 


Installing 
---------------------------------------------

### ROS package installation ###

After copying the Cheetah udev rules you can download and compile the ROS package. Also make sure you have a working catkin workspace (look at the ROS tutorials).

Download the package to the catkin workspace:

    cd ~/catkin_ws/src/
    git clone -b noetic https://github.com/kth-ros-pkg/biotac_driver.git
    cp 99-totalphase.rules /etc/udev/rules.d/
    cd ~/catkin_ws && catkin_make

Electrical connections
---------------------------------------------

(Try for this order, but it doesn't really matter)
1. Plug the biotac sensors into the Multi-BioTac board

2. Plug the +5V nano-USB cable into the MBTB and your computer's USB

3. Plug the Cheetah's 10 pin ribbon cable into the MBTB

4. Plug the Cheetah's USB into your computer's USB port


Running the ROS nodes 
---------------------------------------------

1. To start reading the sensors
    rosrun biotac_sensors biotac_pub

2. Check to make sure your sensors are working:
    rostopic echo biotac_pub

3. Then to log some data in JSON form:
    rosrun biotac_logger biotac_json_logger.py _filename:=trial_001.json


Matlab GUI 
---------------------------------------------

Please see the Penn Bolt Wiki for instructions on how to use the GUI

http://bolt-haptics.seas.upenn.edu/index.php/Software/MatlabGUI



