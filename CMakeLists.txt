cmake_minimum_required(VERSION 3.6)
project(Particle_Simulation)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

# includes cmake/FindSDL2.cmake
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake_modules)
find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIR})

set(SOURCE_FILES src/main.cpp src/Screen.cpp include/Screen.h src/Particle.cpp include/Particle.h src/Swarm.cpp include/Swarm.h)
add_executable(Particle_Simulation ${SOURCE_FILES})
target_link_libraries(Particle_Simulation ${SDL2_LIBRARY})
