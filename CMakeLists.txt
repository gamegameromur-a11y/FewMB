# CMakeLists.txt for WebView2 C++ Project

cmake_minimum_required(VERSION 3.8)

# Set the project name and version
project(WebView2Demo VERSION 1.0)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Find the WebView2 SDK
find_package(WebView2 REQUIRED)

# Add the executable
add_executable(WebView2Demo main.cpp)

# Link the WebView2 SDK
target_link_libraries(WebView2Demo PRIVATE WebView2::WebView2)