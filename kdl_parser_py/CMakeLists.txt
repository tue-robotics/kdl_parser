cmake_minimum_required(VERSION 3.0.2)

project(kdl_parser_py)

find_package(catkin REQUIRED)

catkin_package(
  CATKIN_DEPENDS urdfdom_py
)

catkin_python_setup()

catkin_install_python(PROGRAMS ${PROJECT_NAME}/urdf.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

if(CATKIN_ENABLE_TESTING)
  find_package(catkin REQUIRED COMPONENTS rostest)
  add_rostest(test/test_kdl_parser.launch)
endif()
