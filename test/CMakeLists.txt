cmake_minimum_required(VERSION 3.10)

# Include GoogleTest
# include(FetchContent)
# FetchContent_Declare(
#   googletest
#   URL https://github.com/google/googletest/archive/609281088cfefc76f9d0ce82e1ff6c30cc3591e5.zip
# )
# set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
# FetchContent_MakeAvailable(googletest)
# include(GoogleTest)

set(GTest_DIR ${CMAKE_CURRENT_SOURCE_DIR}/third_party/googletest)
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
add_subdirectory(${GTest_DIR})
include(GoogleTest)

# Compile option (re-do this, because GoogleTest seems to set CMAKE_CXX_STANDARD to 11)
include(${CMAKE_SOURCE_DIR}/cmakes/compile_option.cmake)

# Add test modules
add_subdirectory(./main)
