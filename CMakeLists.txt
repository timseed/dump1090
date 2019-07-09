cmake_minimum_required(VERSION 3.14)
project(dump1090)

set(CMAKE_CXX_STANDARD 14)

include_directories("/usr/local/Cellar/librtlsdr/0.6.0/include/"
        "/usr/local/Cellar/libusb/1.0.22/include/libusb-1.0/")

find_library(rtl NAMES librtlsdr HINTS /usr/local/Cellar/librtlsdr/0.6.0/lib)
if (RTL_FOUND)
    include_directories(${RTL_INCLUDE_DIRS})
    target_link_libraries (dumpo1090 ${RTL_LIBRARIES})
endif (RTL_FOUND)

add_executable(dump1090
        anet.c
        anet.h
        dump1090.c dump1090.h)
