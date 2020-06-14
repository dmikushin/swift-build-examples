cmake_minimum_required(VERSION 3.15.1)
  
project(SwiftDemo LANGUAGES C Swift)

# place all modules into `swift` in the root of the build tree
set(CMAKE_Swift_MODULE_DIRECTORY ${CMAKE_BINARY_DIR}/swift)

add_library(Foo SHARED foo.swift)
set_target_properties(Foo PROPERTIES Swift_LANGUAGE_VERSION 4.2)

add_executable(Interop main.c)
target_link_libraries(Interop Foo)

