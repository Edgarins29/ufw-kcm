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
