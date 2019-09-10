# Open Source Rover Code
* [Development Repo](https://gitlab.com/IrisDroidology/osr-rover-code) - forked from [Github/NASA-JPL](https://github.com/nasa-jpl/open-source-rover)

# Code examples
```python
# This is from https://gitlab.com/IrisDroidology/osr-rover-code/blob/master/ROS/osr/scripts/rover.py

#!/usr/bin/env python
import time # Importing time function
from osr_msgs.msg import Joystick, Commands, Encoder # import functions?
import rospy
from robot import Robot
import message_filters


global encs
global osr
osr = Robot()
encs = [0]*4

def joy_callback(message):
	global encs
	cmds = Commands()
	out_cmds = osr.generateCommands(message.vel,message.steering,encs)
	cmds.drive_motor  = out_cmds[0]
	cmds.corner_motor = out_cmds[1]
	try:
		pub.publish(cmds)
	except:
		pass

def enc_callback(message):
	global encs
	temp = [0]*4
	for i in range(4):
		temp[i] = message.abs_enc[i] + 1
	encs = temp

if __name__ == '__main__':
	rospy.init_node('rover')
	rospy.loginfo("Starting the rover node")
	global pub
	joy_sub = rospy.Subscriber("/joystick",Joystick, joy_callback)
	enc_sub  = rospy.Subscriber("/encoder", Encoder, enc_callback)
	rate = rospy.Rate(10)
	#time_sync = message_filters.TimeSynchronizer([joy_sub, mc_sub],10)
	#time_sync.registerCallback(callback)

	pub = rospy.Publisher("/robot_commands", Commands, queue_size = 1)
	rate.sleep()
	rospy.spin()
```

# What is the OSR?
The JPL Open Source Rover is an open source, build it yourself, scaled down version of the 6 wheel rover design that JPL uses to explore the surface of Mars. The Open Source Rover is designed almost entirely out of consumer off the shelf (COTS) parts. This project is intended to be a teaching and learning experience for those who want to get involved in mechanical engineering, software, electronics, or robotics.

# Timeline - For ACORD members
Check out [the Python Discussion](https://github.com/orgs/acord-robotics/teams/python-development) & [the OSR project](https://github.com/orgs/acord-robotics/projects/5?add_cards_query=is%3Aopen) to discuss and work on the development of the OSR.

We are currently in the process of learning about Raspberry Pi, Python & Arduinos on Udemy. Check out our development journeys [here](http://github.com/irisdroidology/python-learning) & [here](http://github.com/acord-robotics/arduino-stellarios)
