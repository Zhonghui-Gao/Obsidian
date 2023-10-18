---
Date: 2023/10/18
result: okay
new: environment
type: problem
project: configure
rating: ⭐⭐
status: 🌲done
---

# 烧录笔记本

|    笔记本     | 工具         | 系统版本      |
|:-------------:| ------------ | ------------- |
| thinkpad E450 | balenaEtcher | LUbuntu 23.04 |

· balenaEtcher 用U盘烧录系统 (Fn+F1 bios)
· 笔记本进入bios界面 笔者用的thinkpad 为F12进入菜单，在Boot Menu中选择**USB HDD**，将U盘作为启动盘。
![[Pasted image 20230716123151.png]]
· 参考连接：[联想thinkpad怎么设置u盘启动 联想笔记本thinkpad怎么设置u盘启动-电脑技术吧 (tpbz008.cn)](http://www.tpbz008.cn/post/18619.html) 

参考分区： https://arch.icekylin.online/

下面的分区要参考上面的连接 有说明

|  /   |   /boot   | linuxswap | /home  | free    | 
|:----:|:---------:|:---------:|:------:| --- |
| 128G | 1G(256MB) |    50G    | 剩下的 |   2G（以备不需）  |

# 安装软件环境

安装clash软件
· github 链接： 将linux 版本下载 [Releases · Fndroid/clash_for_windows_pkg (github.com)](https://github.com/Fndroid/clash_for_windows_pkg/releases)
解压命令：
`sudo tar -xzf clash xxx`
`./cfw`
设置开机启动即可，加入机场，笔者用的大航海的机场 非常好用捏。

系统代理 配置端口：
`$env:http_proxy="http://127.0.0.1:7890"`
`$env:https_proxy="http://127.0.0.1:7890"`

写入/etc/profile/
source 就可以
```SHELL
export http_proxy=http://127.0.0.1:7890 
export https_proxy=http://127.0.0.1:7890
export all_proxy=socks5:http://127.0.0.1:7890
```

# git：使用方法



`git init`
`git clone http`

`ssh-keygen -t rsa -C "404597513@qq.com"`
`cat ~/.ssh/id_rsa.pub`
在github配置ssh

`git remote add origin git@github.com:Zhonghui-Gao/new.git`
`git remote add new git@github.com:Zhonghui-Gao/new.git`


`git add .`
`git status`
`git commit -m`
`git push -u 分支 仓库`
`touch .gitignore` // 忽略大文件

# armbian
- **  
    The officially supported** compilation environment is [Ubuntu Jammy 22.04.x amd64](https://www.releases.ubuntu.com/jammy/ubuntu-22.04.2-live-server-amd64.iso)
找到Lubuntu分支


# 实现远程连接方案：
找了很多ssh的方案 
						最后发现不如`**向日葵**`
浪费了很多时间找方案和配置环境，向日葵不仅能直连还能传输文件。这里建议使用用路由器构建个局域网，低延时。   

# 安装 balenaEtcher 

[balena-io/etcher: Flash OS images to SD cards & USB drives, safely and easily. (github.com)](https://github.com/balena-io/etcher)










