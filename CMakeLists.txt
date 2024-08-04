### Main
cmake_minimum_required(VERSION 3.30)

set(CMAKE_C_COMPILER clang)
set(CMAKE_CXX_COMPILER clang++)

### ### Copied from main project
### set(CXX_SCAN_FOR_MODULES ON)
set(CMAKE_CXX_SCAN_FOR_MODULES ON)
set(CXX_MODULE_STD ON)
### 

# For the directives commented out with one #,
# it causes the build to fail.

#set(CMAKE_CXX_FLAGS "-stdlib=libc++")
#set(CMAKE_CXX_MODULE_STD ON)

### 
### set(CMAKE_EXPERIMENTAL_CXX_MODULE_DYNDEP 1)
### set(CMAKE_EXPERIMENTAL_CXX_MODULE_CMAKE_API "2182bf5c-ef0d-489a-91da-49dbc3090d2a")
### 
set(CMAKE_CXX_STANDARD 26)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPERIMENTAL_CXX_IMPORT_STD "0e5b6991-d74f-4b3d-a41c-cf096e0b2508")
### 
add_compile_options(-std=c++26 -fmodules)
#add_compile_options(-stdlib=libc++)
### 
### # Default to C++ extensions being off. Clang's modules support have trouble
### # with extensions right now and it is not required for any other compiler
set(CMAKE_CXX_EXTENSIONS OFF)
### ### End copied from main project

project(std_module_example CXX)

add_subdirectory (OneWeekend)
