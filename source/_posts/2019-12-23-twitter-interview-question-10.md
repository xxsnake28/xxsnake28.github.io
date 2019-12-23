---
title: '#10 Twitter面试题'
categories: interview-question
date: 2019-12-23 17:45:52
tags: Twitter
---

# 题目
假如你有一个电商网站，我们将订单的ID按时间从新到旧记录到log文件中。

要求：

假如订单的ID的数量为N，我们需要提供给两个函数：
- `record(order_id)`：添加订单ID到log中。
- `getLast(i)`：获取 `i` 条最新的订单列表。

要求尽可能的以最高的效率实现