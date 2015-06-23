cmake_minimum_required(VERSION 3.2)
project(rpi_hello_servo)

set(CMAKE_C_FLAGS "-std=c99")

find_package (Threads REQUIRED)
find_package(Curses REQUIRED)

link_libraries(ncurses pthread)

include_directories( ${CURSES_INCLUDE_DIR} )

set(SOURCE_FILES
    clock.c
    my_ui_thread.c
    my_ui_thread.h
    time_utils.c
    time_utils.h)

add_executable(rpi_hello_servo ${SOURCE_FILES})
