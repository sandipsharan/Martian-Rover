# ENPM662 - Project 2  <br /> Modeling and Simulation of Martian Rover

## 1. Project Goals

1. Build a martian rover model on SolidWorks and export it as URDF.

2. To achieve the goals mentioned in the project proposal.

3. Simulate the rover in the martian environment in Gazebo and visualize it using RViz.

4. Code up a simple publisher and subscriber for your rover to move.

## 2. Installation of Dependencies

We need ROS to run the modeled rover
To install the ROS - Noetic type the following command in the terminal:

```` 
$ sudo apt install ros-noetic-desktop-full
````
To install the python 3 type the following command in the terminal:

```` 
$ sudo apt-get install python3
````

## 3. Setting up the package

1. Download the folder Sandip26_Project2<br />

2. When you unzip the file, you will see a main folder named Sandip26_Project2, which contains subfolders such as Package, Assembly, and Report.<br />

3. Inside the package is the ROS package which is required to run the rover & the package is named as mars_rover_v8<br />

4. Go to your catkin_ws by typing the command  ````$ cd <your catkin_ws_name>```` 

5. Place that package in your catkin_ws<br />

6. Then run the command ```` $ catkin_make clean && catkin_make ```` to build the package<br />

7. Source ROS everytime you open a new terminal or made any changes in the ROS package using the command
````
source devel/setup.bash
````
## 4. Instruction to run RViz to visualize LiDAR

1. Open two terminals and source ROS using the command mentioned above <br />

2. Run the command below to launch the toy car in Gazebo environment
```` 
roslaunch mars_rover_v8 template_launch.launch 
```` 
3. When you want to spawn the rover in Martian world uncomment the line shown below
````
<arg name="world_name" value="$(find mars_rover_v8)/worlds/mars_curiosity.world"/>
````
4. Then change the z value in pos to -8.75 from 0, so that it'll get spawned perfectly on the land

5. In your other terminal run the command, to launch RViz
````
rosrun rviz rviz
````

4. Add the RobotModel and Camera. There you go you can see the Rover and Camera visualization in RViz

## 5. Instructions to run the toy car using Teleop

1. Open two terminals and source ROS using the command mentioned above <br />

2. Run the command below to launch the toy car in Gazebo environment
```` 
roslaunch mars_rover_v8 template_launch.launch 
```` 
3. In your other terminal run the command, to launch the teleop controllers
````
rosrun mars_rover_v8 Script_move.py
````
