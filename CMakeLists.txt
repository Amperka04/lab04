#cmake_minimum_required(VERSION 3.4)

#set(CMAKE_CXX_STANDARD 11)
#set(CMAKE_CXX_STANDARD_REQUIRED ON)

#option(BUILD_EXAMPLES "Build examples" OFF)

#project(print)

#add_library(print STATIC ${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)

#target_include_directories(print PUBLIC
#  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
#  $<INSTALL_INTERFACE:include>
#)

#if(BUILD_EXAMPLES)
#  file(GLOB EXAMPLE_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/examples/*.cpp")
#  foreach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
#    get_filename_component(EXAMPLE_NAME ${EXAMPLE_SOURCE} NAME_WE)
#    add_executable(${EXAMPLE_NAME} ${EXAMPLE_SOURCE})
#    target_link_libraries(${EXAMPLE_NAME} print)
#    install(TARGETS ${EXAMPLE_NAME}
#      RUNTIME DESTINATION bin
#    )
#  endforeach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
#endif()

#install(TARGETS print
#    EXPORT print-config
#    ARCHIVE DESTINATION lib
#    LIBRARY DESTINATION lib
#)

#install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include)
#install(EXPORT print-config DESTINATION cmake)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
cmake_minimum_required(VERSION 3.4)

project(lab03)

include_directories("formatter_lib/" "formatter_ex_lib/" "solver_lib/")

add_subdirectory(formatter_ex_lib)
add_subdirectory(formatter_lib)
add_subdirectory(solver_lib)
add_subdirectory(solver_application)
add_subdirectory(hello_world_application)
