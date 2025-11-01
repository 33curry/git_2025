#git 问题回答
1.若你已经修改了部分文件、并且将其中的一部分加入了暂存区，应该如何回退这些修改，恢复到修改前最后一次提交的状态？给出至少两种不同的方式
  1.使用git reset 相对当前版本默认将暂存区重置，保留工作区，也可git reset --hard重置工作区和暂存区
    ![picture](./picture/1.reset%20做法.png)
  2.使用git stash -u将工作区和暂存区相对当前版本的修改保存后，马上使用git stash drop 丢弃使其恢复到最后一次提交的状态
    ![picture](./picture/1.stash%20做法.png)
2.若你已经提交了一个新版本，需要回退该版本，应该如何操作？分别给出不修改历史或修改历史的至少两种不同的方式
  1.使用git reset --soft HEAD~1将回退一个版本，不重置暂存区和工作区（修改历史）
    ![picture](./picture/2.reset%20做法.png)
  2.使用git rebase -i HEAD~1 表示从上一次提交后的提交，即最新提交，在修改界面删除该版本，这样实现回退（修改历史）
    ![picture](./picture/2.rebase%20做法1.png)
    ![picture](./picture/2.rebase%20做法2.png)
  3.使用git checkout +上次提交 进入分离头指针状态，再创建新分支指向该版本（不修改历史）
    ![picture](./picture/2.checkout%20做法.png)
  4.使用git switch --detach 和git switch 思路同3.
    ![picture](./picture/2.switch%20做法.png)
3.我们已经知道了合并分支可以使用 merge，但这不是唯一的方法，给出至少两种不同的合并分支的方式
  1.用git checkout切换目标分支，用git rebase +分支 将分支与目标分支合并
    ![picture](./picture/3.rebase%20做法.png)
  2.用git cherry-pick +提交（可多选）将其他分支的提交与目标分支合并
    ![picture](./picture/3.cherry-pick%20做法.png)
