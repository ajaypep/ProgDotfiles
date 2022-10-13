cmake_minimum_required(VERSION 3.20)

project(ProjectName C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED TRUE)
set(CMAKE_C_EXTENSIONS OFF)
set(DO_TESTS FALSE)

if (MSVC)
    add_compile_options(/W4 /WX)
else()
    add_compile_options(-Wall -Wextra -pedantic -Werror)
endif()

if(DO_TESTS)
    enable_testing()
    add_subdirectory(test) 
    target_link_libraries(run_test PRIVATE <library_name>)
endif()

