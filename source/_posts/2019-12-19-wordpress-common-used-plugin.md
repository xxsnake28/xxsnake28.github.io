---
title: '推荐一些自己用过的wordpress插件'
categories: note
date: 2019-12-19 09:24:45
tags:
  - Wordpress
---

| 插件名称 | 描述 |
| :- | :- |
| No Category Base (WPML) | 移除链接中的‘/category’ |
| Contact Form 7 | 一个联系表单插件，简单而灵活 |
| Admin Menu Editor | 自定义后台管理端的菜单 |
| Akismet Anti-Spam | 由千百万人使用，Akismet可能是保护您的站点免受垃圾评论的世界上最好的方式。 即使你在睡觉时，它也保护您的站点。 使用方式：激活Akismet插件，然后转到Akismet设置页面来设置您的API密钥。 |
| Autoptimize | 自动打包js和css |
| Baidu Sitemap Generator | 生成百度 Sitemap XML 文件。就相当于网站被百度--全球最大的中文搜索引擎订阅，进而为您的网站带来潜在的流量。同时生成一个静态的站点地图页面，对所有的搜索引擎都有利。 |
| Crayon Syntax Highlighter | 高亮各种代码块，可支持多种语言 |
| Disable Google Fonts | 取消google字体 |
| Menu Icons | 自定义菜单的图标 |
| User Role Editor | 自定义多种角色角色权限 |
| WordPress Database Backup | 数据库备份插件 |
| WP Crontrol | 自定义定时任务 |
| 转向(Redirection) | 管理301跳转和404跳转 |
| WP Super Cache | 快速缓存插件，不带压缩功能 |
| W3 Total Cache | 快速缓存插件，功能更强大，自带压缩功能 |
| Disable Comments | 取消评论功能 |
| Duplicator | 备份整个网站，用于网站迁移，和The7主题配套使用时有bug，详见下方解决方式。|
| Show Hide Author | 在文章中关闭作者显示 |
| Smart Slider 3 | 比较好用的slider插件 |
| Useso take over Google | 替换所有的Google字体、谷歌JS公用库、Gravatar头像为geekzu资源。 |
| WP Baidu Map | 百度地图插件 |
| WP-Mail-SMTP | 邮件插件，可配合Contact Form 7使用 |

> Duplicator插件和The7主题配合使用的bug，如下：
1. 在使用了demo后的The7主题中，会存在迁移后主题不对的情况，解决方式如下：
  1. 首先导出The7主题的配置文件
  2. 在新网站上线导入demo，只选择导入配置项
  3. 导入完成后再次导入The7主题的配置文件
2. 在网站迁移时，会存在数据库中对应的链接地址和资源地址不正确的情况，在数据库导入前需要对应修改数据库文件