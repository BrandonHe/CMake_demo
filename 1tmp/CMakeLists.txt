cmake_minimum_required(VERSION 2.6)
project(HELLO)
set(SRC_LIST main.c)
message(STATUS "This is binary directory." ${HELLO_BINARY_DIRECTORY})
message(STATUS "This is source directory." ${HELLO_SOURCE_DIRECTORY})
add_executable(hello ${SRC_LIST})

