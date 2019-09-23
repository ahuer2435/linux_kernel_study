#set(CMAKE_TOOLCHAIN_FILE ${CMAKE_CURRENT_SOURCE_DIR}/../../toolchains/aarch64-linux-gnu.toolchain.cmake)

project(test-thread)

message(STATUS "--Current src dir: ${CMAKE_CURRENT_SOURCE_DIR}")
message(STATUS "--Current bin dir: ${CMAKE_CURRENT_BINARY_DIR}")
message(STATUS "--CMAKE_SYSTEM_PROCESSOR: ${CMAKE_SYSTEM_PROCESSOR}")

# Better ARM support
set(CMAKE_CXX_STANDARD 11)

cmake_minimum_required(VERSION 3.8)
message(STATUS "Cmake version = ${CMAKE_VERSION}")

add_executable(test_thread  control.c queue.c workcrew.c)
target_link_libraries(test_thread pthread)