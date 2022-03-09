---
layout:     post
title:      Python
subtitle:   开发
date:       2021-01-11
author:     JackyCJ
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - Python
    - Popen

---

# 如何在Python调用cmd时隐藏窗口

```
from subprocess import Popen
from win32process import CREATE_NO_WINDOW

Popen(args, creationflags=CREATE_NO_WINDOW)

```