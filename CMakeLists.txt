cmake_minimum_required(VERSION 4.0)

set(PROJECT_NAME OpenGL)

set(CMAKE_CXX_STANDARD 17)

set(SRC_FILES
        src/main.cpp
        src/libs/glad.c
        src/libs/std_image.cpp
        src/libs/std_image.cpp
        include/learnopengl/mesh.h
        include/learnopengl/shader.h)

set(INCLUDE_FOLDER include)

project(${PROJECT_NAME})

find_package(glfw3 CONFIG REQUIRED)
find_package(assimp CONFIG REQUIRED)

add_executable( ${PROJECT_NAME} ${SRC_FILES} )

target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_FOLDER})

target_link_libraries(${PROJECT_NAME} PRIVATE glfw)
target_link_libraries(${PROJECT_NAME} PRIVATE assimp::assimp)