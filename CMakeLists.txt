cmake_minimum_required (VERSION 3.7.0)

project(ripole)

if(MSVC)
    add_definitions(-D_CRT_SECURE_NO_WARNINGS)
endif()

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

set(SOURCE ${PROJECT_SOURCE_DIR}/ole.c
${PROJECT_SOURCE_DIR}/olestream-unwrap.c
${PROJECT_SOURCE_DIR}/bytedecoders.c
${PROJECT_SOURCE_DIR}/logger.c
${PROJECT_SOURCE_DIR}/pldstr.c
${PROJECT_SOURCE_DIR}/bt-int.c
${PROJECT_SOURCE_DIR}/ripole.c)

add_executable(ripole ${SOURCE})

set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT ripole)
