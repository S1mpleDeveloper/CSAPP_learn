时间	    任务	                       说明	
0:00-0:10	安装 WSL2 + Ubuntu 22.04	   打开 PowerShell（管理员），执行：`wsl --install -d Ubuntu-22.04`	
0:10-0:20	初始化 Ubuntu 用户	            设用户名 `csapp`，密码 `123456`（简单好记）	
0:20-0:30	换国内源 + 更新	                执行：`sudo sed -i 's@http://.*.ubuntu.com@https://mirrors.tuna.tsinghua.edu.cn@g' /etc/apt/sources.list``sudo apt update && sudo apt upgrade -y`	
0:30-0:40	安装开发工具链	                执行：`sudo apt install -y build-essential gdb make git vim cmake`	
0:40-0:50	安装 VSCode + 插件	            1. 从官网装 VSCode（Windows版）2. 装插件：Remote-WSL、C/C++、CodeLLDB	
0:50-1:00	创建项目目录	                在 Ubuntu 终端：`mkdir -p ~/csapp-6-month/01-day1 && cd ~/csapp-6-month/01-day1`	
1:00-1:20	写第一个 C 程序	                文件 `hello.c`：#include <stdio.h>int main() {    printf("Hello CSAPP, from Windows!\n");    return 0;}	
1:20-1:30	写 Makefile	                   文件 `Makefile`：CC=gccCFLAGS=-Wall -ghello: hello.c	(CC) (CFLAGS) -o hello hello.cclean:	rm -f hello	
1:30-1:40	编译 + 运行	                    终端执行：`make``./hello`	
1:40-1:50	GDB 调试	                    终端执行：`gdb ./hello`在 gdb 里输入：`break main``run``next``print "OK"`	
1:50-2:00	提交到 GitHub	                 1. 先在 GitHub 新建空仓库 `csapp-6-month`2. 本地：`git init``git add .``git commit -m "day1: hello world + Makefile + gdb"``git branch -M main``git remote add origin https://github.com/<你的用户名>/csapp-6-month.git``git push -u origin main`	
