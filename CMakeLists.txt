cmake_minimum_required(VERSION 3.7)
project(obj)
set(CMAKE_CXX_STANDARD 11)
add_definitions("-DCONF_NO_GL")

add_library(lib-obj STATIC obj.c)

if(APPLE)
	set(platform "osx")
elseif(UNIX AND NOT APPLE)
	set(platform "linux")
else()
	set(platform "win32")
endif()

install(
    TARGETS lib-obj
    CONFIGURATIONS Debug
    DESTINATION "${CMAKE_INSTALL_PREFIX}/lib/${platform}/Debug"
)

install(
    TARGETS lib-obj
    CONFIGURATIONS Release
    DESTINATION "${CMAKE_INSTALL_PREFIX}/lib/${platform}/Release"
)

install(
	FILES obj.h 
	DESTINATION "${CMAKE_INSTALL_PREFIX}/include"
)