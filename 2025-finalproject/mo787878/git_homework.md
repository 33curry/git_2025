# Git 应用

## 第一题 回退修改

### 方式一：

> git reset --hard HEAD

*`git reset`用于重置当前分支的HEAD到指定状态*

*`--hard`选项会同时重置工作区和暂存区，将他们恢复到HEAD指向的提交状态*

*`HEAD`表示当前分支的最新提交*

### 方式二：

> git reset HEAD readme.txt

*该命令可将暂存区的修改撤回到工作区*

> git checkout -- readme.txt

该命令可丢弃工作区的修改，让他恢复到最后一次提交的状态

![第一题的图片](task1.png)



## 第二题 版本回退

### 方式一：（修改历史）

> git reset --hard commit_id

*`git reset`可将当前分支的HEAD指针移动到指定的提交`commit_id`，`--hard`选项会同时重置暂存与工作区*

![第二题方式一](task2_1.png)

### 方式二：（不修改历史）

> git revert commit_id

*`git revert`会创建一个新提交，这个新提交的内容刚好只缺失`commit__id`所做的修改而带来的内容变化*

![方式二图片](task2_2.png)

### 方式三：（不修改历史）

> git checkout commit_id --file

*这个方法专门针对文件`file`，将文件`file`恢复到`commit_id`所对应的版本*

![方式三图片](task2_3.png)





## 第三题 合并分支

### 方式一：

> git rebase branch

*`git rebase`是变基操作，可以将当前分支的提交挪到目标分支的最新提交后，让提交历史呈线性，更加整洁*

![图1](task3_1.1.png)

![图2](task3_1.2.png)

### 方式二：

> git cherry-pick commit_id

*`git cherry-pick`可以选择一个其他分支上的指定提交，应用到当前分支上*

![图1](task3_2.1.png)

![图2](task3_2.2.png)









