# 收获

**<u>最大的帮助</u>**：**独立解决问题的能力增强了，提问题变得规范了（大概），学习效率提高了**

------

## 1一切的开始——ubuntu

### 遇到困难

- **u盘无法格式化为fat32数据类型**
- **找不到vmd开关**
- **bios面板第一次打开的方式不太一样**
- **关闭vmd后不能打开win11**
- **上不了无线网**
- **驱动冲突，被迫重装ubuntu**

### 解决问题

- **学习diskpart、磁盘管理器的用法，只分配不大于32g的空间**
- **接触csdn社区，上面有很多对应的解决方案**
- **取舍，有时候没有linux的网卡驱动，那就氪金买无线网卡吧**
- **重装ubuntu的速度比之前快很多**

## 2我的c++呢？——shell

### 遇到困难

- **语法格式差异有点儿大**
  - **定义变量**
  - **条件/流程控制语句**
  - **运算符**
  - **各种各样的-参数**
  - **第一次（疑似？）接触正则表达式**	

### 解决问题

#### 2.1基本的操作

- ```bash
  mkdir #创建文件夹
  man #查看操作手册
  rm #删除一个文件 rmdir删除一个空文件夹 rm -rf删除整个文件夹
  echo "内容"#会展开变量
  echo '内容'#原封不动输出
  $() #执行括号中的命令并返回
  $变量 #返回变量的值
  cat "文件路径"#输出文件内容
  exec 1 > 文件名或者另外一个输出 #重定向输出
  ls #-l长格式 -a全部文件 -t修改时间顺序 -r逆序 -u访问时间排序 -h人类可读数据大小
  ```
  

#### 2.2流程与判断语句

- ```bash
  while 条件   ；do      
  done
  
  if [条件] ;then 
  else  
  fi
  #-ne -gt -ge -lt -le
  for 变量 in item1 item2 
  do
  done
  #例 for fruit in apple banana for i in {1..5}/{a..c}
  ```

#### 2.3文本处理工具

- ```bash
  #vim and grep and awk and sed
  vim 文件名 #i插入模式 esc状态下u 撤销 d删除整行
  grep -eoP #e启用转义字符 o输出匹配内容 P启用扩展正则表达式
  sed s/被换掉的/替代换掉的 文件名 #-i 可表示原地替换
  awk '{$1=" ";print substr($0,2)}' |sort -n |tail -n 10 #$1表示第一个字段，substr后面的$0表示正行内容。2表示从第二个字符开始截取。sort -n表示按大小排序。tail -n 10表示截取最后十行
  
  #注：awk语法中的if是 if （），条件判断代码格式类似c++
  ```

#### 2.4正则表达式

- ```bash
  #正则表达式
  * #匹配任意个字符
  ** #匹配任意中间目录
  ？ #匹配单个字符
  . #除换行符外任意单个字符
  [abc] #匹配a或b或c
  [0-9] #匹配0-9中一位
  ！ #！后的内容不会被忽略
  \d #表示数字
  + #匹配1个到多个前面的字符
  ```

#### 2.5终端相关

- ```bash
  #终端相关
  tmux #终端服用软件
  ctrl b "" #水平分割
  ctrl b % #垂直分割
  ctrl b 方向键 #移动
  ```

#### 2.6杂项

- ```bash
  #杂项
  alias ""='' #启用别名 ，加上>> ~/.bashrc可在全局生效
  sleep xx #休眠当前进程xx秒
  bg fg #后台/前台运行
  ctrl c/z #终止/暂停运行
  kill 进程id
  pgrep -fa #查找进程 -f表示匹配完整名字与参数 a表示显示完整命令行，如进程ID加完整命令
  ps aux | grep "关键词" | grep -v grep #查找进程，最后一行的作用是把grep进程排除在外
  #定义不用类型关键字，使用要$
  ```



## 3魔法最有用的一集——git

### 3.1从入门开始

```bash
#创建仓库
git init
git clone

```

```bash
#暂存与提交
git status
git add 文件名/. #.表示当前目录及所有子目录所有文件
git commit -m "提交说明" #-am可同时完成暂存和提交
git log --oneline 
git reflog
git diff 
git diff 版本号 版本号 文件名（可选）
git rm 文件名 #同时删除工作区和暂存区中的文件，加--cached 只从版本库删除文件
#注：HEAD表示当前分支最新修改，~/^表示上一个版本，~2表示上二个版本
```

### 3.2理解版本，爱上版本(?)

```bash
#切换分支
git switch
#撤销操作
git restore --staged
git restore
git reset HEAD
git checkout --
#回退操作
git revert
git checkout
git reset
git rebase -i
#分支操作
git branch #创建分支/查看分支
git branch -d/-D #-d表示删除已合并的分支 -D表示强制删除分支
git checkout -b 分支名 版本号
#合并操作
git merge
git rebase

```

### 3.3远程仓库的使用

```bash
#当以clone方式进行时
git pull 
git push
#当以关联的方式进行时
git remote add 远程仓库别名 <url>
git remote -v
git push -u 别名 本地仓库分支名：远程仓库分支名
git pull 别名 远程仓库分支名：本地仓库分支名
```

------

**写出来发现自己学到了很多很多**

------

待开发
