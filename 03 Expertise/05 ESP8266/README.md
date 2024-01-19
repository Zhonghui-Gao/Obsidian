环境搭建：
vscode + platform

参考连接：[【ESP32DEVKITV1学习笔记】点亮一盏LED灯-CSDN博客](https://blog.csdn.net/weixin_44415862/article/details/122369703)

驱动：CP2102驱动 要去下载
[Legacy OS Software and Driver Packages (silabs.com)](https://community.silabs.com/s/article/legacy-os-software-and-driver-packages?language=en_US)

|**Windows XP/Vista Software**|**Link**|**Release Notes**|
|CP210x VCP Driver|[Driver](http://www.silabs.com/documents/public/software/CP210x_VCP_Windows_XP_Vista.zip)|[Release Notes](http://www.silabs.com/documents/public/release-notes/CP210x_VCP_Windows_XP_Vista_Release_Notes.txt)|
安装x64的驱动，就可以识别到了
按下boot键才能下载

开发板资料：
[DOIT ESP32 DevKit V1 Wi-Fi Development Board - Pinout Diagram & Arduino Reference - CIRCUITSTATE Electronics](https://www.circuitstate.com/pinouts/doit-esp32-devkit-v1-wifi-development-board-pinout-diagram-and-reference/)
重映射UART1
三个串口
esp接ttl转485模块连接温度变送器然后接PT100传感器

电压变耦，升压用的，在接外面的模块


温度传感器

霍尔传感器：GPIO27



继电器
电源接口:
VCC:接电源正极(3.3V)
GND:接电源负极
IN:高电平控制继电器吸合
负载接口:
反馈
NO:继电器常开接口，继电器吸合前悬空，吸合后与CO不顶部
COM:继电器公用接口
NC:继电器常闭接口，继电器吸合前与COM短接，吸合后悬空
![[继电器.png]]

IN：GPIO13

UART IMT
蓝TX
黄RX
4.常开点（NO）：该引脚正常时不连接到公共端，在继电器被激活时连接。

5.常闭点（NC）：该引脚正常时连接到公共端，并在继电器激活时断开。

6.公共端（COM）：在大多数情况下，此引脚连接到驱动应用的电源地。