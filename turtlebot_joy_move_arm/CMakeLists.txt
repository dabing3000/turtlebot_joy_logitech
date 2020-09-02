cmake_minimum_required(VERSION 3.0.2)
project(turtlebot_joy_move_arm)

## Find catkin macros and libraries
find_package(catkin REQUIRED COMPONENTS roscpp geometry_msgs joy std_msgs)

include_directories(${catkin_INCLUDE_DIRS})

catkin_package(
  INCLUDE_DIRS
  CATKIN_DEPENDS roscpp geometry_msgs joy
  DEPENDS
)

###########
## Build ##
###########

add_executable(turtlebot_joy_move_arm src/turtlebot_joy_move_arm.cpp)
target_link_libraries(turtlebot_joy_move_arm ${catkin_LIBRARIES})

#############
## Install ##
#############
## Mark executables and/or libraries for installation#
install(TARGETS turtlebot_joy_move_arm
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

## Mark all other useful stuff for installation
install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
