C project template
==================
This is a basic template for C project. This template doesn't contain lots of useful features, so you can (but not necessary need) extend it (sanitizers, LPO, documentation, etc.).

Contents
--------
This template contains uses:
* CMake - buildsystem generator
* CMocka - unit and mock testing

This template also includes .clang-format file for code formatting (just Microsoft style). If you have CMocka installed (CMake manages to find it), it will use system's version, or else it will download it for this project only.

Structure
---------
This template has the following structure:

    .
    ├── CMakeLists.txt                      # Main CMakeLists file (options, etc.)
    ├── README.md                           
    ├── src                                 # Source code
    │   ├── CMakeLists.txt                  # Instructions for building executable
    │   └── project.c
    └── tests                               # Tests
        ├── CMakeLists.txt                  # Test definitions 
        └── test_project.c                  # Test sources

For adding new tests, you should edit `tests/CMakeLists.txt` file, this file is responsible for everything related to tests stuff. 

Using
-----
For building project with this structure:
```bash
mkdir build/
cd build/
cmake ..
```
If you want, you can build tests by create build with tests:
```bash
mkdir build/
cd build/
cmake -DOPT_BUILD_TESTS=on ..
```
And than you can build:
```bash
cmake --build .
```
If you've build your project with unittests, you can run them with CTest 
```bash
ctest .
```
License
-------
This template doesn't contain any LICENSE.md file, so you're free to use it in any way you want (because it's template :p)
