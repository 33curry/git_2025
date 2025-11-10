## 回退修改
  ## 法一
  git restore --staged <filename>
  git checkout <filename>
  -移回工作区后删除 更稳妥
  ## 法二
  git reset --hard HEAD
  -直接删除

## 不修改历史回退版本
  ## 法一
  git revert HEAD
  -提交"撤销"这个指令
  ## 法二
  git checkout -b new-branch <old-commit-hash>
  -在旧提交中创建新分支
## 修改历史回退版本
  ## 法一
  git reset --soft HEAD~1
  -保留修改在工作区
  git reset --hard HEAD~1
  -完全丢弃提交和修改
  ## 法二
  git rebase -i HEAD~3
##不用merge合并分支
  ## 法一
  git rebase main
  git checkout main
  git merge feature-branch
  -把分支变基后合并
  ## 法二
  git cherry-pick <commit-hash>
