# robotics_class

This package contains the simulation and low-level core of the jetauto robot that will be used in the robotics discipline.

## How to install

1 - Make a workspace.

2 - Clone this repository in src folder.

3 - Go to the workspace root and install dependencies.

``` sh
  rosdep install --from-paths src
```

4 - Build your workspace.

``` sh
  colcon build
```

## How to Use

1 - Launch the description of the jet auto transformations.

``` sh
  ros2 launch robotics_class robot_description.launch.py
```

2 - Launch the simulation world.

``` sh
  ros2 launch robotics_class simulation_world.launch.py
```

2 - Launch the ekf.

``` sh
  ros2 launch robotics_class ekf.launch.py
```

## Communication interfaces

### Topics

``` yaml
topic: /jetauto/cmd_vel
type: geometry_msgs:msg:Twist
I/O: input

topic: /jetauto/odometry/filtered
type: nav_msgs::msg::Odometry
I/O: output

topic: /jetauto/odometry/unfiltered
type: nav_msgs::msg::Odometry
I/O: output

topic: /jetauto/imu/data
type: sensor_msgs::msg::Imu
I/O: output

topic: /jetauto/lidar/scan
type: sensor_msgs::msg::LaserScan
I/O: output
```

**/jetauto/cmd_vel** is a topic that makes it possible to send a speed setpoint to jetauto.

**/jetauto/odometry/filtered** It is a topic where you can read the jetauto odometry information after the ekf filter.

**/jetauto/odometry/unfiltered** It is a topic where you can read the jetauto odometry information before the ekf filter.

**/jetauto/imu/data** is a topic where you can read the measurement information of the IMU sensor.

**/jetauto/lidar/scan** is a topic where the measurement information of the lidar sensor can be read.
