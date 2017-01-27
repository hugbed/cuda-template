cmake_minimum_required(VERSION 2.8)
find_package(CUDA QUIET REQUIRED)

INCLUDE_DIRECTORIES(
    include
)

CUDA_ADD_LIBRARY(
    simplecuda
    src/init.cu
)
TARGET_LINK_LIBRARIES(simplecuda ${CUDA_LIBRARIES})

ADD_EXECUTABLE(main src/main.cpp)
TARGET_LINK_LIBRARIES(main simplecuda)

