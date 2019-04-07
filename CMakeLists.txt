project(kcf)

set (TARGET_NAME "kcf")

cmake_minimum_required(VERSION 2.8)
set (CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR /opt/ocv/lib/cmake/opencv4)
find_package(OpenCV REQUIRED)

if(OpenCV_FOUND)
    message("OPENCV Found")
else()
    message("Failed to find OpenCV")
    return()
endif()

include_directories(include)
FILE(GLOB_RECURSE src_files "src/*.cpp")

add_executable(${TARGET_NAME} ${src_files})
target_link_libraries(${TARGET_NAME} ${OpenCV_LIBS})

