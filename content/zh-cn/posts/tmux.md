+++ 
date = "2022-02-11"
title = "终端高效工具"
slug = "tmux" 
tags = ["tmux", "tools"]
categories = ["blog"]
+++

## 终端高效工具

https://github.com/tmux/tmux

session
window
pane

## 新建会话
tmux new -s <session-name>

## 列出所有会话
tmux ls

## 连上某一会话
tmux attach -t 0

## 分离当前会话
ctrl+b d

## 列出所有会话
ctrl+b s

## 创建window
ctrl+b c

## 左右创建pane
ctrl+b %

## 上下创建pane
ctrl+b "

## 查看所有windows
ctrl+b w
    可以在里面使用vim的hjkl

## 切换pane
ctrl+b ;
或
ctrl+b o
