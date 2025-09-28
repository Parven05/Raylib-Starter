cmake_minimum_required(VERSION 3.16)

# C based Project
#project(main C)
project(main CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# C standard
#set(CMAKE_C_STANDARD 99)
#set(CMAKE_C_STANDARD_REQUIRED ON)

# Find raylib
find_package(raylib REQUIRED)

# Add include directory for headers
include_directories(${CMAKE_SOURCE_DIR}/include)

# Collect all cpp files in src/
file(GLOB SRC_FILES ${CMAKE_SOURCE_DIR}/src/*.cpp)

# Collect all .c files in src/
#file(GLOB SRC_FILES ${CMAKE_SOURCE_DIR}/src/*.c)

# Create executable from sources
add_executable(${PROJECT_NAME} ${SRC_FILES})

# Link raylib
target_link_libraries(${PROJECT_NAME} PRIVATE raylib)

# Recommended compile warnings
target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -Wpedantic)
