---
title: flutter study day 10 part 3 如何自定义字体
date: 2022-05-18 18:51:14
tags: [flutter]
categories: flutter
thumbnail:
---

![如何自定义字体](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/FCF6B334-1BA5-47F2-A08D-57EDDDD0696D/8CAF7FDB-70E2-4902-ADB6-7EEB9216C4FE_2/VlZ8MtVXBhO9iyf4Gk1wuw0zrvcKNRWktGmzuKCiWfoz/Image.png)
<!-- more -->

1. 字体注册
	1. 字体下载官网：

	///字体下载地址：[https://fonts.google.com/specimen/Rubik+Mono+One?selection.family=Rubik+Mono+One](https://fonts.google.com/specimen/Rubik+Mono+One?selection.family=Rubik+Mono+One)

	///更多参考：[https://flutter.dev/docs/cookbook/design/fonts](https://flutter.dev/docs/cookbook/design/fonts)


	2. 在项目目录创建font文件夹，将字体文件拷贝至该目录。

    ```other
    修改pubspec.yml 底部添加字段
    fonts:
        - family: Koulen-Regular
          fonts:
            - asset: font/Koulen-Regular.ttf
    
    运行flutter pubget
    ```

2. 使用字体

	全局应用：在MaterialApp>theme>ThemeData

	加入字段：  
fontFamliy: ‘Koulen-Regular’;//全局生效

	页面内所有文字都应用该字体

	实现效果：

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/FCF6B334-1BA5-47F2-A08D-57EDDDD0696D/8CAF7FDB-70E2-4902-ADB6-7EEB9216C4FE_2/VlZ8MtVXBhO9iyf4Gk1wuw0zrvcKNRWktGmzuKCiWfoz/Image.png)

	局部应用：Text(‘11’, style: TextStyle( fontFamliy:'Koulen-Regular'))

	实现效果：

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/FCF6B334-1BA5-47F2-A08D-57EDDDD0696D/777839C2-197D-4D78-98AD-17634E5E0035_2/yMGvSAmOEiVP4jlXtc6HAOVYaNdUtzWbVt2onAb7CI4z/Image.png)
