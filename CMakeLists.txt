cmake_minimum_required(VERSION 3.6)
project(SDLTesting)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${SDLTesting_SOURCE_DIR}/cmake")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package(SDL2 REQUIRED)
find_package(SDL2_Image REQUIRED)
find_package(SDL2_ttf REQUIRED)
find_package(SDL2_mixer REQUIRED )
include_directories(${SDL2_INCLUDE_DIR} ${SDL2_IMAGE_INCLUDE_DIR} $(SDL2_TTF_INCLUDE_DIRS) $(SDLMIXER_INCLUDE_DIR) ${SDLTesting_SOURCE_DIR}/source/headers)

set(SOURCE_FILES 24_calculating_frame_rate/24_calculating_frame_rate.cpp)
add_executable(SDLTesting ${SOURCE_FILES})

target_link_libraries(SDLTesting mingw32 SDL2main SDL2 SDL2_ttf SDL2_mixer ${SDL2_IMAGE_LIBRARIES})