cmake_minimum_required(VERSION 3.7)
project(obj)
set(CMAKE_CXX_STANDARD 11)
add_definitions("-DCONF_NO_GL")

add_library(lib-obj STATIC obj.c)

install(
    TARGETS lib-obj
    CONFIGURATIONS Debug
    DESTINATION "${CMAKE_INSTALL_PREFIX}/lib/Debug"
)

install(
    TARGETS lib-obj
    CONFIGURATIONS Release
    DESTINATION "${CMAKE_INSTALL_PREFIX}/lib/Release"
)

install(
	FILES obj.h 
	DESTINATION "${CMAKE_INSTALL_PREFIX}/include"
)