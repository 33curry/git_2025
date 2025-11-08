# **Git应用**



## 1. 回退修改到最近提交状态



### 方法一：使用 git checkout 回退工作区修改
`git checkout -- ||git checkout -- filename`

![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-10-30 22-37-25 的屏幕截图.png){width=50%}


### 方法二：使用 git reset 回退暂存区修改
##### 将暂存区的修改移回工作区
`git reset HEAD

##### 然后使用 checkout 回退工作区修改.
`git checkout 

![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-10-30 22-36-08 的屏幕截图.png)


### 方式三：使用 git restore
#### 恢复工作区文件
`git restore .

#### 恢复暂存区文件到工作区
`git restore --staged 

![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-10-30 22-39-07 的屏幕截图.png)
## 2. 回退已提交版本

### （1）不修改历史的方式
#### 方式一：使用 git revert
`git revert HEAD

![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-10-30 22-48-32 的屏幕截图.png)

#### 方式二：使用 `git cherry-pick`
`git cherry-pick <fix_commit_hash>

![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-11-03 19-16-10 的屏幕截图.png)

### （2）修改历史的方式
#### 方式一：使用 git reset --hard
`git reset --hard HEAD~1

![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-10-31 15-28-55 的屏幕截图.png)

#### 方式二：使用 `git revert`
git revert <哈希值>
![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-11-03 18-51-24 的屏幕截图.png)

## 3.合并分支的不同方式
### 方法一：使用 rebase（变基）
`git checkout feature-branch
`git rebase main

![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-10-31 16-51-56 的屏幕截图.png)


### 方法二：使用 squash merge（压缩合并）
`git merge --squash feature-branch
`git commit -m "合并feature分支的所有更改"


![](/home/stewie/桌面/homework/homework/2025-finalproject/Stewie-crlt/images/2025-10-31 16-57-50 的屏幕截图.png)