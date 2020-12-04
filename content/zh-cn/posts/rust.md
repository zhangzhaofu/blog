+++ 
date = "2020-11-06"
title = "Rust"
slug = "rust" 
tags = ["rust", "cs"]
categories = ["blog"]
+++

# Rust

## 安装Rust

curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

## 设置环境变量

export PATH=$PATH:$HOME/.cargo/bin

## 用rustup管理工具链

rustup target list
rustup target add x86_64-pc-windows-gnu
rustup target add x86_64-apple-darwin

## 在Windows中使用gnu工具链
rustup set default-host x86_64-pc-windows-gnu
查看C:\Users\zhangzf\.rustup\toolchains\stable-x86_64-pc-windows-gnu\lib\rustlib\x86_64-pc-windows-gnu\bin中gcc的版本
下载mingw-w64对应的版本,并设置环境变量

## cargo
cargo update
cargo clean
cargo build

## 数据类型
- 标量类型 (scalar)
- 复合类型 (compound)

标量类型
- 整型
- 浮点型
- 布尔类型
- 字符类型

整型
- i8    u8
- i16   u16
- i32   u32
- i64   u64
- i128  u128
- isize usize

浮点型
- f32
- f64

布尔类型
- bool (true, false)

字符类型
- char


复合类型
- 元组
- 数组

元组
元组是一个将多个其他类型的值组合进一个复合类型的主要方式。元组长度固定：一旦声明，其长度不会增大或缩小。
我们使用包含在圆括号中的逗号分隔的值列表来创建一个元组。元组中的每一个位置都有一个类型，而且这些不同值的类型也不必是相同的
```
fn main() {
    let tup: (i32, f64, u8) = (500, 6.4, 1);
}
```
tup 变量绑定到整个元组上，因为元组是一个单独的复合元素。为了从元组中获取单个值，可以使用模式匹配（pattern matching）来解构（destructure）元组值
```
fn main() {
    let tup = (500, 6.4, 1);
    let (x, y, z) = tup;
    println!("x: {}", x);
}
```
除了使用模式匹配解构外，也可以使用点号（.）后跟值的索引来直接访问它们
```
fn main() {
    let x: (i32, f64, u8) = (500, 6.4, 1);

    let five_hundred = x.0;

    let six_point_four = x.1;

    let one = x.2;
}

```

数组
与元组不同，数组中的每个元素的类型必须相同。Rust 中的数组与一些其他语言中的数组不同，因为 Rust 中的数组是固定长度的：一旦声明，它们的长度不能增长或缩小。
Rust 中，数组中的值位于中括号内的逗号分隔的列表中：
```
fn main() {
    let a = [1, 2, 3, 4, 5];
}

```
可以像这样编写数组的类型：在方括号中包含每个元素的类型，后跟分号，再后跟数组元素的数量。
```
#![allow(unused)]
fn main() {
let a: [i32; 5] = [1, 2, 3, 4, 5];
}
```

以这种方式编写数组的类型看起来类似于初始化数组的另一种语法：如果要为每个元素创建包含相同值的数组，可以指定初始值，后跟分号，然后在方括号中指定数组的长度
```
let a = [3; 5]
```
变量名为 a 的数组将包含 5 个元素，这些元素的值最初都将被设置为 3

数组是一整块分配在栈上的内存。可以使用索引来访问数组的元素
```
fn main() {
    let a = [1, 2, 3, 4, 5];
    let first = a[0];
    let second = a[1];
}
```

函数
函数遍布于 Rust 代码中。你已经见过语言中最重要的函数之一：main 函数，它是很多程序的入口点。你也见过 fn 关键字，它用来声明新函数。
Rust 代码中的函数和变量名使用 snake case 规范风格。在 snake case 中，所有字母都是小写并使用下划线分隔单词。
```
fn main() {
    println!("Hello, world!");
    another_function();
}

fn another_function() {
    println!("Another function.");
}
```

函数参数
函数也可以被定义为拥有 参数（parameters），参数是特殊变量，是函数签名的一部分。当函数拥有参数（形参）时，可以为这些参数提供具体的值（实参）
```
fn main() {
    another_function(5);
}

fn another_function(x: i32) {
    println!("The value of x is: {}", x);
}
```

在函数签名中，必须 声明每个参数的类型。这是 Rust 设计中一个经过慎重考虑的决定：要求在函数定义中提供类型注解，意味着编译器不需要你在代码的其他地方注明类型来指出你的意图。

包含语句和表达式的函数体
函数体由一系列的语句和一个可选的结尾表达式构成。
因为 Rust 是一门基于表达式（expression-based）的语言，这是一个需要理解的（不同于其他语言）重要区别
语句（Statements）是执行一些操作但不返回值的指令。表达式（Expressions）计算并产生一个值

具有返回值的函数
函数可以向调用它的代码返回值。我们并不对返回值命名，但要在箭头（->）后声明它的类型
在 Rust 中，函数的返回值等同于函数体最后一个表达式的值。使用 return 关键字和指定值，可从函数中提前返回；但大部分函数隐式的返回最后的表达式。
```
fn five() -> 32 {
    5
}

fn main() {
    let x = five();
    println!("The value of x is: {}", x);
}
```

控制流
if
else if
else

loop
while
for
