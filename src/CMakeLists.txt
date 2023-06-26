set(LIBRARY_NAME faker)

set(SOURCES
        Generator.cpp
        )

set(UT_SOURCES
        GeneratorTest.cpp
        )

add_library(${LIBRARY_NAME} ${SOURCES})

add_executable(${LIBRARY_NAME}UT ${SOURCES} ${UT_SOURCES})

target_link_libraries(${LIBRARY_NAME}UT PRIVATE
        GTest::gtest_main
        )

target_include_directories(${LIBRARY_NAME}UT
        PRIVATE
        ${Boost_INCLUDE_DIR}
        ${GTEST_INCLUDE_DIR}
        )

add_test(NAME ${LIBRARY_NAME}UT COMMAND ${LIBRARY_NAME}UT WORKING_DIRECTORY ${CMAKE_CURRENT_LIST_DIR})