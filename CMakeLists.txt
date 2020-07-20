cmake_minimum_required(VERSION 2.8)

project(spaceinvaders)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
add_subdirectory(glfw)
#find_library(GLEW_LIBRARY glew32 HINTS /usr/lib/x86_64-linux-gnu)
#find_library(GLEW_LIBRARY opengl32 HINTS /usr/lib/x86_64-linux-gnu)
find_package(GLEW REQUIRED)
set(GL_LIBRARY GL GLU X11)

add_executable(${PROJECT_NAME} "main.cpp")

target_link_libraries(spaceinvaders glfw GLEW -lGL libGL.so)
