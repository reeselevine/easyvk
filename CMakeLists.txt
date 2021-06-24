cmake_minimum_required(VERSION 2.8.9)
project(directory_test)
set(CMAKE_BUILD_TYPE Release)

#Bring the headers, such as Student.h into the project
include_directories(include)

#However, the file(GLOB...) allows for wildcard additions:
file(GLOB SOURCES "src/*.hpp")

#Generate the shared library from the sources
add_library(easyvk SHARED ${SOURCES})
set_target_properties(easyvk PROPERTIES LINKER_LANGUAGE CXX)

#Set the location for library installation -- i.e., /usr/lib in this case
# not really necessary in this example. Use "sudo make install" to apply
install(TARGETS easyvk DESTINATION /usr/lib)
