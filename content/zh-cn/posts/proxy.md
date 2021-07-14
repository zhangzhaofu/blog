+++ 
date = "2020-11-06"
title = "命令行代理"
slug = "proxy" 
tags = ["proxy", "tools"]
categories = ["blog"]
+++

# 翻墙
- 购买VPS, 安装openvpn
- 购买收费vpn, ExpressVPN, Lantern
- 使用免费vpn, Lantern, 无界, 赛风

## 命令行代理
```
export http_proxy="http://127.0.0.1:64678"
export https_proxy="http://127.0.0.1:64678"

export http_proxy=""
export https_proxy=""

alias sethttpproxy='export http_proxy="http://127.0.0.1:64678" && export https_proxy="http://127.0.0.1:64678"'
alias unsethttpproxy='export http_proxy="" && export https_proxy=""'
```
