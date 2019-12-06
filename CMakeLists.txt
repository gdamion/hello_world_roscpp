cmake_minimum_required(VERSION 2.8.3)
project(hello_world)

add_compile_options(-std=c++11)

find_package(catkin REQUIRED COMPONENTS
  roscpp
)

catkin_package(
#  INCLUDE_DIRS
#  LIBRARIES hello_world
 CATKIN_DEPENDS roscpp
#  DEPENDS system_lib
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(${PROJECT_NAME}_node src/hello_world.cc)
add_dependencies(${PROJECT_NAME}_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
target_link_libraries(${PROJECT_NAME}_node ${catkin_LIBRARIES})


# cmake_minimum_required(VERSION 2.8.3)
# project(turtlebot3_bringup)

# add_compile_options(-std=c++11)

# find_package(catkin REQUIRED COMPONENTS
#   roscpp
#   std_msgs
#   sensor_msgs
#   diagnostic_msgs
#   turtlebot3_msgs
# )

# catkin_package(
#   CATKIN_DEPENDS roscpp std_msgs sensor_msgs diagnostic_msgs turtlebot3_msgs
# )

# include_directories(
#   ${catkin_INCLUDE_DIRS}
# )

# add_executable(turtlebot3_diagnostics src/turtlebot3_diagnostics.cpp)
# add_dependencies(turtlebot3_diagnostics ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})
# target_link_libraries(turtlebot3_diagnostics ${catkin_LIBRARIES})
