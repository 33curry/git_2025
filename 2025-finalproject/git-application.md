

#Learning Courses Record
# Git Application Answers

## Question 1: Reverting Modifications

### Method 1: Using git restore
Discard changes in working directory for specific file
git restore <filename>
Discard all changes in working directory
git restore .
![Method 1: git restore step 1](images/method1-restore-1.png)
![Method 1: git restore step 2](images/method1-restore-2.png)
![Method 1: git restore step 3](images/method1-restore-3.png)

### Method 2: Using git reset and git checkout
Unstage files but keep changes in working directory
git reset
Discard all changes in working directory
git checkout -- .
![Method 2: git reset and checkout](images/method2-reset-checkout.png)

### Method 3: Using git reset --hard
Completely reset to last commit (loses all changes)
git reset --hard HEAD
![Method 3: git reset --hard](images/method3-reset-hard.png)

## Question 2: Reverting Commits

### Without Modifying History:

#### Method 1: Using git revert
Create a new commit that undoes the changes
git revert <commit-hash>
#### Method 2: Using git restore with specific commit
Restore files to previous commit state
git restore --source=HEAD~1 <filename>

![Revert without modifying history 1](images/question2-method1-1.png)
![Revert without modifying history 2](images/question2-method1-2.png)

### Modifying History:

#### Method 1: Using git reset –soft
Move HEAD back but keep changes staged
git reset --soft HEAD~1

#### Method 2: Using git reset –hard
Completely remove the last commit and all changes
git reset --hard HEAD~1

![Revert modifying history 1](images/question2-method2-1.png)
![Revert modifying history 2](images/question2-method2-2.png)

## Question 3: Branch Merging Methods

### Method 1: Merge Commit
Standard merge creating a merge commit
git checkout main
git merge feature-branch

![Standard merge](images/question3-merge-1.png)

### Method 2: Rebase and Fast-forward
Rebase feature branch onto main
git checkout feature-branch
git rebase main
Fast-forward merge
git checkout main
git merge feature-branch

![Rebase and fast-forward](images/question3-merge-2.png)

### Method 3: Squash Merge
Squash all commits from feature branch into one
git checkout main
git merge --squash feature-branch
git commit -m "Squashed feature branch"

![Squash merge](images/question3-merge-3.png)


# Shell基础知识部分

## 通配符

## 正则表达式

## 管道符号 |

# Markdown语法手记

+ - [ ] 和 - [x] 表示动态的选项框
## 表示标题

# Git基础知识部分

## Gitghub托管平台

## 了解集中式和分布式版本控制

## 本地仓库与远程仓库、推送、创建
### 基础仓库（通常是原始仓库）和目标分支（main或者master）

## 协同开发工作流程、remote、push、clone、fetch、pull

## 暂存区的概念

## diff命令

## rm命令和文件删除原理

## mv命令和文件改名原理

## log命令

## 文件忽略

## add命令原理

## commit命令原理

## 分支创建查看删除

## 分支checkout切换switch切换及其影响

## checkout撤销修改和强制切换

## Git分支状态储存、Git储存的使用、与暂存区的关系、原理

## 远程分支跟踪

## 工作树

## 分支合并、快进式与典型式

## 代码冲突、分类、远程协作代码冲突

## Git merge命令

## Git还原restore命令

## 修正提交amend命令

## 数据回退reset命令

## 配置项config命令

# 开发问题部分

## 找到Git目录并记住他的位置
- Ubuntu终端的默认起始目录是家目录，也叫家目录，简写形式是~，完整路径是/home/用户名
- pwd命令可以用来打印当前目录，输出/home/用户名，其中第一个/表示根目录，是所有目录的父目录

## 小技巧
- 自动补全名称 Tab
- 使用之前键入的命令 ⬆ ⬇

