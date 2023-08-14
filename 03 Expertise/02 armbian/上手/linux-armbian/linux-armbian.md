
---
dg-publish: true
dg-home: true
---


远程创建仓库
然后在fork一份liunx内核源码 
再根据armbian拿到的内核源码 编译 后生成 
git add 到仓库 git commit 


git diff 比较 aimbian 究竟做了什么捏

chmod -R u+x 6.4__rockchip64_arm64 让可读可写
单独复制一份 6.4__rockchip64_arm64/

`cd` 
`make ARCH=arm64 CROSS_COMPILE=aarch64-linux-gnu- -j4 `

git diff  这里想法
创建两个branch
原生版本：main（官网push的）
hm3568版本：armbian（cp 的）

然后比较两个分支的区别