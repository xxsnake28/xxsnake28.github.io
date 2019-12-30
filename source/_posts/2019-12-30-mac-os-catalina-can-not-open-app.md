---
title: 'macOS的Catalina系统中已损坏文件无法打开的解决办法'
sitemap: false
baidusitemap: false
categories: notice
date: 2019-12-30 18:24:24
tags:
  - macOS
  - Catalina
---

一些旧版本的APP 在 macOS的Catalina系统中可能会出现`已损坏无法打开`的问题。  
以下是解决方式：
1. 打开系统终端
2. 输入 `sudo xattr -d com.apple.quarantine /Applications/APP包名`
> 输入前面一段后，可以直接拖动app到终端中，可以自动生成路径。
3. 重启APP即可。