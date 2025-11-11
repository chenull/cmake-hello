cmake_minimum_required(VERSION 3.20)

project(hello_cmake LANGUAGES CXX)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

include(GNUInstallDirs)

add_executable(hello_cmake src/main.cpp)
target_compile_features(hello_cmake PRIVATE cxx_std_17)

install(TARGETS hello_cmake
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
)

