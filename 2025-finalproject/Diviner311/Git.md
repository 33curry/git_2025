# Git应用问题解答

## 1. 回退修改
### 方式1：针对暂存区文件
```bash
# 将暂存区文件撤回到工作区
git reset HEAD<文件名>
# 丢弃工作区修改
git check -- <文件名>
```
### 方式2：直接恢复到上次提交
```bash
# 重置暂存区和工作区到上次提交
git reset --hard HEAD
```

## 2. 回退已提交的版本
### 不修改历史的方式
#### 方式1：git revert
```bash
# 回退最近1次提交
git revert HEAD
```
### 修改历史的方式
#### 方式1：git reset
```bash
# 重置到上一个版本
git reset --hard HEAD^
```
#### 方式2：git rebase -i
```bash
# 进入交互式变基界面，删除对应提交行
git rebase -i HEAD~2
```

## 3. 合并分支的其他方式
### 方式1：git  rebase
```bash
# 切换到目标分支
git check out main
# 将feature分支变基到main
git rebase feature
```
### 方式2：git cherry-pick
```bash
# 切换到目标分支
git checkout main
# 挑选feature分支的指定提交合并到当前分支
git cherry-pick <commit-id>
```

