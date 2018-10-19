cmake_minimum_required(VERSION 3.1)

project(crunch_cli)


add_executable(${PROJECT_NAME} "")
include(src/CMakeLists.txt)

set_target_properties(${PROJECT_NAME} PROPERTIES PREFIX "")

target_include_directories(${PROJECT_NAME} PUBLIC include)


if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "MSVC")
	target_link_libraries(${PROJECT_NAME} PUBLIC crnlib)
elseif ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
	target_compile_options(${PROJECT_NAME} PRIVATE -Wextra -Wall -g -Wno-unused-value -Wno-unused -fno-strict-aliasing -ffast-math -fno-math-errno)
	target_link_libraries(${PROJECT_NAME} PUBLIC pthread crnlib)
endif()

