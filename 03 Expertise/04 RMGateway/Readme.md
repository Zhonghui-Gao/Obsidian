RMGWClient.xml 放到/bin 下 配置文件 

压缩：`tar czvf xxx.tgz`
解压：`tar xzvf xxx.tgz`
第三方库：3rdparty
mqtt service

.xml 放到/opt/生成的文件

《QT MQTT》 

[Qt 5.15 Ubuntu安装 [转]_ubuntu安装qt5.15_NGC_2070的博客-CSDN博客](https://blog.csdn.net/baidu_41388533/article/details/128135334)

下载qt5.15.2 然后配置 kit配置gcc和g++ 文件

sudo apt-get install g++ 配置 kit


# error 
```shell
Project ERROR: json-c development package not found

make: *** [/home/gao/workspace/build-RMGateway-Desktop_Qt_5_15_2_GCC_64bit-Debug/Makefile:42: sub-RMGWClient-qmake_all] Error 3
21:41:58: The process "/usr/bin/make" exited with code 2.
Error while building/deploying project RMGateway (kit: Desktop Qt 5.15.2 GCC 64bit)
When executing step "qmake"
```

缺少json-C:
```SHELL
安装依赖
sudo apt-get install libjson-c-dev
安装pkg工具
sudo apt install pkg-config
```

```shell
6:10: fatal error: curl/curl.h: No such file or directory
    6 | #include <curl/curl.h>
```

安装依赖：
```SHELL
sudo apt-get install libcurl4-openssl-dev
```

