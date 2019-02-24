cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)

include(tools/gate/cmake/HunterGate.cmake)

huntergate(
    URL "https://github.com/bboyfat/hunter/archive/v0.23.89.1.tar.gz"
    SHA1 ""
)

project(demo)

hunter_add_package(print)
find_package(print)

add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/sources/demo.cpp)
target_link_libraries(demo print)

install(TARGETS demo RUNTIME DESTINATION bin)
