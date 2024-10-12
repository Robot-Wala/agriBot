# agribot
Agribot is the ROS-Based Open-source mobile robot wich is capable of doing Teleoperation, Manual as well as Autonomous Mapping, Navigation, Simulation and referring this project you can make your own fully autonomous robot
#  create and build a catkin workspace: 
mkdir -p ~/catkin_ws/src  
cd ~/catkin_ws/  
catkin_make  
# Clone this repo
Use the following command to clone the reop  
$ git clone --recursive https://github.com/Robot-Wala/agribot.git

# Demos
Gazebo
![Screenshot from 2024-10-12 16-18-09](https://github.com/user-attachments/assets/c9804601-171c-492f-8a85-1729696814e5)  
RViz   
![Screenshot from 2024-10-12 16-16-41](https://github.com/user-attachments/assets/4dc4cfc9-b63d-4b4d-8725-68001e9ddd0c)  
Mapping  
![Screenshot from 2024-10-12 16-16-35](https://github.com/user-attachments/assets/f8e3dd30-569b-48cd-83e9-eadffad2d903)  
# Simulation
Open the terminal and type the following command    
$ roscore    
Then open second terminal and type the following command      
$ roslaunch agribot_description agricultureworld.launch  

This will launch up the simulation in Gazebo and you can view the gazebo simulating environment 
https://github.com/user-attachments/assets/3949c77b-f821-4cb4-93bb-c4c14a1890aa  

Just run the following command and it will open up RViz which is a robot visualization tool that helps you visualize sensor data from the robot.  

$ roslaunch agribot_description display.launch 

If you now wish to move the robot around in the Simulation, you can open up a new terminal and type in:  

rosrun teleop_twist_keyboard teleop_twist_keyboard.py

# Mapping  
Once you have tested that both Gazebo and RViz are working properly, then comes the part where you can actually simulate the robot in a virtual world and do mapping and navigation.  

The command of mapping is the same as the original robot. Just you don't need to open up RViz separetly as you already have 'display.launch' running.  

$ rosrun gmapping slam_gmapping scan:=scan

run the teleop node in a separate terminal and move the robot around once you completed generating the map run the following command to save the map

$ rosrun map_server map_saver -f name_of_map

![grapesfarm](https://github.com/user-attachments/assets/ea8ada20-e71b-4903-b545-f3162341b8dc)

# Navigation
open the new terminal and run following command so that the navigation will start and once you set the goal in the RViz  robot will autonomously move and reach the goal 

roslaunch agribot_navigation agribot_navigation.launch 


https://github.com/user-attachments/assets/a7fb8ab6-87fd-4cbb-be88-ceeac5a461d8


