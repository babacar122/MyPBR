# CMakeList.txt : CMake project for MyPBR, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Enable Hot Reload for MSVC compilers if supported.
if (POLICY CMP0141)
  cmake_policy(SET CMP0141 NEW)
  set(CMAKE_MSVC_DEBUG_INFORMATION_FORMAT "$<IF:$<AND:$<C_COMPILER_ID:MSVC>,$<CXX_COMPILER_ID:MSVC>>,$<$<CONFIG:Debug,RelWithDebInfo>:EditAndContinue>,$<$<CONFIG:Debug,RelWithDebInfo>:ProgramDatabase>>")
endif()

include_directories("E:\\Libs\\include")
link_libraries("E:\\Libs\\libs\\glfw3.lib" "opengl32.lib" "kernel32.lib")

project ("MyPBR")

# Add source to this project's executable.
add_executable (MyPBR "MyPBR.cpp" "MyPBR.h" "glad.c")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET MyPBR PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
