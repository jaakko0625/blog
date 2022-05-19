---
title: 'flutter study day 11 part 1 拍照app开发:image_picker依赖'
date: 2022-05-19 16:55:20
tags: [flutter]
categories: flutter
thumbnail:
---

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8E30083A-CCE6-4393-83CD-7CD1A48E9816/5FE870E6-23EA-4C42-8DF5-D268E08E5E7D_2/09W6wtLF4CQ7mTzxxCvelqxUIbOcbitGyzMo8jSAk0Ez/Image.png)
<!-- more -->
需求：点击拍照按钮-》弹出选项（拍照/照片图库）

点击拍照图库：可以选择照片，

点击拍照：调用相机自带功能

app内部页面内显示/删除：已经添加的照片

照片布局：自动换行


1.导包

	image_picker: ^0.8.5+3


2.修改IOS的runner/info.plist

按照插件说明修改添加权限说明

	NSCameraUsageDescription Used to demonstrate image picker plugin NSMicrophoneUsageDescription Used to capture audio for image picker plugin NSPhotoLibraryUsageDescription Used to demonstrate image picker plugin UIBackgroundModes remote-notification


3.按照插件提供的代码进行测试相机功能

IOS模拟机无相机功能，仅测试相册获取照片

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8E30083A-CCE6-4393-83CD-7CD1A48E9816/9DE561A3-06DB-41BB-BC1C-0FBBC237B9E1_2/Ia1BbsyHrNV67Sua2Kxb3lup71jDEqQB9BFnBHIKK8Ez/Image.png)
