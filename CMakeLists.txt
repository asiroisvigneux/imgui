cmake_minimum_required(VERSION 3.10)
project(imgui
  LANGUAGES CXX
)

if(CMAKE_VERSION VERSION_GREATER 3.12)
        add_compile_definitions(IMGUI_IMPL_OPENGL_LOADER_GLAD=1)
else()
        add_definitions("-DIMGUI_IMPL_OPENGL_LOADER_GLAD=1")
endif()

add_library(
        imgui STATIC
        imgui.cpp
        imgui_draw.cpp
        imgui_internal.h
        imstb_textedit.h
        imgui.h
        imgui_widgets.cpp
        imgui_tables.cpp
        imstb_truetype.h
        imconfig.h
        imgui_demo.cpp
        imstb_rectpack.h
        backends/imgui_impl_glfw.h
        backends/imgui_impl_glfw.cpp
        backends/imgui_impl_opengl3.cpp
        backends/imgui_impl_opengl3.h
        )

target_link_libraries(imgui PRIVATE glfw glad)