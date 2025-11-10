# question1

若你已经修改了部分文件、并且将其中的一部分加入了暂存区，应该如何回退这些修改，恢复到修改前最后一次提交的状态？给出至少两种不同的方式

方式一:用reset --hard :

![](./photos/8b3b309aeb16677f5da702315f5bfbf4.png)

方法二：用restore取消缓存后恢复

![](./photos/4b19fd58-8256-499a-8153-9447917d5d2a.png)





# question2

若你已经提交了一个新版本，需要回退该版本，应该如何操作？分别给出不修改历史或修改历史的至少两种不同的方式

## 修改历史：

方式一：用reset ,如果只是回退版本不用回退工作区和暂存区，哪个参数都可以

![](./photos/7bf076a4-169d-43dc-8ce5-fcdd4c5c23fa.png)





方式二：用checkout

![](./photos/10173944-89d7-4a16-af26-a423609044b4.png)

## 不修改历史

方式一：用revert

![](./photos/91201897-b79e-4d8d-835c-ea4ba5d76ed6.png)

# question 3

我们已经知道了合并分支可以使用 merge，但这不是唯一的方法，给出至少两种不同的合并分支的方式

## 方式一：rebase





![](./photos/1867e4ed-cf0a-4c31-a3b3-f4a61068c50c.png)





## 方式二：merge，与rebase用法基本一样







## 方式三：用cherry-pick





![](./photos/6b940587-9c04-4c43-9da0-9db82102dc07.png)

