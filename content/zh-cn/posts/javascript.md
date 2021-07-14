+++ 
date = "2020-10-29"
title = "JavaScript教程"
slug = "javascript" 
tags = ["javascript", "web", "cs"]
categories = ["blog"]
+++

## 数据类型
布尔 (Boolean)
数字 (Number)
字符串 (String)
数组 (Array)
对象 (Object)
空 (Null)
未定义 (Undefined)

在 JavaScript 中有 5 种不同的数据类型：

    string
    number
    boolean
    object
    function

3 种对象类型：

    Object
    Date
    Array

2 个不包含任何值的数据类型：

    null
    undefined

你可以使用 typeof 操作符来查看 JavaScript 变量的数据类型。

constructor 属性返回所有 JavaScript 变量的构造函数。


## 声明（创建）变量
```
var name;
name = "hello";
```
或者
```
var name = "hello";
```

## undefined
未使用值来声明的变量，其值实际上是 undefined。
```
var name;   // name的值是undefined
```

## 重新声明 JavaScript 变量
如果重新声明 JavaScript 变量，该变量的值不会丢失：
在以下两条语句执行后，变量 carname 的值依然是 "Volvo"：
```
var carname="Volvo";        
var carname;
```

## JavaScript 拥有动态类型
JavaScript 拥有动态类型。这意味着相同的变量可用作不同的类型：
```
var x;               // x 为 undefined
var x = 5;           // 现在 x 为数字
var x = "John";      // 现在 x 为字符串
```

##  字符串
字符串是存储字符（比如 "Bill Gates"）的变量。
字符串可以是引号中的任意文本。您可以使用单引号或双引号：
```
var carname="Volvo XC60";
var carname='Volvo XC60';
```

可以使用内置属性 length 来计算字符串的长度：
```
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var sln = txt.length;
```

通常， JavaScript 字符串是原始值，可以使用字符创建： var firstName = "John"
但我们也可以使用 new 关键字将字符串定义为一个对象： var firstName = new String("John")
```
var x = "John";
var y = new String("John");
typeof x // returns String
typeof y // returns Object 
```
不要创建 String 对象。它会拖慢执行速度，并可能产生其他副作用：

## 数字
JavaScript 只有一种数字类型。数字可以带小数点，也可以不带：
```
var x1=34.00;      // 使用小数点来写
var x2=34;         // 不使用小数点来写
```
##  布尔
布尔（逻辑）只能有两个值：true 或 false。
```
 var x=true;
 var y=false;
```

##  数组
下面的代码创建名为 cars 的数组： 
```
 var cars=new Array();
 cars[0]="Saab";
 cars[1]="Volvo";
 cars[2]="BMW";
```
或者 (condensed array):
```
 var cars=new Array("Saab","Volvo","BMW");
```
或者 (literal array):
```
var cars=["Saab","Volvo","BMW"]; 
```

## 对象
对象由花括号分隔。在括号内部，对象的属性以名称和值对的形式 (name : value) 来定义。属性由逗号分隔：
```
 var person={firstname:"John", lastname:"Doe", id:5566};
```
上面例子中的对象 (person) 有三个属性：firstname、lastname 以及 id。
空格和折行无关紧要。声明可横跨多行：
```
 var person={
 firstname : "John",
 lastname  : "Doe",
 id        :  5566
 };
```
对象属性有两种寻址方式： 
```
name=person.lastname;
name=person["lastname"]; 
```

## Undefined 和 Null
Undefined 这个值表示变量不含有值。
可以通过将变量的值设置为 null 来清空变量。
```
cars=null;
person=null;
```
## 声明变量类型
当您声明新变量时，可以使用关键词 "new" 来声明其类型：
```
 var carname=new String;
 var x=      new Number;
 var y=      new Boolean;
 var cars=   new Array;
 var person= new Object;
```

## 函数
函数就是包裹在花括号中的代码块，前面使用了关键词 function：
```
function functionname()
{
    执行代码
}
```
函数参数
```
function myFunction(var1,var2)
{
    代码
}
```
返回值
```
function myFunction()
{
    var x=5;
    return x;
}
```

JavaScript 函数可以通过一个表达式定义。
```
var x = function (a, b) {return a * b};
var z = x(4, 3);
```

## 局部变量，全局变量 (作用域，生存期)
在 JavaScript 函数内部声明的变量（使用 var）是局部变量，所以只能在函数内部访问它
在函数外声明的变量是全局变量

JavaScript 变量的生命期从它们被声明的时间开始
局部变量会在函数运行以后被删除。
全局变量会在页面关闭后被删除。

如果您把值赋给尚未声明的变量，该变量将被自动作为全局变量声明。
```
 carname="Volvo";
```
将声明一个全局变量 carname，即使它在函数内执行。

HTML 中的全局变量
在 HTML 中, 全局变量是 window 对象: 所有数据变量都属于 window 对象。

## 事件
事件是可以被 JavaScript 侦测到的行为。
以下是 HTML 事件的实例：
    HTML 页面完成加载
    HTML input 字段改变时
    HTML 按钮被点击
通常，当事件发生时，你可以做些事情。

## 运算符
算术运算符
    +
    -
    *
    /   (除法)
    %
    ++
    --

赋值运算符
    =
    +=
    -=
    *=
    /=
    %=

两个数字相加，返回数字相加的和，如果数字与字符串相加，返回字符串

比较运算符
    ==
    === (绝对等于，值和类型都相等)
    !=
    !==
    >
    <
    >=
    <=

逻辑运算符
    &&
    ||
    !

三目运算符
condition ? value1 : value2

## 语句
if
else
switch

for
for in
while
do while

break
continue

## 错误处理
throw、try 和 catch

## 调试
如果浏览器支持调试，你可以使用 console.log() 方法在调试窗口上打印 JavaScript 值：

