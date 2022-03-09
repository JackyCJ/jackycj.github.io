---
layout:     post
title:      Electron生成可执行程序
subtitle:   支持Windows/Mac
date:       2021-04-21
author:     JackyCJ
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - Electron
    - forge

---



# Electron打包


```
npm install
npm install @electron-forge/cli
npx electron-forge import
npm run make
```

## vue安装

```
npm install --global vue-cli
```

vue搭建报错处理
用管理员启动powershell
```
get-ExecutionPolicy
set-ExecutionPolicy RemoteSigned
```


## yarn安装

- npm安装

```
npm install -g yarn
```
- Homebrew安装

```
brew install yarn
```

# 参考
- [nodejs](https://nodejs.org)
- [Electron 文档](https://www.electronjs.org/docs/tutorial/quick-start#package-and-distribute-the-application)