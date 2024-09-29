cmake_minimum_required(VERSION 3.25)
cmake_policy(VERSION 3.25...3.30)
set(CMAKE_POLICY_DEFAULT_CMP0069 NEW)
set(CMAKE_POLICY_DEFAULT_CMP0077 NEW)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_C_STANDARD 11)

project(main LANGUAGES CXX)

add_library(project_options INTERFACE)
target_compile_features(project_options INTERFACE "cxx_std_${CMAKE_CXX_STANDARD}")

add_executable(main main.cpp)

find_package(FMT REQUIRED)

target_link_libraries(main PRIVATE project_options fmt::fmt-header-only)

