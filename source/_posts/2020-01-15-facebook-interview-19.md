---
title: '#19 Facebook面试题'
categories: interview-question
date: 2020-01-15 17:28:09
tags: Facebook
---
# 题目
假设有如下的正则规则
- `.`表示任意的单个字符
- `*`表示0及以上个字符

设计一个函数用来检测给定的正则表达式和字符串是否匹配。

# 例子
## 例1
给定正则 `"ra."`   
如果字符串为 `ray` ，则返回 true。  
如果字符串为 `raymond` ， 则返回 false。

## 列2
给定正则 `".*at"`  
如果字符串为 `chat`， 则返回 true。  
如果字符串为 `chats`， 则返回 false。