cmake_minimum_required(VERSION 3.16)
set (CMAKE_CXX_STANDARD 20)

add_subdirectory(lib)

add_executable(a.out main.cpp)
target_link_libraries(a.out mylib)

target_include_directories(a.out PUBLIC ${PROJECT_SOURCE_DIR}/include)