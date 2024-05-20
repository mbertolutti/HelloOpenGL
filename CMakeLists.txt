cmake_minimum_required(VERSION 3.29)

project(HelloOpenGL)

set(glfw3_DIR "~/vcpkg/installed/arm64-osx/share/glfw3")
find_package(glfw3 3.3 REQUIRED CONFIG)

set(glad_DIR "~/vcpkg/installed/arm64-osx/share/glad")
find_package(glad REQUIRED CONFIG)

set(glm_DIR "~/vcpkg/installed/arm64-osx/share/glm")
find_package(glm REQUIRED)

set(fmt_DIR "~/vcpkg/installed/arm64-osx/share/fmt")
find_package(fmt REQUIRED)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(HelloOpenGL main.cpp)

target_link_libraries(HelloOpenGL PRIVATE fmt::fmt glfw glad::glad glm::glm-header-only)
target_compile_features(HelloOpenGL PRIVATE cxx_std_23)
