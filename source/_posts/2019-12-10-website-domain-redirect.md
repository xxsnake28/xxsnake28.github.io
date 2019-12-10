---
title: "前端网站域名跳转方法"
categories: note
date: 2019-12-10 17:34:55
tags:
  - 大前端
  - 域名
---

# 域名若干秒后跳转
可以在html代码的`<head></head>`部分加上这样的域名跳转代码
```html
<meta http-equiv="refresh" content="3; url=http://需要跳转的域名">
```
> content中的数字表示停留时间

# 不隐藏跳转后的地址
```html
<html>
    <body>
        <meta http-equiv="refresh" content="0.1;url=将这里改成要跳转的域名">
    </body>
</html> 
```

# 隐藏跳转后的地址
```html
<html>
    <frameset framespacing="0" border="0" rows="0" frameborder="0">
        <frame name="main" src="将这里改成要跳转的域名" scrolling="auto" noresize>
    </frameset>
</html> 
```

# 让域名在客户端跳转
```html
<script language="javascript" type="text/javascript">window.location="http://将这里改成要跳转的域名";</script>
```