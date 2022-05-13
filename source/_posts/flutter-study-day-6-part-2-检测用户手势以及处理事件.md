---
title: flutter study day 6 part 2 检测用户手势以及处理事件
date: 2022-05-09 21:11:53
tags: [flutter]
categories: flutter
---

**1.检测用户手势**

创建GesturePage类

```other
class GusturePage extends StatefulWidget {
  @override
  State<GusturePage> createState() => _GusturePageState();
}
```
<!-- more -->


**2.return MaterialApp页面**

正常设置AppBar

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8C717632-7754-4A90-8F74-29DC5AD2965B/863ECC3A-A13F-4F21-863F-50BF13C4ED74_2/VnxFQTlor4UQocg7JUF9v6n66VVMipcthHmyQJvaz9cz/Image.png)

FractionallySizedBox:设置空间大小

widthFatory:设置占用比例

通过Stack与Column布局

设置GestureDetector监听器

监听所有的点按操作,使用自定义方法_printMsg

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8C717632-7754-4A90-8F74-29DC5AD2965B/6E570C93-7E31-4D33-B6B6-0BCA3741EBEF_2/5nTC5MQJuqscn2BN3GTjIOcFNfaI8k5Dv3TiDX8P0SUz/Image.png)

添加一个容器Container设为点击目标

设置大小 文字 以及 样式

最后为输出每次操作对应的点按方式

**实现效果**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8C717632-7754-4A90-8F74-29DC5AD2965B/150C1A8B-9B96-454D-B693-835221955164_2/ntGTuWRMiSohvp9dR2cSQmhOHIDodeyNbWgNaxUmKpsz/Image.png)

点按后的效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8C717632-7754-4A90-8F74-29DC5AD2965B/D9EDE697-97AE-4B3B-AB37-08269C8F5B1D_2/4cHyHuafc2JWYBwF3TJVg5nFlxSjjGiaCAtwcXfPjWYz/Image.png)

**2.点击事件**

在Stack内调用Positioned类生成一个球

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8C717632-7754-4A90-8F74-29DC5AD2965B/CA6F58F1-B50B-4772-9C77-821BF53B5843_2/CE1KPR9TxVujrbv02GxnqRDaCatrVvKjsfbQb7SqeH0z/Image.png)

初始化X轴与Y轴

添加子元素：调用GestureDetector手势监听器

设置点击事件触发方法改变球的X&Y轴

使用自定义方法_doMove(e)方法

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8C717632-7754-4A90-8F74-29DC5AD2965B/795C08AC-A85D-4D7E-9636-3AFFEF1E90CA_2/U0qmrHcsGWVWPdayxxCiayw4lmF39j5KkuD9sTpLFJUz/Image.png)

添加子元素：Container容器

设定容器长宽

设定容器的装饰器：颜色amber黄

容器的边角为直径的一半以此形成圆形的球

**实现效果**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8C717632-7754-4A90-8F74-29DC5AD2965B/E441C551-54A7-4BB5-B829-27B60A55DBB5_2/e0xXW4Gg6lw0lvOA26yEH2kk2E2l6bFyf9cPd2YQCcoz/Image.png)

长按球进行移动

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/8C717632-7754-4A90-8F74-29DC5AD2965B/E71B3DC2-4869-4207-A90B-88E36AE6326B_2/H5d8p29vFtJUwsSXFdxTZ7Q9Js2VSvFkKIqlr312jwkz/Image.png)

代码示例：

```other
import 'package:flutter/material.dart';

class GusturePage extends StatefulWidget {
  @override
  State<GusturePage> createState() => _GusturePageState();
}

class _GusturePageState extends State<GusturePage> {
  String printString = '';//
  double moveX=0, moveY=0;
  @override
  Widget build(BuildContext context) {
    return MaterialApp(//使用MaterialApp包裹
      theme: ThemeData(//主题库
        primarySwatch: Colors.blue,//设置主题颜色 蓝色
      ),
      home: Scaffold(//使用scaffold包裹
        appBar: AppBar(
          title: Text("如何检测用户手势以及处理点击事件？"),//设置标题
          leading: GestureDetector(//设置顶栏左侧按钮
            onTap: (){//点击事件
              Navigator.pop(context);//pop离开某个页面
            },
            child: Icon(Icons.arrow_back),//leading左侧按钮的图标 arrow_back(返回)
          ),
        ),
        body: FractionallySizedBox(//FractionallySizedBox控件会根据现有空间，来调整child的尺寸
          widthFactor: 1,//占满屏幕
          child: Stack(//层叠布局
            children: <Widget>[
              Column(//使Widget里面的组件能够上下排列
                children: <Widget>[
                  GestureDetector(//flutter内所有的手势都会委托给GestureDetector处理
                    onTap: () => _printMsg("点击"),//单击事件 触发自定义方法 打印文字
                    onDoubleTap: () => _printMsg("双击"),//双击事件 触发自定义方法 打印文字
                    onLongPress: () => _printMsg("长按"),//长按事件 触发自定义方法 打印文字
                    onTapCancel: () => _printMsg("取消"),//取消事件 触发自定义方法 打印文字
                    onTapUp: (e) => _printMsg("手指松开"),//手指松开事件 触发自定义方法 打印文字
                    onTapDown: (e) => _printMsg("手指按下"),//手指按下事件 触发自定义方法 打印文字
                    child: Container(//添加容器
                      padding: EdgeInsets.all(60),//设置全部边距为60
                      decoration: BoxDecoration(color: Colors.blue,),//设置装饰器
                      child: const Text('点我',style: TextStyle(
                        fontSize: 36,
                        color: Colors.white,
                      )),
                    ),
                  ),
                  Text(printString),
                ],
              ),
              Positioned(//创建一个跟随用户手势的小球
                left: moveX,//设定X轴
                top: moveY, //设定Y轴
                child: GestureDetector(//手势监听器
                  onPanUpdate:(e) => _doMove(e),//跟随触控更新
                  child: Container(
                    width: 72,//宽72
                    height: 72,//长72
                    decoration: BoxDecoration(//装饰器
                      color:Colors.amber,//颜色 amber黄
                      borderRadius: BorderRadius.circular(36),//圆角等于直径的一般 形成圆形
                    ),
                  ),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }
  _printMsg(String msg) {//自定义_printMsg方法，接收一个字符串
    setState((){
      printString += ' ,$msg';//字符串拼接
    });
  }
  _doMove(DragUpdateDetails e) {//球移动的方法
    setState(() {
      moveY += e.delta.dy;//更新每次移动的位置Y
      moveX += e.delta.dx;//更新每次移动的位置X
    });
  }
}



```

