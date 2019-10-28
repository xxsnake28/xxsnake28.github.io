---
title: 'javascript/js 小数转整数方法'
categories: note
date: 2019-10-28 14:30:30
tags:
  - javascript
  - 大前端
---

#### 丢弃小数部分，只保留整数
```javascript
parseInt(7 / 2); 
```

#### 向上取整,有小数就整数部分加1
```javascript
Math.ceil(7 / 2);
```

#### 进行四舍五入
```javascript
Math.round(7 / 2);
```

#### 向下取整
```javascript
Math.floor(7 / 2);
```