cmake_minimum_required(VERSION 3.2)
project(xonixpacman)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES main.cpp)
add_executable(xonixpacman ${SOURCE_FILES})

set(CMAKE_MODULE_PATH "~/CLionProjects/Código Pacman/cmake_modules")
find_package(SFML REQUIRED system window graphics network audio)
if (SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(xonixpacman ${SFML_LIBRARIES})
endif()