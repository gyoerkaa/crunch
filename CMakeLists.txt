cmake_minimum_required(VERSION 3.1)

project(crunch)

include_directories(${PROJECT_SOURCE_DIR}/crnlib/include)

add_subdirectory(crnlib)
add_subdirectory(crunch_cli)

