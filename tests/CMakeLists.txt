enable_testing()

# Test sources
set(TEST_SOURCES
	test_porject.c
)

find_library(CMOCKA_LIB NAMES cmocka)

# CMocka git repo link and tag (to use specific version)
set(CMOCKA_REPO https://git.cryptomilk.org/projects/cmocka.git)
set(CMOCKA_TAG cmocka-1.1.7)

# Use existing library in the system, or fetch from source
if (CMOCKA_LIB)
	message(STATUS "CMocka found, linking against installed version...")
else()
	message(STATUS "CMocka library not found in system, downloading...")
	include(FetchContent)

	FetchContent_Declare(
		CMocka
		GIT_REPOSITORY ${CMOCKA_REPO}
		GIT_TAG ${CMOCKA_TAG}
	)

	FetchContent_MakeAvailable(CMocka)
endif()

add_test(NAME "Test project" COMMAND test_project)

add_executable(test_project test_project.c)

target_link_libraries(test_project PUBLIC cmocka)

