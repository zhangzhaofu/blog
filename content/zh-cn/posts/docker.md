+++ 
date = "2020-11-06"
title = "Docker"
slug = "docker" 
tags = ["docker", "tool", "cs"]
categories = ["blog"]
+++

# Docker

## Install
```
sudo apt install docker.io
```

## Get Ubuntu16.04 image
```
sudo docker pull ubuntu:16.04
```

## Start ubuntu16.04 and make /home/zhangzf/Workspace to docker's /Workspace
```
sudo docker run -it -v /home/zhangzf/Workspace:/Workspace ubuntu:16.04 /bin/bash
```

## Create user: 'zhangzf'

## Install sudo, make 'zhangzf' into sudoer

## su - zhangzf

## 查看所有的容器
```
sudo docker container ls -a
```

## 运行一个已有的容器
```
sudo docker start 81414ed72371
sudo docker attach 81414ed72371
```

## 把容器打包成镜像
```
 sudo docker commit 81414ed72371 hoba-desktop:init
```

## 查看已有的镜像
```
sudo docker image ls
```

## Docker Hub
```
my id is doubledog
```

## change tag
```
sudo docker tag hoba-desktop:init doubledog/hoba-desktop:init
```

## 登陆自己的docker hub
```
sudo docker login
```

## push
```
sudo docker push doubledog/hoba-desktop:init
```

## 清理
```
docker system df
docker system prune -a
```
