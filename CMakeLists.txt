cmake_minimum_required(VERSION 2.8.3)
if (EXISTS /opt/vcpkg)
    set(CMAKE_TOOLCHAIN_FILE "/opt/vcpkg/scripts/buildsystems/vcpkg.cmake")
endif ()
project(peac)

add_compile_options(-std=c++11)

find_package(OpenCV 3 REQUIRED)
find_package(Eigen3 REQUIRED)
find_package(Freetype REQUIRED)

include_directories(include/peac ${EIGEN3_INCLUDE_DIR})

add_executable(demo_peac src/demo_peac.cpp)
target_link_libraries(demo_peac ${OpenCV_LIBRARIES} Freetype::Freetype)
