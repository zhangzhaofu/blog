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




## 下载安装
```
wget golang.google.cn/dl/go1.16.linux-amd64.tar.gz
tar -xvf go1.16.linux-amd64.tar.gz -C /usr/local/
```

## 设置PATH及GOPATH
```
export PATH=/usr/local/go/bin:$PATH
export GOPATH=$HOME/go
```

## 设置国内代理
```
go env -w GO111MODULE=on
go env -w GOPROXY=https://goproxy.cn,direct
time go get golang.org/x/tour
```

## go tour
通过tour来学习go语言
```
go get golang.org/x/tour
cd $GOPATH/pkg/mod/tour
tour
```






比较全的基础
    http://www.topgoer.com/

https://studygolang.com/books

## 书籍
《The Way To Go》 - Go语言百科全书
《Go 101》 - Go语言规范全方位解读
《Go语言实战》 - 实战系列(in action)经典之作，紧扣Go语言的精华

[Go语言学习笔记](https://studygolang.com/book/33)
[Go语言圣经](https://books.studygolang.com/gopl-zh/) (也叫Go语言程序设计)
[Go语言高级编程](https://chai2010.cn/advanced-go-programming-book/)
[Go语言标准库](https://studygolang.com/book/34)

[Go语言学习之路](https://www.liwenzhou.com/posts/Go/go_menu/)
[Go语言入门教程](http://c.biancheng.net/golang/)
[Go语言设计与实现](https://draveness.me/golang/)
[Go语言四十二章经](https://github.com/ffhelicopter/Go42)
[Go语言核心编程]

Effective Go
Go语言内存模型
Go语言诊断
Go并发编程实战

## 网站
[C语言编程网](http://c.biancheng.net/golang/)
[Go语言中文网](https://studygolang.com/)
[Tony Bai](https://tonybai.com/articles/)

## 视频
[千锋教育](https://www.qfgolang.com/)
[Go开发语言(21世纪的C语言)从入门到项目实战，21周搞定go语言](https://www.bilibili.com/video/BV1Qk4y1R74q)

## 时间
起源于2007年，2009年正式对外发布

## 创始人
Rob Pike
Ken Thompson
Robert Griesemer 

## 项目
编译器等工具
    Go
调试器
    [delve](https://github.com/go-delve/delve)
Web框架
    Beego
数据库
    [etcd]()
区块链
    [btcd](https://github.com/btcsuite/btcd)
    [Ethereum)(https://github.com/ethereum/go-ethereum)
    [blockbook](https://github.com/trezor/blockbook)
云计算
    [docker]
    [kubernetes]
    [Terraform]
