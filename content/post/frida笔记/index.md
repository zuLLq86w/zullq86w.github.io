---
title: frida笔记
description: 
slug: 
date: 2025-02-28 00:00:00+0000
image: 
categories:
    - Frida
tags:
    - Frida
weight: 1       # You can add weight to some posts to override the default sorting (date descending)
---

##### 1.Frida简介
[frida](https://github.com/frida/frida)是一款基于Python + JavaScript的hook框架，可用于Android、Windows、IOS等多个平台

##### 2.Frida安装

###### 2.1 Window安装
```python
pip install frida-tools
```

###### 2.2 Android安装
根据手机CPU型号下载[Frida-server](https://github.com/frida/frida/releases)，解压重命名为frida-server
```shell
adb shell

su root

getprop ro.product.cpu.abi # 查看手机CPU型号

adb push .\frida-server /data/local/tmp # 推送到安卓目录

cd /data/local/tmp

chmod 777 frida-server

./frida-server # 运行frida服务
```

##### 3.Frida常用命令

###### 3.1查看运行中的程序信息
```shell
frida-ps -Ua
```

###### 3.2查看安装程序的包名
```shell
frida-ps -Uia
```

###### 3.3启动并加载脚本
```shell
frida -U -f [包名] -l [脚本文件]
```
