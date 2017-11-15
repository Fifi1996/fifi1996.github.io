---
layout: win7
title: VM虚拟机安装centos
date: 2017-10-23 14:35:49
categories: Linux
---
---
周知计算机相关的多少需要掌握一些linux知识，笔记本上是win10+centos（虚拟机）的系统，奈何每天背电脑太重。故计划在我司台式上新装一个虚拟机。台式是win7的，虚拟机选择了常用的VMware，linux有许多版本，eg：centos,unbuntu。。读者可以根据需求自行选择安装，网盘里有centos6.5的iso就直接下载，扔个链接：http://pan.baidu.com/s/1gfgX7Ej 密码：r8ct
#  1 、 安装VM
 VM的安装就省略不讲现在已经更新到12，同其他软件类似一路next后选择路径就好
#  ２、下载linux镜像
#  ３、 创建新虚拟机，选择下载的镜像添加
![](http://upload-images.jianshu.io/upload_images/4975863-ad1132f8fffe0d9e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 以上步骤都比较简单，但是在台式机上遇到CPU不支持虚拟化问题

![](http://upload-images.jianshu.io/upload_images/4975863-c365eac0626bb425.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
搜索后发现此主机支持 Intel VT-x，但 Intel VT-x 处于禁用状态，可通过CPU检测工具查看（LeoMoon CPU-V）链接：http://pan.baidu.com/s/1i4K8PKh 密码：7m4n

![](http://upload-images.jianshu.io/upload_images/4975863-5f63adcbfd73a060.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
#  4 、Intel VT-x 处于禁用状态解除方式
* 关机等待品牌logo出现后进入bios模式，一般是F2
* 选择 configuration ->intel virtual technology ，此时该选项应该是disabled（关闭）的；将disabled（关闭）改为 enabled（开启）。
* 此时检查工具若还是报错，也许是360核晶防护有关，关闭后便正常。
重新检测如下
![](http://upload-images.jianshu.io/upload_images/4975863-9b4cb31b1975f093.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
# 5、开启centos，播放虚拟机

![](http://upload-images.jianshu.io/upload_images/4975863-809f829bba989754.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/4975863-6e9ef65c81cb015f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
* 通过以上步骤就能开启linux学习之路啦~
步骤和解决方式本人亲测有效，欢迎交流

