+++ 
date = "2020-11-01"
title = "桌面软件开发技术"
slug = "desktop" 
tags = ["gui", "cs"]
categories = ["blog"]
+++

# 桌面软件开发技术

## 桌面操作系统
Windows
    xp, win7, win10
Mac
    OS X (macOS)
Linux发行版
    Redhat系
        RHEL, CentOS, Fedora
    Debian系
        Debian, Ubuntu, Raspberry Pi OS
    其他

## 开发方式
使用原生接口开发
使用web技术开发


## Windows下开发技术
在windows下开发技术的变化主要分为两部分，以.Net技术为分水岭，分为.Net出现之前及.Net出现之后

### .Net出现之前
编写 Windows 上可以运行的程序就要直接和系统API交互,或者封装好的框架。主要技术是Win32核心编程，MFC编程。主要的开发语言是C/C++

### .Net出现之后
.NET 框架是由微软开发的软件开发平台，其最主要的两个组成部分是公共语言运行时 (CLR) 和框架类库 (FCL)， 开发语言主要为C#

#### 2002年 - .NET1.0
2002 年微软推出了 .NET Framework 1.0，相应地 Visual Studio 也升级到 7，称为 Visual Studio 2002 上一个版本叫做 Visual Studio 6）
该框架包括 C# 和 VB.NET（ Visual Basic 的继任者）
同时，第一个版本的 ASP.NET 也在 .NET Framework 1.0 亮相，它作为网站的解决方案，一直是 .NET 框架最重要的产品线之一。

#### 2005年 - .NET2.0
Visual Studio 也升级到 Visual Studio 2005
ASP.NET         - web框架
Windows Form    - Windows桌面框架
ADO.NET         - 数据库框架

#### 2007年 - .NET3.0
NET 3.0 是 .NET 框架最重大的一个更新，包括三大产品线：
    WCF：统一了过去 Web 服务混乱的形式，形成了一个统一的格式。
    WPF：作为前端用户界面的解决方案
    WF：提供工作流的管理。
.NET 3.0 标志着 Windows 平台开始全面转向 .NET 时代（以后所有版本的 Windows 都预装 .NET）。而在这之前，只有服务器版本的 Windows 会预装 .NET。

#### 2008年 - .NET3.5
Visual Studio 也升级到了 Visual Studio 2008。

#### 2010年 - .NET4.0
Visual Studio 也升级到了 Visual Studio 2010。

#### 2012年 - .NET4.5
Visual Studio 也升级到了 Visual Studio 2012。

#### 后续
在这之后，.NET 还有更高的版本 4.6 和 4.7，对应 Visual Studio 2015 和 Visual Studio 2017。

#### 2016年 - .NET Core
.NET Core 是 .NET Framework 的新一代版本，也是另外一种实现方式，是微软开发的第一个跨平台的（Windows、Mac OSX、Linux）、开源的、模块化的应用程序开发框架。
.NET Core 的应用层包括 UWP，用于开发 Windows 商店应用（部署到任何支持 Win10 的设备上，例如 XBox，智能手机甚至眼镜），和 ASP.NET Core，用于开发网站应用（通常展现为微服务的形式）

## macOS的开发
主要使用Cocoa框架来开发
Cocoa
    Foundation框架 (Foundation框架包含所有和界面显示无关的类。)
    Application Kit（AppKit）框架 (Application Kit 框架包含实现图形的、事件驱动的用户界面需要的所有对象)
	
## Linux下的开发
Linux下主要分为两大桌面环境，Gnome和KDE
Gnome桌面环境使用的是gtk+
KDE桌面环境使用的是Qt

## 其他类库
C/C++
    GTK+
    Qt
    wxWidgets
    duilib (Windows)
    Delphi (Windows)

Java
    Swing/AWT

C#
    .NET Core

Python
    Tkinter
    PyGTK
    PyQt/PySide
    wxPython
    Kivy

## web技术
CEF
NW.js
Electron

### CEF
用chromium&webkit来呈现web页面，客户端里面嵌入浏览器，浏览器显示网页

### NW.js
基于Chromium和node.js, 利用web方式开发跨平台桌面应用

### Electron
也是基于Chromium和node.js，和NW.js不同的是它更像是node.js程序

Chromium   - 可以在不考虑兼容性的情况下利用强大的web生态来开发界面
Node.js    - 提供了底层能力，比如文件读写及集成C/C++等，还可以使用npm包
Native API - 提供了跨平台和原生能力，提供了窗口、托盘、系统通知、软件更新
