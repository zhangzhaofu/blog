+++ 
date = "2021-07-14"
title = "git"
slug = "git" 
tags = ["git", "tool", "cs"]
categories = ["tools"]
+++

## git

## 邮箱，名字
```
git config --global user.email "zhang_zhao_fu@sina.com"
git config --global user.name "zhangzhaofu"
```

## 默认编辑器
```
git config --global core.editor vim
```

## 保存密码
```
vi ~/.gitconf
[credential]
    helper = store
```

## 获取vps中git仓库
```
git clone git@zhangzhaofu.com:Note.git
```

## git获取自己搭建的git服务器
```
git clone git@108.160.130.72:~/Note.git
```

## 取消所有更改
```
git checkout . && git clean -xdf
git submodule foreach 'git checkout . && git clean -fxd'
```

## 有时tag更新不了最新
```
git tag | xargs git tag -d
git fetch --tag
```


### git log 更改时区
```
git config --global log.date local
```

### git svn

- install git-svn
```
sudo apt install git-svn
```

### 用法
```
初始化本地代码库： git svn clone -s svn-repository-url
建立分支，切换，提交，合并等纯git操作
推送到远端Git 仓库中
当前分支和远程SVN同步： git svn rebase 。 当同步SVN时出现冲突，需要手动修改冲突，git add 添加后继续rebase: git svn rebase --continue
或者提交到远端的SVN仓库中，假如你本地是git ， 远端是SVN， git svn dcommit
svn和git的工作原理毕竟不同，git对代码提交的非线性特性在svn中难以再现，如果使用了git-merge或者git-pull，再提交到svn，相关分支上的提交历史有可能无法体现在svn上。从svn的使用者的角度，无法辨别这是一个提交还是一次合并，所以在和svn协作过程中，尽量让代码库保持线性。
尽量保持git代码库的线性特征。比如在new_branch分支中，先和master做rebase，再合并到master分支中：
    git rebase master
    git checkout master
    git merge new_branch
然后在master上做dcommit，就可以在svn代码库中看到完整的提交历史
```


## 大桥bridge的git-svn
```
git svn clone https://39.100.74.73:9000/svn/A24港珠澳大桥维检机器人/03开发阶段/V10/02软件 bridge
```

## git代码管理 rebase
```
git checkout master
git pull
git checkout local
git rebase -i HEAD~2  //合并提交 --- 2表示合并两个
git rebase master---->解决冲突--->git rebase --continue
git checkout master
git merge local
git push
```

## git全局忽略.DS_Store文件
```
git config --global core.excludesfile /Users/zhangzf/.gitignore_global
echo ".DS_Store" >> ~/.gitignore_global
```

## git server authorized_keys
```
sudo adduser git
su git
cd
mkdir .ssh && chmod 700 .ssh
touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys
```



