title: npm&yarn换源
author: bigboss
tags: 
  - 大前端
  - 大后端
  - npm&yarn
categories:
  - note
date: 2019-09-03 18:10:00
---
# 源地址

源名称 | 源地址
---|---
淘宝 | http://registry.npm.taobao.org/
cnpmjs | http://r.cnpmjs.org/

# 替换方式
- npm

```shell
# 替换
npm config set registry https://registry.npm.taobao.org

# 还原
npm config set registry https://registry.npmjs.org/

# 查看
npm config get registry
```

- yarn

```shell
# 替换
yarn config set registry https://registry.npm.taobao.org

# 还原
yarn config set registry https://registry.yarnpkg.com

# 查看
yarn config get registry
```

