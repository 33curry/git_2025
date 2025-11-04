# Git 学习过程完整总结

经过学习，我已经初步了解了Git 的工作流和团队协作功能，从基础的版本操作到高效的团队协作开发过程。

##概况

### 1. 基础概念
- **仓库结构**：工作区 → 暂存区 → 本地仓库 → 远程仓库
- **提交规范**：提交信息要清晰

### 2. 分支管理

#### 分支操作
```bash
# 查看分支
git branch
git branch -a

# 创建并切换分支
git checkout -b new-branch
# 或使用新语法
git switch -c new-branch

# 切换分支
git checkout main
git switch main

# 删除分支
git branch -d new-branch

### 3.远程协作流程

####克隆与远程连接
```bash
# 克隆远程仓库
git clone <new_repository>
cd new_project

# 查看远程仓库信息
git remote -v

####推送与拉取
```bash
# 推送到远程分支
git push origin feature-branch
git push -u origin feature-branch  # 首次推送设置上游

# 拉取远程更新
git pull origin main

### 4.完整协作流程
```bash
# 1. 基于主分支创建功能分支
git checkout -b feature/user

# 2. 开发并提交功能
git add .
git commit -m "实现用户登录功能"

# 3. 同步主分支最新代码
git checkout main
git pull origin main

# 4. 变基或合并到功能分支
git checkout feature/user
git rebase main

# 5. 推送到远程并创建 Pull Request
git push origin feature/user

# 6. 代码审查后合并到主分支

##总结
Git 是一种团队协作文化的体现。通过基础学习，我深刻理解了团队协作开发的基础原理，为未来的项目开发和团队合作奠定了坚实基础。
