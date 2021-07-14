+++ 
date = "2021-07-14"
title = "ROS"
slug = "ros" 
tags = ["ros", "emb", "cs"]
categories = ["blog"]
+++

## ROS

张新宇老师的专栏《机器人操作系统ROS--史话36篇》

http://wiki.ros.org/cn/ROS/Tutorials
https://answers.ros.org/questions/
http://lists.ros.org/lurker/list/ros-users.en.html

https://github.com/ros

### catkin
#### 
```
mkdir -p catkin_ws/src
```

#### 
```
cd catkin_ws/src
catkin_init_workspace
```

#### 
```
catkin_create_pkg test_pkg
```

test_pkg中
    include/    头文件
    src/        源文件
    node/       用于rospy的脚本
    launch/     用于roslaunch的启动文件
    msg/        消息文件
    srv/        服务文件

#### 
```
cd catkin_ws
catkin_make
```

#### 
```
source ~/catkin_ws/devel/setup.bash
```
