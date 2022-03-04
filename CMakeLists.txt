cmake_minimum_required(VERSION 3.0.2)
project(cpr_robot_customizer)

find_package(catkin REQUIRED)

catkin_package()

install(DIRECTORY urdf meshes launch scripts rviz example
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)
  roslaunch_add_file_check(launch)
endif()
