cmake_minimum_required(VERSION 2.8.3)
project(mbf_msgs)

find_package(catkin REQUIRED
  COMPONENTS
  actionlib_msgs
  genmsg
  geometry_msgs
  message_generation
  message_runtime
  nav_msgs
  std_msgs
)

add_service_files(
  DIRECTORY
  srv
  FILES
  CheckPoint.srv
  CheckPose.srv
  CheckPath.srv
)

add_action_files(
  DIRECTORY
  action
  FILES
  GetPath.action
  ExePath.action
  Recovery.action
  MoveBase.action
)

generate_messages(
  DEPENDENCIES
  actionlib_msgs
  geometry_msgs
  nav_msgs
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS
  actionlib_msgs
  geometry_msgs
  message_runtime
  nav_msgs
  std_msgs
)

if(CMAKE_COMPILER_IS_GNUCXX)
    set(CMAKE_CXX_FLAGS " ${CMAKE_CXX_FLAGS} -std=c++11")
    message(STATUS "optional:-std=c++11")
endif(CMAKE_COMPILER_IS_GNUCXX)
