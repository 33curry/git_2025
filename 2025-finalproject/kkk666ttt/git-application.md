Git 应用实践解答

问题1：回退修改（部分在暂存区）

方式一：
使用 git restore

回退暂存区的修改（取消暂存）
git restore --staged <file>

方式二：
使用 git reset 和 git checkout

回退工作区的修改
git restore <file>

回退暂存区的修改
git reset HEAD <file>

回退工作区的修改（旧版本Git）
git checkout -- <file>

问题2

创建一个新的提交来撤销之前的提交
git revert <commit-hash>

硬重置到指定提交（不太号）
git reset --hard <commit-hash>

问题3

方式一：git merge (合并提交)
git checkout main
git merge feature-branch

方式二：git rebase (变基)
git checkout feature-branch
git rebase main
