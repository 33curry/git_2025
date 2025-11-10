# Git应用

### 第一题

#### 第一种方式：

`git reset HEAD <文件名>`

![image-20251108150458542](/home/robot/.config/Typora/typora-user-images/image-20251108150458542.png)

![image-20251108150516219](/home/robot/.config/Typora/typora-user-images/image-20251108150516219.png)

![image-20251108150528502](/home/robot/.config/Typora/typora-user-images/image-20251108150528502.png)

![image-20251108150549873](/home/robot/.config/Typora/typora-user-images/image-20251108150549873.png)

#### 第二种方式：

`git reset --hard HAED`

![image-20251108150612294](/home/robot/.config/Typora/typora-user-images/image-20251108150612294.png)

![image-20251108150618459](/home/robot/.config/Typora/typora-user-images/image-20251108150618459.png)

![image-20251108150627550](/home/robot/.config/Typora/typora-user-images/image-20251108150627550.png)

![image-20251108150650453](/home/robot/.config/Typora/typora-user-images/image-20251108150650453.png)

![image-20251108151447826](/home/robot/.config/Typora/typora-user-images/image-20251108151447826.png)

### 第二题

#### 不修改历史

##### 第一种方法

`git revert <哈希值>`

![image-20251108151504856](/home/robot/.config/Typora/typora-user-images/image-20251108151504856.png)

![image-20251108151510699](/home/robot/.config/Typora/typora-user-images/image-20251108151510699.png)

![image-20251108151524832](/home/robot/.config/Typora/typora-user-images/image-20251108151524832.png)

![image-20251108151531038](/home/robot/.config/Typora/typora-user-images/image-20251108151531038.png)

##### 第二种方式：

`git reset --soft <哈希值>`

`git reset --hard <哈希值>`

![image-20251108151554911](/home/robot/.config/Typora/typora-user-images/image-20251108151554911.png)

![image-20251108151600479](/home/robot/.config/Typora/typora-user-images/image-20251108151600479.png)

![image-20251108151605846](/home/robot/.config/Typora/typora-user-images/image-20251108151605846.png)

![image-20251108151611135](/home/robot/.config/Typora/typora-user-images/image-20251108151611135.png)

#### 修改历史

##### 第一种操作

`git reset --hard <哈希值>`

![image-20251108153031914](/home/robot/.config/Typora/typora-user-images/image-20251108153031914.png)

![image-20251108153043306](/home/robot/.config/Typora/typora-user-images/image-20251108153043306.png)

![image-20251108153049729](/home/robot/.config/Typora/typora-user-images/image-20251108153049729.png)

![image-20251108153057233](/home/robot/.config/Typora/typora-user-images/image-20251108153057233.png)

##### 第二种方式

`git rebase -i <哈希值>`

![image-20251108153143484](/home/robot/.config/Typora/typora-user-images/image-20251108153143484.png)

![image-20251108153218775](/home/robot/.config/Typora/typora-user-images/image-20251108153218775.png)

![image-20251108153157619](/home/robot/.config/Typora/typora-user-images/image-20251108153157619.png)

![image-20251108153225765](/home/robot/.config/Typora/typora-user-images/image-20251108153225765.png)

![image-20251108153231215](/home/robot/.config/Typora/typora-user-images/image-20251108153231215.png)

![image-20251108153239383](/home/robot/.config/Typora/typora-user-images/image-20251108153239383.png)

![image-20251108153244139](/home/robot/.config/Typora/typora-user-images/image-20251108153244139.png)

## 第三题

#### 第一种解法

`git rebase`

![image-20251108153337961](/home/robot/.config/Typora/typora-user-images/image-20251108153337961.png)

#### 第二种解法

`git cherry-pick <哈希值>`

![image-20251108153350516](/home/robot/.config/Typora/typora-user-images/image-20251108153350516.png)

![image-20251108153356184](/home/robot/.config/Typora/typora-user-images/image-20251108153356184.png)