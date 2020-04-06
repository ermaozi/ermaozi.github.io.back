---
layout: post 
title: Python的日常应用06
categories: python的日常应用
description: 安装PyCharm
keywords: pycharm
typora-root-url: ../..
---

> 习得一身武艺，怎能不配三尺青锋？
> 今天我们来学习如何安装并使用编程利器——IDE

## **安装IDE**

### **什么是IDE**

学了这么几天的python，大家应该对编程有了一个大概的了解。

我来简单的总结一下：“编程就是把自己懒得去做的事情交给计算机去做，由于现在这个时代的计算机还听不懂人类的语言，所以我们要学习编程语言来跟计算机交流。我们把需要让计算机做的事情，一条一条明明白白的写在一个文件中。我们的**解释器**就会翻译给计算机。”

如此说来，我们写的程序其实就是按照一定格式写下来的一些字嘛！拿个文本文档来写完全没有问题！为啥还要搞其他那么麻烦的东西呢？

在前面几节中如果我们手动敲了代码。我相信会有不少同学因为语法错误导致程序执行失败。其中有一些非常低级的错误，比如：多了个空格，引号用成了中文引号，语法拼写错误……

这些错误在文本文档里编写很难保证不会出现。

此时我们就需要一个能检索全局语法问题的功能了！而这就是IDE的功能之一。

IDE是集成开发环境的意思，它集成了许多我们在编码过程中会用到的功能，比如语法错误提示、语法补全、断点调试、变量点击跳转、工程全局搜索等十分方便的功能！

![img](/images/posts/python_daily/06/01)

虽然IDE并不是必须的。

但是如果用文本文档来编程像是原始人扔石块，那么一个好用的IDE无疑是长枪火炮！

来感受一下科技带来的便利吧！

### **安装PyCharm**

我前前后后用过不少IDE，最后还是留在了PyCharm上。

今天也只介绍PyCharm。

先说其优点：

1. 这是针对python开发的一个工具，术业有专精。
2. 配置简单，学习成本极低。
3. 功能齐全，常见的场景都能覆盖。
4. 可扩展性高，支持各种第三方插件。

再说其缺点：

1. 重量级应用，体积大，打开较慢。
2. 免费版部分功能缺失。

其他的不再多说，是否使用大家仁者见仁智者见智。我们直接开始安装教程。

首先访问官网下载页面：[https://www.jetbrains.com/pycharm/download](https://www.jetbrains.com/pycharm/download)



![img](/images/posts/python_daily/06/02)

我们选择Communtiy（社区版）

![img](/images/posts/python_daily/06/03)

如果没有直接开始下载，我们在弹出的页面中点击“direct link”

![img](/images/posts/python_daily/06/04)

![img](/images/posts/python_daily/06/05)

![img](/images/posts/python_daily/06/06)

这里根据自己的需求选择对应的选项。

![img](/images/posts/python_daily/06/07)

点击Install后等待安装成功。

![img](/images/posts/python_daily/06/08)

安装成功后打开。

![img](/images/posts/python_daily/06/09)

如果以前安装过PyCharm则会出现此选项，我们可以选择“Do not import settings”重新配置。

![img](/images/posts/python_daily/06/10)

选择基础主题，我觉得黑色比较酷，所以选了黑色。选择后点击“Next”。

![img](/images/posts/python_daily/06/11)

选择安装插件。Markdown还是很好用！我写的这系列教程就是用Markdown格式。以后有时间我会讲一下Markdown的

![img](/images/posts/python_daily/06/12)

点击“Create New Project”

![img](/images/posts/python_daily/06/13)

选择工程目录后点击“Creat”。这里其实就是建一个文件夹。

![img](/images/posts/python_daily/06/14)

记得把这该死的“show tips on startup”取消勾选，再点击“CLose”。

![img](/images/posts/python_daily/06/15)

右键左上方的根目录，New > Python File，我们来创建第一个脚本。

![img](/images/posts/python_daily/06/16)

这个脚本感觉样子很奇怪，但它本质上还是一个文本文档。

这样一来，我们PyCharm就算安装完成了！

下一节我们再说这个玩意该怎么用！