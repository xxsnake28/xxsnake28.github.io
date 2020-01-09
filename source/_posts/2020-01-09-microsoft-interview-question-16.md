---
title: '#16 Microsoft 面试题'
categories: interview-question
date: 2020-01-09 17:16:37
tags: Microsoft
---
# 题目
给定一个字符串数组 `array`，给定一个目标字符串 `s`（没有空格）

要求：
根据 `s` 的字符串，查找出 `array`中包含的字符串。  
如果有多种组合方式的，则需要全部输出。  
如果没有组合方式，则输出`null`。

# 例子
## 例1
```python
array = ['quick', 'brown', 'the', 'fox']
s = 'thequickbrownfox'

// 返回
res = ['the', 'quick', 'brown', 'fox']
```

## 例2
```python
array = ['bed', 'bath', 'bedbath', 'and', 'beyond']
s = 'bedbathandbeyond'

// 返回
res1 = ['bed', 'bath', 'and', 'beyond']
res2 = ['bedbath', 'and', 'beyond']
```