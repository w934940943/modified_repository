project (pupiltracker)
cmake_minimum_required(VERSION 2.8)

#set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake")
set(CMAKE_DEBUG_POSTFIX "d")

set(OpenCV_DIR "D:/opencv-3.4.1/build/install")

set(Boost_INCLUDE_DIRS  "D:/boost_1_62_0")
set(BOOST_LIBRARYDIR "D:/boost_1_62_0/lib64-msvc-14.0")
set(BOOST_ROOT "D:/boost_1_62_0/boost")

set(TBB_INCLUDE_DIRS  "D:/tbb2018_20180822oss/include")
set(TBB_LIBRARIES "D:/tbb2018_20180822oss/lib/intel64/vc14")


if (NOT MSVC)
    if (${CMAKE_CXX_COMPILER_ID} STREQUAL "GNU")
        execute_process(COMMAND ${CMAKE_CXX_COMPILER} -dumpversion OUTPUT_VARIABLE GCC_VERSION)
        if (GCC_VERSION VERSION_LESS 4.7)
            set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++0x")
        else ()
            set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
        endif ()
    else ()
        set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
    endif ()
endif ()

add_subdirectory (lib)
add_subdirectory (cmd)
