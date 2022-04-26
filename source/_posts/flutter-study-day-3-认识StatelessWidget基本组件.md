---
title: flutter study day 3 认识StatelessWidget基本组件
date: 2022-04-25 19:38:24
tags: [flutter]
categories: flutter
---
![认识StatelessWidget基本组件](https://tva4.sinaimg.cn/large/0072Vf1pgy1foxkcpa9qqj31kw0w07sa.jpg)

Stateless Widget的基本组件
========================

Stateless Widget的特点：
---------------------
**特点：不依赖自身状态，不必渲染自己**

**Contrainer 容器**

约束子节点，居中，内边距、宽高、颜色、背景、装饰器

**Text 文本** 显示文本

使用方法：Text(“文本内容”),

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/252A0C58-AC05-42C0-B5C0-D63E1992C0D1/2798CF63-4C43-443C-B013-792DA7DE14F4_2/nSAJMHtokxoXfG7hlqwxHyOJI8MhcnUKpMdiHM9gzewz/Image.png)

**Icon 图标** icon库里面有多个flutter原生图标可以调用

使用方法：Icons(Icons.android,Colors.color.blue,)

将会显示一个绿色的安卓图标

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/252A0C58-AC05-42C0-B5C0-D63E1992C0D1/471CDCE8-0AD0-46EF-A5AB-C688D1F384AB_2/qpaQYGNARNK0PBtFXNix4UT4Rlyp0bT1WZuiMv9VwCsz/Image.png)

**CloseButton 关闭按钮** 动作按钮

CloseButton(点击后将触发什么…),

**BackButton 返回按钮** 动作按钮

BackButton(点击后将触发什么…),

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/252A0C58-AC05-42C0-B5C0-D63E1992C0D1/9897418F-2DAF-43C0-8B12-CDA5EF7F52DD_2/OhpQFdsX7n83TtHGYmwrxSswnNJr4KO7xbx4yEj7M8Az/Image.png)

**Chip 材料设计**

Chip(),

有多个属性，可以设置avatar：图标

设置padding边距 margin边距 插入text文字内容等

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/252A0C58-AC05-42C0-B5C0-D63E1992C0D1/F8EBB7BB-A486-47CE-851F-FDCDE3540297_2/wZUawMCyY6yPN3ZYqViGpdlbtrvxFWdJoKG5n7H8XB4z/Image.png)

**Divider 分隔线**

Divider(),

多个属性 可以设置容器高度、侧边距 分隔线显色等

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/252A0C58-AC05-42C0-B5C0-D63E1992C0D1/4ED58CF5-842F-4F6B-8DE7-180E90B0D3B5_2/AuL1Ib3PGO41xxGBB7p7BzMMQMDfvRv05r4gwIimMN4z/Image.png)

**Card 卡片**

Card(),

多个属性，可设置color颜色、elevator内间距、margin外边距、child子元素设置padding、显示文本等

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/252A0C58-AC05-42C0-B5C0-D63E1992C0D1/E911BD5B-B48C-49CC-97A1-01197E7544EF_2/gJ9TXuaxoxhw6IuIlblUgprJyUmIlddZhdi2NtoCcmUz/Image.png)

**AlertDialog 弹框**

AlertDialog(),

title: Text(“设置弹窗标题”),

content(‘设置弹窗内容’)，

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/252A0C58-AC05-42C0-B5C0-D63E1992C0D1/4BB0FF3A-5E98-4275-B0B9-169EB71E64D9_2/4uFhNQKJlkZIGAqz3LeBARhjlyTIpy0Q9kmJugIbbTwz/Image.png)

代码示例：

```other
import 'package:flutter/material.dart';

class LessGroupPage extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Stateless基础组件',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: const Text("Stateless基础组件"),//标题
        ),
        body: Container(//容器组件
          decoration: const BoxDecoration(color: Colors.white10),//装饰器
          alignment: Alignment.center,//居中显示
          child: Column(
            children: const <Widget>[
              Text(//文本组件
                "Text",
                style: TextStyle(fontSize: 25),//显示文本，字体大小25
              ),
              Icon(//图标组件
                Icons.android,//安卓图标
                size: 50,//大小50
                color: Colors.green,//图标颜色绿色
              ),
              CloseButton(),//关闭按钮
              BackButton(),//返回按钮
              Chip(//内容元素组件
                avatar: Icon(Icons.apple),//元素图标 苹果
                label: Text("hello World!"),//元素内文本
              ),
              Divider(//分隔线
                height: 20,//容器高度
                indent: 10,//左侧间距
                color: Colors.grey,//分隔线颜色黑色
              ),
              Card(//卡片组件
                color: Colors.blue,//卡片颜色蓝色
                elevation: 5,//内边距 5
                margin: EdgeInsets.all(15),//所有外边距15
                child: Padding(//添加一个子元素 Padding
                  padding: EdgeInsets.all(8.0),//设置所有外边距 8
                  child: Text(//显示文本
                    'fuck me!',
                  ),
                ),
              ),
              AlertDialog(//弹窗组件
                title: Text('基础组件之AlertDialog弹窗'),//弹窗标题
                content: Text('good job!'),//弹窗内容
              )
            ],
          ),
        ),
      ),
    );
  }
}

```


编译后样例：

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/252A0C58-AC05-42C0-B5C0-D63E1992C0D1/FC300307-A7C5-4D64-9B03-4B10FECFC65D_2/iarHFJUEsVz9DHNlwfYxb1q4ivbVAiqx4qUjXmzrMokz/Image.png)
