project(opencv_camera)
find_package(catkin REQUIRED COMPONENTS
  roscpp
  OpenCV
  cv_bridge
  image_transport
)

find_package(OpenCV REQUIRED)
find_package(Boost REQUIRED)

catkin_package()

include_directories(
  include 
  
  ${catkin_INCLUDE_DIRS}
  ${OpenCV_INCLUDE_DIRS}
)

add_executable(image_pub src/image_pub.cpp)
target_link_libraries(image_pub ${catkin_LIBRARIES} ${OpenCV_LIBS} ${Boost_LIBRARIES})

