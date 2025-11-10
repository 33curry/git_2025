## 回退修改
  ## 法一
  git restore --staged <filename>
  git checkout <filename>
  -移回工作区后删除 更稳妥
  <img width="1186" height="548" alt="8d10975c5b5a88fcfcef1a6602f59c80" src="https://github.com/user-attachments/assets/38596d08-410d-4279-b40c-c405ab2ca44e" />

  ## 法二
  git reset --hard HEAD
  -直接删除
  <img width="1206" height="1077" alt="25a3407dd6ebb9e74f6cb828b4eaaed1" src="https://github.com/user-attachments/assets/ac7a3ddc-e600-4338-9259-6f3088db2c6b" />

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

