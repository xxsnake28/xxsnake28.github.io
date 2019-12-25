---
title: '#12 Google 面试题'
categories: interview-question
date: 2019-12-25 17:42:08
tags: Google
---

# 题目
给定一个整型数组 array， 一个指定整型 k
- 数组 array的子数组只要求按顺序的子数组，见例子
- k 的取值范围为 `1 <= array <= array.length`

要求：  
找出该数组的所有长度为K的子数组中的最大值。

# 例子
```
array = [10, 5, 2, 7, 8, 7]
k = 3

# output
[10, 7, 8, 8]
```
因为：  
```
10 = max(10, 5, 2)
7 = max(5, 2, 7)
8 = max(2, 7, 8)
8 = max(7, 8, 7)
```