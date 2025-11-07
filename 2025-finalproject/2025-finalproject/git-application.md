```bash 
# Git Application Q&A

## 问题1：回退已修改但未提交的更改

### 方式一：使用git checkout
git checkout -- <file>
#方式二：使用git restore
bash
git restore <file>
#方式三：使用git reset
bash
git reset --hard HEAD
#问题2：回退已提交的版本
#不修改历史的方式：
bash
# 方式一：使用git revert
git revert HEAD

# 方式二：创建反向提交
git revert <commit-hash>
#修改历史的方式：
bash
# 方式一：使用git reset --hard
git reset --hard HEAD~1

# 方式二：使用git reset --soft
git reset --soft HEAD~1
#问题3：合并分支的不同方式
#方式一：使用merge
bash
git merge <branch-name>
#方式二：使用rebase
bash
git rebase <branch-name>
#方式三：使用cherry-pick
bash
git cherry-pick <commit-hash>
EOF
