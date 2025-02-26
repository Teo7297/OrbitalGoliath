cmake_minimum_required(VERSION 3.27)
project(OrbitalGoliath LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

include(FetchContent)

FetchContent_Declare(
  ShakEngine
  GIT_REPOSITORY https://github.com/Teo7297/ShakEngine.git
  GIT_TAG master
  )
FetchContent_MakeAvailable(ShakEngine)

file(GLOB_RECURSE SOURCES src/*.cpp)

add_executable(${PROJECT_NAME} ${SOURCES})

target_include_directories(${PROJECT_NAME} PUBLIC src) # better use a classic include dir

target_link_libraries(${PROJECT_NAME} PUBLIC ShakEngine)