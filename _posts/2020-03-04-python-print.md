---
layout: post
title: Python的日常应用02
categories: python的日常应用
description: 教会你的程序说话
keywords: print
typora-root-url: ..
---

> 大部分人在编写自己第一个程序的时候会做什么？
>
> 当然是让你的程序对我们的世界大喊一声“Hello world!”了。
>
> 今天我们来学习的便是Python中的输出语句。

## 如何让你的程序“说话”？

我们想要让程序帮我们做事之前首先要教会程序怎么“说话”，这样我们才能更清楚的明白程序究竟做了什么。

python让程序“说话”的方式比较简单。只需要使用`print()`打印语句就可以了！

下面我们一步一步来。

1. 进入Python的console界面。
2. 输入`print("Hello world!")`
3. 按下回车键

屏幕上是不是已经打印出了“Hello world!”呢？

![helloworld](/images/posts/python_daily/02/helloworld.png)

这就是我们教程序说的第一句话！

## 如何让程序更聪明的“说话”？

但是如果我们想让程序打印不同的东西，难道说每次都要重新修改`print()`语句吗？

这样做的话实在是过于繁琐。

于是我们来引入一个**“变量”**的概念。

我们接下来的可以这样写！

1. 回到我们的python console界面。
2. 输入`a = "Hello world!"` 按回车。
3. 输入`print(a)` 按回车。

打印的结果跟之前一样！

![](/images/posts/python_daily/02/helloworld2.png)

我们接下来改变一下`a`的值，再进行一次打印试试？

![](/images/posts/python_daily/02/f×ckworld.png)

打印的结果居然也跟着变了！

这里面定义的`a`就是我们上文中提到的变量。

顾名思义，变量`a`所代表的数据是可变的，它将忠诚的记录你用‘=’赋予它的值。

用大白话来说就是：“你让它等于什么它就等于什么！”

**即使是非常匪夷所思的“等式”，它也会忠实的记录！**

我们不妨尝试一下面的几条语句：

```python
i = 1
i = i + 1
print(i)
```

什么鬼？道理我都懂，可是为什么i会等于i + 1？

这里就得强调一下：在编程黑话里“=”读做“赋值号”，而非“等号”

其意为：“将赋值号右边的值赋予左边的变量”

如果能理解这句话，便可以猜的出来最后的打印结果是什么了！

![printi](/images/posts/python_daily/02/printi.png)

不知道我的朋友们有没有回答正确呢？

最后留两个思考题，感兴趣的同学可以做一下并在下方评论区写下你的答案！

1. 下方的代码打印结果是什么？

   ```python
   i = 2
   j = 3
   i, j = j, i
   print(i, j)
   ```

2. 下方代码的打印结果是什么？

   ```python
   s = "Hey"
   s = s + "beautiful"
   print(s)
   ```

   

