---
layout: post
title:  "GitHub pages预览Vue项目"
date:   2019-05-14 16:51:54
categories: Git
tags: github git
excerpt: 介绍Git和SVN、GitHub, 并进行对比
author: LpZ
---

## 在github上预览Vue项目
由于直接上传Vue代码，在github上无法通过github pages预览项目。
1. 不想上传整个项目代码时，可以直接将打包后的dist文件夹上传到github，然后开启github pages功能预览。
2. 如果想在上传整个项目代码的同时，又能预览系统。





步骤如下：
- 在github里面创建一个仓库
- 将整个项目上传到github
- 将远程仓库clone到本地中，删除除.git以外的所有文件
```
git clone ...
```
- 在克隆文件创建分支gh-pages
```
git checkout --orphan gh-pages
```
- 然后把打包好的dist文件复制到克隆文件
- 提交代码到分支
```
git add .
git commit -m"备注"
git remote add origin ...
git push -u origin gh-pages
```