#############
# DearImGUI #
#############

cmake_minimum_required(VERSION 3.25)

project(dearimgui)

set(IMGUI_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp"
)

add_library(${PROJECT_NAME} STATIC ${IMGUI_SOURCES})
add_library(dearimgui::dearimgui_static ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME} 
	INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}"
)

install(TARGETS ${PROJECT_NAME})
