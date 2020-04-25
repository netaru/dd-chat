cmake_minimum_required (VERSION 3.14.0)
project (dd-chat-test)

set (CMAKE_CXX_STANDARD 17)
include_directories("${dd-chat_SOURCE_DIR}/include")

include(GoogleTest)

add_executable(ServerTest "src/server_test.cc")
target_link_libraries(ServerTest gtest gtest_main)
gtest_add_tests(TARGET ServerTest TEST_SUFFIX .noargs TEST_LIST normal)
