cmake_minimum_required(VERSION 3.10.0 FATAL_ERROR)

set(CMAKE_CONFIGURATION_TYPES Release Debug)
set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake)

project(ProjectMoonlord)

# Set application to GUI type for Win32 and MacOS
if(WIN32)
  set(GUI_TYPE WIN32)
endif(WIN32)
if(APPLE)
  set(GUI_TYPE MACOSX_BUNDLE)
endif(APPLE)

set_property(GLOBAL PROPERTY OS_FOLDERS ON)

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

add_subdirectory(${CMAKE_SOURCE_DIR}/src)

