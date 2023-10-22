RMGWClient.xml 放到/bin 下 配置文件 

压缩：`tar czvf xxx.tgz`
解压：`tar xzvf xxx.tgz`
第三方库：3rdparty
mqtt service


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

缺少`json-C`:
```SHELL
安装依赖
sudo apt-get install libjson-c-dev
安装pkg工具
sudo apt install pkg-config
```

缺少：`libcurl`库
```shell
6:10: fatal error: curl/curl.h: No such file or directory
    6 | #include <curl/curl.h>
```

安装依赖：
```SHELL
sudo apt-get install libcurl4-openssl-dev
```

缺少`libssl-dev`库：
```shell
19:10: fatal error: openssl/md5.h: No such file or directory
   19 | #include <openssl/md5.h>
```

安装依赖：
```shell
sudo apt-get install libssl-dev
```


创建文件权限不够
```shell
mkdir: cannot create directory ‘/opt/RMGateway’: Permission denied
```

```shell
sudo 运行qt
```

缺少`libGL.so`库
```shell
/usr/bin/ld: cannot find -lGL: No such file or directory
```

安装依赖： 
```shell
sudo apt-get install libgl1-mesa-dev
```

安装spdlog库
 ```shell 
fatal error: spdlog/spdlog.h: No such file or directory
   18 | #include "spdlog/spdlog.h"
```
[「spdlog库」spdlog库的安装与简单使用_spdlog安装_Hfjsbdhc的博客-CSDN博客](https://blog.csdn.net/HAICHANG1105/article/details/131432547)

```shell
git clone https://github.com/gabime/spdlog.git

cd spdlog && mkdir build && cd build
cmake .. && make -j
sudo make install
```


```shell
Failed opening file /opt/RMGateway/bin/../log/upgrade_2023-10-20.txt for writing: No such file or directory
[2023-10-20 08:26:53.284] [E] failed to load and parse file /opt/RMGateway/bin/RMGWClient.xml
```

```shell
mv RMGWClient.xml /opt/RMGateway/bin
```


安装mqtt

https://github.com/qt/qtmqtt/tree/dev
```shell
cd qtmqtt 
git checkout 5.15.2 

qmake 
make && make install
```
qtmqtt会自动安装到Qt Creator的路径下
![[qtmqtt.png]]


```
http://218.17.239.195/，
这个对应的是我们172.16.1.100的内网，
现在mqtt服务在内网

administrator 
123456

tcp://218.17.239.195:1884


```

![[mqtttopic.jpg]]

```
mqtt的连接账号roymark 密码123456
在这个页面点击关闭或者开启按钮，或者修改值都会往mqtt发送报文

```

![[2300fdc1adca19ad3b0c3ffe00ebb61.jpg]]

$roymark/device/cmd/request/123
![[580fbe6c86e1483d8fd286d77bb366b.jpg]]

向这个topic发送

