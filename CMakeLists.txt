cmake_minimum_required(VERSION 3.28)
project(clion_vs_vcpkg_config)

# 设置 C++ 标准
set(CMAKE_CXX_STANDARD 17)

# 设置 vcpkg 的工具链文件路径
set(CMAKE_TOOLCHAIN_FILE "C:/vcpkg/scripts/buildsystems/vcpkg.cmake")
set(CMAKE_PREFIX_PATH "C:/vcpkg/packages")


# 添加可执行文件
add_executable(clion_vs_vcpkg_config learn.cpp)

# 查找并链接 fmt 库
find_package(fmt CONFIG REQUIRED)
target_link_libraries(clion_vs_vcpkg_config PRIVATE fmt::fmt)


