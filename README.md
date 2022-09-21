###$ sudo apt update

asadbek@ubuntu:~$ sudo apt update
Hit:1 http://packages.microsoft.com/repos/code stable InRelease
Hit:2 http://packages.ros.org/ros/ubuntu focal InRelease                        
Hit:3 http://us.archive.ubuntu.com/ubuntu focal InRelease                       
Hit:4 http://packages.ros.org/ros2/ubuntu focal InRelease                       
Hit:5 http://us.archive.ubuntu.com/ubuntu focal-updates InRelease               
Get:6 http://us.archive.ubuntu.com/ubuntu focal-backports InRelease [108 kB]
Get:7 http://us.archive.ubuntu.com/ubuntu focal-security InRelease [114 kB]
Hit:8 http://archive.canonical.com/ubuntu focal InRelease                
Fetched 222 kB in 5s (43.1 kB/s)
Reading package lists... Done
Building dependency tree       
Reading state information... Done
26 packages can be upgraded. Run 'apt list --upgradable' to see them.


###$ sudo apt install ros-foxy-turtlesim
asadbek@ubuntu:~$ sudo apt install ros-foxy-turtlesim
Reading package lists... Done
Building dependency tree       
Reading state information... Done
ros-foxy-turtlesim is already the newest version (1.2.5-1focal.20220209.151154).
0 upgraded, 0 newly installed, 0 to remove and 26 not upgraded.


###source the ros2 and check the pakages
asadbek@ubuntu:~$ source /opt/ros/foxy/setup.sh
ROS_DISTRO was set to 'noetic' before. Please make sure that the environment does not mix paths from different distributions.
asadbek@ubuntu:~$ ros2 pkg executables turtlesim
turtlesim draw_square
turtlesim mimic
turtlesim turtle_teleop_key
turtlesim turtlesim_node
asadbek@ubuntu:~$ ros2 run turtlesim turtlesim_node
[INFO] [1663640360.666032002] [turtlesim]: Starting turtlesim with node name /turtlesim
[INFO] [1663640360.677479702] [turtlesim]: Spawning turtle [turtle1] at x=[5.544445], y=[5.544445], theta=[0.000000]


####Check the list
asadbek@ubuntu:~$ ros2 node list
/teleop_turtle
asadbek@ubuntu:~$ ros2 topic list
/parameter_events
/rosout
/turtle1/cmd_vel
asadbek@ubuntu:~$ ros2 service list
/teleop_turtle/describe_parameters
/teleop_turtle/get_parameter_types
/teleop_turtle/get_parameters
/teleop_turtle/list_parameters
/teleop_turtle/set_parameters
/teleop_turtle/set_parameters_atomically
asadbek@ubuntu:~$ ros2 action list
/turtle1/rotate_absolute
asadbek@ubuntu:~$ 


####Run the turtle_teleop_key
asadbek@ubuntu:~$ source /opt/ros/foxy/setup.sh
ROS_DISTRO was set to 'noetic' before. Please make sure that the environment does not mix paths from different distributions.
asadbek@ubuntu:~$ ros2 run turtlesim turtle_teleop_key
Reading from keyboard
---------------------------
Use arrow keys to move the turtle.
Use G|B|V|C|D|E|R|T keys to rotate to absolute orientations. 'F' to cancel a rotation.
'Q' to quit.

####Run turtlesim turtlesim_node
asadbek@ubuntu:~$ source /opt/ros/foxy/setup.sh
ROS_DISTRO was set to 'noetic' before. Please make sure that the environment does not mix paths from different distributions.
asadbek@ubuntu:~$ ros2 run turtlesim turtlesim_node
[INFO] [1663641213.835052574] [turtlesim]: Starting turtlesim with node name /turtlesim
[INFO] [1663641213.843843646] [turtlesim]: Spawning turtle [turtle1] at x=[5.544445], y=[5.544445], theta=[0.000000]
[INFO] [1663641652.042988255] [turtlesim]: Spawning turtle [turtle2] at x=[1.000000], y=[1.000000], theta=[0.000000]
[WARN] [1663641958.871626326] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.941882, y=11.099703])
[WARN] [1663641958.886837813] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.933865, y=11.119869])
[WARN] [1663641958.903235761] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.925849, y=11.119869])
[WARN] [1663641958.919503554] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.917833, y=11.119869])
[WARN] [1663641958.935489939] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.909817, y=11.119869])
[WARN] [1663641958.950991549] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.901801, y=11.11.......
....skipped.........

#######rqt
asadbek@ubuntu:~$ ros2 run turtlesim turtlesim_node
[INFO] [1663641213.835052574] [turtlesim]: Starting turtlesim with node name /turtlesim
[INFO] [1663641213.843843646] [turtlesim]: Spawning turtle [turtle1] at x=[5.544445], y=[5.544445], theta=[0.000000]
[WARN] [1663641958.871626326] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.941882, y=11.099703])
[WARN] [1663641958.886837813] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.933865, y=11.119869])
[WARN] [1663641958.903235761] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.925849, y=11.119869])
[WARN] [1663641958.919503554] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.917833, y=11.119869])
[WARN] [1663641958.935489939] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.909817, y=11.119869])
[WARN] [1663641958.950991549] [turtlesim]: Oh no! I hit the wall! (Clamping from [x=3.901801, y=11.11



####Remapping
asadbek@ubuntu:~$ source /opt/ros/foxy/setup.sh
ROS_DISTRO was set to 'noetic' before. Please make sure that the environment does not mix paths from different distributions.
asadbek@ubuntu:~$ ros2 run turtlesim turtle_teleop_key --ros-args --remap turtle1/cmd_vel:=turtle2/cmd_vel
Reading from keyboard
---------------------------
Use arrow keys to move the turtle.
Use G|B|V|C|D|E|R|T keys to rotate to absolute orientations. 'F' to cancel a rotation.
'Q' to quit.

