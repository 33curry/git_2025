## 第一问：若你已经修改了部分文件、并且将其中的一部分加入了暂存区，应该如何回退这些修改，恢复到修改前最后一次提交的状态？给出至少两种不同的方式

### 方法一：`git checkout`命令丢弃修改



git reset HEAD <文件名>

git checkout -- <文件名>

git checkout .

### 方法二：`git stash`临时保存修改

git stash save "临时保存修改"

#要恢复修改，使用以下命令

git stash apply stash@{0}  *# 恢复指定的stash*



## 第二问：若你已经提交了一个新版本，需要回退该版本，应该如何操作？分别给出不修改历史或修改历史的至少两种不同的方式

### 方式一：`git reset`

git log --oneline

git reset --soft <提交哈希> #保留工作目录和暂存区的更改
git reset --mixed <提交哈希> #保留工作目录更改，重置暂存区
git reset --hard <提交哈希> #丢弃所有更改，完全回退到指定状态

### 方式二：`git revert`

git log --oneline

git revert <提交的哈希值>

git revert <较早提交>..<较新提交>

## 第三问：我们已经知道了合并分支可以使用 merge，但这不是唯一的方法，给出至少两种不同的合并分支的方式

### 方法一：git rebase 进行变基操作

git checkout feature-branch#切换到要变基的特性分支

git rebase main#将当前分支变基到主分支

### 方法二：git cherry-pick 选择性应用提交

git log --oneline another-branch#查看要选取的提交哈希值

git checkout main#切换到目标分支

git cherry-pick <提交哈希1> <提交哈希2>#将特定提交应用到当前分支