cmake_minimum_required(VERSION 3.1)
project(game.libretro.mame2014)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(MAME2014_LIB NAMES mame2014_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(MAME2014_CUSTOM_BINARY ${MAME2014_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} MAME2014 "")

include(CPack)
