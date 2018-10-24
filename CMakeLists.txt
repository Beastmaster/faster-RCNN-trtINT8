


cmake_minimum_required(VERSION 2.8)
project (fasterRCNN)
file (GLOB _INCS "*.h")
file (GLOB _SRCS "*.cpp" "*.cu")
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

# CUDA
find_package (CUDA)
include_directories (${CUDA_INCLUDE_DIRS})
message (STATUS "CUDA_INCLUDE_DIRS: ${CUDA_INCLUDE_DIRS}")
link_directories(${CUDA_TOOLKIT_ROOT_DIR}/lib64/)
find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )
set(TensorRT_ROOT $ENV{TensorRT_ROOT})
include_directories(${TensorRT_ROOT}/include/)
link_directories(${TensorRT_ROOT}/lib/)
add_executable( fasterRCNN ${_SRCS} )
target_link_libraries( fasterRCNN ${OpenCV_LIBS} nvparsers nvinfer nvinfer_plugin cudnn cuda cudart cublas ${OpenCV_LIBS} )





