---
layout: post
title:  "数组去重"
date:   2019-05-08 10:51:54
categories: JavaScript
tags: 数组去重
excerpt: 记录一些数组去重的方法：set结构
author: LpZ
---

## ES6-Set数据结构去重
使用数据结构Set,去除数组中重复元素。
```
function dedupe(array) {
    return Array.from(new Set(array));
}

dedupe([1, 1, 2, 3]) // [1, 2, 3]
```
