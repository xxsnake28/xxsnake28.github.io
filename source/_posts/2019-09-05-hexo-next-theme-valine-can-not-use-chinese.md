---
title: 'hexo-next主题使用valine评论标题部分无法显示中文'
categories: note
date: 2019-09-05 17:57:14
tags: 
  - hexo
  - next
  - valine
---

# 无法显示中文的现象
![显示的是英文](https://i.loli.net/2019/09/05/GeLzHs4p3cQCuWP.jpg)

# 当前的软件环境
- hexo版本 `3.9.0`
- next版本 `7.4.0`

# 修改的办法
打开`themes -> next -> languages -> zh-CN.yml`
```yaml
# 在post标签下添加如下代码
comments:
    valine: 评论次数 # 这里的中文随便自己定义
```

# 造成问题的原因
由于主题在加载这部分内容时，跟其他的加载方式不一样，无法通过layout文件来调整。  

## 先看通常标题下方的标签的通用修改方式。
打开`themes -> next -> layout -> menu -> post.swig`

如下图，为相关代码的地方
![2.jpg](https://i.loli.net/2019/09/05/lLfCB3vnFYwXhWT.jpg)

这段代码显示了这块的相关的配置

## 找到根源文件
打开`themes -> next -> scripts -> filters -> comment -> valine.js`，如图
![3.jpg](https://i.loli.net/2019/09/05/ofpWj8LyGMs7hZE.jpg)

这里关键是`iconText`函数

打开同目录下的`common.js`，如图
![Jietu20190905-183014.jpg](https://i.loli.net/2019/09/05/jigHJdzRBep7bW5.jpg)
可以看到对应的参数值需要`post.comments.valine`
