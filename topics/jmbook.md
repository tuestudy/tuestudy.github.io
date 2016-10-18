---
layout: default
title: 알고리즘 문제 해결 전략
---

## 알고리즘 문제 해결 전략

![알고리즘 문제 해결 전략 표지]({{ site.url }}/images/jmbook.png)

* [공식 웹사이트](http://book.algospot.com/)

### 모임 안내

{% for post in site.categories.JMBOOK reversed %}
1.  <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}
