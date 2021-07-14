+++ 
date = "2020-11-10"
title = "nmap"
slug = "nmap" 
tags = ["nmap", "tools", "cs"]
categories = ["blog"]
+++

## nmap
```
brew install nmap
```

## 查看远程机器47.102.112.2的端口号
```
nmap -v -p 1-65535 -sV -O -sS -T4 47.102.112.2
```
