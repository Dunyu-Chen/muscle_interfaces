cmake_minimum_required(VERSION 3.8)
project(muscle_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(rosidl_default_generators REQUIRED)
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/MuscleState.msg"
  "msg/MotorState.msg"
  "msg/BinaryValveInput.msg"
  "msg/PwmValveInput.msg"
  "msg/UnifiedInput.msg"
  DEPENDENCIES builtin_interfaces
)

ament_package()
