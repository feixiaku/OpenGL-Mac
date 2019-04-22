
SET(SRC_LIST main.cpp ../thirdParty/glad/src/glad.c)
add_executable(helloGLFW ${SRC_LIST})

target_link_libraries(helloGLFW glfw)

find_package(OpenGL REQUIRED)
if(OPENGL_FOUND)
    target_include_directories(helloGLFW PUBLIC ${OPENGL_INCLUDE_DIR})
    target_link_libraries(helloGLFW ${OPENGL_gl_LIBRARY})
endif(OPENGL_FOUND)

