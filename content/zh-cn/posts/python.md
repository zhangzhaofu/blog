+++ 
date = "2020-11-04"
title = "Python教程"
slug = "python" 
tags = ["python", "lang", "cs"]
categories = ["blog"]
+++

Ubuntu20.04默认安装的是3.8.2

## 升级Python
```
sudo apt upgrade python3
```

## 安装virtualenv
```
sudo apt install virtualenv
```

## env
```
python3 -m venv env
source env/bin/activate
```

## 国内源
```
mkdir $HOME/.pip
vi $HOME/.pip/pip.conf
[global]                                                                    index-url = http://mirrors.aliyun.com/pypi/simple/                              [install]                                                                       trusted-host=mirrors.aliyun.com
```

## requirements.txt
```
pip install -r requirements.txt

遇到没有Python.h这个文件报错时
sudo apt-get install python-dev
```

## 运行run_pypay.py
```
报错信息：
starting pypay ...
qt.qpa.plugin: Could not load the Qt platform plugin "xcb" in "" even though it was found.
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.

Available platform plugins are: eglfs, linuxfb, minimal, minimalegl, offscreen, vnc, wayland-egl, wayland, wayland-xcomposite-egl, wayland-xcomposite-glx, webgl, xcb.

设置export QT_DEBUG_PLUGINS=1，重新启动看详细报错
Got keys from plugin meta data ("xcb")
QFactoryLoader::QFactoryLoader() checking directory path "/usr/bin/platforms" ...
Cannot load library /home/zhangzf/Workspace/pypay/env/lib/python3.8/site-packages/PyQt5/Qt/plugins/platforms/libqxcb.so: (libxcb-xinerama.so.0: cannot open shared object file: No such file or directory)
QLibraryPrivate::loadPlugin failed on "/home/zhangzf/Workspace/pypay/env/lib/python3.8/site-packages/PyQt5/Qt/plugins/platforms/libqxcb.so" : "Cannot load library /home/zhangzf/Workspace/pypay/env/lib/python3.8/site-packages/PyQt5/Qt/plugins/platforms/libqxcb.so: (libxcb-xinerama.so.0: cannot open shared object file: No such file or directory)"
qt.qpa.plugin: Could not load the Qt platform plugin "xcb" in "" even though it was found.
This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem.

Available platform plugins are: eglfs, linuxfb, minimal, minimalegl, offscreen, vnc, wayland-egl, wayland, wayland-xcomposite-egl, wayland-xcomposite-glx, webgl, xcb.

Aborted (core dumped)

安装libxcb-xinerama库
sudo apt install libxcb-xinerama0

```

## 退出env
```
deactivate
```


# Python报错

## sudo apt update也有报错ModuleNotFoundError: No module named 'apt_pkg'

解决方法 /usr/lib/python3/dist-packages# sudo cp apt_pkg.cpython-35m-x86_64-linux-gnu.so apt_pkg.so


## Python.h头文件找不到
```
sudo apt install python3-dev
```
