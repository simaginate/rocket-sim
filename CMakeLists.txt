# Set the minimum version of CMake required to build this project
cmake_minimum_required(VERSION 3.10)

# Set the project name
project(RocketSim)

set(SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/src)
set(INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Set the output directories for the built executable and DLL
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/build_msvs_2022/x64/${CMAKE_BUILD_TYPE})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/build_msvs_2022/x64/${CMAKE_BUILD_TYPE})

set(CMAKE_DEBUG_POSTFIX "_d")
set(CMAKE_RELEASE_POSTFIX "_r")
set(CMAKE_MINSIZEREL_POSTFIX "_min")
set(CMAKE_RELWITHDEBINFO_POSTFIX "_rd")

# Add subdirectories for each project
add_subdirectory(${SOURCE_DIR}/Model)
add_subdirectory(${SOURCE_DIR}/Simulator)