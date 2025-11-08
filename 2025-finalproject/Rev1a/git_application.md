# Git Applications

## Part A

### 若你已经修改了部分文件、并且将其中的一部分加入了暂存区，应该如何回退这些修改，恢复到修改前最后一次提交的状态？给出至少两种不同的方式

> 下面的EXAMPLES截图 都能在 Git Bash的安装目录下找到
>
> 路径为  :  Git/mingw64/share/doc/git-doc/

#### 方法1

```
git restore --staged <文件名>   //撤回暂存

git restore <文件名>            //回退修改

                               //对已修改，已暂存和已修改，未暂存的文件回退
                               
         // 可通过 git restore --help 在本地找到对应的html
```

![](/images/git_restore.png)

![](screenshot\restore.png)

#### 方法2

```
git checkout -- 对应文件        //对已修改，未暂存的文件回退到上次commit的版本
```

<img src="/images/git_checkout.png" style="zoom: 33%;" />

![](screenshot\checkout.png)

---



## Part B

### 若你已经提交了一个新版本，需要回退该版本，应该如何操作？分别给出不修改历史或修改历史的至少两种不同的方式

#### 方法1

```
git revert HEAD              //不修改历史的方法来回退上一次提交的版本
```

![](/images/git_revert.png)

![](screenshot\revert.png)

#### 方法2

```
git reset --hard HEAD^       //修改历史记录的回退
      
 //会撤销工作区中所有未提交的修改内容，将暂存区与工作区都回到上一次版本，并删除之前的所有信息提交
```



![](screenshot\reset_1.png)

---



## Part C

### 我们已经知道了合并分支可以使用 merge，但这不是唯一的方法，给出至少两种不同的合并分支的方式

#### 方法1

```
git rebase <commit>         //将对应分支切换到主分支，从而使提交历史更整洁，线性 
```

![](screenshot\rebase.png)

#### 方法2

```
git cherry-pick <对应哈希>   //只会将某部分代码变动进行同步
```

![](screenshot\cherry.png)

![](screenshot\cherry2.png)

![](screenshot\cherry3.png)



---



