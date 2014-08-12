cmake_minimum_required (VERSION 2.6) 
project (Demo) 

list(APPEND CMAKE_INCLUDE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib/cxxtest-4.4) 
list(APPEND CMAKE_PROGRAM_PATH ${CMAKE_CURRENT_SOURCE_DIR}/lib/cxxtest-4.4/bin) 

find_package(PythonInterp QUIET)
if(PYTHONINTERP_FOUND)
  message("Python located")
else()
  message(FATAL_ERROR "Python interpreter cannot be located.")
endif()

add_subdirectory(src)
add_subdirectory(test)

