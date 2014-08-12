Set(CXXTEST_USE_PYTHON TRUE)
find_package(CxxTest)
if(CXXTEST_FOUND)
    include_directories(${CXXTEST_INCLUDE_DIR})
    enable_testing()
    CXXTEST_ADD_TEST(unittest_demo demo_test.cpp
                      ${CMAKE_CURRENT_SOURCE_DIR}/demo_test.h)
    #target_link_libraries(unittest_demo foo) # as needed
else()
  message(FATAL_ERROR "CxxTest cannot be found.")
endif()