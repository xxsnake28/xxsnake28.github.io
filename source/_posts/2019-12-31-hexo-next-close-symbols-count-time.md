---
title: 'hexo的NexT主题中，关闭字数和阅读时长统计'
categories: note
date: 2019-12-31 11:54:10
tags:
  - hexo
  - next
  - 大前端
---

# 现象
默认情况下，hexo的next主题中会打开字数统计和阅读时长统计。  
并且包含文章本身的统计和全局统计，如图：
![全局统计](https://i.loli.net/2019/12/31/7wsOGI2k9goylxf.jpg)
![文章统计](https://i.loli.net/2019/12/31/kMsdlJHSfUW5OwP.jpg)

# 问题
可能有些人不喜欢这个，比如我，那么我就要关闭他。

# 怎么做
1. 将插件`hexo-symbols-count-time` 更新到最新版本
```
    yarn upgrade hexo-symbols-count-time@^版本号
```
2. 打开`hexo` 根目录的文件 `_config.yml` 并修改
```yaml
# 增加如下配置
symbols_count_time:
  symbols: false # 关闭文章字数统计
  time: false # 关闭文章时长统计
  total_symbols: false # 关闭全局字数统计
  total_time: false # 关闭全局时长统计
```

> 已测试版本：  
> hexo: 4.0.0 ~ 4.2.0  
> next: 7.6.0

# 原理
在 `theme/next/layout/_partials/footer.swig` 文件中，是对应改全局配置的地方。
其中，如下代码表明了对应的全局配置：
![代码](https://i.loli.net/2019/12/31/A5mfw7srv93OEi6.jpg)
