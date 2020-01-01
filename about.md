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
* 2014년 하반기에는 지난 [ipsc] 문제들을 [풀었습니다](http://github.com/tuestudy/ipsc).
* 2015년 상반기에는 2013년에 다 보지 못했던 [JMBook]을 다시 펼쳤습니다.
* 2016년 상반기에는 [조선장기 알파장 프로젝트](https://github.com/tuestudy/janggi)를 진행했으나 인공지능은... orz!
* 2016년 하반기에는 [OpenCV](https://github.com/tuestudy/opencv_playground) 와 친해졌습니다.
* 2017년 시작과 함께 [500LinesOrLess]를 읽었습니다.
* 2017년 하반기에는 함께 [ipsc] 문제들을 [풀고있습니다](http://github.com/tuestudy/ipsc).
* 2018년 상반기에는 함께 [unity]를 공부합니다.
* 2018년 하반기에는 함께 모각코(모여서 각자 코딩)를 합니다.
* 2019년에는 모각코를 하기도 하고, [JMBook]을 좀 보다가 [Nand2Tetris]를 공부합니다.

## 연도별 결산

### 2019

* 모임 주제: [JMBOOK X 모각코](https://www.tuestudy.org/topics/jmbook.html), [Nand2Tetris X 모각코](https://www.tuestudy.org/topics/nand2tetris.html)
* 2번의 공휴일을 제외한 51일의 화요일 중 **41**회 모임
* 최대 연속 주간은 **13주** (3월 첫째주 ~ 5월 마지막주)
* **12명**의 사람들이 다녀갔고, **4명**의 새로운 멤버가 스터디에 합류함
* 평균 참석 인원은 **4명**
* 가장 많은 사람이 참석한 날은 [8월 13일](https://www.tuestudy.org/nand2tetris/2019/08/13/meeting.html)로 **7명**이 참석함
* 가장 적은 사람이 참석한 날은 [4월 16일](https://www.tuestudy.org/jmbook/2019/04/16/meeting.html)로 **1명**이 참석함
* 2019년도 출석왕: haru(40), garuda(25), hannah(23)
  * 상반기 출석왕: haru(22), bill(15), hannah(14)
  * 하반기 출석왕: haru(18), garuda(18), fred(14)
  * 최다 연속 출석: haru(31주), garuda(12주), bill(7주), hannah(7주)

## Members

2013년 이후 활동 중인 멤버들을 기준으로 작성되었습니다 (알파벳 순으로 정렬).

{% assign active_members = (site.data.members | where_exp:"item", "item.active == true" | sort: 'nickname') %}
{% assign inactive_members = (site.data.members | where_exp:"item", "item.active == false" | sort: 'nickname') %}

### 활동 중 ({{ active_members.size }})

최근 1년 이내 스터디 모임에 참석한 멤버들입니다.

{% for member in active_members %}
* [{{ member.nickname }}](https://github.com/{{ member.github }}) ({{ member.join_date }})
{% endfor %}

### 휴식 중 ({{ inactive_members.size }})

{% for member in inactive_members %}
* [{{ member.nickname }}](https://github.com/{{ member.github }}) ({{ member.join_date }})
{% endfor %}

[SICP 함께 공부하기]: https://groups.google.com/forum/?fromgroups#!forum/study-sicp
[SICP]: http://mitpress.mit.edu/sicp/
[HtDP]: http://www.htdp.org
[aosabook]: http://www.aosabook.org
[JMBook]: http://algospot.com/wiki/read/JMBook
[500LinesOrLess]: http://aosabook.org/en/index.html
[ipsc]: http://ipsc.ksp.sk/
[unity]: https://unity3d.com/
[Nand2Tetris]: https://www.nand2tetris.org/
