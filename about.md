---
layout: default
title: About
---

# About

## What's TSG?

TSG는 Tueday Study Group의 약자로, 매주 화요일 스터디 모임을 가지는 것을 정체성으로 하는 커뮤니티입니다.

성지는 2008년에 시작된 [SICP 온라인 스터디]가 오프라인으로 이어지고, [SICP]을 마무리 하면서 오프라인 모임을
했던 매주 화요일에 계속 스터디를 진행하기로 하면서 이름을 TSG로 변경하였습니다.

2012년에 [HtDP], [aosabook] 스터디를, 2013년에는 [JMBook]을 함께 공부하면서 알고리즘 정복을 노렸
습니다.

2014년 1분기에 TAOCP Vol.1 MMIX 파트를 공부하고 있습니다.

## Members

2013년 이후 활동 중인 멤버들을 기준으로 작성되었습니다.

{% for member in site.data.members %}
* [{{ member.nickname }}](https://github.com/{{ member.github }}) 
{% endfor %}

[SICP 온라인 스터디]: https://groups.google.com/forum/?fromgroups#!forum/study-sicp
[SICP]: http://mitpress.mit.edu/sicp/
[HtDP]: http://www.htdp.org
[aosabook]: http://www.aosabook.org
[JMBook]: http://algospot.com/wiki/read/JMBook
