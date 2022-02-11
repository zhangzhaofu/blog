+++ 
date = "2022-02-11"
title = "C学习"
slug = "c_learn" 
tags = ["C"]
categories = ["blog"]
+++

## C学习

git clone https://e.coding.net/weidongshan/rtos_training/c_improve.git

* 变量与指针
* 链表操作
* ARM架构简述
* 几条汇编指令
* 综合汇编掌握：全局变量、局部变量、变量赋值、地址操作、栈等深层次的知识


## 变量
在内存中

STM32F103
    CPU
    RAM
    Flash

## 关键字
volatile
    对寄存器操作的变量必须加入volatile
const

static

extern

## 结构体

结构体指针
typedef struct {
    char *name;
    int age;
    struct student *classmate;
} studnet, *pstudent;

int main()
{
    studnet zhangsan = { "zhangsan", 10, NULL };
    studnet lisi = { "zhangsan", 10, NULL };
    zhangsan.classmate = &lisi;
}

函数指针
struct student {
    char *name;
    int age;
    void (*good_work)(void);
};

void play_ball(void)
{
    // print
}

int main() 
{
    struct student zhangsan = { "zhangsan", 10, play_ball };
}

链表
typedef struct spy {
    char *name;
    struct spy *next;
}spy, *p_spy;

ARM架构和汇编

