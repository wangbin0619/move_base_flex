cmake_minimum_required(VERSION 2.8.3)
project(move_base_flex)
find_package(catkin REQUIRED)
catkin_metapackage()

if(CMAKE_COMPILER_IS_GNUCXX)
    set(CMAKE_CXX_FLAGS " ${CMAKE_CXX_FLAGS} -std=c++11")
    message(STATUS "optional:-std=c++11")
endif(CMAKE_COMPILER_IS_GNUCXX)
