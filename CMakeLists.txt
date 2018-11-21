cmake_minimum_required(VERSION 3.2)
project(xonixpacman)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES main.cpp Scene.cpp Scene.h Entities.cpp Entities.h Player.cpp Player.h Ghost.cpp Ghost.h Item.cpp Item.h Game.cpp Game.h Menu.cpp Menu.h)
add_executable(xonixpacman ${SOURCE_FILES})

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})
find_package(SFML REQUIRED system window graphics network audio)
if (SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(xonixpacman ${SFML_LIBRARIES})
endif()