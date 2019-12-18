---
title: '推荐一些PHP，Laravel常用开源扩展包'
categories: note
date: 2019-12-18 14:34:21
tags:
  - PHP
  - Laravel
  - 大后端
---

| 库名 | 地址 | 描述 |
| :- | :- | :- |
| briannesbitt/Carbon | https://github.com/briannesbitt/Carbon | 日期处理的扩展包 |
| jenssegers/date | https://github.com/jenssegers/date | 日期处理工具（让 Carbon 支持多语言，中文用户的福音）|
| intervention/image | https://github.com/Intervention/image | 图片处理扩展包，支持裁剪、水印等处理，使用教程请见 https://laravel-china.org/topics/1903 |
| barryvdh/laravel-ide-helper | https://github.com/barryvdh/laravel-ide-helper | 使用 IDE 开发 Laravel 项目的好帮手，支持 Facade 方法跳转，相关讨论请见：https://laravel-china.org/topics/2532 |
| maatwebsite/excel | https://github.com/Maatwebsite/Laravel-Excel | Excel 处理工具，中文处理时会出现乱码，推荐使用 [laravel-snappy](https://github.com/barryvdh/laravel-snappy)，历史讨论请见 https://laravel-china.org/topics/2477 |
| zizaco/entrust | https://github.com/Zizaco/entrust | 基于用户组的用户权限系统（必备），教程请见：https://laravel-china.org/topics/166 |
| barryvdh/laravel-dompdf | https://github.com/barryvdh/laravel-dompdf | PDF 操作工具（基于 dompdf ）|
| laravelbook/ardent | https://github.com/laravel-ardent/ardent | 自动 数据模型 验证工具 |
| tymon/jwt-auth | https://github.com/tymondesigns/jwt-auth | JWT (JSON Web Token) 用户认证机制 |
| lucadegasperi/oauth2-server-laravel | https://github.com/lucadegasperi/oauth2-server-laravel | OAuth 2.0 支持，实例教程：https://laravel-china.org/topics/1792 |
| jenssegers/mongodb | https://github.com/jenssegers/laravel-mongodb | MongoDB 数据库的支持 ，教程：https://laravel-china.org/topics/309 |
| dingo/api | https://github.com/dingo/api | 构建 API 服务器的完整解决方案，教程：https://laravel-china.org/topics/1159 |
| anahkiasen/underscore-php | https://github.com/Anahkiasen/underscore-php | Underscore.js 类似的 PHP 语法支持 |
| laracasts/generators | https://github.com/laracasts/Laravel-5-Generators-Extended | Laracasts 出品的代码快速生成工具（推荐） ，使用教程：https://laravel-china.org/topics/2535 |
| cviebrock/eloquent-sluggable | https://github.com/cviebrock/eloquent-sluggable | 文章标题 URL 别名处理工具，教程：https://laravel-china.org/topics/1926 |
| roumen/sitemap | https://github.com/RoumenDamianoff/laravel-sitemap | Sitemap 生成工具 |
| yajra/laravel-datatables-oracle | https://github.com/yajra/laravel-datatables | jQuery DataTables 的后端支持 |
| webpatser/laravel-uuid | https://github.com/webpatser/laravel-uuid | RFC 4122 标准生成的 UUID ，使用教程 https://laravel-china.org/topics/2538 |
| baum/baum | https://github.com/etrepat/baum | 嵌套集合 (Nested Set) 模型的支持，教程：https://laravel-china.org/topics/2124 |
| anahkiasen/former | https://github.com/formers/former | 强大的表单构造器，教程请见 https://laravel-china.org/topics/2539 |
| barryvdh/laravel-snappy | https://github.com/barryvdh/laravel-snappy | HTML 生成 PDF/Image 工具（利用 wkhtmltopdf）|
| laracasts/presenter | https://github.com/laracasts/Presenter | Laracasts 出品的 Presenter 方案 | 
| venturecraft/revisionable | https://github.com/VentureCraft/revisionable | 数据模型的操作记录（如管理员操作日记） |
| mcamara/laravel-localization | https://github.com/mcamara/laravel-localization | Laravel 本地化功能增强 |
| robclancy/presenter | https://github.com/robclancy/presenter | Elequent 的 Presenter 方案 |
| dimsav/laravel-translatable | https://github.com/dimsav/laravel-translatable | 数据库的多语言翻译方案 |
| torann/geoip | https://github.com/Torann/laravel-geoip | 通过 IP 获取到对应的地理位置信息（GeoIP 数据库），请参考：https://laravel-china.org/topics/2537 |
| davibennun/laravel-push-notification | https://github.com/davibennun/laravel-push-notification | App 的 Push Notification 发送工具，支持苹果的 APNS 和 安卓的 GCM |
| chumper/zipper | https://github.com/Chumper/Zipper | ZIp 打包工具（基于 ZipArchive） |
| simplesoftwareio/simple-qrcode | https://github.com/SimpleSoftwareIO/simple-qrcode | 二维码生成工具 |
| graham-campbell/markdown | https://github.com/GrahamCampbell/Laravel-Markdown | Markdown 解析器 |
| propaganistas/laravel-phone | https://github.com/Propaganistas/Laravel-Phone | 手机号码，电话号码验证支持 |
| orangehill/iseed | https://github.com/orangehill/iseed | 将数据从数据库以 seed 的方式导出，数据填充 的逆向操作。（推荐） |
| vinkla/hashids | https://github.com/vinkla/laravel-hashids | Hash ID 生成器，方便把数字的 ID 隐藏（基于Hashids），教程：https://laravel-china.org/topics/2536 | 
| spatie/laravel-backup | https://github.com/spatie/laravel-backup | 数据备份工具，支持压缩，支持各种文件系统（推荐） |
| mccool/laravel-auto-presenter | https://github.com/laravel-auto-presenter/laravel-auto-presenter | 自动注入 Presenter，教程：https://laravel-china.org/topics/1267 |
| codesleeve/laravel-stapler | https://github.com/CodeSleeve/laravel-stapler | 专为 ORM 定制的文件上传支持 |
| webpatser/laravel-countries | https://github.com/webpatser/laravel-countries | 世界所有国家数据，包括首都汇率等 | 
| toin0u/geocoder-laravel | https://github.com/geocoder-php/GeocoderLaravel | 地理位置操作工具集（基于Geocoder） |
| felixkiss/uniquewith-validator | https://github.com/felixkiss/uniquewith-validator | 表单验证规则增加字段之间的唯一性验证 |
| mews/captcha | https://github.com/mewebstudio/captcha | 图片验证码方案，使用教程请见：https://laravel-china.org/topics/2895 | 
| fedeisas/laravel-mail-css-inliner | https://github.com/fedeisas/laravel-mail-css-inliner | 将 CSS 样式写入 HTML 里，用于邮件发送内容的样式定制 |
| liebig/cron | https://github.com/liebig/cron | 计划任务分发器（直接可替换掉 Cron），L5 内置了类似的功能 |
| hieu-le/active | https://github.com/letrunghieu/active | 非常方便的方案来判断导航元素的 active 状态，使用教程请见：https://laravel-china.org/topics/2858 |