cmake_minimum_required(VERSION 3.5)

project(robot_application)

find_package(ament_cmake REQUIRED)

# Install project launch files
install(
  DIRECTORY
    scripts/
  DESTINATION share/${PROJECT_NAME}/scripts
)

ament_package()
