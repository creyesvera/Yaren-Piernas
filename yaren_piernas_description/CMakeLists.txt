cmake_minimum_required(VERSION 2.8.3)

project(yaren_piernas_description)

find_package(catkin REQUIRED COMPONENTS
	message_generation
	roscpp
	rospy
	std_msgs
	urdf
	message_generation
	geometry_msgs
	xacro
	)

find_package(gazebo REQUIRED)

catkin_package(CATKIN_DEPENDS
	geometry_msgs
	roscpp
	rospy
	std_msgs
	urdf
	xacro)

include_directories(
	include
	$(catkin_INCLUDE_DIRS)
	$(GAZEBO_INCLUDE_DIRS)
)

find_package(roslaunch)

install(DIRECTORY include/${PROJECT_NAME}/
	DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(DIRECTORY config launch meshes textures urdf
	DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

