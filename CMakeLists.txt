cmake_minimum_required(VERSION 2.8.3)
project(ihmc_atlas)

find_package(catkin REQUIRED COMPONENTS
#  std_msgs
#  message_generation
#  geometry_msgs
  ihmc_msgs
  ihmc_ros_common
)

#add_message_files(
#   FILES
#   AtlasDesiredPumpPSIPacketMessage.msg
#   AtlasElectricMotorEnablePacketMessage.msg
#   AtlasWristSensorCalibrationRequestPacketMessage.msg
#   RawImuData.msg
#   BatchRawImuData.msg
#)

#generate_messages(
#   DEPENDENCIES
#   std_msgs
#   geometry_msgs
#   ihmc_msgs
# )

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES ihmc_msgs
#  CATKIN_DEPENDS std_msgs
#  DEPENDS system_lib
)

install(DIRECTORY configurations
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
  PATTERN "*.ini"
  PATTERN "*.yaml"
)

install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
  FILES_MATCHING PATTERN "*.launch"
)

install(DIRECTORY urdf
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
  FILES_MATCHING PATTERN "*.urdf"
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
