cmake_minimum_required(VERSION 3.8)
project(ros2_parameters)

# Default to C++17
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 17)
endif()

# Find dependencies
find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)

# Create executable
add_executable(param_node src/param_node.cpp)

# Link dependencies
ament_target_dependencies(param_node rclcpp)

# Install executable
install(TARGETS
  param_node
  DESTINATION lib/${PROJECT_NAME}
)

# Required for ament
ament_package()

