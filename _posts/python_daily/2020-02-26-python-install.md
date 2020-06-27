---
layout: post 
title: Python的日常应用01
categories: python的日常应用
description: 安装
keywords: install
typora-root-url: ../..
---

> 我们要先有 python 才能学习 python

## 安装python

- 这里以windows系统下安装Python 3.8为例

### 下载 Python

1. 访问 python 官网的下载页面： [https://www.python.org/downloads/](https://www.python.org/downloads/)
2. 选择需要下载的版本点击`Download`

![img](/images/posts/python_daily/01/01.jpg)



3. 在打开的页面中找到`Windows x86-64 executable installer`下载项, 点击Download

![img](/images/posts/python_daily/01/02)

### 安装 Python

1. 下载成功后打开安装包开始安装

![img](/images/posts/python_daily/01/03)

- 注意勾选`Add Python 3.8 to PATH`

- 若不想改变安装路径则可以选择第一项默认安装
- 若想自定义安装路径则选第二项自定义安装

2. 这里以自定义安装为例

![img](/images/posts/python_daily/01/04)

- 建议选择全选, 其中pip选项必须勾选
- 确认后点击`Next`进入下一步

3. 继续选择相关配置与安装路径

![img](/images/posts/python_daily/01/05)

| 选项                  | 作用                             |
| --------------------- | :------------------------------- |
| Install for all users | 为当前计算机下所有用户安装Python |
|Associate files with Python(requires the py lanuncher)| 关联所有的python文件, .py/.pyc等文件打开时默认使用python直接执行|
|Create shortcuts for installed applications |创建快捷方式|
|Add python to environment variables |将python添加至环境变量|
|Precompile standard library |预编译标准库|
|Download debugging symbols |下载debug工具(非常不好用)|

4. 选择完成配置后点击`install`进行安装

5. 安装完成后即可点击`Close`关闭

![img](/images/posts/python_daily/01/06)



### 验证安装

1. 按`win + R`打开运行窗口, 输入`cmd`后按回车

![img](/images/posts/python_daily/01/07)

2. 在出现的窗口中输入`python`后按回车

![img](/images/posts/python_daily/01/08)

3. 若回显的信息如上图所示则证明安装成功