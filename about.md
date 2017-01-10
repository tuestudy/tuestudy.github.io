---
layout: default
title: About
---

# About

## What's TSG?

TSG는 Tueday Study Group의 약자로, 매주 화요일 스터디 모임을 가지는 것을 정체성으로 하는 커뮤니티입니다.

2008년에 시작된 [SICP 함께 공부하기]가 매주 화요일 오프라인 모임을 가졌던 것에서 시작하여,
[SICP]가 끝난 후에도 주제(책)를 바꿔 스터디를 진행하면서 TSG로 이름을 변경하였습니다.

* 2012년에 [HtDP], [aosabook] 스터디를,
* 2013년에는 [JMBook]을 함께 공부하면서 알고리즘 정복을 노렸습니다.
* 2014년 1분기에는 TAOCP Vol.1 MMIX 파트를 공부했습니다.
* 2014년 하반기에는 지난 [ipsc](http://ipsc.ksp.sk/) 문제들을 [풀었습니다](http://github.com/tuestudy/ipsc).
* 2015년 상반기에는 2013년에 다 보지 못했던 [JMBook]을 다시 펼쳤습니다.
* 2016년 상반기에는 [조선장기 알파장 프로젝트](https://github.com/tuestudy/janggi)를 진행했으나 인공지능은... orz!
* 2016년 하반기에는 [OpenCV](https://github.com/tuestudy/opencv_playground) 와 친해졌습니다.
* 2017년 시작과 함께 [500LinesOrLess](http://aosabook.org/en/index.html)를 읽고 있습니다.

## Members

2013년 이후 활동 중인 멤버들을 기준으로 작성되었습니다 (알파벳 순으로 정렬). 

{% assign sorted_members = (site.data.members | sort: 'nickname') %}
{% for member in sorted_members %}
* [{{ member.nickname }}](https://github.com/{{ member.github }})
{% endfor %}

[SICP 함께 공부하기]: https://groups.google.com/forum/?fromgroups#!forum/study-sicp
[SICP]: http://mitpress.mit.edu/sicp/
[HtDP]: http://www.htdp.org
[aosabook]: http://www.aosabook.org
[JMBook]: http://algospot.com/wiki/read/JMBook
