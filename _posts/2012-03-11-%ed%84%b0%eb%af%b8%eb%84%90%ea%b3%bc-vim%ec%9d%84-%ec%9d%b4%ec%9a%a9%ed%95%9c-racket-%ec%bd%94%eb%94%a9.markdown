---
layout: post
status: publish
published: true
title: 터미널과 vim을 이용한 racket 코딩
author: master
author_login: master
author_email: etsg.master@gmail.com
wordpress_id: 214
wordpress_url: http://www.tuestudy.org/bp/?p=214
date: 2012-03-11 19:21:13.000000000 +09:00
categories:
- HtDP
tags: []
comments:
- id: 18
  author: falsetru
  author_email: falsetru@gmail.com
  author_url: ''
  date: '2012-03-12 13:50:11 +0900'
  date_gmt: '2012-03-12 04:50:11 +0900'
  content: (enter! ..) 대신 (load ..) 를 사용하면 언어지정(#lang ..) 필요 없습니다.
- id: 19
  author: soochul
  author_email: masterguru9@gmail.com
  author_url: ''
  date: '2012-03-12 22:02:01 +0900'
  date_gmt: '2012-03-12 13:02:01 +0900'
  content: "lisp 커뮤니티 보니까 emacs를 다 이런방식으로 쓰고 있더라구요. \r\n하지만 전 평범한 보통사람이니.. 그냥 Dr.
    racket이나.."
- id: 20
  author: master
  author_email: etsg.master@gmail.com
  author_url: ''
  date: '2012-03-13 00:01:31 +0900'
  date_gmt: '2012-03-12 15:01:31 +0900'
  content: "언어 지정 하고 (enter! ..) 하면 정의된 프로시저가 undefined identifier로 나오는군요.\r\nenter!와
    load 내부 구현을 비교해봐야하나..."
- id: 21
  author: falsetru
  author_email: falsetru@gmail.com
  author_url: ''
  date: '2012-03-13 11:10:37 +0900'
  date_gmt: '2012-03-13 02:10:37 +0900'
  content: "http://docs.racket-lang.org/guide/load.html\r\n\r\nhttp://docs.racket-lang.org/guide/module-basics.html"
- id: 25
  author: falsetru
  author_email: falsetru@gmail.com
  author_url: ''
  date: '2012-03-14 14:00:02 +0900'
  date_gmt: '2012-03-14 05:00:02 +0900'
  content: "racket -il readline 옵션 으로 실행하면 REPL에서 편집이 수월해집니다.  (적어도 리눅스에서는... )\r\n\r\nreadline
    만세!\r\n\r\nhttp://docs.racket-lang.org/readline/index.html"
- id: 26
  author: falsetru
  author_email: falsetru@gmail.com
  author_url: ''
  date: '2012-03-14 14:16:56 +0900'
  date_gmt: '2012-03-14 05:16:56 +0900'
  content: echo '(require readline)' &gt;&gt; ~/.racketrc
- id: 27
  author: master
  author_email: etsg.master@gmail.com
  author_url: ''
  date: '2012-03-17 21:33:09 +0900'
  date_gmt: '2012-03-17 12:33:09 +0900'
  content: "Mac용 터미널에서도 잘 되네요. :D\r\n좋은 팁 감사합니다~ \r\n\r\n알려주신 내용을 포스트에 추가했습니다."
---
줄곧 DrRacket에서 코딩을 했는데 github에 코드를 올리면서 DrRacket이 자동으로 추가하는 코드의 존재를 알게 되었습니다. 별건 아니고 언어와 teachpack을 설정하는 코드들이었지요. 

<pre lang="scheme">
;; The first three lines of this file were inserted by DrRacket. They record metadata
;; about the language level of this file in a form that our tools can easily process.
#reader(lib "htdp-beginner-reader.ss" "lang")((modname test) (read-case-sensitive #t) (teachpacks ((lib "convert.ss" "teachpack" "htdp") (lib "draw.ss" "teachpack" "htdp"))) (htdp-settings #(#t constructor mixed-fraction #f #t none #f ((lib "convert.ss" "teachpack" "htdp") (lib "draw.ss" "teachpack" "htdp")))))
(define (square x)
  (* x x))
</pre>

그렇긴해도 제가 코딩하지도 않은 코드를 자동을 추가하다니라는 약간 괘씸한(?) 마음이 들어 이참에 racket 명령과 제가 좋아하는 vim을 이용해서 htdp 문제를 풀어보기로 마음을 먹었습니다.

또, racket 도움말에 <a href="http://docs.racket-lang.org/guide/other-editors.html">Command-Line Tools and Your Editor of Choice</a> 라는 내용을 이미 제공하고 있어 어렵지 않게 시도해볼 수 있었습니다. emacs를 좋아하는 누군가가 emacs 버전을 만들어줘도 좋겠지요? ^^


<h3>터미널에서 racket 실행하기</h3>

racket이 설치된 위치의 bin 디렉토리로 들어가서 명령어를 실행하거나 아니면 명령어의 절대 경로를 입력해서 실행할 수도 있겠지만 매번 그러기는 귀찮으므로 다들 아시는 방법대로 PATH에 racket의 bin 디렉토리 경로를 추가해줍니다. 제 경우에는 bash shell을 사용하고 racket은 ~/tools에 설치되어 있습니다.

~/.bash_profile
<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
export PATH=$PATH:~/tools/Racket\ v5.2/bin
</p>

이제 아무 위치에서나 racket을 실행할 수 있습니다.

<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
heaven:~ god$ racket
Welcome to Racket v5.2.
> 
</p>


<h3>vim 설정</h3>

vim 설정과 관련된 내용은 <a href="http://docs.racket-lang.org/guide/Vim.html">여기</a> 설명된 내용을 참고하여 착실하게 .vimrc에 racket 관련 내용을 추가 해주면 됩니다. 또 코드의 syntax highlight를 위해 vim-racket 플러그인을 설치해줍니다.

vim-racket은 쉬운 설치를 위해 <a href="https://github.com/tpope/vim-pathogen">pathogen</a>을 이용합니다.

우선 pathogen을 설치합니다.

<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
heaven:~ god$ mkdir -p ~/.vim/autoload ~/.vim/bundle
heaven:~ god$ curl -so ~/.vim/autoload/pathogen.vim https://raw.github.com/tpope/vim-pathogen/HEAD/autoload/pathogen.vim
</p>

vim-racket을 설치합니다.

<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
heaven:~ god$ cd ~/.vim/bundle
heaven:~ god$ git clone https://github.com/wlangstroth/vim-racket.git
</p>

.vimrc에 pathogen 관련 설정과 racket syntax 관련 설정을 추가합니다.

~/.vimrc
<pre lang="vim">
call pathogen#infect()

if has("autocmd")
    au BufReadPost *.rkt,*.rktl set filetype=scheme
endif

if has("autocmd")
    au BufReadPost *.rkt,*.rktl set filetype=racket
    au filetype racket set lisp
    au filetype racket set autoindent
endif
</pre>

이러고 나면 vim에서 예쁘게 racket 코드를 작성할 수 있어요.

<a href="http://www.tuestudy.org/bp/wp-content/uploads/2012/03/vim-racket.png"><img src="http://www.tuestudy.org/bp/wp-content/uploads/2012/03/vim-racket.png" alt="" title="vim-racket" width="651" height="463" class="alignnone size-full wp-image-231" /></a>

참 파일의 맨 처음에 언어를 지정해줘야 하는 거 잊지마세요~
<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
#lang racket
</p>


<h3>Racket 파일 실행하기</h3>

간단히 racket 파일이름을 적어주면 됩니다. 
<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
heaven:htdp god$ racket PART-I/ex.2.2.1.rkt 
</p>

racket 코드에 정의만 있는 경우 REPL을 실행해서 racket 파일을 로드합니다.
<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
heaven:htdp god$ racket
Welcome to Racket v5.2.
> (enter! "PART-I/ex.2.2.1.rkt")
> (Fahrenheit->Celsius 212)
100
> 
</p>

참고로 터미널용 racket REPL은 좀 많이 구립니당. <del datetime="2012-03-17T12:33:34+00:00">Up/down 키로 이전에 실행한 명령들로 이동하는 것이 안되요. ㅠㅠ</del> falsetru님이 주신 팁을 이용하면 이 문제가 해결됩니다. racket을 실행할 때 다음과 같은 옵션을 주어 실행하거나,
<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
heaven:htdp god$ racket -il readline
</p>

다음과 같이 관련 내용을 .racketrc에 추가해줍니다.
<p style="font-family:monaco;consolas;courier new;color:#fff;background-color:#000;padding: 5px;">
heaven:htdp god$ echo '(require readline)' >> ~/.racketrc
</p>

이걸로 vim에서 racket 코딩하시는데 도움이 되셨길 바라면 전 이만 총총.

<h3>설정 환경</h3>
<ul>
	<li>Mac OS X Lion</li>
	<li>Terminal (bash)</li>
	<li>MacVim</li>
	<li>Racket v5.2</li>
</ul>

<h3>참고자료</h3>
<ul>
	<li><a href="http://docs.racket-lang.org/guide/intro.html">Welcome to Racket</a></li>
	<li><a href="http://docs.racket-lang.org/guide/Vim.html">Command-Line Tools and Your Editor of Choice >> Vim</a></li>
	<li><a href="https://github.com/wlangstroth/vim-racket">vim-racekt</a></li>
	<li><a href="https://github.com/tpope/vim-pathogen">vim-pathogen</a></li>
</ul>
