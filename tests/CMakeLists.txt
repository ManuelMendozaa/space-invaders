include(FetchContent)

FetchContent_Declare(
    googletest
    GIT_REPOSITORY https://github.com/google/googletest.git
    GIT_TAG v1.17.0
)

FetchContent_MakeAvailable(googletest)

add_executable(src_tests
    sample.test.cpp
)

target_link_libraries(src_tests
    PRIVATE
        GTest::gtest_main
        src
)

include(GoogleTest)
gtest_discover_tests(src_tests)
