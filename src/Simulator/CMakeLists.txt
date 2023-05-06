# Set the minimum version of CMake required to build this project
cmake_minimum_required(VERSION 3.10)

# Set the project name and language
project(Simulator CXX)

# Set the source files for this project
set(SOURCE_FILES
    # Add any source files here
    main.cpp
)

# Add an executable for this project
add_executable(Simulator ${SOURCE_FILES})

# Add the include directory to the target
target_include_directories(Simulator PUBLIC ${INCLUDE_DIR})

# Link the Simulator executable with the Model library
target_link_libraries(Simulator PRIVATE Model)