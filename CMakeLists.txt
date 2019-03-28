cmake_minimum_required (VERSION 3.12.1)
project (ConvexHull)
enable_testing()
include(CTest)
set(CMAKE_CXX_FLAGS -std="c++17")

find_package(Boost 1.55 REQUIRED COMPONENTS unit_test_framework)
include_directories (tests ${Boost_INCLUDE_DIRS})
add_definitions (-DBOOST_TEST_DYN_LINK)

add_library(libconvexhull
    convex_hull.cpp
)

add_executable(main main.cpp)
target_link_libraries(main libconvexhull)
