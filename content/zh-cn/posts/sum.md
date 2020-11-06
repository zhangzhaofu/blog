+++ 
date = "2020-11-06"
title = "sum校验"
slug = "sum" 
tags = ["sum", "cs"]
categories = ["blog"]
+++

## 文件校验
网上下载很多文件，都会提供md5或者SHA256校验，防止文件内容被篡改，文件下载到本地后，我们可以对文件进行校验。

### 文件MD5、SHA1、SHA256校验
```
2f6c38be914b756fde482fff83064d37  test.txt                                      // md5sum test.txt
228dfdb10e9ad6fdf5ca97f402355df1952112fe  test.txt                              // shasum -a 1 test.tx
d8a0785f3ce124ee8c79c172eefdc6989141aafaf9deab2dac8437ed5e60f5c4  test.txt      // shasum -a 256 test.txt
```

