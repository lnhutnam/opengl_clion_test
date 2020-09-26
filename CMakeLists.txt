cmake_minimum_required(VERSION 3.17)
project(opengl_clion_test)

find_package(OpenGL REQUIRED)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# Including GLFW
add_subdirectory(dependencies/GLFW)
include_directories(dependencies/GLFW/include)

# Including GLAD
include_directories(dependencies/glad/include)

set(SOURCE_FILES main.cpp dependencies/glad/src/glad.c)

add_executable(${CMAKE_PROJECT_NAME} ${SOURCE_FILES})

# Linking GLFW and OGL
target_link_libraries(${CMAKE_PROJECT_NAME} glfw ${GLFW_LIBRARIES} ${OPENGL_LIBRARY})