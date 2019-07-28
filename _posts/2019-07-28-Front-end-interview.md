---
layout: post
title:  "前端面试题"
date:   2019-07-28 12:12:54
categories: 前端面试
tags: 前端面试
excerpt: 前端面试题合集
author: LpZ
---

### 1、如何对元素进行居中（垂直水平）？
答：(1)使用单元格
```
/* 父元素 */
display: table-cell;
text-align: center;
vertical-align: middle;
/* 子元素 */
display: inline-block;
```
(2)使用弹性模型
```
// 父元素
display: flex;
// 子元素
margin: auto;
```
或者
```
// 父元素
display：flex;
align-items: center;
justify-content:center;
```
(3)使用transform移位
```
// 父元素
position: relative;
// 子元素
position: absolute;
left: 50%;
top: 50%;
transform: translate(-50%, -50%);
```

2. 