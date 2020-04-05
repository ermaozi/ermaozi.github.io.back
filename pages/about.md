---
layout: page
title: About
description: 科技是第一生产力
keywords: Ermaozi , 二猫子
comments: true
menu: 关于
permalink: /about/
---

Hey， 你好吗？

## 联系

{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}

## Skill Keywords

{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
