cmake_minimum_required(VERSION 3.16.0)

set(project helloworld)

set(gui
    gui/MainWindow.ui
)

set(include
    include/MainWindow.h
)

set(source
    source/MainWindow.cc
    source/main.cc
)

project(${project} VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(CMAKE_AUTOUIC_SEARCH_PATHS
    "gui"
)

find_package(Qt6 COMPONENTS Widgets REQUIRED)

add_executable(${project}
    ${gui}
    ${include}
    ${source}
)

target_include_directories(${project}
    PUBLIC
        "include"
)

target_link_libraries(${project} PRIVATE Qt6::Widgets)
