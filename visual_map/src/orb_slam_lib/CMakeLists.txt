cmake_minimum_required(VERSION 2.8.3)
project(orb_slam_lib)

find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)

file(GLOB ALL_HEADER_FILES "include/*")

file(COPY ${ALL_HEADER_FILES} DESTINATION ${CATKIN_DEVEL_PREFIX}/include)

cs_add_library(${PROJECT_NAME}
  src/two_frame_pose.cc
  src/DescMatcher.cc
  src/DescExtractor.cc
  src/sim3_match.cc
)

############
## EXPORT ##
############
cs_install()
cs_export()
