cmake_minimum_required(VERSION 3.16)
set (CMAKE_CXX_STANDARD 17)

add_subdirectory(lib)

add_executable(a.out main.cpp)
target_link_libraries(a.out mylib)

find_package(LLVM REQUIRED CONFIG)
include_directories(${LLVM_INCLUDE_DIRS})
target_link_directories(a.out PRIVATE ${LLVM_LIBRARY_DIRS})
target_link_libraries(a.out LLVM-16)


target_include_directories(a.out PUBLIC ${PROJECT_SOURCE_DIR}/include)