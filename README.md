本project测试在clion和visual studio中联合使用cmake和vcpkg的方法。这个project既可以在clion中运行，也可以在visual studio中运行。(2024年5月17日)

# clion中使用vcpkg的方法

https://github.com/microsoft/vcpkg

1. 视图 - 工具 - Vcpkg。点击后vcpkg会在底部左侧显示。通过垃圾桶标志可以删除多余的库。
2. 把vcpkg的路径设为c盘，比如C:/vcpkg/scripts/buildsystems/vcpkg.cmake
3. 在CMakeLists.txt中加入set(CMAKE_TOOLCHAIN_FILE "C:/vcpkg/scripts/buildsystems/vcpkg.cmake") 
4. 由于MinGW包经常遇到不兼容的问题，所以把编译器设为Visual Studio 
5. 设置CMake选项 -DCMAKE_TOOLCHAIN_FILE=C:/vcpkg/scripts/buildsystems/vcpkg.cmake 。注意这里必须用反斜杠，正斜杠因为是转义会报错。
6. 使用vcpkg下载软件包选择x64-windows版本。Mingw-dynamic版本可能是兼容性问题总是链接失败。当然，把编译器设置为visual studio后vcpkg下载的判断默认就是x64-windows版了。(2024年5月15日)
7. 果然，clion还是要复制fmtd.dll的（因为在C:\gitcloud\clion-vcpkg-config\cmake-build-debug找到了fmtd.dll文件），只不过clion把这个过程自动化了。(2024年5月17日)

# visual studio中联合使用cmake和vcpkg的方法

1. 在labpc上，vcpkg的环境变量不用专门设置也不影响visual studio跑相关程序。(2024年5月17日)
2. 启动项要选择当前文档CMakeLists.txt才行。(2024年5月17日)
3. 在labpc上，set(CMAKE_PREFIX_PATH "C:/vcpkg/packages")并不是必需的。(2024年5月17日)

