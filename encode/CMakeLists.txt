# CMakeList.txt: avstream_checker 的 CMake 项目，在此处包括源代码并定义
# 项目特定的逻辑。
#
cmake_minimum_required (VERSION 3.8)

project ("encode")

set(FFMPEG_DIR "D:/msys64/home/code/FFmpeg-n7.0.1/build_out")
set(FFMPEG_LIB_DIR ${FFMPEG_DIR}/bin)

include_directories(
	${FFMPEG_DIR}/include
)

# 将源代码添加到此项目的可执行文件。
add_executable (${PROJECT_NAME} 
	"encode.cpp" 
	"encode.h"
)

target_link_libraries(${PROJECT_NAME} 
	PRIVATE
	${FFMPEG_LIB_DIR}/avdevice.lib
	${FFMPEG_LIB_DIR}/avformat.lib
	${FFMPEG_LIB_DIR}/postproc.lib
	${FFMPEG_LIB_DIR}/swresample.lib
	${FFMPEG_LIB_DIR}/swscale.lib
	${FFMPEG_LIB_DIR}/avfilter.lib
	${FFMPEG_LIB_DIR}/avcodec.lib
	${FFMPEG_LIB_DIR}/avutil.lib
)