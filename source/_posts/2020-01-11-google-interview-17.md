---
title: '#17 Google 面试题'
categories: interview-question
date: 2020-01-11 18:08:45
tags: Google
---
# 题目
现有一个 `M x N`的矩阵，矩阵中，true表示当前位置为墙，false表示当前位置为地板。

对于给定的起点 `start = (a, b)` , 给定的终点 `end = (m, n)`

要求：
给定一个算法函数，计算出从起点到达终点的最短路径，如果无可行进路径，则返回null

# 例子
给定的矩阵为 
```javascript
// 给定的矩阵
const s = [[f, f, f, f],
        [t, t, f, t],
        [f, f, f, f],
        [f, f, f, f]]

// 参数
const start = [3, 0] // 左下角
const end = [0, 0] // 左上角

// 结果
var steps = 7
/**
 * 因为路径是从左下角开始到右上角
 * 经过的路线是：(3, 0) -> (3, 1) -> (3, 2) -> (2, 2) -> (1, 2) -> (0, 2) -> (0, 1) -> (0, 0)
 * 合计 7 步（不包含终点）
**/

```