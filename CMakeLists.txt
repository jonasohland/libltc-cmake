cmake_minimum_required(VERSION 3.5)

project(ltc C)

add_library(ltc
    STATIC
    ${CMAKE_CURRENT_LIST_DIR}/libltc/src/decoder.c
    ${CMAKE_CURRENT_LIST_DIR}/libltc/src/encoder.c
    ${CMAKE_CURRENT_LIST_DIR}/libltc/src/timecode.c
    ${CMAKE_CURRENT_LIST_DIR}/libltc/src/ltc.c
)

target_include_directories(ltc
    PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}/libltc/src
)

if(WIN32)
    # yeah we ignore there here...
    target_compile_options(ltc PRIVATE /wd4244 /wd4996 /wd4267)
endif()