---
layout: default
title: 알파장
---

## 알파장

[조선 장기](https://ko.wikipedia.org/wiki/%EC%9E%A5%EA%B8%B0#.EC.9E.A5.EA.B8.B0.EC.9D.98_.ED.8A.B9.EC.A7.95) 인공지능 만들기

![조선장기]({{ site.url }}/images/janggi.png)

* [Github 저장소](https://github.com/tuestudy/janggi)

### 모임 로그

{% for post in site.categories.Janggi reversed %}
* <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}