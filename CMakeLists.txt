cmake_minimum_required(VERSION 2.8.3)
project(ros_profinet_experimental)


find_package(catkin REQUIRED COMPONENTS 
  roscpp
  message_generation
  )

include_directories(${catkin_INCLUDE_DIRS})
include_directories(${PROJECT_SOURCE_DIR}/include/)


SET(SOURCES ${PROJECT_SOURCE_DIR}/src/ros_profinet_experimental.cpp
            ${PROJECT_SOURCE_DIR}/src/ros_profinet_experimental_lib.cpp
          )
SET(HEADERS ${PROJECT_SOURCE_DIR}/include/ros_profinet_experimental/ros_profinet_experimental_lib.h
	  )
	  
catkin_package(
  DEPENDS
  INCLUDE_DIRS
  CATKIN_DEPENDS roscpp 
  LIBRARIES
  roscpp

  
)

add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})
add_dependencies(${PROJECT_NAME} ${catkin_EXPORTED_TARGETS})
target_link_libraries(${PROJECT_NAME} ${ROS_LIBRARIES} ${catkin_LIBRARIES})
