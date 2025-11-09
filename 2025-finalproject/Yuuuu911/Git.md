### 1. 若你已经修改了部分文件、并且将其中的一部分加入了暂存区，应该如何回退这些修改，恢复到修改前最后一次提交的状态？给出至少两种不同的方式
#### 使用git restore 指令取消暂存
![alt text](<image/Pasted image 20251031092611.png>)
![alt text](<image/Pasted image 20251031093111.png>)
- #### 使用git checkout HEAD 
![alt text](<image/Pasted image 20251031094007.png>)
### 2.若你已经提交了一个新版本，需要回退该版本，应该如何操作？分别给出不修改历史或修改历史的至少两种不同的方式
- #### 不修改历史git revert +版本号
![alt text](<image/Pasted image 20251031100237.png>)
![alt text](<image/Pasted image 20251031100300.png>)
- #### 修改历史git reset重置到指定的提交
![alt text](<image/Pasted image 20251031100801.png>)
### 3.我们已经知道了合并分支可以使用 merge，但这不是唯一的方法，给出至少两种不同的合并分支的方式
- #### git merge
![alt text](<image/Pasted image 20251031140243.png>)
- #### git rebase
![alt text](<image/Pasted image 20251031155110.png>)
![alt text](<image/Pasted image 20251031160024.png>)
- #### git cherry-pick
![alt text](<image/Snipaste_2025-10-31_17-48-36.png>)
![alt text](<image/Snipaste_2025-10-31_17-48-59.png>)
