---
layout: post
title:  "js相关逻辑问题"
date:   2019-08-16 18:12:54
categories: js
tags: js函数
excerpt: 值互换、统计字母等
author: LpZ
---

## 值互换
方法一：
var c = a;
    a = b;
    b = c;

方法二：
a = b + a;
b = a - b;
a = a - b;

## 清除字符串前后空格
```js
// 清除字符串前后空格
function trim(str) {
    if (str && typeof str === "string") {
        var strReplace = str.replace(/^(\s*)|(\s*)$/g,"");
        document.getElementById('myId').innerText = strReplace;
        return strReplace;
    }
}
```

## 统计字符串以及最多字母个数
```js
 // 统计字符串中字母个数或统计最多字母数
    function countWord(str) {
        var obj = {
            largest: {
                value: null,
                count: 0
            }
        };
        var strLen = str.length;
        for(var i = 0; i < strLen; i++) {
            var j = str[i];
            if (obj.hasOwnProperty(j)) {
                obj[j].count++;
                if (obj.largest.count < obj[j].count) {
                    obj.largest = {
                        value: j,
                        count: obj[j].count
                    }
                }
            } else {
                obj[j] = {count: 1}
            }
        }
    }
```