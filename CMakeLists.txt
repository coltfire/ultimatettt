cmake_minimum_required(VERSION 3.21)

project(ultimatettt C)

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})

find_package(PkgConfig)
pkg_check_modules(SDL2_GFX SDL2_gfx)
include_directories(${SDL2_GFX_INCLUDE_DIRS})

SET(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O0 -Wall -Werror -fdump-rtl-expand")

set(SRCS
  src/main.c
  src/logic.c
  src/rendering.c
)

set(HEADERS
  src/game.h
  src/logic.h
  src/rendering.h
)

add_executable(ultimatettt ${SRCS} ${HEADERS})
target_link_libraries(ultimatettt ${SDL2_LIBRARIES} ${SDL2_GFX_LIBRARIES})
