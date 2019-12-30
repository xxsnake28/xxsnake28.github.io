---
title: 'Wordpress 全局字体的设置方法'
categories: note
date: 2019-12-30 15:59:01
tags:
  - Wordpress
---

# 增加代码的位置
- 如果主题支持自定义CSS，那么在自定义CSS的地方加入如下代码
- 如果主题不支持自定义CSS，那么在添加到你的 `style.css` 的第一行

## 常规情况下
```css
* {
    font-family: "Microsoft YaHei" !important;
}
```

## 在图标字体的情况下
很多国外主题采用的图标字体化，会导致很多图标无法显示。  

此时可采用如下的方式：
```css
@font-face {
    font-family:’Open Sans’;unicode-range:U+2E80-FFFF;src: local(‘Microsoft YaHei’);
}
```
如果上述无效，可以用如下方式尝试：
```css
*:not([class*="icon"]):not(i){
    font-family: “Microsoft YaHei” !important;
}
```

## 上述方式都无效的情况下
```css
*:not([class*="icon"]):not(i) {
    font-family: Segoe UI, "Microsoft Yahei" !important;
}
```

> 因为每个主题都不一样，在大多数情况下可以通过上述方式解决。  
> 如果上述方式都无效的情况下，需要专门针对该主题进行分析。
>
> 以上的方法只用其中一种即可。