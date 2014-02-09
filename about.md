---
layout: default
title: About
---

# About

## What's TSG?

TSG는 Tuesday Study Group의 약자로 매주 화요일 저녁에 스터디 모임을 하는데서 붙여진 이름입니다.

## Members

{% for member in site.data.members %}
* [{{ member.nickname }}](https://github.com/{{ member.github }}) 
{% endfor %}
