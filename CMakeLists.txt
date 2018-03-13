cmake_minimum_required(VERSION 3.2.0)
project(hello_gstreamer C)
include (${CMAKE_CURRENT_SOURCE_DIR}/FindGStreamer.cmake)

set(hello_INCLUDE_DIRECTORIES
    ${GSTREAMER_INCLUDE_DIRS}
    )

set(hello_LIBRARIES
    ${GSTREAMER_LIBRARIES}
)
  
include_directories(SYSTEM ${hello_INCLUDE_DIRECTORIES})

#Bring the headers, such as Student.h into the project
include_directories(include)

#Can manually add the sources using the set command as follows:
set(SOURCES hellogst.c)
add_executable(hello_gstreamer ${SOURCES})
target_link_libraries(hello_gstreamer ${GSTREAMER_LIBRARIES})
