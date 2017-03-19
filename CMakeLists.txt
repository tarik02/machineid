cmake_minimum_required(VERSION 3.5)

set(CMAKE_CXX_STANDARD 11)

add_library(machineid STATIC src/machineid/machineid.cpp)
target_include_directories(machineid
	PRIVATE src
	PUBLIC include)
