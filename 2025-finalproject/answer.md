

# answers

## 1. 回退未提交的修改

### 场景描述
已经修改了部分文件，并且其中一部分已经加入了暂存区，需要恢复到修改前最后一次提交的状态。

### 方式一：使用 `git restore`和 `git restore --staged`

```bash
# 回退暂存区的修改（取消暂存）
git restore --staged <file>
或
 git restore --staged .
# 回退工作区的修改
git  restore  <file>
或
git  restore .
```

### ![2025-11-09 15-20-56 的屏幕截图](2025-11-09 15-20-56 的屏幕截图.png)方式二：使用 `git reset` 和 `git checkout`

```bash

# 回退暂存区的修改（取消暂存）
git reset

# 回退工作区的修改
git checkout -- .
```
![2025-11-09 17-15-11 的屏幕截图](2025-11-09 17-15-11 的屏幕截图.png)

## # 2.回退已提交版本的多种方式

## 场景描述

已经提交了一个新版本，需要回退该版本。
### 不修改历史的方式

### 方式一：使用 `git revert`

#### 回退最新提交
```bash

# 创建一个新的提交来撤销最新的提交
git revert HEAD
或git revert <哈希值>
# 推送到远程仓库
git push origin master
```
![2025-11-09 15-54-19 的屏幕截图](2025-11-09 15-54-19 的屏幕截图.png)

## 使用 `git checkout` 命令

-  查看提交历史：`git log`（获取目标版本的提交哈希值）
-   直接切换版本：`git checkout <commit-hash>`（仅切换工作区文件，分支指针不动）
-   你看到的 “头指针分离于 e3c0e58”（`HEAD detached at e3c0e58`），表示当前处于**分离 HEAD 状态**
-   若要保留在分离状态下的新提交，需要基于当前 HEAD 创建一个新分支：`git checkout -b <新分支名>`，这样新分支会指向当前 HEAD 所在的提交，新提交也会被该分支跟踪。
-   接下来可以再合并分支
-   ![2025-11-09 17-06-29 的屏幕截图](2025-11-09 17-06-29 的屏幕截图.png)

## 修改历史的方式

### 方式一：使用 `git reset --mixed`（保留工作区修改）

```bash

# 混合重置，保留修改在工作区但取消暂存
git reset --mixed HEAD~1

# 查看状态，修改都在工作区
git status

# 可以选择重新提交或丢弃修改
git checkout -- .  # 丢弃所有修改

# 如果需要推送到远程
git push --force-with-lease origin master
```
![2025-11-09 16-28-39 的屏幕截图](2025-11-09 16-28-39 的屏幕截图.png)

### 方式二：使用交互式 rebase

```bash

# 重写最近1个提交的历史
git rebase -i HEAD~1

# 在编辑器中，将要删除的提交前的 "pick" 改为 "drop" 或 "d"
# 保存并退出后，历史将被重写

# 强制推送到远程
git push --force-with-lease origin master
```
![2025-11-09 16-31-17 的屏幕截图](2025-11-09 16-31-17 的屏幕截图.png)

## 3.合并分支的多种方式

### 1.使用 `git rebase` 进行变基合并

**原理**：将当前分支的提交 “移植” 到目标分支的最新提交之后，形成线性的提交历史（避免 merge 产生的合并节点）。

**操作流程**：



```bash
# 切换到需要合并到目标分支的分支（如 feature 分支）
git checkout feature-branch

# 将当前分支变基到目标分支（如 main 分支）
git rebase main

# 若过程中出现冲突，解决冲突后执行：
git add <冲突文件>
git rebase --continue  # 继续完成变基
# （若需放弃变基，执行 git rebase --abort）

# 变基完成后，将结果推送到远程（若远程已有该分支，可能需要 -f 强制推送）
git push origin feature-branch
```
![2025-11-09 17-23-12 的屏幕截图](2025-11-09 17-23-12 的屏幕截图.png)

### 2. 使用 `git cherry-pick` 选择性合并单个提交

**原理**：从目标分支中挑选一个或多个特定的提交，应用到当前分支（无需合并整个分支的所有提交）。

**操作流程**：

bash

```bash
# 切换到接收提交的分支（如 main 分支）
git checkout main

# 查看目标分支（如 feature 分支）的提交历史，获取需要合并的提交哈希
git log feature-branch

# 挑选单个提交应用到当前分支
git cherry-pick <commit-hash>

# 若需挑选多个连续提交，可指定范围（前开后闭）
git cherry-pick <start-commit-hash>..<end-commit-hash>

# 若出现冲突，解决后执行：
git add <冲突文件>
git cherry-pick --continue  # 继续应用提交
# （若需放弃，执行 git cherry-pick --abort）
```

![2025-11-09 16-44-52 的屏幕截图](2025-11-09 16-44-52 的屏幕截图.png)

![2025-11-09 16-40-52 的屏幕截图](2025-11-09 16-40-52 的屏幕截图.png)
