cmake_minimum_required(VERSION 4.0)

set(PROJECT_NAME OpenGL)

set(CMAKE_CXX_STANDARD 17)

set(SRC_FILES
        src/main.cpp
        src/libs/glad.c
        src/libs/std_image.cpp
        src/libs/std_image.cpp
#        include/learnopengl/mesh.h
#        include/learnopengl/shader.h
        src/libs/imgui/imgui.cpp
        src/libs/imgui/imgui_demo.cpp
        src/libs/imgui/imgui_draw.cpp
        src/libs/imgui/imgui_impl_glfw.cpp
        src/libs/imgui/imgui_impl_opengl3.cpp
        src/libs/imgui/imgui_tables.cpp
        src/libs/imgui/imgui_widgets.cpp
        )

set(INCLUDE_FOLDER include include/learnopengl)

project(${PROJECT_NAME})

find_package(glfw3 CONFIG REQUIRED)
find_package(assimp CONFIG REQUIRED)
#find_package(imgui CONFIG REQUIRED)
find_package(GLEW REQUIRED)

add_executable( ${PROJECT_NAME} ${SRC_FILES} )

target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_FOLDER})

#target_link_libraries(${PROJECT_NAME} PRIVATE imgui::imgui)
target_link_libraries(${PROJECT_NAME} PRIVATE glfw)
target_link_libraries(${PROJECT_NAME} PRIVATE assimp::assimp)
target_link_libraries(${PROJECT_NAME} PRIVATE GLEW::GLEW)