project(test1_gcc_cmake)

# 这里生成动态库后还是要手动复制一下到项目中
add_subdirectory(test1_hello)

set(MAIN_PROGRAM MainProgram)

include_directories(./test1_hello)

# 直接编译源文件是可以的
add_executable(MAIN_PROGRAM main.cpp ./test1_hello/Test1_hello.cpp)

# 链接动态库还有路径问题，待解决
#target_link_libraries(MAIN_PROGRAM testHello)