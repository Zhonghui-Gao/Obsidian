
---
dg-publish: true
dg-home: true
---

思路：
远程创建仓库
然后在fork一份liunx内核源码 v6.4.8
再根据armbian拿到的内核源码 编译 后生成 
git add 到仓库 git commit 
内核源码太大，修改git add 容量：
`git config http.postBuffer **524288000**`


git diff 比较 aimbian 究竟做了什么捏

chmod -R u+x 6.4__rockchip64_arm64 让可读可写
单独复制一份 6.4__rockchip64_arm64/

配 置 文 件 位 于 内 核 源 码 arch/arm/configs/目录

`cd` 

`make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- rockchip__xx__defconfig`
    
`make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- -j4 `

git diff  这里想法
创建两个branch
原生版本：main（官网push的）
hm3568版本：hm3568（cp 的）
具体操作：
创建分支
1. `git checkout -b hm3568`
由于创建分支会继承原始的仓库文件，所以先清除一下，然后在操作
2. `git rm -rf .git`
然后添加编译的文件
3. 
``` C
git add . 
git commit -m "mes"
git push -u linux-armbian hm3568
```


然后比较两个分支的所需要修改的文件的区别

git diff hm3568[path name] main [path name] > dtb1.patch
[branch1] : hm3568 
[branch2] : main
[patch name] : dtb1.patch 

生成两个警告：
```
warning: exhaustive rename detection was skipped due to too many files. 
warning: you may want to set your diff.renamelimit variable to at least 80290 and retry the command.
```

