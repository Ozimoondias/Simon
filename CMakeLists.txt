#Project Simon
cmake_minimum_required(VERSION 3.0)

project(Simon)

include_directories(include)

include_directories(/usr/include/irrklang)
include_directories(/usr/include/irrlicht)

#Add the files
file(GLOB_RECURSE SOURCES src/*.cpp)
add_executable(simon ${SOURCES})

target_link_libraries(
		simon
		IrrKlang
        	Irrlicht
        	GL
        	Xxf86vm
        	Xext
        	X11
		pthread
        	Xcursor
)

#Copy resources
file(COPY ${CMAKE_SOURCE_DIR}/res DESTINATION ${CMAKE_BINARY_DIR})
