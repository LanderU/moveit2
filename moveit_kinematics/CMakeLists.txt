cmake_minimum_required(VERSION 3.5)
project(moveit_kinematics)

if(NOT WIN32)
  add_definitions(-std=c++11)
endif()

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

add_compile_options(-std=c++14)

# add_compile_options(-Wall -Wextra
#   -Wwrite-strings -Wunreachable-code -Wpointer-arith -Wredundant-decls -Wcast-qual
#   -Wno-unused-parameter -Wno-unused-function)

if(NOT CMAKE_CONFIGURATION_TYPES AND NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

find_package(ament_cmake REQUIRED)
find_package(Boost REQUIRED)
find_package(Eigen3 REQUIRED)
find_package(orocos_kdl REQUIRED)
#find_package(moveit_core REQUIRED)
# find_package(moveit_ros_planning REQUIRED)
find_package(pluginlib REQUIRED)
# find_package(actionlib REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rclcpp_action REQUIRED)
# find_package(rosconsole REQUIRED)
# find_package(srdfdom REQUIRED)
find_package(urdf REQUIRED)
# find_package(tf2 REQUIRED)
# find_package(tf2_kdl REQUIRED)
find_package(random_numbers REQUIRED)
find_package(hrim_moveit_srvs REQUIRED)
find_package(hrim_moveit_msgs REQUIRED)


set(THIS_PACKAGE_INCLUDE_DIRS
    kdl_kinematics_plugin/include
    # lma_kinematics_plugin/include
    # srv_kinematics_plugin/include
    # cached_ik_kinematics_plugin/include
)


# catkin_package(
#   LIBRARIES
#   INCLUDE_DIRS
#     ${THIS_PACKAGE_INCLUDE_DIRS}
#   CATKIN_DEPENDS
#     pluginlib
#     moveit_core
#     moveit_ros_planning
#   DEPENDS
#     EIGEN3
# )

# ament_package(
#   LIBRARIES
#   INCLUDE_DIRS
#     ${THIS_PACKAGE_INCLUDE_DIRS}
#   CATKIN_DEPENDS
#     pluginlib
#     moveit_core
#     moveit_ros_planning
#   DEPENDS
#     EIGEN3
# )

set(dependencies
random_numbers
pluginlib
moveit_core
moveit_ros_planning
hrim_moveit_srvs
hrim_moveit_msgs
)

include_directories(${rclcpp_INCLUDE_DIRS}
                    ${rmw_implementation_INCLUDE_DIRS}
										${THIS_PACKAGE_INCLUDE_DIRS}
                    ${Boost_INCLUDE_DIRS}
                    ${EIGEN3_INCLUDE_DIRS}
                    ${catkin_INCLUDE_DIRS}
                    ${random_numbers_INCLUDE_DIRS}
										${hrim_moveit_srvs_INCLUDE_DIRS}
										${hrim_moveit_msgs_INCLUDE_DIRS}
)

add_subdirectory(kdl_kinematics_plugin)
# add_subdirectory(lma_kinematics_plugin)
# add_subdirectory(srv_kinematics_plugin)
# add_subdirectory(ikfast_kinematics_plugin)
# add_subdirectory(cached_ik_kinematics_plugin)

ament_export_dependencies(dependencies)

install(
  FILES
    kdl_kinematics_plugin_description.xml
    lma_kinematics_plugin_description.xml
    srv_kinematics_plugin_description.xml
    cached_ik_kinematics_plugin_description.xml
  DESTINATION
    # ${CATKIN_PACKAGE_SHARE_DESTINATION}
		share/${PROJECT_NAME})

ament_package()
