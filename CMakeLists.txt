cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 17)

project(Calculator_project)

set(SOURCE_EXE src/main.cpp)

set(SOURCE_LIB src/Calculator.cpp)

set(SOURCE_HEADER src/Calculator.h)

add_library(
    Calculator STATIC 
    ${SOURCE_LIB} 
    ${SOURCE_HEADER}
    )

target_include_directories(
    Calculator
    PUBLIC
    "src"
)

add_executable(main ${SOURCE_EXE})

target_link_libraries(main Calculator)
