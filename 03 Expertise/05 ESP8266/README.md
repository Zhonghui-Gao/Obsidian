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

