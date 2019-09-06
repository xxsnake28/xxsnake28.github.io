---
title: 'ua(user-agent)判断浏览器或设备信息(微信，app等)，较完整版'
categories: note
date: 2019-09-06 15:06:21
tags:
  - user-agent
---

通过浏览器的userAgent判断各类设备信息，浏览器类型等
# 获取方式
```javascript
const ua = navigator.userAgent
```

# 判断浏览器内核
```javascript
const ua = navigator.userAgent

const match = {
  'Trident': ua.indexOf('Trident') > -1 || ua.indexOf('NET CLR') > -1,
  'Presto': ua.indexOf('Presto') > -1,
  'WebKit': ua.indexOf('AppleWebKit') > -1,
  'Gecko': ua.indexOf('Gecko/') > -1
}
```

# 判断浏览器类型
```javascript
const ua = navigator.userAgent

const match = {
  'Safari': ua.indexOf('Safari') > -1,
  'Chrome': ua.indexOf('Chrome') > -1 || ua.indexOf('CriOS') > -1,
  'IE': ua.indexOf('MSIE') > -1 || ua.indexOf('Trident') > -1,
  'Edge': ua.indexOf('Edge') > -1,
  'Firefox': ua.indexOf('Firefox') > -1 || ua.indexOf('FxiOS') > -1,
  'Firefox Focus': ua.indexOf('Focus') > -1,
  'Chromium': ua.indexOf('Chromium') > -1,
  'Opera': ua.indexOf('Opera') > -1 || ua.indexOf('OPR') > -1,
  'Vivaldi': ua.indexOf('Vivaldi') > -1,
  'Yandex': ua.indexOf('YaBrowser') > -1,
  'Arora': ua.indexOf('Arora') > -1,
  'Lunascape': ua.indexOf('Lunascape') > -1,
  'QupZilla': ua.indexOf('QupZilla') > -1,
  'Coc Coc': ua.indexOf('coc_coc_browser') > -1,
  'Kindle': ua.indexOf('Kindle') > -1 || ua.indexOf('Silk/') > -1,
  'Iceweasel': ua.indexOf('Iceweasel') > -1,
  'Konqueror': ua.indexOf('Konqueror') > -1,
  'Iceape': ua.indexOf('Iceape') > -1,
  'SeaMonkey': ua.indexOf('SeaMonkey') > -1,
  'Epiphany': ua.indexOf('Epiphany') > -1,
  '360': ua.indexOf('QihooBrowser') > -1||ua.indexOf('QHBrowser') > -1,
  '360EE': ua.indexOf('360EE') > -1,
  '360SE': ua.indexOf('360SE') > -1,
  'UC': ua.indexOf('UC') > -1 || ua.indexOf(' UBrowser') > -1,
  'QQBrowser': ua.indexOf('QQBrowser') > -1,
  'QQ': ua.indexOf('QQ/') > -1,
  'Baidu': ua.indexOf('Baidu') > -1 || ua.indexOf('BIDUBrowser') > -1|| ua.indexOf('baiduboxapp') > -1,
  'Maxthon': ua.indexOf('Maxthon') > -1,
  'Sogou': ua.indexOf('MetaSr') > -1 || ua.indexOf('Sogou') > -1,
  'LBBROWSER': ua.indexOf('LBBROWSER') > -1,
  '2345Explorer': ua.indexOf('2345Explorer') > -1||ua.indexOf('Mb2345Browser') > -1,
  'TheWorld': ua.indexOf('TheWorld') > -1,
  'XiaoMi': ua.indexOf('MiuiBrowser') > -1,
  'Quark': ua.indexOf('Quark') > -1,
  'Qiyu': ua.indexOf('Qiyu') > -1,
  'Wechat': ua.indexOf('MicroMessenger') > -1,
  'Taobao': ua.indexOf('AliApp(TB') > -1,
  'Alipay': ua.indexOf('AliApp(AP') > -1,
  'Weibo': ua.indexOf('Weibo') > -1,
  'Douban': ua.indexOf('com.douban.frodo') > -1,
  'Suning': ua.indexOf('SNEBUY-APP') > -1,
  'iQiYi': ua.indexOf('IqiyiApp') > -1,
  'DingTalk': ua.indexOf('DingTalk') > -1,
  'Huawei': ua.indexOf('Build/HUAWEI') > -1,
}
```

# 判断系统或平台
```javascript
const ua = navigator.userAgent

const match = {
  'Windows': ua.indexOf('Windows') > -1,
  'Linux': ua.indexOf('Linux') > -1 || ua.indexOf('X11') > -1,
  'Mac OS': ua.indexOf('Macintosh') > -1,
  'Android': ua.indexOf('Android') > -1 || ua.indexOf('Adr') > -1,
  'Ubuntu': ua.indexOf('Ubuntu') > -1,
  'FreeBSD': ua.indexOf('FreeBSD') > -1,
  'Debian': ua.indexOf('Debian') > -1,
  'Windows Phone': ua.indexOf('IEMobile') > -1 || ua.indexOf('Windows Phone')>-1,
  'BlackBerry': ua.indexOf('BlackBerry') > -1 || ua.indexOf('RIM') > -1,
  'MeeGo': ua.indexOf('MeeGo') > -1,
  'Symbian': ua.indexOf('Symbian') > -1,
  'iOS': ua.indexOf('like Mac OS X') > -1,
  'Chrome OS': ua.indexOf('CrOS') > -1,
  'WebOS': ua.indexOf('hpwOS') > -1,
}
```

# 判断设备
```javascript
const ua = navigator.userAgent

const match = {
  'Mobile': ua.indexOf('Mobi') > -1 || ua.indexOf('iPh') > -1 || ua.indexOf('480') > -1,
  'Tablet': ua.indexOf('Tablet') > -1 || ua.indexOf('Pad') > -1 || ua.indexOf('Nexus 7') > -1
}
```
