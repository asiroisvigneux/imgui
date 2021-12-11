cmake_minimum_required(VERSION 3.1)
project(imgui)

add_compile_definitions(IMGUI_IMPL_OPENGL_LOADER_GLAD=1)

file(GLOB SRC_FILES *.cpp *.h)
add_library(imgui STATIC
    ${SRC_FILES}
    backends/imgui_impl_opengl3.cpp
    backends/imgui_impl_glfw.cpp
)

# includes
target_include_directories(imgui PRIVATE
    .
    ../glad/include
    ../glfw/include
)

target_link_libraries(imgui PRIVATE glfw glad)