cmake_minimum_required(VERSION 3.18)
project(pcg-cpp-wrapper NONE)

include (FetchContent)

FetchContent_Declare(pcg_cpp
  GIT_REPOSITORY     https://github.com/imneme/pcg-cpp.git
  GIT_TAG            master)
FetchContent_MakeAvailable(pcg_cpp)
FetchContent_GetProperties(pcg_cpp)

add_library(pcg-cpp INTERFACE)
target_include_directories(pcg-cpp INTERFACE $<BUILD_INTERFACE:${PROJECT_BINARY_DIR}/${pcg_cpp_SOURCE_DIR}/include>)
