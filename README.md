<img src="http://moveit.ros.org/assets/images/moveit2_logo_black.png" alt="MoveIt! Logo" width="200"/>

The MoveIt! Motion Planning Framework **for ROS 2.0**

- [Legal disclaimer](#legal-disclaimer)
- [Milestones](#milestones)
- [Overview of MoveIt! for ROS 2.0](#)
- [Installation Instructions](#)
- [Documentation](#)
- [Get Involved](#)

## Legal disclaimer
**WORK IN PROGRESS**

*The material and information contained in this repository is published in good faith and is for the benefit of the general ROS 2.0 community only. You should not rely upon the material or information in this repository as a basis for making any business, legal or any other decisions. Acutronic Robotics makes no representations, claims, promises, guarantees or warranties of any kind, express or implied about the completeness, accuracy, reliability, suitability or adequacy with respect to the software, information or related graphics contained in this repository for any purpose. Acutronic Robotics is not liable for any loss, damage or injury that may arise in connection with this repository. Any action or reliance you take or place based upon the information in this repository is strictly at your own risk.*

## Milestones
- [ ] Setup instructions
  - [ ] Install instructions
    - [ ] Ubuntu 18.04
    - [ ] OS X 10.14
- [ ] Update/setup infrastructure for development
  - [x] Delete metapackages
  - [ ] Upgrade continuous integration for ROS 2.0 @LanderU
  - [ ] Refactor/cleanup folder hierarchy
- [ ] Convert moveit packages to ROS 2.0
  - [ ] Include moveit_msgs in HRIM (**in progress @ibaiape**)
  - [ ] Convert moveit_core (**in progress @vmayoral**)
    - [ ] Convert all headers and link it to HRIM
    - [ ] Dependencies on other packages
      - [x] tf2_kdl https://github.com/ros2/geometry2/pull/90
      - [x] eigen_stl_containers https://github.com/AcutronicRobotics/eigen_stl_containers/tree/ros2
      - [x] geometric_shapes https://github.com/ros-planning/geometric_shapes/pull/96
      - [x] random_numbers https://github.com/ros-planning/random_numbers/pull/12
  - [ ] Convert moveit_kinematics
  - [ ] Convert moveit_planners_ompl
  - [ ] Convert moveit_ros_planning
  - [ ] Convert moveit_ros_planning_interface
  - [ ] Convert moveit_ros_benchmarks
  - [ ] Convert moveit_ros_control_interface
  - [ ] Convert moveit_ros_manipulation
  - [ ] Convert moveit_ros_move_group
  - [ ] Convert moveit_ros_perception
  - [ ] Convert moveit_ros_robot_interaction
  - [ ] Convert moveit_ros_visualization
  - [ ] Convert moveit_ros_warehouse
  - [ ] Convert moveit_setup_assistant
  - [ ] Convert moveit_simple_controller_manager
  - [ ] Convert moveit_visual_tools
  - [ ] Convert moveit_task_constructor
  - [ ] Convert moveit_resources
  - [ ] Convert moveit_commander
  - [ ] Convert moveit_fake_controller_manager
- [ ] New features in ROS 2.0
  - [ ] Migrate plugin architecture to ROS2 nodelets
- [ ] Documentation
  - [ ] Create tutorials

## Continuous Integration Status
TODO

## Docker Containers

TODO

## ROS Buildfarm

TODO
