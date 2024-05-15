# clion中使用vcpkg的方法

1. 视图 - 工具 - Vcpkg。点击后vcpkg会在底部左侧显示。
2. 把vcpkg的路径设为c盘，比如C:/vcpkg/scripts/buildsystems/vcpkg.cmake
3. 在CMakeLists.txt中加入set(CMAKE_TOOLCHAIN_FILE "C:/vcpkg/scripts/buildsystems/vcpkg.cmake") 
4. 
