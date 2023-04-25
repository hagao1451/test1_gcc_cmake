# 设置库的输出路径
set(LIBRARY_OUTPUT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/../dll)

# 生成静态库
add_library(testHello STATIC Test1_hello.cpp Test1_hello.h)

# 生成动态库
#add_library(testHello SHARED Test1_hello.cpp Test1_hello.h)