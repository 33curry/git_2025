# Dynamic X Lesson 

<a id="title"></a>

##  1.1 Markdown基本语法



### 1.1.1  标题

Markdown里"#"后面是标题，标题有一到六级，"#"的个数与其级数相同

```
#          一级标题
##         二级标题
###        三级标题
####       四级标题
#####      五级标题
######     六级标题
！ 没有七级标题 ！
```



---



### 1.1.2 字体



```
***   粗斜体   ***
**    粗体      **
*     斜体       *
_     斜体       _
~     下标小写    ~
^     上标小写    ^
`     粗阴影      `
==    高亮       ==

```



---



### 1.1.3 分割线

---

分割线是

```--
--
```



---



### 1.1.4 引用和注释

```
>      这是注释，导出pdf等其他格式可见
<!--   这也是注释，导出pdf等其他格式不可见       -->
```



---



### 1.1.5 列表

``` 
- 或 * 是无序列表

```

- 无序列表 

  - 有序列表:

  - 1. 数字 + " . "  + 内容 是有序列表

       

---

### 1.1.6 链接

#### 1.1.6.1 md内跳转

```
[<跳转的名字>]
下面蓝标的全文为 -->  [<回到开头>](#title)
按住Ctrl 左键即可跳转
```

[<回到开头>](#title)

脚注跳转 [^test1]









[^test1]: Link To "脚注跳转"



#### 1.1.6.2 链接跳转

[git_checkout](images/git_checkout.png)

```
上面链接的实际代码    [git_checkout](images/git_checkout.png)
```

Ctrl+左键能打开对应图片



---



## 1.2 Git总结

### 1.2.1 常用命令

```
git init	                  初始化一个 Git 仓库
git clone <url>	              从远程仓库复制项目到本地
git status	                  查看当前状态（修改、暂存等）
git add <file>	              将文件加入暂存区
git commit -m "message"	      提交修改并附上说明
git log	                      查看提交历史
git branch	                  查看或创建分支
git checkout <branch>	      切换分支
git merge <branch>	          合并分支
git push	                  上传到远程仓库
git pull                      从远程仓库更新到本地




最常用:
git pull
git status
git add .
git commit -m"更新说明"
git push origin main

```

### 1.2.2 GitHub

```
https://github.com/Rev1a/Remote-Coding

个人简单的Git的实际应用
用于在多台设备间同步Code文件夹
```





































