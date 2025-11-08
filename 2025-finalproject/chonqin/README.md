# README

## 说明

这是一个在这门课程中学习的总结文档，包含：

- git的使用
- linux命令的使用
- bash脚本的使用

## **Git 的使用**

Git 是分布式版本控制工具，主要用于管理源码版本。

### **基本概念**

* **仓库（Repository）**：保存代码及历史版本。
* **工作区（Working Directory）**：你正在编辑的文件所在目录。
* **暂存区（Staging Area / Index）**：你准备提交的文件集合。
* **提交（Commit）**：将暂存区的内容保存到本地仓库。
* **分支（Branch）**：开发线，可以平行进行不同功能开发。
* **远程仓库（Remote Repository）**：例如 GitHub、GitLab，用于多人协作。


### **常用命令**

#### 初始化仓库

```bash
git init        # 在当前目录初始化本地仓库
git clone <url> # 克隆远程仓库到本地
```

#### 文件操作

```bash
git status      # 查看当前文件状态
git add <file>  # 添加文件到暂存区
git add .       # 添加所有修改的文件
git commit -m "描述信息"  # 提交暂存区到本地仓库
```

#### 查看历史

```bash
git log         # 查看提交历史
git log --oneline  # 简化历史显示
```

#### 分支管理

```bash
git branch      # 查看分支
git branch <name>  # 创建分支
git checkout <name> # 切换分支
git merge <name>    # 合并分支
```

#### 与远程仓库交互

```bash
git remote add origin <url>  # 添加远程仓库
git push -u origin main      # 推送到远程仓库
git pull origin main         # 拉取远程仓库最新内容
```

### **实用技巧**

* **撤销操作**：

  ```bash
  git checkout -- <file>      # 恢复工作区文件
  git reset HEAD <file>       # 从暂存区移除文件
  git revert <commit>         # 撤销某次提交（生成新提交）
  ```
* **分支协作**：

  * 每个新功能创建独立分支，完成后再合并到 `main` 或 `master`。
* **解决冲突**：

  * 编辑冲突文件 → `git add` → `git commit`

## **Linux 命令使用**

Linux 下常用命令可以分为 **文件操作、系统管理、网络操作、文本处理** 等几类。

### **文件与目录操作**

```bash
ls -l         # 查看目录详情
cd /path      # 进入目录
pwd           # 查看当前路径
mkdir dir     # 创建目录
rm file       # 删除文件
rm -r dir     # 删除目录
cp src dst    # 复制文件/目录
mv src dst    # 移动/重命名
```

###  **文件查看与编辑**

```bash
cat file       # 查看文件内容
less file      # 分页查看
head -n 10 file # 查看前10行
tail -n 10 file # 查看后10行
grep "text" file # 搜索文本
```

### **权限管理**

```bash
chmod +x file  # 添加可执行权限
chown user file # 改变文件所有者
```

###  **系统管理**

```bash
ps aux       # 查看进程
top          # 实时查看系统状态
kill <pid>   # 杀死进程
df -h        # 查看磁盘空间
free -h      # 查看内存使用
```

###  **网络命令**

```bash
ping www.baidu.com   # 测试连通性
ifconfig             # 查看网络信息
wget url             # 下载文件
```
