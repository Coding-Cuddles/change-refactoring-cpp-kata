cmake_minimum_required(VERSION 3.19)
project(change-refactoring-cpp-kata CXX)
enable_testing()

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_INCLUDE_DIRECTORIES ${CMAKE_CXX_IMPLICIT_INCLUDE_DIRECTORIES})
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(GTest)

add_executable(test_change test_change.cpp)
add_test(test_change test_change)
target_include_directories(test_change PRIVATE .)
target_link_libraries(test_change PRIVATE GTest::gmock GTest::gmock_main)

add_custom_target(  
    copy-compile-commands ALL
    ${CMAKE_COMMAND} -E copy_if_different
    ${CMAKE_BINARY_DIR}/compile_commands.json
    ${CMAKE_CURRENT_LIST_DIR}
)
