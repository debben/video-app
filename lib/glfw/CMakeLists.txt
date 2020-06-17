cmake_minimum_required(VERSION 3.14)
project(glfw)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GLFW3     REQUIRED IMPORTED_TARGET glfw3)

add_library(glfw3 INTERFACE IMPORTED GLOBAL)
target_include_directories(glfw3 INTERFACE
    ${GLFw3_INCLUDE_DIRS}
)

target_link_libraries(glfw3 INTERFACE ${GLFW3_LIBRARIES})
