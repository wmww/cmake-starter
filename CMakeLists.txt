cmake_minimum_required(VERSION 3.0)

project(your-project-name)

# C++ version
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Set the variable source_files to the list of names of your C++ source code
# Note the lack of commas or other deliminators
set(source_files
   main.cpp
   other.cpp
)

# Build a program called 'program' from the source files we specified above
set(EXECUTABLE_NAME "program")
add_executable(${EXECUTABLE_NAME} ${source_files})

# Find pkg-config, which will help you use libraries
find_package(PkgConfig REQUIRED)

# Detect and add SFML
pkg_check_modules(SFML REQUIRED sfml-all)
include_directories(${SFML_INCLUDE_DIR})
target_link_libraries(${EXECUTABLE_NAME} ${SFML_LIBRARIES} ${SFML_DEPENDENCIES})
