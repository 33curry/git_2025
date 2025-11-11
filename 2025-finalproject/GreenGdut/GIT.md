# GIT应用

## 问题一回答：

在所有版本的git中，我们可以使用命令

```bash
git reset <filename>
```

​	

在较新版本中，我们也可以使用命令

```bash
git restore --staged <filename>
```

*实例演示：（请忽视其中某次错误的命令演示）*

![](/home/green_gdut/Liuyanchen-work/2025-finalproject/2025-11-09 15-56-15 的屏幕截图.png)

## 问题二回答：

首先，利用log命令获取提交历史，比如：

```bash
git log --oneline
```

记住所得信息里附带的commit id；

若不要修改历史，则：

```bash
git reset head <commit id>
```

git reset实际上有三种模式，对应的对于暂存区的文件等的处理略有不同，如果没有指定模式，则默认使用--mixed模式。

若要保留修改历史，则可使用

```bash
git revert <commit id>
```

## 问题三回答：

我们可以使用

```bash
git cherry-pick <分支名>
```

这样就会把指定的分支线性合并到当前分支。

![](/home/green_gdut/Liuyanchen-work/2025-finalproject/2025-11-09 23-08-04 的屏幕截图.png)

也可以使用

```bash
git rebase <分支名>
```

这样就可以把当前分支复制到指定分支的最新提交之后。

例如：

指定分支：A - B - C;

当前分支：A - D - E;

rebase后：

指定分支：A - B - C - D - E

这需要两个分支存在“分歧”。比如这里，两个分支在A后发生分歧，rebase的作用就是把分支合并到分歧之后从而解决分歧。

如果分歧不存在，呈现线性关系，那么rebase是无效的。

![](/home/green_gdut/Liuyanchen-work/2025-finalproject/2025-11-09 23-50-29 的屏幕截图.png)

实例解析：我们在分支new_test_branch里添加新的提交。然后回到分支dev添加测试文件test.md,同样的，新增提交。此时两个分支存在分歧，使用rebase后，我们回到dev分支，可以看到右下角增加了一个“test.md”。这表明rebase完成了。
