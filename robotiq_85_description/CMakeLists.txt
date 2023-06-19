cmake_minimum_required(VERSION 3.10.2)
project(robotiq_85_description)

find_package(ament_cmake REQUIRED)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++17
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 17)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(rclcpp REQUIRED)
find_package(angles REQUIRED)
find_package(control_toolbox REQUIRED)
find_package(gazebo_dev REQUIRED)
find_package(gazebo_msgs REQUIRED)
find_package(gazebo_ros REQUIRED)
find_package(hardware_interface REQUIRED)
find_package(gazebo_ros2_control REQUIRED)
find_package(yaml_cpp_vendor REQUIRED)
find_package(pluginlib REQUIRED)

include_directories(
  ${GAZEBO_INCLUDE_DIRS}
)
link_directories(${GAZEBO_LIBRARY_DIRS})

install(
  DIRECTORY
    config
    launch
    meshes
    urdf
  DESTINATION
    share/${PROJECT_NAME}
)

ament_package()
