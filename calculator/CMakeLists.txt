cmake_minimum_required(VERSION 3.5)
project(hello)

include(CMakeDependentOption)

cmake_dependent_option(BUILD_CALC_F0 "Build the F0 features" ON "BUILD_CALC" OFF)
cmake_dependent_option(BUILD_CALC_F1 "Build the F1 features" OFF "BUILD_CALC" OFF)

set(CALC_SRCS "")

if (BUILD_CALC_F0)
    set(CALC_SRCS ${CALC_SRCS} ${CMAKE_CURRENT_SOURCE_DIR}/f0.cpp)
endif (BUILD_CALC_F0)

if (BUILD_CALC_F1)
    set(CALC_SRCS ${CALC_SRCS} ${CMAKE_CURRENT_SOURCE_DIR}/f1.cpp)
endif (BUILD_CALC_F1)

set(SRCS ${SRCS} ${CALC_SRCS} PARENT_SCOPE)
