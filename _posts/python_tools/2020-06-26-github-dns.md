---
layout: post 
title: 配置 DNS 解决国内访问github过慢的问题
categories: python小工具
description: github
keywords: github dns github过慢
typora-root-url: ../..
---

# 问题现象
1. GitHub 访问过慢。
2. GitHub clone 过慢。
3. GitHub 访问页面加载失败。

# 问题原因
由于以下三个域名遭到 DNS 污染，导致我们我发适用 GitHub 加速服务。
```
github.com
assets-cdn.github.com
github.global.ssl.fastly.net
```
所以我们只需要跳过 DNS 解析，直接访问对应的 IP 地址即可。

# 解决方法
1. 访问 https://www.ipaddress.com/ 
2. 分别输入： `github.com`，`assets-cdn.github.com`，`github.global.ssl.fastly.net` 三个域名进行查询。
3. 以“ip 域名”的格式写入 hosts 文件。windows 位置：`c:\windows\system32\drivers\etc\hosts`；linux 位置：`/etc/hosts`。
4. 更新 DNS 配置。windows 命令：`ipconfig /flushdns`；linux 命令：`sudo /etc/init.d/networking restart`。

# 获取域名对应的 IP 脚本
``` python
import re
import requests
import os

domain_dict = {

    "github.com": "https://github.com.ipaddress.com/",

    "assets-cdn.github.com": "https://github.com.ipaddress.com/assets-cdn.github.com",

    "github.global.ssl.fastly.net": "https://fastly.net.ipaddress.com/github.global.ssl.fastly.net"
}


hosts_dict = {}


for domain, url in domain_dict.items():

    method = "GET"

    req = requests.request(method=method, url=url)
    pattern = r'<th>IPv4 Addresses</th><td><ul class="comma-separated"><li>(.+?)</li>'
    com = re.compile(pattern)
    ip = com.findall(req.content.decode())[0]
    hosts_dict[ip] = domain

hosts_path_dict = {
    "nt": "c:\\windows\\system32\\drivers\\etc\\hosts",
    "posix": "/etc/hosts"
}

hosts_path = hosts_path_dict.get(os.name)

print("\nhosts文件路径:", hosts_path, "\n")

print("\n".join([f"{k} {v}" for k, v in hosts_dict.items()]))

```