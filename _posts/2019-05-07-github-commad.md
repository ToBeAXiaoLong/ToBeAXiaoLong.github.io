---
layout: post
title:  "github指令"
date:   2019-05-07 18:14:54
categories: github
tags: github
mathjax: true
author: LpZ
---

* content
{:toc}

## 上传代码到github库
1. 在github上创建仓库
2. 在文件夹执行(执行后，本地仓库会多一个.git文件，则说明本地仓库创建成功)
    ```
    $ git init
    ```
3. (初始上传配置github)设置SSH KEY,并执行以下命令检测是否成功
    ```
    $ ssh -T git@github.com
    ```
4. 设置username 和 email
    ```
    $ git config --global user.name"your name"
    $ git config --global user.email"your_email@yourRepo.git"
    ```
5. 选择要上传的github仓库
    ```
    $git remote add origin git@github.com:yourName/yourRepo.git
    ```
6. 选择文件到本地仓库
    ```
    $ git add fileName
    $ git commit -m"dec"
    ```
7. 上传文件到github仓库
    ```
    $ git push origin master
    ```
8. 从github拉取文件
    ```
    $ git pull
    ```

## 提交代码到github
1. 添加文件到本地仓库（带.后缀名）
    ```
    $ git add fileName
    or
    $ git add --all
    ```
2. 将add文件提交到本地仓库(dec为备注信息)
    ```
    git commit -m"dec"
    ```
3. 提交代码到github仓库
    ```
    $ git push -u origin master
    ```

## 其他指令
    ```
    $ git status //查看文档状态
    $ git config --global core.autocrlf false // 解决windows系统下换行符为CRLF
    ```