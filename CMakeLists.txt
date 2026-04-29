cmake_minimum_required(VERSION 3.16)
project(FewMB)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# WebView2 configurations
find_package(WebView2 REQUIRED CONFIG)

# Add executable
add_executable(FewMB src/main.cpp)

# Link WebView2
target_link_libraries(FewMB PRIVATE WebView2::WebView2)

# Link system libraries for Windows
if(WIN32)
  target_link_libraries(FewMB PRIVATE 
    ole32
    oleaut32
    uuid
  )
endif()