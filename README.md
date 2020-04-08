This will describe how to do forward and inverse kinematic analysis to control the end point effector of a robotic pick and place arm using the robot operating system(ROS).

Requirements:

I used the following environment to work on the project:
-Ubuntu 16.04 LTS OS
-ROS Kinetic 1.12.12
-Gazebo 7.9
-RVIZ version 1.12.15


After installing Ross on Ubuntu, we will build the workspace and download the project files as follows:
-Create a WorkSpace:
	$ mkdir -p ~/catkin_ws/src
	$ cd ~/catkin_ws/
	$ catkin_make

-Download the repository project files:
	$ cd ~/catkin_make/src/ 
	$ git clone https://github.com/udacity/RoboND-Kinematics-	Project.git

-Installation of missing dependencies:
	$ cd ~/catkin_ws
	$ rosdep install --from-paths src --ignore-src –	rosdistro=kinetic -y

-Change script permissions to make them executable:
	$ cd ~/catkin_ws/src/RoboND-Kinematics-				Project/kuka_arm/scripts
	$ sudo chmod u+x target_spawn.py
	$ sudo chmod u+x IK_server.py
	$ sudo chmod u+x safe_spawner.sh
	
-Build the project:
	$ cd ~/catkin_ws
	$ catkin_make

-bash file:
	$ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
	$ echo "export GAZEBO_MODEL_PATH=~/catkin_ws/src/RoboND-	Kinematics-	Project/kuka_arm/models" >> ~/.bashrc
	$ source ~/.bashrc

-Run the project, and ensure everything is working.
	open file "inverse_kinematics.launch" it locate in 	/catkin_ws/src/RoboND-	Kinematics-Project/kuka_arm/launch, and change the "demo value" to "true".


<launch>
  <node name="trajectory_sampler" pkg="kuka_arm" type="trajectory_sampler">
    <!--set demo value="false" when using IK_server-->
    <param name="demo" value="false" type="bool"/>
  </node>
</launch>

	$ cd ~/catkin_ws/src/RoboND-Kinematics-	Project/kuka_arm/scripts/
	$ ./safe_spawner.sh

-Now you can see both GAZEBO and RVIZ running as I show now:

you can click at RVIZ (next) to see the project.

i
alpha
a
d
theta

0<1
0




1<2





2<3





3<4





4<5





5<6





6<EE






