cmake_minimum_required(VERSION 3.5.1)
project(lib)

set(CMAKE_CXX_STANDARD 14)

set(SOURCES huffman.cpp
        Tree.cpp BitSet.cpp)

set(TEST tests/huffman_testing.cpp
        tests/gtest/gtest-all.cc
        tests/gtest/gtest.h
        tests/gtest/gtest_main.cc)

set(HEADERS Tree.h huffman.h BitSet.h)

add_library(lib ${SOURCES} ${HEADERS})

add_executable(testing ${SOURCES} ${HEADERS} ${TEST})

target_link_libraries(testing -lpthread)