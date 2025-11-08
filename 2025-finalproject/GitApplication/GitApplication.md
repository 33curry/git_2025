**Git应用**

*NO.1*

1.使用 "git restore --staged <文件>..." 以取消暂存[图片2]

![5503D1D93EC927A8CBE29F86D85460CA](GitApplication.assets/5503D1D93EC927A8CBE29F86D85460CA.jpg)

2.git reset HEAD <文件>回退暂存区到工作区[图片1]

![E7FE5D00A3E8C6F64FE3C402381D83C9](GitApplication.assets/E7FE5D00A3E8C6F64FE3C402381D83C9.jpg)

*NO.2*
(不修改历史)

1.git revert <commit-hash>回到指定哈希值的历史[图片3]

![4A6A3EDC6F3049B2E281621236E8A32D](GitApplication.assets/4A6A3EDC6F3049B2E281621236E8A32D.jpg)

2.git checkout <commit-hash>分离头指针到制定哈希值的位置(在另一个分支)[图片4.5]

![BFEBE8D23AE6148DA1D52F7FA43FCC90](GitApplication.assets/BFEBE8D23AE6148DA1D52F7FA43FCC90.jpg)

![410E2F2206C1F7350BADC92FFA5070F4](GitApplication.assets/410E2F2206C1F7350BADC92FFA5070F4.jpg)

(修改历史)

1.git reset --hard  HEAD~1回到上一次提交，并删掉前面的历史[图片6]

![7F476EAB7C26D70E9CDEB488A8690A6C](GitApplication.assets/7F476EAB7C26D70E9CDEB488A8690A6C.jpg)

2.gir reset --hard <commit-hash>回到指定哈希的历史，并删掉前面的历史

*NO.3*

1.git switch master
  git rebase <分支名>将分支加到master上

  git switch <分支名>
  git rebase master 将master的部分加到<分支名>上，使其成为线性的[图片7]

![DB3B41BCA893AD35D3D7AB8ECACD07D4](GitApplication.assets/DB3B41BCA893AD35D3D7AB8ECACD07D4.jpg)

2.git cherry-pick <commit-hash>将指定的提交合并到当前分支[图片8]

![B22A11EDF6CCC46DD1F72DFC623D6C9A](GitApplication.assets/B22A11EDF6CCC46DD1F72DFC623D6C9A.jpg)

DJ20251106
