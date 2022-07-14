cmake_minimum_required(VERSION 3.20)  # CMake version check
project(SUSY_PPS_experiment)               # Create project "simple_example"
set(CMAKE_CXX_STANDARD 14)            # Enable c++14 standard

# Tell cmake where to look for cmake modules..
set(CMAKE_MODULE_PATH "${CMAKE_MODULE_PATH};${CMAKE_SOURCE_DIR}/cmake")

# Include ROOT
find_package(ROOT REQUIRED)
if (ROOT_FOUND)
    include_directories(${ROOT_INCLUDE_DIR})
    link_directories(${ROOT_LIBRARY_DIR})
    list(APPEND LIBRARIES ${ROOT_LIBRARIES})
endif(ROOT_FOUND)

# Add executable target with source files listed in SOURCE_FILES variable
add_executable(main main.cpp)
target_link_libraries(main ${LIBRARIES})
