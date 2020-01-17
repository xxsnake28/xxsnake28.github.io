---
title: 'git仓库迁移后，如何变更项目地址而无需重新checkout'
categories: note
date: 2020-01-17 13:42:14
tags: git
---

当我们变更了项目仓库地址时，如果不想重新 checkout，可以通过修改 git 的配置 来指向新的仓库地址。

假设仓库地址如下：  
旧地址为：`https://github.com/old_name/project_name.git`
新地址为：`https://github.com/new_name/project_name.git`

### 方法一，通过命令直接修改远程地址
```bash
# 进入项目目录
cd path_to_project

# 检查现有配置
git remote -v

# 变更远程仓库
git remote set-url origin https://github.com/new_name/project_name.git
git remote set-url --push origin https://github.com/new_name/project_name.git
```

### 方法二，通过命令先删除再添加远程仓库
```bash
# 进入项目目录
cd path_to_project

# 检查现有配置
git remote -v

# 删除原有仓库
git remote rm origin

# 添加新仓库
git remote add origin https://github.com/new_name/project_name.git
```

### 方法三，直接修改配置文件
```bash
# 进入项目中的git目录
cd path_to_project/.git

# 编辑config文件
vim config

# 找到标签  [remote “origin”]
# 将标签下的 url 后面的地址替换为新地址 https://github.com/new_name/project_name.git
```