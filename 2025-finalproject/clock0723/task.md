#我的答案

##任务一

###方法一
 使用git reset --hard HEAD撤销所有修改
![使用git reset --hard HEAD撤销所有修改](1_2.png)

###方法二
 使用git restore 选择文件分步撤销修改（已add加--staged，没有不用加）
![使用git restore 选择文件分步撤销修改](1_1.png)

##任务二

###方法一
 使用git revert回退版本（不修改历史）
！[使用git revert 回退版本](2_1.png)

###方法二
 使用git reset回退版本（修改历史）
！[使用git reset 回退版本](2_2.png)

##任务三

###方法一
使用git merge合并分支
![使用git merge合并分支](3_1.png)

###方法二
使用git rebase合并分支
![使用git rebase合并分支](3_2.png)

