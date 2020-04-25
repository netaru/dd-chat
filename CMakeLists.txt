cmake_minimum_required(VERSION 3.14.0)
project(dd-chat)

set (CMAKE_CXX_STANDARD 17)

set(BUILD_TESTS OFF CACHE BOOL "Build with tests.")

find_package(PkgConfig REQUIRED)

include_directories("include")

add_executable(server "src/server.cc")

if(${BUILD_TESTS})
  enable_testing()
  add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/test test)
endif()
