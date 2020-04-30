# Copyright 2020 Heath Stewart.
# Licensed under the MIT License. See LICENSE.txt in the project root for license information.

cmake_minimum_required(VERSION 3.9)
project(Aziz)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

# vcpkg install cpprestsdk cpprestsdk:x64-windows
find_package(cpprestsdk REQUIRED)

add_executable(Aziz WIN32 src/aziz.cpp)
target_compile_definitions(Aziz PRIVATE UNICODE _UNICODE)
target_precompile_headers(Aziz PRIVATE src/precomp.h)
target_link_libraries(Aziz PRIVATE cpprestsdk::cpprest)

# TODO: Add tests and install targets if needed.
