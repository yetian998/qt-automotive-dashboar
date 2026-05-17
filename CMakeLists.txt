cmake_minimum_required(VERSION 3.16)
project(qt-automotive-dashboar)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt6 COMPONENTS
    Core
    Gui
    Widgets
    REQUIRED
)

set(PROJECT_SOURCES
    src/main.cpp
    src/models/vehicle_data.h
    src/models/vehicle_data.cpp
    src/models/vehicle_status.h
    src/widgets/gauge_widget.h
    src/widgets/gauge_widget.cpp
    src/widgets/speedometer.h
    src/widgets/speedometer.cpp
    src/widgets/rpm_gauge.h
    src/widgets/rpm_gauge.cpp
    src/widgets/fuel_indicator.h
    src/widgets/fuel_indicator.cpp
    src/widgets/temperature_gauge.h
    src/widgets/temperature_gauge.cpp
    src/widgets/warning_lights.h
    src/widgets/warning_lights.cpp
    src/widgets/digital_display.h
    src/widgets/digital_display.cpp
    src/widgets/trip_computer.h
    src/widgets/trip_computer.cpp
    src/views/dashboard_view.h
    src/views/dashboard_view.cpp
    src/views/navigation_view.h
    src/views/navigation_view.cpp
    src/views/settings_view.h
    src/views/settings_view.cpp
    src/utils/constants.h
    src/utils/data_simulator.h
    src/utils/data_simulator.cpp
    src/utils/theme_manager.h
    src/utils/theme_manager.cpp
)

add_executable(${PROJECT_NAME}
    ${PROJECT_SOURCES}
)

target_link_libraries(${PROJECT_NAME}
    Qt6::Core
    Qt6::Gui
    Qt6::Widgets
)

target_include_directories(${PROJECT_NAME} PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/src
)
