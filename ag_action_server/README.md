### Action Server 

Questo package è un esempio di comunicazione tra ROS e Niryo tramite un action server.
Basato sul codice di ![Steve Maassen](https://github.com/smaassen/niryo_one_tester).

### Dependencies
This package depends on the actionlib and the niryo_one_msgs packages

### Included nodes
- simple_command_node
An example node that walks you through simple commands like move to pose (rpy, or qutarniion) and close/open gripper

### Conect to Niryo one and change ROS_MASTER
First you have to connect to the niryo one wifi according to their documentation. Onec wifi connection is established you shoudl open a new terminal and change the ROS_MASTER_URI
```
export ROS_MASTER_URI=http://10.10.10.10:11311
```
You should now be able to see all the published topics by the robot by typing
```
rostopic list
```
### Run the node 
In the same terminal window, run the node (for example simple_command_node) by 
```
rosrun niryo_one_tester simple_command_node
```

___
![alt text](https://gavazzionline.files.wordpress.com/2014/01/img_6916.jpg?w=300)
