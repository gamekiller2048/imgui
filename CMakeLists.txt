add_library(Imgui OBJECT
    imgui.cpp
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_tables.cpp
    imgui_widgets.cpp
    "backends/imgui_impl_${BACKEND}.cpp"
)

target_include_directories(Imgui PUBLIC . backends)

if(WIN32)
    target_sources(Imgui PRIVATE backends/imgui_impl_win32.cpp)
else()
    message(FATAL_ERROR "TODO: add OS here")
endif()