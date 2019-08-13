---
layout: page
title: About
description: mqsnq的个人博客
keywords: mqsnq, blog
comments: true
menu: 关于
permalink: /about/
---

mqsnq的小窝。

不积跬步无以至千里。

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
