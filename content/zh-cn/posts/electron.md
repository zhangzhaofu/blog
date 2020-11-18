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
