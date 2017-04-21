cmake_minimum_required(VERSION 2.8.3)
project(ardrone_control)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  sensor_msgs
  cv_bridge
  image_transport
  message_generation
)

find_package(OpenCV REQUIRED)

catkin_package(
  CATKIN_DEPENDS 
)

include_directories(
  ${catkin_INCLUDE_DIRS}
  include
)

add_executable(serial_control 
  src/serial_control.cpp
)
target_link_libraries(serial_control
  ${catkin_LIBRARIES}
)

