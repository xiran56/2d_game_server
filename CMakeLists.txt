cmake_minimum_required(VERSION 3.5)

project(2dgame_server)

add_subdirectory(src)
add_subdirectory(deps)

add_executable(${PROJECT_NAME} ${SOURCES})

find_package(Boost COMPONENTS system regex thread)
target_link_libraries(${PROJECT_NAME} ${Boost_LIBRARIES})

include(CMakePrintHelpers)
cmake_print_variables(INCLUDES)
cmake_print_variables(SOURCES)

target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDES})

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD_REQUIRED ON)
