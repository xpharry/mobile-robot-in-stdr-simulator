# mobile robot in STDR simulator

under Ubuntu 16.04 / ROS Kinetic

## Instruction

#### 1. Get STDR Simulator from apt packages

```
sudo apt-get install ros-kinetic-stdr-simulator
```

#### 2. Test Open-loop Control

Start the simulator with

```
roslaunch stdr_launchers server_with_map_and_gui_plus_robot.launch
```

Run an open‐loop command sequence with:	

```
rosrun my_stdr_control my_stdr_open_loop_commander
```

**Idea:** In a loop with specified time durations, use "publisher" as the commander to drive the robot "robot0" to move forward or spin by z axis until it arrives at the left top corner.

#### 3. Test Obtacle Avoidance using Lidar Scanning

```
roslaunch stdr_launchers server_with_map_and_gui_plus_robot.launch
```

Start Lidar Scanning:

```
rosrun my_lidar_alarm 
```

Run a commander using lidar scan information:

```
rosrun my_stdr_control my_reactive_commander
```
#### 4. Test Sending Commands with Service and Client scheme

```
roslaunch stdr_launchers server_with_map_and_gui_plus_robot.launch

rosrun my_ros_service my_path_service2

rosrun my_ros_service my_path_client
```

**Idea:** Design a path constructed by a sequence of state information and stored by a pose vector.