# 任务1

## 要求：撤销修改

#### 方法1：restore

<img src="./images/revoke1.png"  />

#### 方法2reset HEAD和checkout --搭配

![](./images/revoke2.png)



# 任务2

## 要求：回退版本（修改历史和不修改历史各两种）

### 不修改历史

#### 方法1revert反转操作

![](./images/back-n-mod-history1.png)

#### 方法2checkout分离头指针

![](./images/back-n-mod-history2.png)

### 修改历史

#### 方法1reset

![](./images/back-mod-history1.png)

#### 方法2rebase -i

*在此图前进行rebase -i操作，进入文件编辑界面*

![](./images/back-mod-history2.1.png)

![](./images/back-mod-history2.2.png)

# 任务3

## 要求：合并分支

#### 方法1 merge

![](./images/merge1.png)

#### 方法2 rebase

![](./images/merge2.png)