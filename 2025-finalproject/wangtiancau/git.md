题目 1：回退部分修改到上一次提交状态

在修改部分文件并将其中一部分加入暂存区后，我们可以通过以下两种方式将修改回退到修改前的最后一次提交状态。

方法一：使用 `git restore`
命令：
```bash
git restore --staged <文件名>
git restore <文件名>
方法二：git reset
git reset --hard HEAD

题目二，回退已提交版本
方法一：不修改历史：git revert
git revert <commit_id>
方法二：修改历史：git reset
git reset --hard HEAD^



题目三：合并分枝的其他方法：
方法一：用git rebase
git rebase <分支名>
方法二：用git cherry pick
git cherry-pick <commit_id>
