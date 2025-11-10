1 回退已暂存的修改

方法 1：使用 git reset

如果已经将文件修改并暂存（git add），但希望回退这些修改，可以使用 git reset：

git reset HEAD <file>  # 将文件从暂存区移除，保留文件的修改

方法 2：使用 git checkout

如果希望恢复到最后一次提交的状态，并且丢弃所有修改，可以使用：

git checkout -- <file>  # 丢弃暂存区和工作区的修改

3.2 回退提交版本

方法 1：不修改历史（使用 git revert）

如果已经提交了更改，但不想改变历史（保持提交记录），可以使用：

git revert <commit_id>  # 创建一个新的提交来撤销特定的提交

方法 2：修改历史（使用 git reset）

如果希望回退到某个提交并修改历史，可以使用 git reset：

git reset --hard <commit_id>  # 回到指定的提交，修改历史

3.3 合并分支

方法 1：使用 git merge

最常用的合并分支方法是 git merge：

git checkout main

git merge <feature-branch>  # 合并 feature-branch 到 main

方法 2：使用 git rebase

如果想让分支的历史更清晰，可以使用 git rebase：

git checkout <feature-branch>
git rebase main  # 将 feature-branch 的更改应用到 main 的最新提交上

![回退操作示意](./images/截图 2025-10-26 11-57-56.png)