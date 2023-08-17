|  工作指示灯  | GPIO端口号 |     工作情况     |
|:------------:|:----------:|:----------------:|
| 系统是否正常 |  GPIO0_C0  | 闪烁不同颜色表示 |

`dtc -I dtb -O dts  rk3568-hm.dtb  -o rk3568-hm.dts`
反编译dtb文件得到dts 修改

```
leds{
	gpio = xxx 

}
```

在编译回去dtb 复制到`/boot/dtb/rockchip/` 
然后 `reboot`

看见灯闪烁

打补丁方式具体见：[[linux-armbian]]

```BASH
./compile.sh  
BOARD=hm3568\ 
BRANCH=edge \
BUILD_DESKTOP=no \ 
BUILD_MINIMAL=no  \
KERNEL_CONFIGURE=no \
RELEASE=jammy  \
BUILD_ONLY="kernel"\
```

修改rk3568-hm-dts 文件 git diff 生成补丁 
放入
./userpatch/kernel/rockchip 


![[Pasted image 20230817122919.png]]
