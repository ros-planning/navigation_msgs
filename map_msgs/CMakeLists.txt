cmake_minimum_required(VERSION 3.0.2)
project(map_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    message_generation
    nav_msgs
    sensor_msgs
    std_msgs
)

add_message_files(
  FILES
    OccupancyGridUpdate.msg
    PointCloud2Update.msg
    ProjectedMapInfo.msg
    ProjectedMap.msg
)
add_service_files(
  FILES
    GetMapROI.srv
    GetPointMapROI.srv
    GetPointMap.srv
    ProjectedMapsInfo.srv
    SaveMap.srv
    SetMapProjections.srv
)

generate_messages(
  DEPENDENCIES
    nav_msgs
    sensor_msgs
    std_msgs
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
    nav_msgs
    sensor_msgs
    std_msgs
)
