cmake_minimum_required(VERSION 2.8.3)
project(march_simulation)

find_package(catkin REQUIRED COMPONENTS
    controller_manager
    gazebo_plugins
    gazebo_ros
    gazebo_ros_control
    joint_state_controller
    joint_trajectory_controller
    march_description
    march_gazebo_plugins
    robot_state_publisher
    xacro
)

catkin_package()

catkin_install_python(PROGRAMS scripts/upload_joint_names scripts/to_world_transform
    DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(DIRECTORY config launch obstacles worlds
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
