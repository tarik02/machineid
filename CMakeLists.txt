cmake_minimum_required(VERSION 3.5)

project(machineid LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)

add_library(machineid STATIC src/machineid/machineid.cpp)
target_include_directories(machineid
	PRIVATE src
	PUBLIC include)
if (WIN32)
	target_link_libraries(machineid PRIVATE iphlpapi)
endif()

if (BUILD_TESTING)
	add_executable(test tests/test.cpp)
	target_link_libraries(test PRIVATE machineid)
endif()
