---
layout: post 
title: Python的日常应用07
categories: python的日常应用
description: 使用PyCharm
keywords: pycharm
typora-root-url: ../..
---

> 上一节我们学习了PyCharm的安装
>
> 这一节我们来学习如何使用PyCharm

## PyCharm的使用

### 初配置

如果安装的 PyCharm 2019 以上的版本且 Python 安装正确，那直接跳过这一步就好了。

如果以上两个条件有任何一个不满足，则需要进行初始配置。

首先打开配置页面

![image-20200405131002498](/images/posts/python_daily/07/01)

在弹出的页面中选择 Project：xxx -> Project Interpreter -> Show All

![image-20200405131335189](/images/posts/python_daily/07/02)

点击右上角的 + 号

![image-20200405131427154](/images/posts/python_daily/07/03)

这里选择Python的绝对路径，完事一路点确定、应用就好了！

![image-20200405131530734](/images/posts/python_daily/07/04)

配置完成后我们可以看到一个名为 venv 的目录，这个就是我们的虚拟环境目录了！

![image-20200405131704690](/images/posts/python_daily/07/05)

之后我们所安装的第三方库以及安装的第三方插件都会存放在这个目录中。

到这一步之后，我们的 PyCharm 就已经可以正常使用了！

### 个性化配置

接下来就是根据自己的喜好来配置 PyCharm 了。

第一步还是打开设置。

![image-20200405131002498](/images/posts/python_daily/07/06)

然后根据自己的喜好进行配置。

#### 快捷键配置（ Keymap ）

![image-20200405132344590](/images/posts/python_daily/07/07)

这里可以选择成套的快捷键配置，也可以单独设置快捷键。

因为我比较习惯用 Eclipse 快捷键，所以这里选择 Eclipse 后点击 Apply 。

#### 字体设置 （ Editor - Font ）

![image-20200405132647444](/images/posts/python_daily/07/08)

这里设置字体，PyCharm 初始的字体通常小的令人发指。建议调整至 20 左右。

另外编程中使用的字体，尽量做到能够区分“ 0，o，1，l ”之类容易混淆的字符。后期遇到类似这样的变量名，可以在一定程度上避免一些低级错误。

同时字体等宽也很重要，等宽字体能够方便代码的“排版”。

不说废话了，这里直接推荐使用 Fira Code Medium 吧！

![image-20200405133517494](/images/posts/python_daily/07/09)

#### 主题（ Editor - Color Scheme ）

![image-20200405133733525](/images/posts/python_daily/07/10)

这里可以更改主题，选一个自己喜欢的就OK。

### 使用 PyCharm 运行代码

#### 创建脚本

上节我们讲过，现在回顾一下。

![image-20200405134006426](/images/posts/python_daily/07/11)

右键最上层的目录 => New => Python File

![image-20200405134110809](/images/posts/python_daily/07/12)

取一个你喜欢的名字，中英文随意。

然后按下回车。

你的脚本就建好了！

#### 运行脚本

![image-20200405134329258](/images/posts/python_daily/07/13)

打开脚本，输入代码。

![image-20200405134358836](/images/posts/python_daily/07/14)

右键脚本点击 Run ，或是直接点击右上角的小箭头。

![image-20200405134514366](/images/posts/python_daily/07/15)

下面弹出的窗口中就会显示脚本输出的结果了！

### 本节的练习题

- 将之前写的代码都在 PyCharm 中跑一遍。