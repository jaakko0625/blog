---
title: flutter study day 7 导入和使用flutter资源
date: 2022-05-11 19:57:03
tags: [flutter]
categories: flutter
---
**导入**
在pubspec.yaml中删除assets的注释以及填写资源文件路径已经文件名

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/5BCFA878-1F9A-493A-9DAB-8CF4D50B5912/0656A165-2C7B-47E0-B623-EEDBD8FF4B26_2/UzgRRxtyGIJJw4KgzKVgkJdfanJRCFq5IqWYHWKZsYsz/Image.png)
<!-- more -->


**使用**

以下为图片资源的用例

通过AssetImage组件使用图片路径进行调用图片

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/5BCFA878-1F9A-493A-9DAB-8CF4D50B5912/7EAE9F06-A57F-470E-991F-4F9F50FC69F8_2/4KoXsuWjtEGzftd0DRXQ5HGneulAQmYElAPYra1ute4z/Image.png)


**实现效果**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/5BCFA878-1F9A-493A-9DAB-8CF4D50B5912/76CC20E2-906E-4E86-8C1F-246AF345AFB6_2/sZT12WReuIl9qNoXKY99WN8AEWcgie8QJSLHDoDwD9sz/Image.png)

代码示例：

```other
import 'package:flutter/material.dart';

class ResPage extends StatefulWidget {
  @override
  State<ResPage> createState() => _Respage();
}

class _Respage extends State<ResPage> {

  @override
  Widget build(BuildContext context) {
    return Scaffold(//页面组件:包含导航 菜单 底部导航 悬浮按钮 主体内容
      appBar: AppBar(//appbar 顶部导航
        title: Text('如何导入和使用flutter资源文件？'),//顶部标题
        leading: GestureDetector(//设定标题最左边的监听器
          onTap: () {//按钮方法
            Navigator.pop(context);//触发离开当前页面
          },
          child: Icon(Icons.arrow_back),//按钮图标 返回键
        ),
      ),
      body: Center(//主体内容：居中布局
        child: Column(//使用column按顺序排列组件
          mainAxisAlignment: MainAxisAlignment.center,//居中显示
          children: const <Widget>[
            Image(//使用图片组件
              width: 350,//定义宽度
              height: 550,//高度
              image: AssetImage('images/night.jpg'),//通过路径图片显示图片
            )
          ],
        ),
      ),
    );
  }
}



```


