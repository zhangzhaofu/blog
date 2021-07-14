+++ 
date = "2020-10-26"
title = "Go学习"
slug = "go" 
tags = ["go", "lang", "cs"]
categories = ["blog"]
+++

# Go学习

## 设置国内代理
vi ~/.zshrc
export GO111MODULE=on
export GOPROXY="https://goproxy.cn,direct"

测试是否安装成功:
time go get golang.org/x/tour

## Go学习资料

[c语言编程网](http://c.biancheng.net/golang/)
[Go语言中文网](https://books.studygolang.com/)
[Go语言圣经](https://books.studygolang.com/gopl-zh/)
[Go语言高级编程](https://chai2010.cn/advanced-go-programming-book/)
[李文周的博客](https://www.liwenzhou.com/posts/Go/go_menu/)
[Go语言101](https://gfw.go101.org/article/101.html)
[Go语言设计与实现](https://draveness.me/golang/)
[Go语言原本](https://golang.design/under-the-hood/zh-cn/part1basic/)

## 帮助文档
go help aSubCommand
go doc fmt.Printf
godoc -http=localhost:6060

## 编译go源码
```
./src/make.bash
```

## 编译运行程序
```
go run .
```

## go子命令 (运行不带参数的go命令将会列出所有支持的go子命令)
go run
go build
go install
go fmt
go test
go doc
go mod
