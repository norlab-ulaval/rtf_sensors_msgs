cmake_minimum_required(VERSION 3.8)
project(rtf_sensors_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

set(CMAKE_BUILD_TYPE "Release")

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/CustomPressure.msg"
  "msg/CustomTemperature.msg"
  DEPENDENCIES std_msgs
)

include_directories(
        ${rtf_sensors_msgs_INCLUDE_DIRS}
)

ament_package()