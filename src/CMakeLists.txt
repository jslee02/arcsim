set(target_name arcsim)

file(GLOB_RECURSE headers "*.hpp")
file(GLOB_RECURSE sources "*.cpp")

add_library(${target_name} ${headers} ${sources})
#string(REPLACE "libalglib" "" ALGLIB_INCLUDE_DIRS ${ALGLIB_INCLUDE_DIRS})
target_include_directories(${target_name}
  PUBLIC
    ${ALGLIB_INCLUDE_DIRS}
    "${CMAKE_SOURCE_DIR}/dependencies/include"
)
target_link_directories(${target_name}
  PUBLIC
    "${CMAKE_SOURCE_DIR}/dependencies/lib"
)
target_link_libraries(${target_name}
  PUBLIC
    ${ALGLIB_LIB}
    jsoncpp_lib
    taucs
)
