---
layout:     post
title:      Python lambda使用
subtitle:   Python开发
date:       2020-02-27
author:     
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - Python

---



# Python lambda使用

## 语法
lambda argument_list: expression

## 用法
lambda语法是固定的，其本质上只有一种用法，那就是定义一个lambda函数。在实际中，根据这个lambda函数应用场景的不同，可以将lambda函数的用法扩展为以下几种：

1. 将lambda函数赋值给一个变量，通过这个变量间接调用该lambda函数。
	
	例如，执行语句add=lambda x, y: x+y，定义了加法函数lambda x, y: x+y，并将其赋值给变量add，这样变量add便成为具有加法功能的函数。例如，执行add(1,2)，输出为3。
	
	```
	add = lambda x, y: x + y
	print(add(1, 2))
	```

2. 将lambda函数赋值给其他函数，从而将其他函数用该lambda函数替换。

	例如，为了把标准库time中的函数sleep的功能屏蔽(Mock)，我们可以在程序初始化时调用：time.sleep=lambda x:None。这样，在后续代码中调用time库的sleep函数将不会执行原有的功能。例如，执行time.sleep(3)时，程序不会休眠3秒钟，而是什么都不做。
	
	```
	time.sleep = lambad x: None
	time.sleep(3)
	```

3. 将lambda函数作为其他函数的返回值，返回给调用者。

	函数的返回值也可以是函数。例如return lambda x, y: x+y返回一个加法函数。这时，lambda函数实际上是定义在某个函数内部的函数，称之为嵌套函数，或者内部函数。对应的，将包含嵌套函数的函数称之为外部函数。内部函数能够访问外部函数的局部变量，这个特性是闭包(Closure)编程的基础，在这里我们不展开。
	
	```
	def fun1(x, y)
		return lambda x, y: x + y
	fun1(1, 2)
	```

4. 将lambda函数作为参数传递给其他函数。

	部分Python内置函数接收函数作为参数。典型的此类内置函数有这些。

	__filter函数__。此时lambda函数用于指定过滤列表元素的条件。例如filter(lambda x: x % 3 == 0, [1, 2, 3])指定将列表[1,2,3]中能够被3整除的元素过滤出来，其结果是[3]。

    __sorted函数__。此时lambda函数用于指定对列表中所有元素进行排序的准则。例如sorted([1, 2, 3, 4, 5, 6, 7, 8, 9], key=lambda x: abs(5-x))将列表[1, 2, 3, 4, 5, 6, 7, 8, 9]按照元素与5距离从小到大进行排序，其结果是[5, 4, 6, 3, 7, 2, 8, 1, 9]。

    __map函数__。此时lambda函数用于指定对列表中每一个元素的共同操作。例如map(lambda x: x+1, [1, 2,3])将列表[1, 2, 3]中的元素分别加1，其结果[2, 3, 4]。

    __reduce函数__。此时lambda函数用于指定列表中两两相邻元素的结合条件。例如reduce(lambda a, b: '{}, {}'.format(a, b), [1, 2, 3, 4, 5, 6, 7, 8, 9])将列表 [1, 2, 3, 4, 5, 6, 7, 8, 9]中的元素从左往右两两以逗号分隔的字符的形式依次结合起来，其结果是'1, 2, 3, 4, 5, 6, 7, 8, 9'。
    
	另外，部分Python库函数也接收函数作为参数，例如gevent的__spawn函数__。此时，lambda函数也能够作为参数传入。

# 参考
+ [关于Python中的lambda，这篇阅读量10万+的文章可能是你见过的最完整的讲解](https://blog.csdn.net/zjuxsl/article/details/79437563)
+ [Python中lambda表达式学习](https://blog.csdn.net/imzoer/article/details/8667176)