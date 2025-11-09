# 学习总结

## vim

### 学习过程
这是一个我久闻大名的工具，在此前学习linux的过程中没少照着教程使用vim来编辑文件，但一直没能掌握，只觉得操作繁琐。
进一步学习发现在掌握了一些基本按键后vim就是一个启动快捷且功能强大的工具。

### 常用模式切换
- `i` - 进入插入模式
- `o` - 换行进入插入模式
- `Esc` - 返回命令模式
- `:` - 进入命令行模式

### 基本操作
- `h/j/k/l` - 左/下/上/右移动光标
- `yy` - 复制当前行
- `dd` - 删除当前行
- `p` - 粘贴
- `u` - 撤销
- `Ctrl+r` - 重做

### 文件操作
- `:w` - 保存文件
- `:q` - 退出
- `:wq` - 保存并退出
- `:q!` - 强制退出不保存
- 
## shell

### 学习过程
此前只是接触过linux的终端，对shell脚本并没有详细的认知。
通过本课程学习shell脚本的基本语法和常用技巧，学会了编写简单的自动化脚本来提高工作效率。

### Shell 脚本基础

#### 脚本结构
```bash
#!/bin/bash
# 这是注释，上一行用来指定执行脚本的解释器
echo "Hello, World!"
```

#### 变量
```bash
name="John"
echo "Hello, $name"
echo "Hello, ${name}"
```

#### 条件判断
```bash
if [ -f "file.txt" ]; then
    echo "文件存在"
else
    echo "文件不存在"
fi
```

#### 循环
```bash
# for 循环
for i in {1..5}; do
    echo "Number: $i"
done

# while 循环
count=0
while [ $count -lt 5 ]; do
    echo $count
    count=$((count + 1))
done
```

#### 子shell
```bash
{
    source ./sub.sh
}
```

### 常用命令
- `chmod +x script.sh` - 给脚本添加执行权限
- `./script.sh` - 运行脚本
- `bash script.sh` - 使用 bash 运行脚本

### 实用技巧
- `$?` - 获取上一个命令的退出状态
- `$#` - 获取参数个数
- `$@` - 获取所有参数
- `grep` - 文本搜索
- `sed` - 流编辑器
- `awk` - 文本处理工具

## cmake

### 基本命令
- `cmake .` - 在当前目录生成构建文件
- `cmake -B build` - 在 build 目录生成构建文件
- `cmake --build build` - 编译项目
- `make` - 执行编译（使用 Makefile）

### CMakeLists.txt 基本语法
```cmake
cmake_minimum_required(VERSION 3.10)
project(ProjectName)
add_executable(app main.cpp)
```

## git

### 基本操作
- `git init` - 初始化仓库
- `git clone <url>` - 克隆远程仓库
- `git add .` - 添加所有文件到暂存区
- `git commit -m "message"` - 提交更改
- `git status` - 查看状态
- `git log` - 查看提交历史

### 分支操作
- `git branch` - 查看分支
- `git branch <name>` - 创建分支
- `git checkout <branch>` - 切换分支
- `git merge <branch>` - 合并分支

### 远程操作
- `git push origin <branch>` - 推送到远程
- `git pull` - 拉取远程更新
- `git remote -v` - 查看远程仓库
