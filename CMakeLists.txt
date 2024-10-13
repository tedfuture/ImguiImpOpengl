cmake_minimum_required(VERSION 3.10)
project(MyImGuiProject)

# include ImGui header path
include_directories(${CMAKE_SOURCE_DIR}/include)

# GLFW library
add_subdirectory(third_party/glfw)

# GLAD document
add_library(glad src/glad.c)

# ImGui Source file
set(IMGUI_SOURCES
    src/glad.c    
    src/imgui.cpp
    src/imgui_demo.cpp    
    src/imgui_draw.cpp
    src/imgui_impl_glfw.cpp
    src/imgui_impl_opengl3.cpp
    src/imgui_tables.cpp
    src/imgui_widgets.cpp
    )

add_library(imgui ${IMGUI_SOURCES})

# link library
add_executable(MyApp src/main.cpp)
target_link_libraries(MyApp imgui glad glfw)
