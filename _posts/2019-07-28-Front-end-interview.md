---
layout: post
title:  "前端面试题"
date:   2019-07-28 12:12:54
categories: 前端面试
tags: 前端面试
excerpt: 前端面试题合集
author: LpZ
---

* content
{:toc}

## 如何对元素进行居中（垂直水平）？
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
/* 父元素 */
display: flex;
/* 子元素 */
margin: auto;
```
或者
```
/* 父元素 */
display：flex;
align-items: center;
justify-content:center;
```
(3)使用transform移位
```
/* 父元素 */
position: relative;
/* 子元素 */
position: absolute;
left: 50%;
top: 50%;
transform: translate(-50%, -50%);
```

## 有使用过vuex(状态管理)？
答：状态管理用于组件之间的数据共享，以store作为容器来管理。
state: 用来存储共享的数据。  
Getter: 类似计算属性，用来获取经过处理后的数据，具有缓存作用。  
Mutation: 同步提交状态的更改。  
Action: 异步提交状态的更改。  
Module: 当状态管理多了，使用Module来划分多模块管理。  

## 请描述一下Vue的生命周期？
答：Vue实例从创建到销毁主要有8个阶段（创建前、创建后、渲染前、渲染后、更新前、更新后、销毁前、销毁后）。  
（1、2）created：使用new Vue()创建Vue的实例，然后调用init()函数初始化对象信息。  
（3、4）在渲染前会检查是否有el属性，没有的话直接调用默认的$mount(el);有el属性的话，检查是否template属性，有的话编译template内容进行渲染，没有的话编译el指定的节点进行渲染。然后创建虚拟的DOM对象，并替换挂载节点的内容渲染到视图上。在渲染后和更新后就可以进行DOM操作。  

## 组件传值的方式有哪些？
答：父传子：在子组件使用props定义属性，父组件通过绑定定义的属性来传递。  
子传父：通过使用$emit自定义事件来传递，在子组件使用$emit自定义事件，在父组件绑定事件来获取子组件传递过来的值。  
组件与组件之间：使用状态管理。  
也可以使用插槽。