cmake_minimum_required(VERSION 3.20)

project(ProjectName CXX)

if(DO_TESTS)
    enable_testing()
    add_subdirectory(test) 
    target_link_libraries(run_test PRIVATE <library_name>)
endif()

if(CMAKE_EXPORT_COMPILE_COMMANDS)
    if(NOT EXISTS ${CMAKE_SOURCE_DIR}/build/compile_commands.json) 
        file(CREATE_LINK ${CMAKE_BINARY_DIR}/compile_commands.json ${CMAKE_SOURCE_DIR}/build/compile_commands.json SYMBOLIC)
    endif()
endif()
