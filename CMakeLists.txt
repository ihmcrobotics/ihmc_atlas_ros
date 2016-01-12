cmake_minimum_required(VERSION 2.8.3)
project(ihmc_msgs)

find_package(catkin REQUIRED COMPONENTS
  std_msgs
  message_generation
  geometry_msgs
  ihmc_msgs
)

add_message_files(
   FILES
   AtlasDesiredPumpPSIPacketMessage.msg
   AtlasElectricMotorEnablePacketMessage.msg
   AtlasWristSensorCalibrationRequestPacketMessage.msg
   RawImuData.msg
   BatchRawImuData.msg
 )

 generate_messages(
   DEPENDENCIES
   std_msgs
   geometry_msgs
   ihmc_msgs
 )

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES ihmc_msgs
#  CATKIN_DEPENDS std_msgs
#  DEPENDS system_lib
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
