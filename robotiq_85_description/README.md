# robotiq_85_description

## Test gripper in Gazebo
```bash
ros2 launch robotiq_85_description gazebo_gripper_mimic_joint.launch.py 
ros2 topic pub /gripper_controller/commands std_msgs/msg/Float64MultiArray "data:
- 0.4"
```
