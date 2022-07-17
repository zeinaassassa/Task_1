Install ROS on Ubuntu 20.04
========

Configure  Ubuntu repositories:
========
Configure  Ubuntu repositories to allow "restricted," "universe," and "multiverse."


Setup sources.list  to accept software from packages.ros.org:
=========
> sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

Set up the keys:
=========
> sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

Installation:
========
it must make sure the Debian package index is up-to-date...
=
> sudo apt update
> sudo apt install ros-noetic-desktop-full

Environment setup:
=======
> source /opt/ros/noetic/setup.bash
> echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc

Dependencies for building packages:
=======
Up to now you have installed what you need to run the core ROS packages. To create and manage your own ROS workspaces, there are various tools and requirements that are distributed separately. For example, rosinstall is a frequently used command-line tool that enables you to easily download many source trees for ROS packages with one command. 

> sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
> sudo apt install python3-rosdep

With the following, you can initialize rosdep:
========

> sudo rosdep init
> rosdep update

Now, to test your installation, please proceed to the ROS Tutorials. 


To check if the ROS is installed and everything is done, we can write on terminal:
========
> roscore


it will show the result and make sure that every thing is fine and show this message:
========

... logging to /home/zeina/.ros/log/b2be9c78-0544-11ed-9374-a580fb158bae/roslaunch-zeina-VirtualBox-31972.log
Checking log directory for disk usage. This may take a while.
Press Ctrl-C to interrupt
Done checking log file disk usage. Usage is <1GB.

started roslaunch server http://zeina-VirtualBox:39335/
ros_comm version 1.15.14


SUMMARY
========

PARAMETERS
 * /rosdistro: noetic
 * /rosversion: 1.15.14

NODES

auto-starting new master
process[master]: started with pid [31982]
ROS_MASTER_URI=http://zeina-VirtualBox:11311/

setting /run_id to b2be9c78-0544-11ed-9374-a580fb158bae
process[rosout-1]: started with pid [31992]
started core service [/rosout]
