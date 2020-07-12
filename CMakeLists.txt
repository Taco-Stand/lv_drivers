cmake_minimum_required(VERSION 3.16)
project(lv_drivers)

find_package(SDL2 REQUIRED)

file(GLOB_RECURSE SOURCES "*.c")

set(LV_DRIVERS_INCLUDE_DIRS ${PROJECT_SOURCE_DIR})
set(LV_DRIVERS_LIBRARIES $<TARGET_FILE:lv_drivers>)

include_directories(${SDL2_INCLUDE_DIRS})

add_library(lv_drivers STATIC ${SOURCES})
target_include_directories(lv_drivers PUBLIC "${PROJECT_SOURCE_DIR}/../")

