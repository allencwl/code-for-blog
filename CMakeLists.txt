cmake_minimum_required (VERSION 2.8)

project(code-for-blog)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g -std=c++11 -Wall")

find_package(Boost COMPONENTS system REQUIRED)
find_package(Threads REQUIRED)

set(SUBDIRS
    grpc_dynamic_thread_pool
    boost_coroutine
    boost_asio_coroutine
    boost_asio
    jsonschema
    gflags
    glog
    googletest
)

foreach(dir ${SUBDIRS})
    add_subdirectory(${dir})
endforeach()

enable_testing()
