cmake_minimum_required(VERSION 3.1)
project(test_package CXX)

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup(TARGETS)

find_package(geotrans REQUIRED dtcc ccs CONFIG)
add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} geotrans::dtcc geotrans::ccs)
