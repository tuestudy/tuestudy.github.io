---
layout: default
title: TAOCP - MMIX
---

## TAOCP: MMIX

![TAOCP - MMIX Book cover ]({{ site.url }}/images/taocp-mmix.jpg)

The Art of Computer Programming, Volume 1, Fascicle 1: MMIX -- A RISC Computer for the New Millennium

## References

* [MMIX Quick Reference Card (PDF)]

## 모임 일정

<div>
<div class="panel panel-default">
  <div class="panel-heading">모임 일정</div>
  <div class="panel-body">
    <table class="table table-hover">
      <thead>
        <tr>
          <th>Date</th>
          <th>Topic</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>2014/01/07</td>
          <td>MMIX 스터디 준비</td>
        </tr>
        <tr>
          <td>2014/01/14 ~ 28</td>
          <td>1.3.1 Description of MMIX </td>
        </tr>
        <tr>
          <td>2014/02/04 ~ 25</td>
          <td>1.3.2 The MMIX Assembly Language</td>
        </tr>
        <tr>
          <td>2014/03/4</td>
          <td>1.4.1 Subroutines</td>
        </tr>
        <tr>
          <td>2014/03/11</td>
          <td>1.4.2 Coroutines</td>
        </tr>
        <tr>
          <td>2014/03/18</td>
          <td>1.4.3 Interpretive Routines</td>
        </tr>
        <tr>
          <td>2014/03/25 ~ 2014/06/03</td>
          <td><strike>마무리</strike>6월까지 하는 걸로... 진도는 각자.</td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
</div>

## 모임 체크인/회고

{% for post in site.categories.MMIX %}
*  <a href="{{ post.url }}">{{ post.title }}</a>
{% endfor %}



[MMIX Quick Reference Card (pdf)]: http://mmix.cs.hm.edu/doc/mmix-refcard-a4.pdf
