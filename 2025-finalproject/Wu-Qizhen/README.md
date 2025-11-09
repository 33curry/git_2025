# Git、GitHub 学习笔记

## 1. 基础配置

### 1.1 配置个人信息

```bash
git config --global user.name "your-username"
git config --global user.email "your-email@example.com"
```

### 1.2 生成 SSH 密钥

```bash
ssh-keygen -t rsa -C "your-email@example.com"
```

- 生成后查看公钥：`cat ~/.ssh/id_rsa.pub`
- 将公钥内容添加到 GitHub 的 Settings > SSH and GPG keys

### 1.3 测试 SSH 连接

```bash
ssh -T git@github.com
```

- 首次连接输入 `yes`，成功后显示 `Hi username! You've successfully authenticated...`



## 2. 核心工作流

### 2.1 本地仓库操作

```bash
# 初始化仓库
git init

# 添加文件到暂存区
git add .          # 添加所有文件
git add filename   # 添加单个文件

# 提交更改
git commit -m "描述性提交信息"
```

### 2.2 远程仓库交互

```bash
# 关联远程仓库
git remote add origin <Rep URL>

# 克隆仓库
git clone <Rep URL>

# 推送代码到远程仓库
git push origin main

# 拉取最新代码
git pull origin main
```



## 3. 分支管理

### 3.1 基本分支操作

```bash
# 创建并切换新分支
git checkout -b new-feature

# 切换分支
git checkout main

# 查看所有分支
git branch

# 合并分支
git checkout main
git merge new-feature

# 删除分支
git branch -d new-feature
```

### 3.2 推送分支到远程

```bash
git push origin new-feature
```



## 4. 常见问题

### 4.1 克隆失败 / 推送失败

- 问题：需要配置 SSH 密钥

### 4.2 本地与远程分支冲突

```bash
# 先拉取最新代码
git pull origin main

# 解决冲突后
git add .
git commit -m "解决冲突"
git push origin main
```

### 4.3 重置本地仓库

```bash
# 重置到远程仓库状态
git fetch origin
git reset --hard origin/main
```



## 5. GitHub 实用技巧

### 5.1 提升访问速度

- 修改 hosts 文件，添加 GitHub IP：

  ```
  140.82.113.3 github.com
  185.199.108.153 assets-cdn.github.com
  199.232.69.194 github.global.ssl.fastly.net
  ```

- 使用镜像加速

### 5.2  Gitee 同步 GitHub 仓库

- 在 Gitee 设置同步 GitHub 镜像



## 6. 实战工作流示例

### 6.1 创建新项目

```bash
# 1. 在 GitHub 创建新仓库
# 2. 本地初始化
git init
echo "# My Project" > README.md
git add .
git commit -m "Initial commit"

# 3. 关联远程仓库并推送
git remote add origin https://github.com/username/repo.git
git push -u origin main
```

### 6.2 提交 PR 流程

```bash
# 1. 创建新分支
git checkout -b fix-bug

# 2. 修改代码并提交
git add .
git commit -m "fix: bug description"

# 3. 推送分支
git push origin fix-bug

# 4. 在 GitHub 上创建 Pull Request
```

### 6.3 更新本地仓库

```bash
# 1. 拉取最新代码
git pull origin main

# 2. 如果有冲突，解决冲突后
git add .
git commit -m "解决冲突"
git push origin main
```



## 7. 常用命令速查表

| 操作         | 命令                          |
| ------------ | ----------------------------- |
| 初始化仓库   | `git init`                    |
| 添加文件     | `git add .`                   |
| 提交更改     | `git commit -m "message"`     |
| 关联远程仓库 | `git remote add origin <url>` |
| 克隆仓库     | `git clone <url>`             |
| 推送代码     | `git push origin main`        |
| 拉取更新     | `git pull origin main`        |
| 创建分支     | `git checkout -b branch-name` |
| 切换分支     | `git checkout branch-name`    |
| 查看分支     | `git branch`                  |
| 删除分支     | `git branch -d branch-name`   |
| 查看状态     | `git status`                  |
| 查看提交历史 | `git log`                     |
