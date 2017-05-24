cmake_minimum_required(VERSION 2.8.3)

project(dvrk-html)
set(CMAKE_CXX_FLAGS "-std=c++11")

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin package
##find_package(catkin REQUIRED),find_package(nodelet REQUIRED)

find_package(catkin REQUIRED COMPONENTS
  cisst_ros_bridge
  dvrk_kinematics
  geometry_msgs
  roscpp
  roslib
  rospy
  sensor_msgs
  std_msgs
  tf
  tf_conversions
  dvrk_robot
)
set (REQUIRED_CISST_LIBRARIES
  cisstCommon
  cisstCommonXML
  cisstVector
  cisstVectorQt
  cisstOSAbstraction
  cisstMultiTask
  cisstMultiTaskQt
  cisstParameterTypes
  cisstRobot
  cisstNumerical
  cisstQt)


# find cisst and make sure the required libraries have been compiled
find_package (cisst REQUIRED ${REQUIRED_CISST_LIBRARIES})
include (${CISST_USE_FILE})

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if you package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES dvrk_teleop
#  CATKIN_DEPENDS cisst_ros_bridge geometry_msgs roscpp rospy sensor_msgs std_msgs tf tf_conversions
#  DEPENDS system_lib
)

###########
## Build ##
###########

include_directories(include)
include_directories(${catkin_INCLUDE_DIRS})



