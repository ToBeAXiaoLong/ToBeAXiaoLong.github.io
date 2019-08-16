---
layout: post
title:  "值互换"
date:   2019-08-16 18:12:54
categories: js
tags: js
excerpt: 值互换
author: LpZ
---

* content
{:toc}

## 方法一
```js
var a = 123,
    b = 234;

var c = a;
    a = b;
    b = c;
```

## 方法二
```js
var a = 123,
    b = 234;

    a = b + a;
    b = a - b;
    a = a - b;
```