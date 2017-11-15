---
title: adb的使用以及常见问题
date: 2017-09-15 19:15:35
tags:
categories: android工具
---
---
## ADB介绍
ADB（Android Debug Bridge）是Android SDK中的一个工具, 使用ADB可以直接操作管理Android模拟器或者真实的Andriod设备。其允许您与模拟器实例或连接的 Android 设备进行通信。它可为各种设备操作提供便利，如安装和调试应用，并提供对 Unix shell（可用来在模拟器或连接的设备上运行各种命令）的访问。该工具作为一个客户端-服务器程序，包括三个组件：
* 客户端，该组件发送命令。客户端在开发计算机上运行。您可以通过发出 adb 命令从命令行终端调用客户端。
* 后台程序，该组件在设备上运行命令。后台程序在每个模拟器或设备实例上作为后台进程运行。
* 服务器，该组件管理客户端和后台程序之间的通信。服务器在开发计算机上作为后台进程运行。
 ADB主要功能有:

    1、在Android设备上运行Shell(命令行)
    2、管理模拟器或设备的端口映射
    3、在计算机和设备之间上传/下载文件
    4、将电脑上的本地APK软件安装至Android模拟器或设备上


## 使用方法
* 要在通过 USB 连接的设备上使用 adb，您必须在设备系统设置中启用 USB debugging（位于 Developer options 下）
在运行 Android 4.2 及更高版本的设备上，Developer options 屏幕默认情况下处于隐藏状态。如需将其显示出来，请转到 Settings > About phone 并点按 Build number 七次。返回上一屏幕，在底部可以找到 Developer options。
在某些设备上，Developer options 屏幕所在的位置或命名方式可能有所不同。
* 启动命令行输入   *adb devices* 可以查看到当前设备已经连上了。
![image.png](http://upload-images.jianshu.io/upload_images/4975863-7b1040bb0645db9d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 常见命令

>  adb install <apk文件路径>

 这个命令将指定的apk文件安装到设备上，如果加-r是覆盖安装
>  adb shell pm list packages
![](http://upload-images.jianshu.io/upload_images/4975863-a397400f22253084.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
列出已安装的包名

>adb uninstall <软件名>
adb uninstall -k <软件名>

如果加 -k 参数,为卸载软件但是保留配置和缓存文件.
> adb shell 

 这个命令将登录设备的shell
> adb shell <command命令>
  
后面加<command命令>将是直接运行设备命令, 相当于执行远程命令
>  adb help

 这个命令将显示帮助信息

  >  adb push <本地路径> <远程路径>

从电脑上发送文件到设备

## 常见问题
1 、5037端口被占用
 *daemon not running. starting it now on port 5037 * error: could not install*
方法：*netstat -ano | findstr "5037"*
找到5037被什么进程占用了，然后杀掉进程*taskkill /f /pid 进程号*
2 、设备显示offline
方法：先检查手机是否开启了debug调试选项，看一下是不是接触不良，或者换一根数据线，检查电脑是否安装了手机的驱动。如果都不行的话更新一下adb工具版本。笔者就是这个问题困扰了一天，红米2调试机上无论什么方法都处于offline状态，其他调试机都没问题。查看了adb版本发现是Android Debug Bridge version 1.0.26，所以换了一个新的版本 1.0.32就好了，目前还没找到原因。
附上链接: https://pan.baidu.com/s/1pKNIaef 密码: d94t
## 参考文献
android studio官网介绍
https://developer.android.com/studio/command-line/adb.html
目前使用adb就遇到这些问题和用法，未完待续。。。
如有错误欢迎指正