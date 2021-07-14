+++ 
date = "2020-10-28"
title = "Raspberry"
slug = "raspberry" 
tags = ["raspberry", "emb", "cs"]
categories = ["blog"]
+++

## 初始设置
用户名: pi
密码:   raspberry

## 查看型号
```
cat /proc/device-tree/model
我的查出来的结果是Raspberry Pi 3 Model B Rev 1.2
```

## 查看32位还是64位
```
getconf LONG_BIT
```

## 配置树莓派
```
很多配置可以进入 sudo raspi-config, 进行配置
```

## 添加wifi
```
vi /etc/wpa_supplicant/wpa_supplicant.conf

network={
        ssid="CU_6USt"
        psk="6ust1qyd"
        key_mgmt=WPA-PSK
        priority=1
}
```

## 设置git服务器
```
添加git用户
sudo useradd git
cd /home
sudo mkdir git
sudo chown git:git git
sudo password git

git仓库
git的家目录里,ssh-keygen
cd .ssh
vi authorized_keys, 添加其他电脑的~/.ssh/id_rsa.pub里的内容
cd ~git
mkdir test.git
cd test.git
git init --bare

其他电脑clone
git clone git@192.168.1.106:test.git
```
