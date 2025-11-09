# 第一题
## 方法一

git reset HEAD --hard
回退至最新版本 覆盖工作区和暂存区达到清除的效果
![1](2025-finalproject/FlechazoTel/jietu/15feaf72fe35cab4c5be120f9a397a73.png)

## 方法二
git reset HEAD 首先覆盖暂存区
git checkout -- 覆盖工作区

## 方法三
git stash push -u
将工作区和暂存区丢到临时空间
![2](2025-finalproject/FlechazoTel/jietu/19ee3dd9bde6e0accb2c558e199b998f.png)

# 第二题
## 不修改历史
git revert 回退版本的哈希值
直接创建一个与旧版本相同的新提交
![1](2025-finalproject/FlechazoTel/jietu/23f294f47156e1e09336318651cb18d5.png)
![2](2025-finalproject/FlechazoTel/jietu/0bb0693a0c7433b39dcc33f6e64602fe.png)

## 修改历史
git reset 旧版本的哈希值
直接回退版本
![3](2025-finalproject/FlechazoTel/jietu/9bb051ca37944858503fbca92f9d5783.png)

# 第三题
## 方法一
git checkout 分支
git rebase 主枝
通过rebase将分支变基到主枝 
![4](2025-finalproject/FlechazoTel/jietu/7037285fa9dea2bb3ed41ba09998deb2.png)

## 方法二
git checkout feature-branch切换分支
git format-patch main --stdout > feature.patch生成补丁
切换到主分支并应用补丁
git checkout main
git apply feature.patch
![5](2025-finalproject/FlechazoTel/jietu/3ca808b6406e5d68234ffeb3b39fd6d6.png)
