# robotiq_85_description

Due to an issue with how Gazebo respects mimic joints, we use a [plugin](https://github.com/roboticsgroup/roboticsgroup_gazebo_plugins) to achieve the desired behavior. In order to have the model work properly, you will need to add the plugin's package to your workspace or install it using [kavrakilab-env](https://github.com/KavrakiLab/kavrakilab_env):
```
kavrakilab-get install ros-roboticsgroup_gazebo_plugins
```

Additionally, if you use kavrakilab-env to install this package, the plugin should automatically be installed as well:
```
kavrakilab-get install ros-robotiq_85_description
```
## Test gripper controller
```bash
ros2 topic pub /gripper_controller/commands std_msgs/msg/Float64MultiArray "data:
- 0.4"
```
