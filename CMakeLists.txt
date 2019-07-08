cmake_minimum_required(VERSION 3.14)
project(dump1090)

set(CMAKE_CXX_STANDARD 14)

include_directories("/usr/local/Cellar/librtlsdr/0.6.0/include/",
        "/usr/local/Cellar/libusb/1.0.22/include/libusb-1.0/")

add_executable(dump1090
        anet.c
        anet.h
        dump1090.c)
