# cannot find IGL
在ubuntu上装了相同版本的Qt库及creator后，打开从windows复制过来的工程，编译，提示"cannot find IGL",在百度尝试后，利用sudo apt-get install libgl1-mesa-dev命令安装了opengl的库，之后顺利通过编译，运行。   参考帖传送门

原因总结：因为目前图形库主要有两种（说错了请指正）：DirectX和OpenGL。 在Qt官网下载的安装包中并不包含opengl的库，在电脑上安装后世界上只有Qt库和opengl的头文件（应该有），所以需要我们自己独立安装opengl库。而在windows下底层绘图应该使用的是DirectX。