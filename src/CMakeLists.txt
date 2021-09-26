cmake_minimum_required(VERSION 3.10.2)
project(smartphone-webserver-template)

set(CMAKE_CXX_STANDARD 11)
SET(CMAKE_LINKER armlink)
SET(CMAKE_C_LINK_EXECUTABLE armlink)

add_library(
        mongoose STATIC
        libs/mongoose/mongoose.h
        libs/mongoose/mongoose.c
)

add_executable(mongoose-webserver
        main.cpp
        )

target_link_libraries(mongoose-webserver
        PRIVATE
        mongoose
        )