#Git应用实践
##问题一
###方法一：
git reset --hard HEAD
###方法二：
git reset HEAD <file>
git checkout -- <file>
##问题二
###不修改历史方法一：
git revert HEAD
###不修改历史方法二：
git revert <connit-hash>
###不修改历史方法三:
git branch temp-branch
git reset --hard HEAD~1
###修改历史方法一：
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
###修改历史方法二：
git rebase -i HEAD~3
##问题三
###方法一：
git merge feature-branch
###方法二：
git merge --no-ff feature-branch
###方法三：
git rebash main
###方法四：
git rebash -i main
###方法五：
git cherry-pick <commit-hash>
