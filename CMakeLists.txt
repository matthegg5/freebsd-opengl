cmake_minimum_required(VERSION 3.0.0)
project(freebsd_opengl VERSION 0.1.0)
cmake_policy(SET CMP0072 NEW)

find_package(OpenGL REQUIRED)

add_executable(freebsd_opengl src/main.cpp src/glad.c src/Camera.h src/shader.h)
add_subdirectory(lib/glfw-3.3.8)
add_subdirectory(lib/glm)
include_directories(/usr/local/include)
include_directories(include)

target_link_libraries(freebsd_opengl
 glfw 
 OpenGL::GL
 )

