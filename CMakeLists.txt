cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
project(ModelPhotoShoot)

# Find Gazebo
find_package(gazebo REQUIRED)
include_directories(${GAZEBO_INCLUDE_DIRS})
link_directories(${GAZEBO_LIBRARY_DIRS})
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${GAZEBO_CXX_FLAGS}")

# Build our plugin
add_library(modelphotoshoot SHARED ModelPhotoShoot.cc)
target_link_libraries(modelphotoshoot ${GAZEBO_LIBRARIES})
