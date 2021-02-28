+++ 
date = "2021-02-21"
title = "Go代理"
slug = "go" 
tags = ["go"]
categories = ["go"]
+++

## 设置国内代理
vi ~/.zshrc
export GO111MODULE=on
export GOPROXY="https://goproxy.cn,direct"

测试是否安装成功:
time go get golang.org/x/tour
