+++ 
date = "2022-02-11"
title = "Go学习"
slug = "go_learn" 
tags = ["go"]
categories = ["blog"]
+++

## Go学习

课程介绍
=======

深度讲解go语言
-------------

罗列语法
不同的语言进行比较

转型定制的课程


基本语法
面向接口
函数式编程
资源管理、错误处理、调优
gorountine channel
爬虫

安装与环境
----------

https://studygolang.com/dl
版本 >= 1.13

go env
    GOPROXY="https://proxy.golang.org, direct"

    go env -w GOPROXY=https://goproxy.cn, direct

https://goproxy.cn


GO111MODULE=""
    go env -w GO111MODULE=on

go imports
----------
go get -v golang.org/x/tools/cmd/goimports

IDE
---
vim, emacs, IntelliJ IDEA, eclipse, vscode, subline ... + go插件
GoLand
IntelliJ IDEA, go插件, file watcher插件
VS Code,

基础语法
========

变量定义
--------
var a,b,c bool
var s1, s2 string = "hello", "world"
可放在函数内，或直接放在包内
使用var()集中定义变量

让编译器自动决定类型
var a, b, i, s1, s2 = true, false, 3, "hello", "world"

使用:=定义变量
a, b, i, s1, s2 := true, false, 3, "hello", "world"
只能在函数内使用

内建变量的类型
--------------
bool
(u)int, (u)int8, (u)int16, (u)int32, (u)int64, uintptr
byte, rune
      |
      |
      |___字符型, int32
float32, float64, complex64, complex128
string

强制类型转换

常量的定义
----------

const filename = "abc.txt"

const 数值可作为各种类型使用
const a, b = 3, 4
var c int = int(math.Sqrt(a*a + b*b))

使用常量定义枚举类型
const (
    cpp = 0
    java = 1
    python = 2
    golang = 3
)

const (
    cpp = iota
    java
    python
    golang
)

const (
    b = 1 << (10 * iota)
    kb
    mb
    gb
    tb
    pb
)

变量定义要点回顾
- 变量类型写在变量名之后
- 编译器可推测变量类型
- 没有char, 只有rune
- 原生支持复数类型

条件语句
--------

func bounded(v int) int {
    if v > 100 {
        return 100
    } else if {
        return 0
    } else {
        return v
    }
}
if的条件不需要括号

func eval(a, b int, op string) int {
    var result int
    switch op {
    case "+":
        result = a + b
    case "-":
        result = a - b
    case "*":
        reuslt = a * b
    case "/":
        result = a / b
    defualt:
        panic("unsupported operator:" + op)       
    }
    return result
}
switch会自动break, 除非使用fallthrough
switch后可以没有表达式

循环
----

sum := 0
for i := 1; i <= 100; i++ {
    sum += i
}

for 的条件里不需要括号
for 的条件里可以忽略初始条件，结束条件，递增表达式

基本语法要点回顾
---------------
for, if 后面的条件没有括号
if 条件里也可定义变量
没有 while
switch 不需要 break, 也可以直接 switch 多个条件

函数
----

func eval(a, b int, op string) int {
}

func div(a, b int) (q, r int) {
}

返回值类型写在最后面
可返回多个值
函数作为参数
没有默认参数，可选参数

指针
----
var a int = 2
var pa *int = &a
*pa = 3
fmt.Println(a)

指针不能运算

函数参数
    值传递
    引用传递

内建容器
=======

数组
----

数组是值类型


切片
----
slice

    ptr
    len
    cap

添加元素时如果超越cap，系统会重新分配更大的底层数组

map
----

m := map[string]string {
    "name": "ccmouse",
    "course": "golang",
    "site": "imooc",
    "quality": "notbad",
}

map[K][V]

创建 make(map[string]int)
获取元素 m[key]
key不存在时，获得value类型的初始值
用value, ok := m[key]来判断是否存在key
用delete删除一个key
使用range遍历key, 或者遍历key, value对
不保证遍历的顺序，如需顺序，需手动对key排序
使用len获得元素的个数
map使用哈希表，必须可以比较相等
除了slice, map, function的内建类型都可以作为key
struct类型不包含上述字段，也可作为key

字符串
------

使用range遍历pos, rune对
使用utf8.RuneCountInString获得字符数量
使用len获得字节长度
使用[]byte获得字节

Fields, Split, Join
Contains, Index
ToLower, ToUpper
Trim, TrimRight, TrimLeft

面向对象
========

结构体和方法
------------

Go语言仅支持封装，不支持继承和多态

值接收者 VS 指针接收者
    - 要改变内容必须使用指针接收者
    - 结构过大也考虑使用指针接收者
    - 一致性：如有指针接收者，最好都是指针接收者

封装
----
名字一般使用CamelCase
首字母大写：public
首字母小写：private

包
---
为结构定义的方法必须放在同一个包内
可以是不同的文件

扩展已有类型
------------

其他语言比如通过继承实现

如何扩充系统类型或者别人的类型
    - 定义别名
    - 使用组合
    - 使用内嵌的方式扩展已有的类型

Go语言的依赖管理
===============

依赖的概念

依赖管理的三个阶段 GOPATH, GOVENDOR, go mod

go mod
    由go命令统一的管理，用户不必关心目录结构
    初始化：go mod init
    增加依赖：go get
    更新依赖：go get [@v...], go mod tidy

目录的整理
----------

工程的概念
    模块化
    可测试
    并发

接口
----

type Traversal interface {
    Traverse()
}

func main() {
    traversal := getTraversal()
    traversal.Traverse()
}

熟悉强类型语言的人, c++, java   - 熟悉接口的概念
熟悉弱类型语言的人, python, php - 不熟悉接口的概念

接口的详解：使用Google Guice实现依赖注入

小孩才分对错
大人只看利弊

duck typing
-----------
像鸭子走路，像鸭子叫（长得像鸭子），那么就是鸭子
描述事务的外部行为而非内部结构
严格来说go属于结构化类型系统，类似duck typing

python中的duck typing
def download(retriever):
    return retriever.get("www.imooc.com")
运行时才知道传入的retriever有没有
需要注释来说明接口

c++中的duck typing
template<class R>
string download(const R &retriever) {
    return retriever.get("https://www.imooc.com")
}
编译时才知道传入的retriever有没有get
需要注释来说明接口

java中类似代码
<R extends Retriever>
String download(R r) {
    return r.get("https://www.imooc.com")
}
传入的参数必须实现Retriever接口
不是duck typing


接口的定义和实现
----------------
接口的定义
    使用者download
    实现者retriever

接口由使用者定义 

接口变量里面有什么
    实现者的类型
    实现者的指针， 指向实现者

接口变量自带指针
接口变量同样采用值传递，几乎不需要使用接口的指针
指针接收者实现只能以指针方式使用；值接收者都可

查看接口变量
    表示任何类型：interface{}
    Type Assertion
    Type Switch

接口的组合
---------

常用系统接口
------------
Stringer
Reader/Writer


函数式编程
==========


错误处理与资源处理
==================

defer调用
    确保调用在函数结束时发生
