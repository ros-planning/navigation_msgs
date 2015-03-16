cmake_minimum_required(VERSION 2.8.3)
project(map_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    std_msgs
    sensor_msgs
    nav_msgs
    message_generation
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
    std_msgs
    sensor_msgs
    nav_msgs
)

catkin_package(
  CATKIN_DEPENDS
    std_msgs
    sensor_msgs
    nav_msgs
)
