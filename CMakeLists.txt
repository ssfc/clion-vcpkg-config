cmake_minimum_required(VERSION 3.28)
project(vkpkg)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 17)

# 设置 vcpkg 的工具链文件路径
set(CMAKE_TOOLCHAIN_FILE "${CMAKE_SOURCE_DIR}/vcpkg/scripts/buildsystems/vcpkg.cmake")

# 添加可执行文件
add_executable(vkpkg learn.cpp)

# 查找并链接 fmt 库
find_package(fmt CONFIG REQUIRED)
target_link_libraries(vkpkg PRIVATE fmt::fmt)


