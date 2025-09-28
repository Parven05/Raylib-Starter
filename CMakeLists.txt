cmake_minimum_required(VERSION 3.16)
project(main CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Find raylib
find_package(raylib REQUIRED)

# Add include directory for headers
include_directories(${CMAKE_SOURCE_DIR}/include)

# Collect all cpp files in src/
file(GLOB SRC_FILES ${CMAKE_SOURCE_DIR}/src/*.cpp)

# Create executable from sources
add_executable(${PROJECT_NAME} ${SRC_FILES})

# Link raylib
target_link_libraries(${PROJECT_NAME} PRIVATE raylib)

# Recommended compile warnings
target_compile_options(${PROJECT_NAME} PRIVATE -Wall -Wextra -Wpedantic)
