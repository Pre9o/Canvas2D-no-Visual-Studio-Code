cmake_minimum_required(VERSION 3.10)
project(canvas2d)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -fexceptions")

#
# SUBSTITUA COM O CAMINHO DO G++ DO CODE BLOCKS!!!
#
set(CMAKE_CXX_COMPILER "D:/Apps/CodeBlocks/MinGW/bin/g++.exe")

# Include directories
include_directories(include)

# Add all source files recursively from subdirectories under 'src'
file(GLOB_RECURSE SOURCES src/*.cpp src/**/*.cpp)

# Executable
add_executable(canvas2d ${SOURCES})

# libs
target_link_libraries(canvas2d
    ${CMAKE_SOURCE_DIR}/lib/libfreeglut32.a
    ${CMAKE_SOURCE_DIR}/lib/libopengl32.a
    ${CMAKE_SOURCE_DIR}/lib/libglu32.a
)
