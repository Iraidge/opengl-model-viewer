cmake_minimum_required(VERSION 3.20)
project(OpenGLModelViewer C CXX)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(glfw3 REQUIRED)
find_package(OpenGL REQUIRED)

add_executable(viewer
    OpenGL_Window/main.cpp
    third_party/glad/src/glad.c)
target_include_directories(viewer PRIVATE third_party/glad/include)
target_link_libraries(viewer PRIVATE glfw OpenGL::GL ${CMAKE_DL_LIBS})
