cmake_minimum_required(VERSION 2.8)
project(hello_world)

set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

aux_source_directory(${PROJECT_SOURCE_DIR}/src/lib_src LIB_SRC)
add_library(hello_world_static ${LIB_SRC})
add_library(hello_world_shared SHARED ${LIB_SRC})

add_executable(hello_world src/main.cc)

target_link_libraries(hello_world hello_world_shared)
