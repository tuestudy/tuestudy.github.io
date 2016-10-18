---
layout: default
title: The Architecture of Open Source Applications
---

## The Architecture of Open Source Applications

[http://aosabook.org/](http://aosabook.org/)

![aosabook vol.1 cover]({{ site.url }}/images/aosabook-vol.1.jpg)
![aosabook vol.2 cover]({{ site.url }}/images/aosabook-vol.2.jpg)

### 모임 로그

{% for post in site.categories.AOSA reversed %}
* <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}
