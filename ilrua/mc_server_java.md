# 搭建Minecraft服务器
> 本章介绍了如何使用Miaofrp搭建Minecraft Java版服务器。(本文仅包含最基本的开服操作,更多功能请自行百度)
同时，您也可以类比此方法映射其他基于TCP的服务。

## 搭建前的准备
+ MiaoFrp账号
+ 一台高性能的电脑/服务器/云服务器(只有手机的,**建议自裁**)
+ 一个**高性能**的脑子和**亿点点**动手能力
> 如果以上要求都达不到,可以联系我们一对一服务(**50CNY起步**)

## 开始搭建
### 方法一 手动搭建
> 此方法适合**动手能力较强**的人类

#### java环境&核心下载
首先打开[oeacle官网](https://www.oracle.com/cn/java/technologies/javase-jdk11-downloads.html)

![下载java](https://img.cncn3.cn/images/5x7Q.png)
期间可能会要求注册登录账号，按提示操作即可

嫌麻烦的 ~~(懒的)~~ 可以到[这里](https://down.ravi.cool/#/1/main/java)下载
下载完成后打开并按照提示安装即可.

到网上挑选你喜欢的核心,也可到这里[这里](https://down.ravi.cool/#/2/main)(目前提供spigot,craftbukkit,paperspigot)下载你喜欢的核心.本文以目前最新的paperspigot做演示.
#### 启动&配置
将下载好的核心移到一个单独的文件夹,右键新建一个文本文档
用记事本或其他编辑工具打开,并输入
``` bash
@echo off
java -Xmx2G -Xms128M -jar paper-1.16.5-468.jar
```
这里面的`paper-1.16.5-468.jar`改为你下载的核心的名字.

`2G`和`128M`分别是允许MC服务器使用的最大内存和最小内存

编辑完成后保存,将文件重命名为`run.bat`即可
> `run`可改为你喜欢的

双击打开,可能会直接闪退,也可能会出现下图的情况
![下载中](https://img.cncn3.cn/images/5g1T.jpg)

闪退请直接跳到后面,出现上图情况的请接着往下看
选择一 等待下载完成即可

但由于不可抗力因素,国内下载较慢

选择二 您可以到[这里](https://mcversions.net/)下载对应版本的文件
> 我们同样也有[对应的镜像](https://down.ravi.cool/#/2/main/server)

![mcversions.net](https://img.cncn3.cn/images/5HY8.jpg)

选择你想要的版本,点击`Download`

![下载页面](https://img.cncn3.cn/images/5EF0.jpg)

再点击`Download Server Jar`即可下载

下载完成后,将文件复制到`cache`文件夹中,重命名并替换原来的文件,如下图所示
![替换文件](https://img.cncn3.cn/images/5oQH.jpg)

完成之后再次双击`run.bat`

此时您的目录看起来应该像这样

![目录](https://img.cncn3.cn/images/5MWD.png)

打开`eula.txt`

![eula](https://img.cncn3.cn/images/5TRV.png)

修改完成后再次打开`run.bat`,不出意外的话,您已经开服成功了

附:server.properties配置详解

![https://minecraft-zh.gamepedia.com/Server.properties?variant=zh-cn](https://img.cncn3.cn/images/5OBX.png)
### 方法二 面板搭建
> 此方法适合不怎么喜欢动手的**懒宅**

具体教程见 https://github.com/Suwings/MCSManager

## 内网穿透(重点)
### 创建隧道
打开[miaofrp](https://miaofrp.net/?page=panel&module=addproxy)

![创建隧道](https://img.cncn3.cn/images/5f7y.png)

### 下载FRP&启动隧道
选择对应的系统下载即可,本文以windows为例
![下载frp](https://img.cncn3.cn/images/5J31.png)

点击`点击下载`,并解压

回到网站,点击`配置文件`
![配置文件](https://img.cncn3.cn/images/56Yv.png)

再打开`frpc.ini`,粘贴并保存
![frp.ini](https://img.cncn3.cn/images/5Ccd.png)

在文件夹空白处按住`Shift`再用鼠标右键单击
![打开powershell](https://img.cncn3.cn/images/5KWh.png)

点击`在此处打开命令提示符`或`在此处打开 PowerShell`
在弹出的窗口中输入命令`./frpc.exe -c frpc.ini` 并按回车即可启动
> 如果是powershell,请输入`./frpc.exe -c frpc.ini`
>
> 如果是cmd,请输入`frpc.exe -c frpc.ini`

出现类似界面代表启动成功
![启动成功](https://img.cncn3.cn/images/5SoZ.png)

>启动成功后,请保持窗口开启状态,不要关闭它,否则映射会中断.

![隧道信息](https://img.cncn3.cn/images/5SoZ.png)

至此您已经成功搭建好了一个MC服务器,将服务器域名和远程端口组合,即可连接.如:`dl1.node.miaofrp.net:39154`
