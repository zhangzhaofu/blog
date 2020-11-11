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