---
title: '#3 Google面试题'
categories: interview-question
date: 2019-09-05 16:04:41
tags: Google
---

# 题目
给定一个二叉树

要求：  
- 编写序列化函数serialize(root)，表示从根路径开始序列化，将该二叉树序列化为字符串 **s**
- 编写反序列化函数deserialize(s)，将该二叉树还原为对应的对象。

# 例子
给定的二叉树如下：
```python
class Node:
    def __init__(self, val, left=None, right=None)
        self.val = val
        self.left = left
        self.right = right
```

用下列代码验证是否有效
```python
node = Node('root', Node('left', Node('left.left')), Node('right'))

assert deserialize(serialize(node)).left.left.val == 'left.left'
```
