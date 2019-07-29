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
答：3种方式如下：
1. 使用单元格
```
/* 父元素 */
display: table-cell;
text-align: center;
vertical-align: middle;
/* 子元素 */
display: inline-block;
```
2. 使用弹性模型
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
3. 使用transform移位
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

## 输入N个字符串，进行分类abc和acb为一类(随意两两对换位置，与之一致)，输出分类个数？

## 实现大整数相加？

## get和post请求有何区别？

## 事件优先级？（冒泡、捕捉）

## 页面性能优化？
答：

## 网页从输入到渲染完成经历了哪些过程？
答：大致可以分为如下7步：
- 输入网站
- 发送到DNS服务器，并获取域名对应的web服务器对应的ip地址；
- 与web服务器建立TCP连接；
- 浏览器向web服务器发送http请求；
- web服务器响应请求，并返回指定url的数据（或错误信息，或重定向的新的url地址）；
- 浏览器下载web服务器返回的数据及解析html源文件；
- 生成DOM树，解析css和js，渲染页面，直至显示完成。

## 了解路由传参吗？怎么实现的？
答：
- 通过在Router设置中使用命名参数定义路由信息，在组件内容使用（$route.param.参数名）的方式获取。  
- 通过props解耦，在路由中设置props:true，路由的参数内容自动映射到子组件对应属性上。  
- 原生js获取路由信息。（不推荐）

## 有使用过Promise吗？用来干什么的？
答：Promise用于异常处理的一个代理对象，有三种状态：
- pending 初始化状态
- fulfilled 操作成功
- rejected 操作失败
使用then捕捉成功的结果，使用catch捕捉失败的结果；new Promise()时，构造参数的参数是函数，第一个参数是reslove函数用于返回成功的结果，第二个参数reject函数，用于返回错误的结果。

## 双向绑定的原理是什么？
答：双向绑定是使用v-model指令来实现的。v-model 用于`<input>`、`<textarea>`及`<select>`这些组件上实现数据的双向绑定，方便获取用户输入的内容，其实是一个语法糖，使用value或checked属性绑定渲染的值，使用input事件或change事件获取用户的输入值给绑定的变量。  
- text、textarea：使用value属性和input事件
- radio、 checkbox：使用checked属性和change事件
- select：使用value属性和change事件

## 路由底层的实现原理是什么？
答：路由有2种方式实现，hash模式和history模式。  
- hash模式利用URL中#后面的内容发生改变不会刷新页面的特性来实现的。
- history模式是利用history.pushState()改变url路径，但页面不会重新加载来实现的。

## 插槽有使用过吗？
答：插槽也是组件传递内容的一种方式，在组件内部可以使用`<slot>`来定义默认和具名插槽，默认插槽传递的内容是组件之间的内容，具名插槽需要通过slot属性指明插槽的名称来传递内容。

## 在vue.js中如何实现组件的继承？
答：使用extends来实现，将一个组件扩展到另一个组件中。

## js实现继承的方式有哪些？
答：
1. 在js中可以使用原型链prototype实现继承（缺点：会改变继承的对象的内容）
2. 遍历对象的内容，进行值拷贝（使用克隆来实现继承）
3. 在prototype可以使用extends实现继承，和java的实现方式相同。

## webpack有使用过吗？
答：webpack是打包工具（分包、压缩、编译），根据项目的依赖关系打包一个或多个文件（打包成js、css、资源文件图片）。打包工具可以引入插件来增强功能，在vue.js项目会有babel编译器还有js和css压缩工具这些。

## 移动端缩放是怎么实现的？
答：在meta标签使用viewport，使用inital-scale设置初始的缩放比例，使用user-scalable=no禁用缩放。
```html
<meta name="viewport" content="width=device-width,inital-scale=1.0">
```

## 对css预处理有了解吗？
答：css预处理器比较流行的有sass和less，都是一种动态样式语言，可以在样式里编写一定的逻辑处理，如变量、继承、运算、函数这样的特性。

## 前端跨域的方式有哪些？
答：因同源策略的限制，不同站点之间不能直接访问。（前后端分离后会出现这个问题）
1. 可以在后端设置Acess-Control-Allow-Credentials=true;'Access-Control-Allow-Origin'='可访问的地址'这是简单的方式。
2. 可以在webpack配置开发服务器上代理接口信息，缺点就是在开发有用，上线后就不行了。

## 