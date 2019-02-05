set(MOVEIT_LIB_NAME moveit_kdl_kinematics_plugin)

add_library(${MOVEIT_LIB_NAME} src/kdl_kinematics_plugin.cpp
  src/chainiksolver_pos_nr_jl_mimic.cpp
  src/chainiksolver_vel_pinv_mimic.cpp)

# find_package(random_numbers)

target_link_libraries(${MOVEIT_LIB_NAME} ${catkin_LIBRARIES})
install(TARGETS ${MOVEIT_LIB_NAME} ARCHIVE DESTINATION lib) #LIBRARY DESTINATION lib
install(DIRECTORY include/ DESTINATION include)
