set(target_name arcsim)

file(GLOB_RECURSE headers "*.hpp")
file(GLOB_RECURSE sources "*.cpp")

add_library(${target_name} ${headers} ${sources})
#string(REPLACE "libalglib" "" ALGLIB_INCLUDE_DIRS ${ALGLIB_INCLUDE_DIRS})
target_include_directories(${target_name}
  PUBLIC
    ${ALGLIB_INCLUDE_DIRS}
    "${CMAKE_SOURCE_DIR}/dependencies/taucs/src"
)
target_link_libraries(${target_name}
  PUBLIC
    ${ALGLIB_LIB}
    jsoncpp_lib
)
