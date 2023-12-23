cmake_minimum_required(VERSION 3.5)
project(hello)
set(VERSION "0.1")
set(VERSION_MAJOR 0)
set(VERSION_MINOR 1)

set(SRCS ${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp)

option(BUILD_CALC "Build the simple calculator library" OFF)

if (BUILD_CALC)
    add_subdirectory(calculator)
endif (BUILD_CALC)

configure_file(${CMAKE_CURRENT_SOURCE_DIR}/g_config.h.in g_config.h @ONLY)

include_directories(${CMAKE_CURRENT_BINARY_DIR})

add_library(myapp STATIC ${SRCS})
link_libraries(myapp)
add_executable(main main.cpp)
