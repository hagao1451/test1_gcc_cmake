project(test1_gcc_cmake)

cmake_minimum_required(VERSION 3.24)

# 这里生成动态库后还是要手动复制一下到项目中
add_subdirectory(test1_hello)

set(MAIN_PROGRAM MainProgram)

# 包含所需头文件
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/test1_hello)

# 设置链接库的路径
link_libraries(${CMAKE_CURRENT_SOURCE_DIR}/dll)

# 直接编译源文件是可以的
add_executable(${MAIN_PROGRAM} main.cpp)

#target_include_directories(${MAIN_PROGRAM} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/test1_hello)

# 链接静态库成功，但链接动态库还有路径问题，待解决
target_link_libraries(${MAIN_PROGRAM} testHello)