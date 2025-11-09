# 学习总结

##              --------主要关于git方面

### 创建版本库

#### 1.找个地方创建一个空目录

> $ mkdir name
>
> $ cd name
>
> $ pwd ../../name

#### 2.初始化

> $ git init

#### 3.把文件添加到仓库（前提是文件一定要在name目录下）

> $ git add readme.txt
>
> $ git commit -m "wrote a readme file"

## 

### 版本回退

#### 1.查看历史修改记录

> $ git log

#### 2.回退到上一个版本

> $ git reset --hard HEAD^

##### 其中，`--hard`会回退到上个版本的已提交状态，`--soft`会回退到上个版本未提交的状态，`--mixed`会回退到上个版本已添加但未提交的状态

#### 3.回退之后，指定回到未来的某个版本

> $ git reset --hard 1094a

##### 其中，1094a是想回到的那个版本的版本号前几位

#### 4.查看历史命令

> $ git reflog



### 撤销修改

#### 场景1.改乱了工作区某个文件的内容，想直接丢弃工作区的修改

> git checkout -- file

#### 场景2.改乱了工作区某个文件的内容，并且添加到了暂存区，想丢弃修改

> git reset HEAD <file>

##### `git reset `在此处将暂存区的修改回退到工作区，HEAD表示最新版本。此时就回到了场景1，按场景1的方法来操作

#### 场景3.已经提交到版本库，想要撤销本次修改（前提是没有推送到远程库）

> 版本回退



### 删除文件

#### 当删除工作区的文件时，工作区和版本库不一致，需要从版本库中删除该文件，并且`git commit`

> $ git rm test.txt
>
> $ git commit -m "remove test.txt"

#### 若场景是删错了文件，则可用下述命令还原

> $ git checkout --test.txt



### 创建与合并分支

#### 1.创建并切换分支

> $ git branch dev
>
> $ git checkout dev

##### 也可以合并为一行命令

> $ git checkout -b dev

#### 2.查看当前分支

> $git branch

##### `git branch`会列出所有分支，当前分支前面会标一个`*`号

#####   然后就可以在当前分支上对文件做修改，并且正常提交

#### 3.将dev分支的工作结果合并到master分支上

> git merge dev

#### 4.   删除dev分支

> git vranch -d dev















