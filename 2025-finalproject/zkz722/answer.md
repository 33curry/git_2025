# Question 1

若你已经修改了部分文件、并且将其中的一部分加入了暂存区，应该如何回退这些修改，恢复到修改前最后一次提交的状态？给出至少两种不同的方式

- 方法一

```shell
git reset
```

| 类型    | 工作区 | 暂存区 |
| ------- | ------ | ------ |
| --soft  | yes    | yes    |
| --hard  | no     | no     |
| --mixed | yes    | no     |

![1](/2025-finalproject/zkz722/images/1.png)

- 方法二

  ``` shell
  # 1. 取消暂存区的修改（恢复到工作区）
  git restore --staged .
  
  # 2. 丢弃工作区的所有修改
  git restore .
  ```

  

![2](/2025-finalproject/zkz722/images/2.png)

---

---

# Question 2

若你已经提交了一个新版本，需要回退该版本，应该如何操作？分别给出不修改历史或修改历史的至少两种不同的方式

- 方式一（不修改历史）

``` shell
# 回退指定提交，但保留历史记录
git revert HEAD
# 回退最近3个提交
git revert HEAD~3..HEAD
```

![3](/2025-finalproject/zkz722/images/3.png)



- 方式二（修改历史）

  ```shell
  #彻底删除提交
  git reset --hard HEAD~1
  #保留修改到暂存区
  git reset --soft HEAD~1
  ```

  

![4](/2025-finalproject/zkz722/images/4.png)

---

---

# Question 3

我们已经知道了合并分支可以使用 merge，但这不是唯一的方法，给出至少两种不同的合并分支的方式

- 方式一 (git rebase)

  ```shell
  # 当前状态：main 分支，想要将 zkz_br 分支的修改合并到 main
  git checkout zkz_br
  git rebase main
  ```

  ![5](/2025-finalproject/zkz722/images/5.png)

> **效果：** 创建线性的提交历史，没有合并提交。

- 方式二(git cherry-pick)

  ```shell
  # 查看 zkz_br 分支的提交
  git log zkz_br --oneline
  git checkout main
  git cherry-pick <commit-hash>
  # 合并多个提交
  git cherry-pick <commit1> <commit2> <commit3>
  # 合并一个范围的提交（左开右闭）
  git cherry-pick <start-commit>..<end-commit>
  ```

  ![6](/2025-finalproject/zkz722/images/6.png)


