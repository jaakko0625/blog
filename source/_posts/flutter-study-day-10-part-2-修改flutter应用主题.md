---
title: flutter study day 10 part 2 修改flutter应用主题
date: 2022-05-18 16:50:50
tags:
categories:
thumbnail:
---

![修改flutter应用主题](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/CE46EE30-54D0-40B0-88C5-80358654CC6A/F47C5F88-5FF8-4F35-AD76-C03135792B94_2/zPnDUn1m2TixgUq2efJpdi7Mf2VCsBQhFKwoudU0FQUz/Image.png)
<!-- more -->
使用StatefulWidget进行修改，因为StateLessWidget不具备对组件进行动态修改的能力。

Material > theme: ThemeData

夜间模式：

	brightness: Brightness.dark,//添加到ThemeData内，页面就会变成夜间模式

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/CE46EE30-54D0-40B0-88C5-80358654CC6A/F47C5F88-5FF8-4F35-AD76-C03135792B94_2/zPnDUn1m2TixgUq2efJpdi7Mf2VCsBQhFKwoudU0FQUz/Image.png)

	使用后页面变成夜间模式

通过私有变量进行动态修改日间/页面模式：

	Brightness _brightness = Brightness.light;//初始化主题模式 默认日间模式

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/CE46EE30-54D0-40B0-88C5-80358654CC6A/C4C919D0-C805-4F51-A5BA-E3AD8B90A2A5_2/yZdeG023JFiPSzK4hwbdMrbYXr04lUmTPtn3ECldkoIz/Image.png)

brightness的值交给setState控制

	brightness: _brightness,//动态切换

以此实现可控制效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/CE46EE30-54D0-40B0-88C5-80358654CC6A/6E93ADF7-69D1-476C-8ED4-1F2A6B045CF6_2/8gTOz8GDrIg6nFzlpj7ND2Tyj9Ajbv18iwisRHKZGUQz/Image.png)

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/CE46EE30-54D0-40B0-88C5-80358654CC6A/8D64F901-C436-432E-92A7-C5FAC9FE9280_2/VyUfDqixfy78kdR6slQdHNZHPzwlOvmSKKf6yJZeQrwz/Image.png)
