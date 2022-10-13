cmake_minimum_required(VERSION 3.10)

# set the project name
project(Pong)

add_subdirectory(deps/glfw)
add_subdirectory(deps/glad)
add_subdirectory(deps/glm)

# add the executable
add_executable(Pong src/main.cpp)

#add glfw and glad to project
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

find_package(OpenGL REQUIRED)

target_link_libraries(Pong PUBLIC glfw glad glm OpenGL::GL)