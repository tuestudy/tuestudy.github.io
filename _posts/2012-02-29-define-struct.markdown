---
layout: post
status: publish
published: true
title: define-struct
author: falsetru
author_login: falsetru
author_email: falsetru@gmail.com
wordpress_id: 142
wordpress_url: http://www.tuestudy.org/bp/?p=142
date: 2012-02-29 00:26:05.000000000 +09:00
categories:
- HtDP
tags: []
comments: []
---
<pre>$ diff -u define-struct.rkt.orig define-struct.rkt
--- define-struct.rkt.orig	2012-02-29 00:09:45.093002047 +0900
+++ define-struct.rkt	2012-03-07 10:20:54.236380622 +0900
@@ -432,7 +432,7 @@
                                           (car (generate-temporaries (list id))))
                                       ctor-name)
                                   (build-name id "make-" id))]
-                       [? (build-name id id "?")]
+                       [? (build-name id "is-a-kind-of-" id "?")]
                        [sels (map (lambda (f)
                                     (build-name id ; (field-id f) 
                                                 id "-" (field-id f)))</pre>


${RACKET_HOME}/collects/racket/private/define-struct.rkt 파일을 위 처럼 바꾸면 아래와 같은짓을 할 수 있습니다.

<pre>$ racket
Welcome to Racket v5.2.1.
- (define-struct rat ())
- (define mb (make-rat))
- (is-a-kind-of-rat? mb)
#t
- (is-a-kind-of-rat? 'mb)
#f
- (rat? mb)
reference to undefined identifier: rat?

 === context ===
/usr/local/racket/collects/racket/private/misc.rkt:87:7
</pre>
