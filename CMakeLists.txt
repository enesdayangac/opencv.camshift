cmake_minimum_required (VERSION 2.8)
project (MeanShift)

#where my opencv is
set (path C:/Users/enes/Dst3rdParty_x64_vs11)

#opencv control
set(OpenCV_DIR			"${path}/OpenCV" CACHE PATH "Path to OpenCV directory")

set(OPENCV_COMPONENT_LIST opencv_core opencv_highgui opencv_video opencv_imgproc)
find_package(OpenCV COMPONENTS ${OPENCV_COMPONENT_LIST} REQUIRED)

# add the binary tree to the search path for include files
include_directories(${PROJECT_BINARY_DIR} ${OpenCV_INCLUDE_DIRS})

# add the executable
add_executable (MeanShift
		main.cpp
		MeanShift.cpp
		MeanShift.h
		)

target_link_libraries (MeanShift
		${OpenCV_LIBS}
)




