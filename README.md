How to install:

1. Make sure you are on Ubuntu 22.04 LTS and have ros humble installed correctly.
2. from the home directory ~/, make a ros workspace:
	$ cd ~
	$ mkdir ros_ws
	$ cd ros_ws

3. Make a src folder in ros_ws:
	$ mkdir src

4. Take the provided zip file and extract it in src folder.
	Note: the directory should look like ~/ros_ws/src/bot_control/ where within this directory, there exists bot_control, resource, test, package.xml, setup.cfg, setup.py
	
5. From ~/ros_ws build the package:
	$ source /opt/ros/humble/setup.bash
	$ colcon build
	$ source install/setup.bash
	
6. Run two instances of turtlesim as such (on two separate terminals, and dont forget to source):
	$ ros2 run turtlesim turtlesim_node __ns:=/turtle1
	$ ros2 run turtlesim turtlesim_node __ns:=/turtle2
	
7. Run the bot control package node as such:
	$ ros2 run bot_control bot_controller
	Note: this will run a flask app that hosts a html ui locally.

8. Access the UI by opening a browser window and in the address bar type in:
	0.0.0.0:5000
	
	The UI is hosted on the default localhost on port 5000.
	By interacting with the controls, you will be able to control both of the turtlesim turtle bots.
