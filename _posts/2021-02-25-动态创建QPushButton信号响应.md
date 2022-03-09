---
layout:     post
title:      Python
subtitle:   开发
date:       2021-02-25
author:     JackyCJ
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - Python
    - QPushButton

---

# 动态创建QPushButton信号响应


```
from PyQt5.QtWidgets import (QPushButton, QWidget)

class app(QWidget):
	
	def __init__():
		super().__init__()
			
		btn_list = ['btn1', 'btn2']
		for each in btn_list:
			btn_test = QPushButton(each)
			btn_test.setObjectName(each)
			btn_test.clicked.connect(self.test)
	
	def test(self):
		print('%s clicked' % self.sender().objectName())
	
```