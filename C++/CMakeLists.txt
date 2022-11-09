cmake_minimum_required(VERSION 3.20)

project(ProjectName CXX)

if(DO_TESTS)
    enable_testing()
    add_subdirectory(test) 
    target_link_libraries(run_test PRIVATE <library_name>)
endif()

