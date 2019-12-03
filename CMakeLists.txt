cmake_minimum_required(VERSION 3.5.1)

project(ARCSim)

find_package(ALGLIB REQUIRED)
message(STATUS "ALGLIB_INCLUDE_DIRS: ${ALGLIB_INCLUDE_DIRS}")
message(STATUS "ALGLIB_LIB: ${ALGLIB_LIB}")

find_package(jsoncpp REQUIRED)

add_subdirectory(src)
