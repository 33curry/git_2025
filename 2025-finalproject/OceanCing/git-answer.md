# Git应用 作业作答

## 1. 恢复提交状态

若你已经修改了部分文件、并且将其中的一部分加入了暂存区，应该如何回退这些修改，恢复到修改前最后一次提交的状态？给出至少两种不同的方式

**方法一：**`git reset`

```bash
git reset HEAD --hard
```

- HEAD：HEAD指针指向的最新提交版本，即未修改的版本
- --hard：撤销暂存区的add并清空工作区的修改，符合要求

![answer01](/2025-finalproject/OceanCing/images/question01.png)

如图：

- 修改了文件`temp01.txt`
- add到暂存区
- `git log`查看历史，可以使用HEAD回退或者直接使用哈希值回退
- 最后查看`git status`发现已经撤销修改

**方法二：**`git restore`

```bash
git restore --staged .		# 这一步取消添加到暂存区的操作
git restore .				# 这一步将最新的一次提交覆盖到当前的状态
```

如图：

![answer02](/2025-finalproject/OceanCing/images/question2.png)

- 对temp.txt修改后，添加后查看状态和日志
- 第一步先撤销添加到暂存区
- 第二部将最新的一次提交覆盖到当前状态



## 2. 回退已提交的版本

若你已经提交了一个新版本，需要回退该版本，应该如何操作？分别给出不修改历史或修改历史的至少两种不同的方式

- 不修改历史：我的理解是已提交的历史保留，然后回退版本的commit也会存在历史，整个提交和回退都保留历史。
- 修改历史：回退版本直接删除上一次commit的历史

### 不修改历史

**方法一：**`git revert`

```bash
git revert HEAD
git revert <hash>
```

- 可以使用HEAD代表上一次提交历史
- 也可以使用上次历史的哈希值
- 原理是创建一个新的commit作为要回退的那次提交抵消上一次提交，会保留这次提交的commit历史，但是也可以实现回退

![](/2025-finalproject/OceanCing/images/question2.1.1.png)

如图：

- 在revert后的回退也会生成一次commit历史

**方法二：**`git checkout 目标hash -b newbr`

```bash
git checkout 目标hash -b newbr
```

-  在目标回退版本上创建新分支进行开发，保持原main/master分支历史不变

如图：

![](/2025-finalproject/OceanCing/images/question2.1.2.png)

- 虽然创建了新分支，但是满足了在目标提交下继续进行开发和不改变原有历史的要求
- git log查看，最新提交成功回退到了“temp commit 01”

### 修改历史

**方法一：**在方法二的基础上强制将分支覆盖到main/master上

```bash
git checkout 目标hash -b newbr
git reset --hard newbr
```

- 可以实现回退到目标版本或者在回退到目标版本继续进行开发后再强制reset实现历史上的从目标版本开始继续开发

![](/2025-finalproject/OceanCing/images/question2.2.1.png)

如图：

- 可以看到，main本来的HEAD提交是‘’checkout br test“，在合并了分支之后，HEAD提交变为原来的“temp commit 01”

**方法二：**直接`git reset --hard`

```bash
git reset --hard <hash>
```

- 直接强制回退到上一次提交状态，删除暂存区和工作区修改

![](/2025-finalproject/OceanCing/images/question2.2.2.png)

如图：

- 开始的HEAD是指向“checkout br test”，在reset之后“HEAD is now at a6bab0e temp commit 01”



**方法三：**`git rebase -i HEAD~n`

```bash
git rebase -i HEAD~3
```

- 交互式变基，手动编辑最近几次提交

| 常用指令 | 作用                                           |
| -------- | ---------------------------------------------- |
| `reword` | 保留提交内容，但修改提交信息                   |
| `edit`   | 暂停变基过程，允许修改提交内容（如补充文件）   |
| `squash` | 将当前提交合并到上一个提交（保留提交信息）     |
| `fixup`  | 将当前提交合并到上一个提交（丢弃当前提交信息） |
| `drop`   | 删除该提交                                     |
|          |                                                |

- 需要使用命令`drop`删除想要撤销的提交的哈希值

![](/2025-finalproject/OceanCing/images/question2.2.3.1.png)

![](/2025-finalproject/OceanCing/images/question2.2.3.2.png)

如图：

- 在编辑器的交互式drop删除想要撤销的修改，保存后就可以回退提交
- 保存后发现`a6bab0e (HEAD -> main, newbr) temp commit 01`变成了最新提交，说明`checkout br test`这次修改已经被撤销

## 3. 合并分支的方式

我们已经知道了合并分支可以使用 merge，但这不是唯一的方法，给出至少两种不同的合并分支的方式

**方法一：**`git rebase`

```bash
git rebase
```

- 变基式合并，将一个分支合并到另一个分支的HEAD上

![](/2025-finalproject/OceanCing/images/question2.3.1.png)

如图：

- 分别在main和newbr里面进行修改提交，再rebase到main上实现合并
- （中间搞错了到main查看）
- 到newbr `ls`查看，发现多了`temp02.txt`文件，说明合并成功



**方法二：**`git cherry-pick <hash>`

```bash
(br)$ git log br --oneline
(main)$ git cherry-pick <br-hash>
```

- 使用log查看分支想要合并的目标提交
- 再checkout到主分支上选择性精准合并目标分支

- 类似这样：

```bash
*——*——*——*——*——*(main)
     \          \  
      *——*——*——*——*——*——*(br)
                  ^
                  |
               (a1b2c3)
```

可以选择将br的哪一次提交合并到main上，类似更加自由的`git merge`

![](/2025-finalproject/OceanCing/images/question2.3.2.png)

- （我先把我的newbr回退了一下再进行的演示）
- 我在newbr上创建了三次提交，但是我的目标是只选择第二次的提交进行合并
- 使用cherry-pick合并，但是我这里有点conflict,解决后成功合并
- log检查发现只合并到到了commit 02,说明选择性合并成功

**方法三：**`git merge`直接合并

- （其实到这里我的newbr和main已经很乱了 6_9 ，而且上一个方法和merge差不多，就不特别敲一遍了吧 >_< ） 
