cmake_minimum_required(VERSION 3.19)
project(sample CXX)
list(APPEND CMAKE_MODULE_PATH ${CMAKE_BINARY_DIR})
list(APPEND CMAKE_PREFIX_PATH ${CMAKE_BINARY_DIR})

set(CMAKE_CXX_STANDARD 20)

find_package(lib-level-1 REQUIRED)
find_package(lib-level-2 REQUIRED)

add_executable(main main.cpp)
target_include_directories(main PUBLIC ${lib-level-1_INCLUDE_DIRS})
target_include_directories(main PUBLIC ${lib-level-2_INCLUDE_DIRS})