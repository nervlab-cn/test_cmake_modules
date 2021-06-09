cmake_minimum_required(VERSION 3.5)

project(test_cmake_modules LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# cmake configuration
message(STATUS "append cmake module search path: ${CMAKE_CURRENT_SOURCE_DIR}")
list(APPEND CMAKE_MODULE_PATH "/Users/zouxiaoliang/workspace/github/nervlab-cn/cmake_modules")
message(STATUS "cmake module path: ${CMAKE_MODULE_PATH}")

# custom make
#set(CMD_MAKE make)

# using proxy to download
set(ENV{http_proxy} "http://127.0.0.1:1087")
set(ENV{https_proxy} "http://127.0.0.1:1087")

include(ExternalProject)
include(openssl)
include(curl)

message(STATUS "USER HOME: $ENV{HOME}")

add_executable(test_cmake_modules main.cpp)
