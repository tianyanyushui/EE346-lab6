# lane following
This is the lab resources for SUSTech EE346.

# Usage

## 1. Clone the source code
  sudo apt-get install ros-melodic-navigation
  cd ~/catkin_ws/src
  git clone https://github.com/tianyanyushui/EE346-lab6
  
## 2. Catkin make the EE346-lab6 package
  cd ..
  
  catkin_make

## 3. Add course models to the end of ~/.bashrc in computer(replace 192.168.3.244 as your comuter ip)
   export TURTLEBOT3_MODEL=burger
   export ROS_MASTER_URI=http://192.168.3.244:11311
   export ROS_HOSTNAME=192.168.3.244
   
## 4. Add course models to the end of ~/.bashrc in your robot(replace 192.168.3.244 as your comuter ip,192.168.3.81 as your robot ip)
   export ROS_MASTER_URI=http://192.168.3.244:11311
   export ROS_HOSTNAME=192.168.3.81

## 5. Source the .bashrc file(in both computer and robot)
   source ~/.bashrc
   
## 6. Connect your robot(replace 192.168.3.81 as your robot ip)
   roscore 
   
   in a new  terminal: ssh pi@192.168.3.81
   
   roslaunch turtlebot3_bringup turtlebot3_robot.launch
   
## 7. Run lane following python node
   
   cd ~/catkin_ws/src/EE346-lab6/lab6/scripts/
   
   chmod +x lane_following_please.py
   
   cd ~/catkin_ws
   
   source devel/setup.bash
   
   rosrun EE346-lab6 lane_following_please.py
   
## 8.1 Open the map
   cd ~/catkin_ws/src/EE346-lab6/
   
   roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map_new.yaml

   
## 8.2 Run navigation node
   cd ~/catkin_ws/src/EE346-lab6/lab6/scripts/
   
   chmod +x navigation_demo.py
   
   cd ~/catkin_ws
   
   source devel/setup.bash
   
   rosrun EE346-lab6 navigation_demo.py
   
## 9. Stop the robot   
   cd ~/catkin_ws/src/EE346-lab6/lab6/scripts/
   python lane_following_reset.py 


