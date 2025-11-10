**Git应用**

*NO.1*

1.使用 "git restore --staged <文件>..." 以取消暂存[图片2]

![2025-11-08 22-00-17屏幕截图.png](https://cdn4.winhlb.com/2025/11/08/690f4e23e2a8a.png)

2.git reset HEAD <文件>回退暂存区到工作区[图片1]

![2025-11-08 21-58-50屏幕截图.png](https://cdn4.winhlb.com/2025/11/08/690f4dae6ac6a.png)

*NO.2*
(不修改历史)

1.git revert <commit-hash>回到指定哈希值的历史[图片3]

![2025-11-08 21-59-29屏幕截图.png](https://cdn4.winhlb.com/2025/11/08/690f4e01cc6ce.png)

2.git checkout <commit-hash>分离头指针到制定哈希值的位置(在另一个分支)[图片4.5]

![BFEBE8D23AE6148DA1D52F7FA43FCC90.jpg](https://cdn4.winhlb.com/2025/11/08/690f4f03a8750.jpg)

![410E2F2206C1F7350BADC92FFA5070F4.jpg](https://cdn4.winhlb.com/2025/11/08/690f4eaf41ef3.jpg)

(修改历史)

1.git reset --hard  HEAD~1回到上一次提交，并删掉前面的历史[图片6]

![7F476EAB7C26D70E9CDEB488A8690A6C.jpg](https://cdn4.winhlb.com/2025/11/08/690f4d6787a9d.jpg)

2.gir reset --hard <commit-hash>回到指定哈希的历史，并删掉前面的历史

*NO.3*

1.git switch master
  git rebase <分支名>将分支加到master上

  git switch <分支名>
  git rebase master 将master的部分加到<分支名>上，使其成为线性的[图片7]

![DB3B41BCA893AD35D3D7AB8ECACD07D4.jpg](https://cdn4.winhlb.com/2025/11/08/690f4f2598fea.jpg)

2.git cherry-pick <commit-hash>将指定的提交合并到当前分支[图片8]

![B22A11EDF6CCC46DD1F72DFC623D6C9A.jpg](https://cdn4.winhlb.com/2025/11/08/690f4ed4aa845.jpg)

DJ20251106
