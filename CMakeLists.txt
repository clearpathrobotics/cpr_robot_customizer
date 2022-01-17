cmake_minimum_required(VERSION 3.0.2)
project(generic_robot)

find_package(catkin)

catkin_package()

install(DIRECTORY urdf meshes launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
