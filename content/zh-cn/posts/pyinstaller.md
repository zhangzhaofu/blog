+++ 
date = "2020-10-23"
title = "pyinstaller使用"
slug = "pyinstaller" 
tags = ["pyinstaller", "python", "cs"]
categories = ["blog"]
+++

## pyinstaller部署pyqt5开发的程序demo
可以查看[hello_pyinstaller](https://github.com/zhangzhaofu/hello_pyinstaller.git)

## 使用python3.8在mac中遇到的问题, TypeError: an integer is required (got type bytes) when compiling any script
解决办法：
```
pip install https://github.com/pyinstaller/pyinstaller/archive/develop.tar.gz
```

## 
Pyinstaller -F setup.py 打包exe
Pyinstaller -F -w setup.py 不带控制台的打包
Pyinstaller -F -i xx.ico setup.py 打包指定exe图标打包
平常我们只需要这三个就好了，足够满足所有需求了。

## pyinstaller -D setup.py 打包成一个文件夹里

## -D和-F选项区别
-F选项应该是对-D选项操作后进行了一次压缩，压缩成了一个单独执行程序，每次启动的时候会比较慢，推荐-D打包方式
