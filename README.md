# clion中使用vcpkg的方法

1. 视图 - 工具 - Vcpkg。点击后vcpkg会在底部左侧显示。
2. 把vcpkg的路径设为c盘，比如C:/vcpkg/scripts/buildsystems/vcpkg.cmake
3. 在CMakeLists.txt中加入set(CMAKE_TOOLCHAIN_FILE "C:/vcpkg/scripts/buildsystems/vcpkg.cmake") 
4. 由于MinGW包经常遇到不兼容的问题，所以把编译器设为Visual Studio 
5. 设置CMake选项 -DCMAKE_TOOLCHAIN_FILE="C:/vcpkg/scripts/buildsystems/vcpkg.cmake" 。注意这里必须用反斜杠，正斜杠因为是转义会报错。
6. 使用vcpkg下载软件包选择x64-windows版本。Mingw-dynamic版本可能是兼容性问题总是链接失败。
