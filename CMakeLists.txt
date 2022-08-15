cmake_minimum_required(VERSION 3.0.0)

project(learn_cmake)

include_directories(${CMAKE_SOURCE_DIR}/INCLUDE)

add_executable(get_time main.cpp SOURCE/get_time.cpp)

