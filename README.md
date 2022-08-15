├── build
├── CMakeLists.txt
├── INCLUDE
│   └── get_time.h
├── main.cpp
└── SOURCE
    └── get_time.cpp
	
1.创建 CMakeLists.txt然后版本，工程名，设置头文件目录，生成可执行文件
2.在main.cpp中点击右边的设置然后g++创建   launch.json tasks.json
3.在launch.json 设置可执行文件目录"program" -->"${wordspaceFolder}/build/get_time
4.在task.json  "options"设置"cwd" 为"${wordspaceFolder}/build"
5.             "presentation"       "pancel":"new"
6.			   "task"   "cmake .."  "make"    "label":BUILD这个名字加到launch的下面
7.f5运行


随笔:   
 新建目录				 mkdir
 新建文件				 touch
 删除					   rm [-rf]
 查看版本号			 	xxx --version 
 查看目录树				tree .
 
 
 g++:	              
 预处理				  g++ -E a.cpp -o a.i
 编译					   g++ -S a.i   -o a.s
 汇编					   g++ -C a.s   -o a.o
 可执行文件				g++    a.o   -o a
 带调试信息				-g
 优化					   -o[0-3]
 指定库文件/库文件路径    -l/-L
 指定头文件搜索目录 	     -I
 打印警告信息				-Wall
 关闭警告信息				-W
 设置编译标准				-std=c++11
 定义宏				   -D[NAME]
 
 GDB调试器相关（vscode）  
 下一步					f10
 进入						 f11
 
 cmake的CMakeLists.txt相关语法
 指定最小版本要求								  cmake_minimum_require
 定义工程名										 project
 定义变量										  set(SRC a.cpp b.cpp)  //${SRC}=a.cpp b.cpp
 向工程添加多个特定的头文件搜索目录（g++ -I）		include_directories
 向工程添加多个特定的库文件搜索目录（g++ -L）		link_directories
 生成库文件									     add_library(name[SHARE|STATIC] SOURCE1 SOURCE2...)
 添加编译参数										add_compile_options(/* -Wall -o2  */)
 生成可执行文件								   add_execulate
 添加需要连接的共享库								 target_link_libraries(可执行文件  库文件)
 
 某例子：
 把当前目录的所有文件定义为SRC                     aux_source_directory(. SRC)             
 生成可执行文件                                    add_executable(main ${SRC})  
 
 cmake流程：   		                            mkdir build
 			                                       cd build 
			                                       cmake ..
			                                       make
		                                     	   ./a
		
