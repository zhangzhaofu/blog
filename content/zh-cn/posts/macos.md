+++ 
date = "2020-11-12"
title = "macOS"
slug = "macos" 
tags = ["macos", "cs"]
categories = ["blog"]
+++

## 学习推荐
https://www.cnblogs.com/gaozhang12345/p/10818557.html

https://github.com/DeveloperLx/macOS_Development_Tutorials_translation

https://sspai.com/post/40060


## create dmg
https://github.com/sindresorhus/create-dmg.git

## macOS开发
Objective-C语言, Swift
Cocoa库/框架
<深入解析Mac OS X & iOS操作系统> <Objective-C高级编程(iOS与OS X多线程和内存管理)> <Cocoa编程开发者手册>
官方文档
    https://developer.apple.com/library/mac/navigation/
XCode开发工具


https://en.wikibooks.org/wiki/Programming_Mac_OS_X_with_Cocoa_for_Beginners_2nd_Edition


https://www.jianshu.com/c/299375a4887f


## macOS
https://github.com/MacStorm/MacTechnologyOverview
https://developer.apple.com/library/archive/navigation/

组成
    Cocoa(Application)
    Media
    Core Services
    Core OS
    Kernel and Device Drivers

Cocoa
    AppKit (在Cocoa层)
    Foundation (在Core Services层) 实现数据管理、文件访问、进程通知、网络通信 和 其他低层级的功能
    Core Data (在 Core Services 层）基于 MVC 设计模式的应用的数据模型。虽然 Core Data 对于应用开发是可选项，但推荐 应用处理大量数据集合时使用
    



## Cocoa入门，使用Objective-C
BSD, Carbon, Cocoa, Java
|       |      |     |
|       +------+-----+
|              |
|              Core foundation
|              |
+--------------+
    |
Darwin内核


Cocoa框架
    Cocoa AppKit
    Cocoa Foundation
    Core Foundation
    kernel

Cocoa Foundation
    根对象类 NSObject
    表示基本数据类型的类，如字符串和字节数组
    存储其他对象的集合类
    表述系统信息和服务的类

Cocoa AppKit
    用户界面
        窗口(windows)
            提供放置视图的空间
            接受并给适当的视图分发用户操作的鼠标和键盘事件
        视图(views)
            对窗口中所有显示对象的一个抽象表示
        面板(panels)
            面板实际上是一种窗口，用来显示临时、或全局、或重要的信息
        控件
        widgets部件
    功能集合
        文本
            可以输入到简单的文本框或更大的文本视图中
        字体
        图像
            将图形数据封装，使用户可以轻松便捷地访问保存在磁盘文件中的图像，将其显示在屏幕上
        颜色
    应用程序工具
        文档体系结构
            通常开发的应用程序很多都是基于文档的
        粘贴板
        拖拽
        打印
        文件系统访问
        拼写检查


Objective-C
```
//
//  main.m
//  hello
//
//  Created by 张召付 on 2020/12/16.
//

#import <Foundation/Foundation.h>

int main(int argc, const char * argv[]) {
    @autoreleasepool {
        // insert code here...
        NSLog(@"Hello, World!");
    }
    return 0;
}
```
clang -framework Foundation main.m
clang -fobjc-arc -framework Foundation main.m


过程化编程注重数据和功能之间的交互
面向对象编程注重对象的设计及对象间的交互

