# Set the minimum version of CMake required to build this project
cmake_minimum_required(VERSION 3.10)

# Set the project name and language
project(Model CXX)

# Set the source files for this project
set(SOURCE_FILES
    # Add any source files here
    model.cpp
)

# Add a library for this project as a DLL
add_library(Model SHARED ${SOURCE_FILES})

# Add the include directory to the target
target_include_directories(Model PUBLIC ${INCLUDE_DIR})

# Set the library name based on the platform and build configuration
if(WIN32)
    set_target_properties(Model PROPERTIES OUTPUT_NAME "Model_Windows")
    set_target_properties(Model PROPERTIES DEBUG_POSTFIX "${CMAKE_DEBUG_POSTFIX}")
    set_target_properties(Model PROPERTIES RELEASE_POSTFIX "${CMAKE_RELEASE_POSTFIX}")
    set_target_properties(Model PROPERTIES MINSIZEREL_POSTFIX "${CMAKE_MINSIZEREL_POSTFIX}")
    set_target_properties(Model PROPERTIES RELWITHDEBINFO_POSTFIX "${CMAKE_RELWITHDEBINFO_POSTFIX}")
else()
    set_target_properties(Model PROPERTIES OUTPUT_NAME "Model_Linux")
endif()