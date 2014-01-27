---
layout: post
status: publish
published: true
title: infix (매크로 활용 예)
author: falsetru
author_login: falsetru
author_email: falsetru@gmail.com
wordpress_id: 204
wordpress_url: http://www.tuestudy.org/bp/?p=204
date: 2012-03-10 19:11:07.000000000 +09:00
categories:
- HtDP
tags: []
comments:
- id: 16
  author: falsetru
  author_email: falsetru@gmail.com
  author_url: ''
  date: '2012-03-10 19:38:56 +0900'
  date_gmt: '2012-03-10 10:38:56 +0900'
  content: (infix 1 + 2 + 3) 이런건 안됩니다;;
- id: 17
  author: falsetru
  author_email: falsetru@gmail.com
  author_url: ''
  date: '2012-03-10 21:00:22 +0900'
  date_gmt: '2012-03-10 12:00:22 +0900'
  content: https://github.com/dyoo/infix-syntax-example/blob/master/infix-lang.rkt
---
<pre>
(define % remainder)
(define ** expt)

(define-syntax infix
  (syntax-rules (+ - * / % **)
    ((_ (opr1 ...) + (opr2 ...))   (+ (infix opr1 ...) (infix opr2 ...)))
    ((_  opr1      + (opr2 ...))   (+  opr1            (infix opr2 ...)))
    ((_ (opr1 ...) +  opr2     )   (+ (infix opr1 ...) opr2))
    ((_  opr1      +  opr2     )   (+  opr1            opr2))

    ((_ (opr1 ...) - (opr2 ...))   (- (infix opr1 ...) (infix opr2 ...)))
    ((_  opr1      - (opr2 ...))   (-  opr1            (infix opr2 ...)))
    ((_ (opr1 ...) -  opr2     )   (- (infix opr1 ...) opr2))
    ((_  opr1      -  opr2     )   (-  opr1            opr2))

    ((_ (opr1 ...) * (opr2 ...))   (* (infix opr1 ...) (infix opr2 ...)))
    ((_  opr1      * (opr2 ...))   (*  opr1            (infix opr2 ...)))
    ((_ (opr1 ...) *  opr2     )   (* (infix opr1 ...) opr2))
    ((_  opr1      *  opr2     )   (*  opr1            opr2))

    ((_ (opr1 ...) / (opr2 ...))   (/ (infix opr1 ...) (infix opr2 ...)))
    ((_  opr1      / (opr2 ...))   (/  opr1            (infix opr2 ...)))
    ((_ (opr1 ...) /  opr2     )   (/ (infix opr1 ...) opr2))
    ((_  opr1      /  opr2     )   (/  opr1            opr2))

    ((_ (opr1 ...) % (opr2 ...))   (% (infix opr1 ...) (infix opr2 ...)))
    ((_  opr1      % (opr2 ...))   (%  opr1            (infix opr2 ...)))
    ((_ (opr1 ...) %  opr2     )   (% (infix opr1 ...) opr2))
    ((_  opr1      %  opr2     )   (%  opr1            opr2))

    ((_ (opr1 ...) ** (opr2 ...))  (** (infix opr1 ...) (infix opr2 ...)))
    ((_  opr1      ** (opr2 ...))  (**  opr1            (infix opr2 ...)))
    ((_ (opr1 ...) **  opr2     )  (** (infix opr1 ...) opr2))
    ((_  opr1      **  opr2     )  (**  opr1            opr2))

    ((_     x)                     x)

    ((_     f ...)                 (f ...))
    ))



(require rackunit)
(require rackunit/text-ui)

(define define-syntax-tests
  (test-suite
   "Test for infix"

   (test-case
    "no op"
    (check-equal? (infix 1) 1)
    )

   (test-case
    "a op b"
    (check-equal? (infix 1 + 2) 3)
    (check-equal? (infix 2 - 1) 1)
    (check-equal? (infix 5 * 6) 30)
    (check-equal? (infix 7 % 2) 1)
    )

   (test-case
    "(op a b)"
    (check-equal? (infix quotient 7 2) 3)
    (check-equal? (infix remainder 7 2) 1)
    )

   (test-case
    "complex expression 1"
    (check-equal? (infix (infix 1 + 2) + (infix 3 + 4)) 10)
    )

   (test-case
    "complex expression 2"
    (check-equal? (infix (1 + 2) + (3 + 4)) 10)
    (check-equal? (infix (1 + (2 * 3)) + (4 + 5)) 16)
    )
   ))

(exit (run-tests define-syntax-tests))
</pre>
