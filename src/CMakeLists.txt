# Make executable name match project name
set(EXECUTABLE_NAME ${CMAKE_PROJECT_NAME})

# Project source files 
set(PROJECT_SOURCES
	project.c	
)

# Adding executable
add_executable(${EXECUTABLE_NAME} ${PROJECT_SOURCES})
