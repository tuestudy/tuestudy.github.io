---
layout: default
title: 알고리즘 문제 해결 전략
---

## 알고리즘 문제 해결 전략

![알고리즘 문제 해결 전략 1권 표지]({{ site.url }}/images/jmbook1.png)
![알고리즘 문제 해결 전략 2권 표지]({{ site.url }}/images/jmbook2.png)

* [공식 웹사이트](http://book.algospot.com/)

### 모임 로그

{% for post in site.categories.JMBOOK reversed %}
* <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}
