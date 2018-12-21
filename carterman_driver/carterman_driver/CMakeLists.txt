cmake_minimum_required(VERSION 2.8.3)
project(carterman_driver)

find_package(catkin REQUIRED COMPONENTS roscpp carterman_driver_msgs std_msgs nav_msgs sensor_msgs topic_tools tf serial)
find_package(Boost REQUIRED COMPONENTS system thread)

catkin_package(
CATKIN_DEPENDS roscpp carterman_driver_msgs std_msgs nav_msgs sensor_msgs topic_tools tf serial)

include_directories(
include
${Boost_INCLUDE_DIRS}
${catkin_INCLUDE_DIRS}
)

add_executable(carterman_driver src/driver.cpp)
target_link_libraries(carterman_driver ${catkin_LIBRARIES})
add_dependencies(carterman_driver carterman_driver_msgs_gencpp)

