# 入门知识

## Unix 程序

* /bin 二进制文件子目录，一般用来保存引导系统用的程序
* /usr/bin 用户级二进制文件子目录，用来保存一般用户使用的标准程序
* /usr/local/bin 本地二进制文件子目录，一般用来保存某种安装情况下的程序
* Unix使用“:”来分隔PATH变量，Dos用“;”

## 库文件
* .a 传统的静态型函数库
* .so .sa 共享型函数库
* cc -o fred fred.c /usr/lib/libm.a # 采用全路径
* cc -o fred fred.c -lm # 简单写法调取的文件是libm.a
* cc -o x11fred -L/usr/openwin/lib x11fred.c -lX11 # L增加路径

* cc -c bill.c fred.c # 编译生成.o文件
* lib.h 文件 void bill(char *) # 声明函数的头文件lib.h
* cc -c program.c # 生成program.o 中间文件
* cc -o program program.o bill.o
* ./program

* Berkley Unix 操作系统需要以下操作
* ar crv libfoo.a bill.o fred.o #生成libfoo.a 编译并使用一个库
* ranlib libfoo.a # 为这个函数库建立一个内容表

* cc -o program program.o -L. -lfoo # 正常编译模式
* nm program libfoo.a # 查看包含fred bill两个函数

## 共享库
* .so 程序运行时加入的 .sa 时加入到可执行文件里去的
* ldd program
