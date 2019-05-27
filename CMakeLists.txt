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

# If you need to use a library, this is a common way to do it
# find_package(PkgConfig REQUIRED)
# pkg_check_modules(SOME_PACKAGE REQUIRED libsomelibrary)
# include_directories(${SOME_PACKAGE_INCLUDE_DIRS})
# link_directories(${SOME_PACKAGE_LIBRARY_DIRS})
# add_definitions(${SOME_PACKAGE_CFLAGS_OTHER})

# Build a program called 'program' from the source files we specified above
add_executable(program ${source_files})

# Also needed to add a library
# target_link_libraries(program ${SOME_PACKAGE_LIBRARIES})
