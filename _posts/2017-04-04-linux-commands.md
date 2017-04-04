---
layout: post
title: Linux commands
tags: 
- Shell Study
---
Useful linux commands and examples.

### ls(list)，查看当前位置都有哪些文件(夹)。
```shell
cricode@ubuntu:~$ ls
Desktop  music  mydocs  python
```
### pwd(print work directory), 查看你所处的位置.

```shell
cricode@ubuntu:~$ pwd
/home/cricode
```

### mkdir, 创建一个目录(文件夹)

```shell
cricode@ubuntu:~$ mkdir cprogram
cricode@ubuntu:~$ ls
cprogram  Desktop  music  mydocs  python
```


### cd, 切换目录(路径)

```shell
cricode@ubuntu:~$ cd cprogram/
cricode@ubuntu:~/cprogram$ 
```
### touch, 创建文件

```shell
cricode@ubuntu:~/cprogram$ touch hello.c
cricode@ubuntu:~/cprogram$ ls
hello.c
```

### vim, 编辑文件

```shell
cricode@ubuntu:~/cprogram$ vim hello2.c
```
### cat, 查看文件内容

```shell
cricode@ubuntu:~/cprogram$ cat hello.c 
# include <stdio.h>
int main()
{
    printf("hello,world!\nwelcome to cricode.com\n");
}
```
### cd -，退到上一次所处的位置

```shell
Blog git:(master) cd -
~/Github/Blog/images

images git:(master) cd -
~/Github/Blog
```
### cd ..，退到上一级位置

```shell
images git:(master) cd ..
Blog git:(master) 
```

### rm -r, 删除文件夹及其文件夹下的所有文件

``` shell
cricode@ubuntu:~$ ls
cprogram  Desktop  music  mydocs  python
cricode@ubuntu:~$ rm -r cprogram/
cricode@ubuntu:~$ ls
Desktop  music  mydocs  python
```
### 其他：
* ifconfig：配置IP地址，默认网关地址等

* man：操作手册，例如:man ifconfig,便可查看ifconfig命令的具体用法

* find：查找文件

* grep：搜索指定文件中包含给定字符串或者单词的行，相当有用的一个命令

* df：查看磁盘的使用情况

* ps ：查看进程状态

* top：查看进程cpu、内存占用情况

* ping：检查网络连通性



**77 Linux commands and utilities you'll actually use**
<http://searchenterpriselinux.techtarget.com/tutorial/77-useful-Linux-commands-and-utilities>