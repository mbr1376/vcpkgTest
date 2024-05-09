cmake_minimum_required(VERSION 3.10)

project(vcpkgTest)
find_package(fmt CONFIG REQUIRED)

add_executable(vcpkgTest main.cpp) 

target_link_libraries(vcpkgTest PRIVATE fmt::fmt)