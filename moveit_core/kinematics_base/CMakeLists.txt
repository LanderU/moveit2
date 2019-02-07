cmake_minimum_required(VERSION 3.5)
set(MOVEIT_LIB_NAME moveit_kinematics_base)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

add_library(${MOVEIT_LIB_NAME} src/kinematics_base.cpp)
find_package(ament_cmake REQUIRED)
find_package(rmw_implementation REQUIRED)
find_package(urdfdom REQUIRED)
find_package(Boost REQUIRED)

# set_target_properties(${MOVEIT_LIB_NAME} PROPERTIES VERSION ${${PROJECT_NAME}_VERSION})

# Avoid warnings about deprecated members of KinematicsBase when building KinematicsBase itself.
# TODO: remove when deperecated variables (tip_frame_, search_discretization_) are finally removed.
# target_compile_options(${MOVEIT_LIB_NAME} PRIVATE -Wno-deprecated-declarations)

# This line is needed to ensure that messages are done being built before this is built
# add_dependencies(${MOVEIT_LIB_NAME} ${catkin_EXPORTED_TARGETS})


# include_directories(${MOVEIT_LIB_NAME}
#                     ${rclcpp_INCLUDE_DIRS}
#                     ${rmw_implementation_INCLUDE_DIRS}
# 										${urdfdom_INCLUDE_DIRS}
# 										${urdfdom_headers_INCLUDE_DIRS}
# 										${Boost_INCLUDE_DIRS})

target_link_libraries(${MOVEIT_LIB_NAME} ${rclcpp_LIBRARIES} ${rmw_implementation_LIBRARIES} ${urdfdom_LIBRARIES} ${urdfdom_headers_LIBRARIES} ${Boost_LIBRARIES})

ament_target_dependencies(${MOVEIT_LIB_NAME}
)

install(TARGETS ${MOVEIT_LIB_NAME}
        LIBRARY DESTINATION lib
        ARCHIVE DESTINATION lib)

install(DIRECTORY include/
				DESTINATION include)

ament_package()
