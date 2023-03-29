cmake_minimum_required(VERSION 2.8)
project(CmakePro)

set(SOURCES
    main.cpp
)
 
set(HEADERS
    main.h
)
 
add_executable(CmakePro
    ${SOURCES}
    ${HEADERS}
)

SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR}/bin)

set(OpenCV_DIR "E:/opencv/OpenCV-MinGW-Build-OpenCV-4.5.5-x64/x64/mingw/lib")
find_package(OpenCV REQUIRED)
if(OpenCV_FOUND)
    target_include_directories(CmakePro PUBLIC ${OpenCV_INCLUDE_DIRS})
    target_link_libraries(CmakePro ${OpenCV_LIBS})
 
endif()