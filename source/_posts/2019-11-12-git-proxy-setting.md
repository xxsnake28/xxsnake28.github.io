---
title: "git代理设置"
categories: note
date: 2019-11-12 14:31:07
tags:
  - git
---

# git 设置代理
```shell
git config --global http.proxy http://127.0.0.1:1080

git config --global https.proxy http://127.0.0.1:1080
```

# git 取消代理
```shell
git config --global --unset http.proxy

git config --global --unset https.proxy
```