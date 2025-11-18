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
  <img width="2498" height="1536" alt="none-history change1" src="https://github.com/user-attachments/assets/de9b943d-64d3-4a48-b173-880451386f00" />

  ## 法二
  git checkout -b new-branch <old-commit-hash>
  -在旧提交中创建新分支
  <img width="1249" height="1536" alt="none-history change2" src="https://github.com/user-attachments/assets/fb41ce4a-a707-49aa-9933-cbb09e600dfb" />

## 修改历史回退版本
  ## 法一
  git reset --soft HEAD~1
  -保留修改在工作区
  git reset --hard HEAD~1
  -完全丢弃提交和修改
  <img width="1239" height="385" alt="history change1" src="https://github.com/user-attachments/assets/30dba137-2b66-4f62-96ab-5f8e507fbcda" />

  ## 法二
  git rebase -i HEAD~3
  ##不用merge合并分支
  <img width="1238" height="827" alt="history change2" src="https://github.com/user-attachments/assets/620288bd-f580-416c-9092-ebfafb44d186" />

## 不用merge合并
  ## 法一
  git rebase main
  git checkout main
  git merge feature-branch
  -把分支变基后合并
  <img width="1239" height="446" alt="rebase1" src="https://github.com/user-attachments/assets/a4b39ea9-6736-4de8-a95e-8d71faf0fe61" />
## 法二
  git cherry-pick <commit-hash>
  <img width="1249" height="1536" alt="rebase2" src="https://github.com/user-attachments/assets/b6651b90-051b-4c6d-b3f0-9bee09eea348" />

