set(BIN_NAME onedof)

find_package(glfw3 REQUIRED)
#include_directories(${GLFW_INCLUDE_DIRS})
#link_libraries(${GLFW_LIBRARY_DIRS})

# find_package(GLEW REQUIRED)
# include_directories(${GLEW_INCLUDE_DIRS})


add_executable(${BIN_NAME} ${BIN_NAME}.cpp)
link_directories(${MUJOCO_PY_MJPRO_PATH}/bin/)
target_link_libraries(${BIN_NAME} ${LIB_MUJOCO})

#Standard libraries for GL
target_link_libraries(${BIN_NAME} "-framework OpenGL" )

#Additional libraries from mujoco package
target_link_libraries(${BIN_NAME} ${GLEW_LIBRARIES} libglfw.3.dylib)
