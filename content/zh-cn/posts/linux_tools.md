+++ 
date = "2022-02-11"
title = "Linux工具"
slug = "linux_tools" 
tags = ["tools", "linux"]
categories = ["blog"]
+++

## Linux工具

## 安装语言
```
sudo dpkg-reconfigure locales
```

## 安装google拼音输入法
```
sudo apt install fcitx-googlepinyin
```

## 调整时区
```
#!/bin/bash 
echo "change timezone to Asia/Shanghai (UTC)"
sudo timedatectl set-timezone "Asia/Shanghai"	#修改时区为上海
 
sudo timedatectl set-timezone UTC	#使用和设置协调世界时间
sudo timedatectl set-local-rtc 0	#将硬件时钟设置为协调世界时（UTC）
 
echo "restart ntp for update localtime,please wait 10s" 
sudo service ntp restart	#重启ntp时间同步服务，等待时间更新，一般需要3~6秒
sleep 10s
 
echo "change Hardware clock"
sudo hwclock -w	#将系统时间写入到硬件时钟，防止重启系统后更改失效
 
sudo timedatectl status
echo "Everything is OK! Please Restart system"
```

## 常用的工具
zsh, oh my zsh
tmux
vim
git
curl
wget
syncthing
openvpn
firefox vim
gcc, gdb
python
go
qt

## 查看桌面管理器
```
cat /etc/X11/default-display-manager
```

## 切换桌面管理器
```
sudo dpkg-reconfigure gdm (如果安装了gdm)
```

### 获取公网IP
```
curl ip.sb
```

### grep 在当前目录下查找包含PyQt内容的文件
```
grep -rn PyQt .
```
