---
title: '#13 Facebook 面试题'
categories: interview-question
date: 2019-12-30 17:25:40
tags: Facebook
---

# 题目
现有一个方块矩阵，包含了 `K`行以及 `N` 列。

并且有 `N` 种颜色（此处的N和上方的N相同）。

要求：  
在相邻两个方块不能为同一种颜色。  
请列出方块的模型，并列出每种颜色的使用次数。

# 例子
K = 3， N = 3。  
颜色分别为red(R), Black(B), White(W)
排列如下：
```
   R  B  W
   B  W  R
   W  B  W

# 其中 red = 2, black = 3, white = 4
```