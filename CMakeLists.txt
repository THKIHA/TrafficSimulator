cmake_minimum_required(VERSION 3.12)
project(TrafficSimulator)

set(CMAKE_CXX_STANDARD 17)

add_executable(TrafficSimulator main.cpp Systems/Render.cpp Systems/Render.h Systems/System.cpp Systems/System.h Components/Component.cpp Components/Component.h Components/TestComponent1.cpp Components/TestComponent1.h Components/TestComponent2.cpp Components/TestComponent2.h Components/ComponentUtility.cpp Components/ComponentUtility.h Entities/Entity.cpp Entities/Entity.h Managers/World.cpp Managers/World.h)

find_package(OpenGL REQUIRED)
#find_package(GLUT REQUIRED) # Disable when GLUT is not installed, only need for OpenGL code
include_directories( ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} )

target_link_libraries(TrafficSimulator ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} )