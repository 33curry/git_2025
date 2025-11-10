课程反思及总结

1. vim + shell + 脚本
vim基础
模式切换：i插入 / ESC返回 / :wq保存退出 / :q!强制退出
常用操作：u撤销 / Ctrl+r重做 / dd删除行 / yy复制行 / p粘贴
shell命令
导航：ls/cd/pwd/mkdir/rm -r
文本处理：cat/grep/awk/sed
脚本基础
结构：#!/bin/bash + 命令序列
变量：var=value / 引用$var
条件：if [ 条件 ]; then ... 
循环：for i in {1..5}; do ... done

2. Linux系统架构 + 命令行环境 + 数据整理
系统架构
内核 → shell → 文件系统（/根目录结构
命令行环境
配置文件：~/.bashrc（别名、环境变量
权限管理：chmod/chown
数据整理
grep "pattern" file 文本过滤
awk -F ',' '{print $1}' 字段处
sed 's/old/new/g' 文本替换

3. git
创建仓库git init git clone
暂存与提交
git status
git add 文件名
git commit -m 
git log --oneline
git reflog
git diff
git diff 版本号 版本号 文件名（可选）
git rm

4. CMake
CMakeLists.txt结构
cmake_minimum_required(VERSION 3.10)
project(MyProject)
add_executable(main main.cpp)
target_link_libraries(main PRIVATE ...)
编译流程
mkdir build && cd build
cmake .. → make
常用命令
include_directories() 添加头文件路径
target_include_directories() 目标级头文件
add_subdirectory() 子目录CMake
