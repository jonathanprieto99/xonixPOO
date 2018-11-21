cmake_minimum_required(VERSION 3.4)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(EXECUTABLE_NAME "MySFML7")
set(SOURCE_FILES main.cpp data/Scene.cpp data/Scene.h data/Entities.cpp data/Entities.h data/Player.cpp data/Player.h data/Ghost.cpp data/Ghost.h data/Item.cpp data/Item.h data/Game.cpp data/Game.h data/Menu.cpp data/Menu.h)
add_executable(${EXECUTABLE_NAME} main.cpp)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})
find_package(SFML REQUIRED system window graphics network audio)

if (SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${EXECUTABLE_NAME} ${SFML_LIBRARIES})
endif()