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

