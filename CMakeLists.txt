cmake_minimum_required(VERSION 3.28.3)

set(CMAKE_CXX_VISIBILITY_PRESET hidden)
set(CMAKE_VISIBILITY_INLINES_HIDDEN YES)

project(foo LANGUAGES CXX VERSION 1.0.0)

add_library(foo)
generate_export_header(foo)

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

