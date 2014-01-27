---
layout: post
status: publish
published: true
title: subtype structure
author: falsetru
author_login: falsetru
author_email: falsetru@gmail.com
wordpress_id: 132
wordpress_url: http://www.tuestudy.org/bp/?p=132
date: 2012-03-07 10:09:54.000000000 +09:00
categories:
- HtDP
tags: []
comments: []
---
<pre>
(define-struct posn (x y))
(define-struct shape (color))
(define-struct (circle shape) (center radius))
(define-struct (square shape) (nw width))

(define a-shape (make-shape 'red))
(define a-circle (make-circle 'white (make-posn 100 100) 50))
(define a-square (make-square 'black (make-posn 100 100) 100))

(shape? a-shape) ; #t
(shape? a-circle) ; #f
(circle? a-shape) ; #f
(circle? a-circle) ; #f

(shape-color a-circle) ; 'white
(circle-color a-circle) ; !error
</pre>
