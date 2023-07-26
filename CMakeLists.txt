cmake_minimum_required(VERSION 3.1)
project(SDL_FontCache VERSION 0.10.0 LANGUAGES C)

find_package(SDL2 REQUIRED)
find_package(SDL2_ttf REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})
include_directories(${_sdl2ttf_incdir})

add_library(FontCache
    SHARED
    SDL_FontCache.h
    SDL_FontCache.c
)

target_link_libraries(FontCache SDL2::SDL2 SDL2::SDL2main SDL2_ttf::SDL2_ttf)
