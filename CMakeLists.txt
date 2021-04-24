cmake_minimum_required(VERSION 3.16.0)

project(helloworld VERSION 1.0.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(CMAKE_AUTOUIC_SEARCH_PATHS
    "gui"
)

find_package(Qt6 COMPONENTS Widgets REQUIRED)

add_executable(helloworld
    gui/MainWindow.ui
    include/MainWindow.h
    source/MainWindow.cc
    source/main.cc
)

target_include_directories(helloworld
    PUBLIC
        "include"
)

target_link_libraries(helloworld PRIVATE Qt6::Widgets)
