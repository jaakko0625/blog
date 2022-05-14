---
title: flutter study day 8 flutter打开第三方应用
date: 2022-05-14 16:09:33
tags: [fllutter]
categories: flutter
---
![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/A33E0CEF-3BA2-42CD-9FE2-51BD3AB959F0/7C906730-EF73-4BE0-8A1B-2EE115D4F5F9_2/RyD5pqQqwWEMyYegbyMnOy1WbfnU0qCpiQkLI2xnMxIz/Image.png)
<!-- more -->
**url_launcher插件：用于打开第三方app**

使用方式：


1. 导入  
在pubspec.yaml的dependencies中添加依赖

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/A33E0CEF-3BA2-42CD-9FE2-51BD3AB959F0/F504E621-F17F-4185-8BD1-618085A12005_2/kL5EItXajcYMrPCRRlA6tb2TweJ4uNJyQ03pMKJAiJ0z/Image.png)

执行 flutter pub get获取依赖包

或者直接在android studio中get dependencies


2. 导入包文件  
在页面中使用import导入包文件  
import 'package:url_launcher/url_launcher.dart';
3. 使用包文件

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/A33E0CEF-3BA2-42CD-9FE2-51BD3AB959F0/B04404E4-BF32-4B5A-BD0D-1DDC0F1CFD53_2/hfK1D4ovi3VJIFQ1D4Wdr4R7CLq2ynMiKeKbVpMH448z/Image.png)

	定义一个按钮 通过_launchUrl()自定义方法调用

	_luanchUrl官方代码修改示例：

    ```other
    final Uri _url = Uri.parse('https://colacloud.online');
    _launchUrl() async {
        if (!await launchUrl(_url)) throw '无法打开 $_url';
      }
    ```


**实现效果：**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/A33E0CEF-3BA2-42CD-9FE2-51BD3AB959F0/7C906730-EF73-4BE0-8A1B-2EE115D4F5F9_2/RyD5pqQqwWEMyYegbyMnOy1WbfnU0qCpiQkLI2xnMxIz/Image.png)

点击后会在app内部拉起浏览器并打开指定网站

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/A33E0CEF-3BA2-42CD-9FE2-51BD3AB959F0/A93A929B-F02B-4C28-9A3D-782F787133AC_2/bpqaR5osLCQMzdpbpEOnCJUXADhHqji06Q5xMHRaSZgz/Image.png)
