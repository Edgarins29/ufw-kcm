# based on systmed-kcm
project(ufw-kcm)
set(PROJECT_VERSION "0.0.1")

cmake_minimum_required(VERSION 2.8.12 FATAL_ERROR)

set(QT_MIN_VERSION "5.2.0")
set(KF5_MIN_VERSION "5.1.0")


find_package(ECM 1.1.0 REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} ${ECM_KDE_MODULE_DIR})
set(CMAKE_AUTOMOC ON)
set(CMAKE_INCLUDE_CURRENT_DIR ON)

find_package(Qt5 ${QT_MIN_VERSION} CONFIG REQUIRED COMPONENTS
             Widgets
             DBus)

find_package(KF5 ${KF5_MIN_VERSION} REQUIRED COMPONENTS
             Auth
             ConfigWidgets
             CoreAddons
             Crash
             I18n
             KIO
             WidgetsAddons)

include(KDEInstallDirs)
include(KDECompilerSettings)
include(KDECMakeSettings)
include(FeatureSummary)
include(CheckIncludeFiles)

find_package(PkgConfig REQUIRED)
pkg_check_modules(UFW "ufw" REQUIRED)

if(UFW_FOUND)
    pkg_check_modules(PYTHON_UFW "python-ufw" REQUIRED)
endif()

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fexceptions")
# Adding local CMake modules
set (
   CMAKE_MODULE_PATH
   ${CMAKE_CURRENT_SOURCE_DIR}/cmake/modules
   ${CMAKE_MODULE_PATH}
   )

configure_file(config.h.cmake ${CMAKE_CURRENT_BINARY_DIR}/src/config.h)

add_definitions(-DTRANSLATION_DOMAIN=\"ufw-kcm\")

add_subdirectory(other)
add_subdirectory(src)

ki18n_install(po)

feature_summary(WHAT ALL FATAL_ON_MISSING_REQUIRED_PACKAGES)
