# electron

技术胖
https://jspang.com/detailed?id=62

李宁
Electron 开发入门

## 打包

## 安装yarn
```
curl -o- -L https://yarnpkg.com/install.sh | bash
```

## electron安装过程
```
先下载安装nodejs

npm install -g electron
npm install -g electron-forge
electron-forge init my-app
cd my-app
npm start
npm run make
``

## 国内源
```
npm config set registry http://registry.npm.taobao.org
```

## 极客时间
https://time.geekbang.org/learning/path-detail/2
https://time.geekbang.org/course/detail/100044201-187014
github开发的
使用web技术构建桌面应用
electron
    chromium (通过web技术写UI)
    node.js (底层能力)
    navtive API (跨平台，原生能力)

历史
1989 万维网
1994 网景
1995 IE
1998 网景消亡
2002 火狐
2008 Chrome
2009 nodejs
2011 NW
2013 Atom Shell
2015 Electron

Chromium
    Browser
    Renderer
        Renderer Process
        Renderer View
        ...
    Renderer
    ...

Electron
    


## nvm安装

## 前端工程化

## 打包工具
electron-builder



http://www.conardli.top/blog/article/%E5%A4%9A%E7%AB%AF%E5%BC%80%E5%8F%91/%E7%A7%BB%E5%8A%A8%E7%AB%AF%E9%80%82%E9%85%8D%E6%80%BB%E7%BB%93%EF%BC%88%E4%BA%8C%EF%BC%89%E5%BA%94%E7%94%A8%E7%AF%87.html#_4-7-%E8%8E%B7%E5%8F%96%E6%B5%8F%E8%A7%88%E5%99%A8%E5%A4%A7%E5%B0%8F







安装最新版
npm install electron@latest

版本
Electron v11.0.3
    Chromium    v87.0.4280.67
    Node        v12.18.3
    v8          v8.7.220.25-electron.0

npm和npx区别
npm是一个node package安装工具。
npx的作用是先检查本地有没有安装某个package，如果没有去远程registry找，找到的话直接使用，不用下载到本地node-modules包里面，这样就能优化本地项目的大小，也可以避免安装package到全局。
