---
layout: post
title: Linux commands
tags: 
- Shell Study
---
Useful linux commands and examples.

### ls(list)，List files
```shell
cricode@ubuntu:~$ ls
Desktop  music  mydocs  python
```
### pwd(print work directory), Show current directory

```shell
cricode@ubuntu:~$ pwd
/home/cricode
```

### mkdir, Make directory dir

```shell
cricode@ubuntu:~$ mkdir cprogram
cricode@ubuntu:~$ ls
cprogram  Desktop  music  mydocs  python
```


### cd, Switch directory (path)

```shell
cricode@ubuntu:~$ cd cprogram/
cricode@ubuntu:~/cprogram$ 
```
### touch, Create file

```shell
cricode@ubuntu:~/cprogram$ touch hello.c
cricode@ubuntu:~/cprogram$ ls
hello.c
```

### vim, edit file

```shell
cricode@ubuntu:~/cprogram$ vim hello2.c
```
### cat, output

```shell
cricode@ubuntu:~/cprogram$ cat hello.c 
# include <stdio.h>
int main()
{
    printf("hello,world!\nwelcome to cricode.com\n");
}
```
### cd -，Go back to last location

```shell
Blog git:(master) cd -
~/Github/Blog/images

images git:(master) cd -
~/Github/Blog
```
### cd ..，Go up a directory

```shell
images git:(master) cd ..
Blog git:(master) 
```

### rm -r, Delete file and everything under it

``` shell
cricode@ubuntu:~$ ls
cprogram  Desktop  music  mydocs  python
cricode@ubuntu:~$ rm -r cprogram/
cricode@ubuntu:~$ ls
Desktop  music  mydocs  python
```
### Others：
* ifconfig：Configure the IP address, the default gateway address, and so on

* man：Manual, for example: man ifconfig, you can view the specific usage of the ifconfig command

* find：Find file

* grep：Search for a command that contains a given string or word line, a useful command

* df：View the usage of the disk

* ps ：View the status of the process

* top：View the process of cpu, memory usage

* ping：Check network connectivity



**77 Linux commands and utilities you'll actually use**
<http://searchenterpriselinux.techtarget.com/tutorial/77-useful-Linux-commands-and-utilities>