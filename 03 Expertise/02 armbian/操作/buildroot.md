---
Date: 2023/10/18
result: okay
new: environment
type: tools
project: compile
rating: ⭐⭐⭐
status: 🌲done
---

编译工具链和内核，uboot。先记录，后面在补全

# 编译工具链
1. 下载Buildroot

下载Buildroot源码包，可以从官网下载最新版本：[https://buildroot.org/download.html ↗](https://buildroot.org/download.html)

2.  配置Buildroot

解压源码包：
						`tar -xzvf xxx.tar.gz` 
						`tar -jxvf xxx.tar.bz2`

进入解压后的目录，运行`make menuconfig` 进入配置菜单，根据需要选择目标系统的架构、交叉编译工具链、内核版本、根文件系统等选项。

![[menuconfig.jpg]]

![[arm.jpg]]

![[toolchain.jpg]]

Target options->Target Architecture 选择CPU架构....
ToolChain 选择C库

3. 保存设置 save，就可以进行`make toolchain -j4 V=0`

4. 编译完成后，交叉编译工具链将被安装在`output/host`目录下。

5. 加入环境变量：

```SHELL 
cd buildroot(dir)/output/host/bin
echo "export PATH=\$PATH:$(pwd)" >> ~/.bashrc
source ~/.bashrc
arm-linux-gcc --version
```


## 遇到的问题error

[make] :  `A compiler with support for C++11 language features is required`
解决问题：`sudo apt install g++ `
