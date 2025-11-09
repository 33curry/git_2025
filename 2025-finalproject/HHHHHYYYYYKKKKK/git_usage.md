#Git应用实践
##问题一
###方法一：
git reset --hard HEAD
![](/home/yikang/图片/images/2025-11-08 01-38-56 的屏幕截图.png)
###方法二：
git reset HEAD <file>
git checkout -- <file>
##问题二
###不修改历史方法一：
git revert HEAD
![](/home/yikang/图片/images/2025-11-08 21-07-27 的屏幕截图.png)
###不修改历史方法二：
git revert <connit-hash>
###不修改历史方法三:
git branch temp-branch
git reset --hard HEAD~1
![](/home/yikang/图片/images/2025-11-08 21-09-04 的屏幕截图.png)
###修改历史方法一：
git reset --soft HEAD~1
![](/home/yikang/图片/images/2025-11-08 21-11-14 的屏幕截图.png)
###修改历史方法二：
git reset --mixed HEAD~1
###修改历史方法三：
git reset --hard HEAD~1
![](/home/yikang/图片/images/2025-11-08 21-12-22 的屏幕截图.png)
###修改历史方法四：
git rebase -i HEAD~3
##问题三
###方法一：
git merge feature-branch
![](/home/yikang/图片/images/2025-11-08 22-07-10 的屏幕截图.png)
###方法二：
git merge --no-ff feature-branch
![](/home/yikang/图片/images/2025-11-08 22-14-12 的屏幕截图.png)
###方法三：
git rebash main
###方法四：
git rebash -i main
###方法五：
git cherry-pick <commit-hash>
