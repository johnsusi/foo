cmake_minimum_required(VERSION 3.28.3)

project(foo LANGUAGES CXX VERSION 1.0.0)

add_library(foo)

target_compile_features(foo PUBLIC cxx_std_20)

target_sources(foo
    PRIVATE
        foo/foo.cpp        
    PUBLIC
        FILE_SET HEADERS
        BASE_DIRS .
        FILES
            foo/foo.h
)

