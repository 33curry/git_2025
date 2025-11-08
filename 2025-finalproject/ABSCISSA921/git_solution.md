#git大作业完成情况

##T1回退修改
###1.1 
![执行git reset --hard HEAD](1.1.png)
![执行git reset HEAD](1.2.png)

##T2
###2.1 不修改历史的方式
![执行git revert HEAD](2.1.1.png)
![执行git checkout commit哈希值](2.1.2.png)
###2.2 修改历史的方式
![执行git reset --hard commit哈希值](2.2.1.png)
![执行git rebase -i commit哈希值](2.2.2.png)

##T3合并分支
###3.1
![执行git rebase 主分支](3.1.png)
![执行git merge --squash](3.2.png)
