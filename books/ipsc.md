---
layout: default
title: TAOCP - MMIX
---

## IPSC

![IPSC logo]({{ site.url }}/images/ipsc.gif)

Internet Problem Solving Contest

### 관련 링크

* [IPSC: Task Archive](http://ipsc.ksp.sk/archive)
* [IPSC: Submit Solution](http://ipsc.ksp.sk/train/submit)

### 모임 체크인/회고

{% for post in site.categories.IPSC %}
*  <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}
