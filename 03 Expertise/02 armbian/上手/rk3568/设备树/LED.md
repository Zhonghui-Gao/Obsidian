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

