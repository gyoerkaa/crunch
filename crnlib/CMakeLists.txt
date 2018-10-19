cmake_minimum_required(VERSION 3.1)

project(crnlib)


add_library(${PROJECT_NAME} STATIC "")
include(src/CMakeLists.txt)

set_target_properties(${PROJECT_NAME} PROPERTIES PREFIX "")

target_include_directories(${PROJECT_NAME} PUBLIC include)

if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "MSVC")

elseif ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
	target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -Wno-unused-value -Wno-unused -fexceptions -fno-strict-aliasing -fno-math-errno -O3 -ffast-math)
endif()

# set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG}   -Wall -Wextra -fexceptions -fomit-frame-pointer -fno-math-errno -fno-strict-aliasing -std=c++11")
# set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE}   -Wall -Wextra -fexceptions -fomit-frame-pointer -fno-math-errno -fno-strict-aliasing -O3 -ffast-math -std=c++11")

