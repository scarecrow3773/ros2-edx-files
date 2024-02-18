# cmake_minimum_required(VERSION 2.8.3)
cmake_minimum_required(VERSION 3.8)
project(hrwros_msgs)

# find_package(catkin REQUIRED COMPONENTS roscpp geometry_msgs std_msgs trajectory_msgs message_generation moveit_msgs actionlib actionlib_msgs)
find_package(ament_cmake REQUIRED)
find_package(roscpp REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(std_msgs REQUIRED)
find_package(trajectory_msgs REQUIRED)
find_package(message_generation REQUIRED)
find_package(moveit_msgs REQUIRED)
find_package(actionlib REQUIRED)
find_package(actionlib_msgs REQUIRED)

################################################
## Declare ROS messages, services and actions ##
################################################

## Generate messages in the 'msg' folder
add_message_files(DIRECTORY msg
  FILES
  ObjectDetection.msg
  TargetToolPoses.msg
  RobotTrajectories.msg
  SensorInformation.msg
  BoxHeightInformation.msg
)

## Generate messages in the 'srv' folder
add_service_files(DIRECTORY srv
  FILES
  ConvertMetresToFeet.srv
)

## Generate messages in the 'action' folder
add_action_files(DIRECTORY action
  FILES
  CounterWithDelay.action
)

## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
  trajectory_msgs
  moveit_msgs
  actionlib_msgs
)


###################################
## catkin specific configuration ##
###################################
# catkin_package(
#  CATKIN_DEPENDS  message_runtime roscpp geometry_msgs std_msgs trajectory_msgs moveit_msgs actionlib_msgs
#)

###########
## Build ##
###########


#############
## Install ##
#############


#############
## Testing ##
#############
