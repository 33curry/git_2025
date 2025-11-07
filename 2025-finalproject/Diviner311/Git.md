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

