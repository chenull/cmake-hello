cmake_minimum_required(VERSION 3.20)

project(hello_cmake LANGUAGES CXX)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(hello_cmake src/main.cpp)
target_compile_features(hello_cmake PRIVATE cxx_std_17)

