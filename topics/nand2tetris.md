---
layout: default
title: 밑바닥부터 만드는 컴퓨팅 시스템
---

## 밑바닥부터 만드는 컴퓨팅 시스템

![nand2tetris korean book cover][Bookcover_of_Nand2Tetris_in_Korean]

- 원서: [The Elements of Computing Systems: Building a Modern Computer from First Principles][Nand2Tetris_in_English]
- 번역서: [밑바닥부터 만드는 컴퓨팅 시스템][Nand2Tetris_in_Korean] / [정오표][Nand2Tetris_in_Korean_typo]
- 공식 웹사이트: [nand2tetris][Nand2Tetris_official_website]

### 모임 로그

{% for post in site.categories.NAND2TETRIS reversed %}
* <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}

[Bookcover_of_Nand2Tetris_in_Korean]: {{ site.url }}/images/nand2tetris.jpg
[Nand2Tetris_official_website]: https://www.nand2tetris.org/
[Nand2Tetris_in_English]: https://www.amazon.com/Elements-Computing-Systems-Building-Principles/dp/0262640686
[Nand2Tetris_in_Korean]: https://blog.insightbook.co.kr/2019/03/29/%EB%B0%91%EB%B0%94%EB%8B%A5%EB%B6%80%ED%84%B0-%EB%A7%8C%EB%93%9C%EB%8A%94-%EC%BB%B4%ED%93%A8%ED%8C%85-%EC%8B%9C%EC%8A%A4%ED%85%9C/
[Nand2Tetris_in_Korean_typo]: https://docs.google.com/document/d/1VE1mJlddADycAT-jBJc4nNID1w_wiKCrmreaF1Z9sb4/edit?usp=sharing
