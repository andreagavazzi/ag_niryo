# API cheatsheet 

##### Template base

```python
#!/usr/bin/env python

from niryo_one_python_api.niryo_one_api import *
import rospy
import time
rospy.init_node('niryo_one_example_python_api')

n = NiryoOne()

try:
    # Your code here
except NiryoOneException as e:
    print e
    # Handle errors here
```

##### Calibrazione automatica da braccio in posizione 0
```python
n.calibrate_auto()
```

##### Learning mode
```python
n.activate_learning_mode(False)
n.activate_learning_mode(False)    # (True) per attivarlo
```

##### Per il movimento ho 3 possibilità
1. move_joints
    array di 6 joints: n.move_joints([1, 0, 0, 0, 0, 0])
2. move_pose
position x (m)
position y (m)
position z (m)
rotation x (rad)
rotation y (rad)
rotation z (rad)
3. shift_pose
    axis (0: pos.x, 1: pos.y, 2: pos.z, 3: rot.x, 4: rot.y, 5: rot.z)
    value (m)
```python
n.move_joints([0,0,0,0,0,0])

```

##### Apertura e chiusura pinza
```python
n.open_gripper()    # Parametri: tool id, open speed (between 0 and 1000, meglio tra 100 and 500)
n.close_gripper()   # Parametri: tool id, close speed (between 0 and 1000, meglio tra 100 and 500)
```

##### Blocca e aspetta
```python
n.wait(2)  # In secondi, equivale a time.sleep(2)
```

___
![alt text](https://gavazzionline.files.wordpress.com/2014/01/img_6916.jpg?w=300)
