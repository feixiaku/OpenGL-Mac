cmake_minimum_required(VERSION 2.8.0)

project(helloOpenGL)

include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${CMAKE_SOURCE_DIR}/thirdParty/glad/include)

SET(SRC_LIST main.cpp ./thirdParty/glad/src/glad.c)

add_executable(helloOpenGL ${SRC_LIST})

SET(GLFW_BUILD_EXAMPLES OFF)
SET(GLFW_BUILD_TESTS OFF)
SET(GLFW_BUILD_DOCS OFF)
SET(GLFW_INSTALL OFF)

add_subdirectory(thirdParty/glfw)
target_link_libraries(helloOpenGL glfw)

find_package(OpenGL REQUIRED)
if(OPENGL_FOUND)
    target_include_directories(helloOpenGL PUBLIC ${OPENGL_INCLUDE_DIR})
    target_link_libraries(helloOpenGL ${OPENGL_gl_LIBRARY})
endif(OPENGL_FOUND)

find_package(OpenCV REQUIRED)
if(OpenCV_FOUND)
    message("opencv found")
    message(${OpenCV_INCLUDE_DIRS})
    #message(${OpenCV_LIBRARIRES})
endif(OpenCV_FOUND)
