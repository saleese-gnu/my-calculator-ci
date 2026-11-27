cmake_minimum_required(VERSION 3.16)
project(googletest_sample CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# googletest download start
include(FetchContent)
FetchContent_Declare(googletest
  URL https://github.com/google/googletest/archive/refs/tags/v1.17.0.zip
  DOWNLOAD_EXTRACT_TIMESTAMP TRUE)
# Windows: 프로젝트와 같은 C 런타임을 쓰도록 설정
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)
# googletest download ended

add_library(sumLibrary STATIC sum.cpp)
add_executable(mainApp main.cpp)
target_link_libraries(mainApp sumLibrary)

add_executable(testRunner sum_test.cpp)
target_link_libraries(testRunner sumLibrary GTest::gtest)
