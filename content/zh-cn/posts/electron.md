+++ 
date = "2020-11-01"
title = "Electron"
slug = "electron" 
tags = ["electron", "web", "cs"]
categories = ["blog"]
+++

# electron

## 极客时间
https://time.geekbang.org/learning/path-detail/2
https://time.geekbang.org/course/detail/100044201-187014
https://github.com/dengyaolong/geektime-electron

## 豆瓣阅读  Electron实战：入门、进阶与性能优化
https://read.douban.com/ebook/145633362/

## 卧梅又闻花
https://mp.weixin.qq.com/s/24SiiGZQSlFQKkYMLTX9dg

ConardLi的blog
http://www.conardli.top/blog/
https://github.com/ConardLi/electron-react

技术胖
https://jspang.com/detailed?id=62


## 安装yarn
```
curl -o- -L https://yarnpkg.com/install.sh | bash
```
## electron安装过程
先下载安装nodejs
npm install -g electron
安装最新版
npm install electron@latest

## npm和npx区别
npm是一个node package安装工具。
npx的作用是先检查本地有没有安装某个package，如果没有去远程registry找，找到的话直接使用，不用下载到本地node-modules包里面，这样就能优化本地项目的大小，也可以避免安装package到全局。
