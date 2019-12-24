---
title: '#11 Google 面试题'
categories: interview-question
date: 2019-12-24 18:39:15
tags: Google
---

# 题目
假如有一个文件系统，文件系统中的路径以字符串的方式构建。  

如：  
字符串`"dir\n\tsubdir1\n\tsubdir2\n\t\tfile.ext"`  
对应的文件接口是  
```
dir  
    subdir1
    subdir2
        file.ext
```
以上表示，文件夹 dir 下面包含两个文件夹 subdir1，subdir2，文件夹 subdir2 下面有个 file.ext

要求：  
给定一个文件系统字符串，计算出该文件系统中，最长的绝对路径（字符串长度最长）的文件  
如果系统中没有该文件，则返回 0

# 例子
文件系统字符串：  
`dir\n\tsubdir1\n\t\tfile1.ext\n\t\tsubsubdir1\n\tsubdir2\n\t\tsubsubdir2\n\t\t\tfile2.ext`

那么，最长的路径为`dir/subdir2/subsubdir2/file2.ext`，长度为 32 个字符