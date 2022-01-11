cmake_minimum_required(VERSION 3.0.2)
project(gnss_comm_msgs)

# to make sure ccache produces colorized output.
add_compile_options(-fdiagnostics-color=always)

find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
)

add_message_files(
  FILES
  GnssTimeMsg.msg
  GnssEphemMsg.msg
  GnssGloEphemMsg.msg
  GnssMeasMsg.msg
  GnssObsMsg.msg
  GnssBestXYZMsg.msg
  GnssPVTSolnMsg.msg
  GnssSvsMsg.msg
  GnssTimePulseInfoMsg.msg
  StampedFloat64Array.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
)

catkin_package(
  CATKIN_DEPENDS message_runtime
                 std_msgs
)
