cmake_minimum_required(VERSION 2.8.0)

project(helloOpenGL)

include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${CMAKE_SOURCE_DIR}/thirdParty/glad/include)

SET(GLFW_BUILD_EXAMPLES OFF)
SET(GLFW_BUILD_TESTS OFF)
SET(GLFW_BUILD_DOCS OFF)
SET(GLFW_INSTALL OFF)

add_subdirectory(thirdParty/glfw)

#application
add_subdirectory(ex01)
