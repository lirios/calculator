cmake_minimum_required(VERSION 3.10.0)

project("Calculator"
    VERSION "1.3.0"
    DESCRIPTION "Calculator application"
    LANGUAGES CXX C
)

## Shared macros and functions:
if(CALCULATOR_WITH_FLUID AND EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/fluid/CMakeLists.txt")
    set(LIRI_LOCAL_ECM TRUE)
    set(FLUID_WITH_DOCUMENTATION FALSE)
    set(FLUID_WITH_DEMO FALSE)
endif()
if(LIRI_LOCAL_ECM)
    list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/fluid/cmake/shared/modules")
else()
    find_package(LiriCMakeShared "2.0.0" REQUIRED NO_MODULE)
    list(APPEND CMAKE_MODULE_PATH "${LCS_MODULE_PATH}")
endif()

## Set minimum versions required.
set(QT_MIN_VERSION "5.10.0")

## Liri specific setup common for all modules:
include(LiriSetup)

## Features:
option(CALCULATOR_WITH_FLUID "Build together with Fluid" OFF)
add_feature_info("Calculator::WithFluid" CALCULATOR_WITH_FLUID "Build together with Fluid")

## Find Qt 5.
find_package(Qt5 "${QT_MIN_VERSION}"
    CONFIG REQUIRED
    COMPONENTS
        Core
        Gui
        Widgets
        Svg
        Qml
        Quick
        QuickControls2
        LinguistTools
)

## Add subdirectories:
if(CALCULATOR_WITH_FLUID)
    add_subdirectory(fluid)
endif()
add_subdirectory(data)
add_subdirectory(src)
