cmake_minimum_required(VERSION 3.0.2)
project(move_base_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    actionlib_msgs
    geometry_msgs
    message_generation
)

# msgs
add_message_files(
  DIRECTORY
    msg
  FILES
    RecoveryStatus.msg
)

# actions
add_action_files(
  DIRECTORY
    action
  FILES
    MoveBase.action
)

generate_messages(
  DEPENDENCIES
    actionlib_msgs
    geometry_msgs
)

catkin_package(
    CATKIN_DEPENDS actionlib_msgs geometry_msgs message_runtime
)
