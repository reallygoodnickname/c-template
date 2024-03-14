cmake_minimum_required(VERSION 3.22.1)

project(project VERSION 0.0.1 LANGUAGES C)

set(PROJECT_SUBDIRECTORIES
	src					# Project sources
)

option(OPT_BUILD_TESTS 		  "Build tests" 	   OFF)

# Add all subdirectories
foreach(subdirectory ${PROJECT_SUBDIRECTORIES})
	add_subdirectory(${subdirectory})
endforeach()

# Add tests if asked to build
if(OPT_BUILD_TESTS)
	enable_testing()
	add_subdirectory(tests)
endif()
