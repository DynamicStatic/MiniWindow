
# CMake configuration for MiniRenderer
cmake_minimum_required(VERSION 3.2)
project(MiniRenderer)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14")
set_property(GLOBAL PROPERTY USE_FOLDERS ON)

set(includePath "${CMAKE_CURRENT_SOURCE_DIR}/include/")
set(includeFiles
    ${includePath}/MiniDefines.hpp
    ${includePath}/MiniGLM.hpp
    ${includePath}/MiniGLM_ex.hpp
    ${includePath}/MiniImage.hpp
    ${includePath}/MiniPgm.hpp
    ${includePath}/MiniRenderer.hpp
    ${includePath}/MiniWindow.hpp
)

macro(create_example target)
    add_executable(${target} ${includeFiles} ${CMAKE_CURRENT_SOURCE_DIR}/examples/${target}.cpp)
    target_include_directories(${target} PUBLIC "${includePath}")
endmacro()

create_example(BlockBuilding)
create_example(BlockBuilding.Golfed)
create_example(Cube)
create_example(GaussianDistribution3D)
create_example(ImgToPgm)
create_example(Mandelbrot)
