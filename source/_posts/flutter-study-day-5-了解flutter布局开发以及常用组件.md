---
title: flutter study day 5 了解flutter布局开发以及常用组件
date: 2022-04-28 19:46:42
tags: [flutter]
categories: flutter
---
![](https://tva3.sinaimg.cn/large/0072Vf1pgy1foxlnx4mk0j31hc0u07k9.jpg)

flutter布局开发常用组件
====================

**布局相关三大控件**
-----------------

### **Container**


约束子节点，居中，内边距、宽高、颜色、背景、装饰器

### **RenderObjectWidget**

**分为单节点与多节点**

**SingleChildRenderObjectWidget-单节点布局组件**

**Opacity-透明度**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/D6AA6BB8-601D-43E8-81FC-3B509291B1E6_2/Amzmyvq5ezo5rphvTPGF3gwbzZvnDEtIVm7VqcE7h5cz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/9C1CD087-FAEB-4CEC-8A91-2873F3917585_2/ed1hyHYygq2FPd68c7tTZT2tcJaNS6ZAOSVit6t4MQEz/Image.png)

**ClipOval-裁剪圆形**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/5514C932-E1B8-46E4-9C62-8B888980E885_2/ATWLKkoJlDrd6hEnsHyFUe4qAPmQRuVsRRXxSir0O4wz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/1331EA4B-59FD-4E42-97D7-81DE2AD8594F_2/LjvHqNjfIDZUQimtOpwoyV7yXuxJLuYZk2vR6VQbVG4z/Image.png)

**ClipRect-裁剪方形**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/4BB25D51-01B4-461F-9F40-62C86E5CC50A_2/rCNdRRhLxYZ1H0X4Hx9UG7PFFqHGpkmN1Z3zm3EuAPwz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/EF7CBBCA-EB89-4422-BFDD-BB8E666C9F00_2/gBKslBux6dcxqHqDwltXvmKAmkRR9Gwry88872yvXZAz/Image.png)

**PhysicalModel-显示不同形状**

使用PhysicalModel包裹需要裁剪的子节点加以修饰

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/50DFAE9F-E869-456D-A58E-927BAA6E0868_2/yxVUqshTlPFxqJp0SWBZDwGYCyysn5oPfE9uEd4qax0z/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/80F3255C-F899-42F9-873D-9146B49F8E7F_2/pXZ3xC5ILtfk6J7SoSXYB1px1rtwA4sXU15tYW4ALtcz/Image.png)

**Align-Center-居中**

……

**Padding-内边距设置**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/2C416E08-0C38-4F64-B7ED-650735A841B5_2/5GVoE36oxoSzDJ8xaZbeMrRxxVtVBxfFSdZqSRfh01sz/Image.png)

**SizeBox-约束布局大小**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/019C4AF6-FFD5-4F97-BB45-F6420519FB40_2/wdGTZXmFB3h4Fpjo3rH764ZVJaNew8tCaxQJSVeKVNwz/Image.png)

**FractionallySizeBox-约束水平方向-垂直方向**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/FAF6FC41-2EB5-4D06-BD30-ED5D41BDAC39_2/JfIeIUXdExN8Jfk1EqJrefjez3ywqjP5vxuFx1J6UsAz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/5877A110-BF29-4764-B910-2CD8FE3C25DE_2/OelyCOCi6E9WgMhRgGQU7Q9xvsfcy7BiVZW1KUmxJywz/Image.png)

**MuitiChildRenderObjectWidget-多节点布局组件**

**Stack-层叠布局组件**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/FCCCBAEA-9EAA-4B0A-A1EF-1BC8174B7501_2/eaPfqGZPr1TcRR4FPhkqlSLIpuXyILxjPq6ko2hTfqIz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/D70F9D35-706B-41CB-8490-D5A0FD383B35_2/IlN5ayq3sLO482z6YJYxquAOZM0gmXyUnxXETnQ6yBoz/Image.png)

**Flex 布局组件**

    Column-从上到下X轴

    Row-从左向右Y轴

**Warp-从左到右（会自动换行）**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/1BDAD04E-452C-4C7E-8579-A636D0E2C533_2/hqFS9tvhPHKUyAcF1xvMszmA0xHutCksEMlwGgmOzfYz/Image.png)

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/75E1F882-44D9-433D-B4F6-01D5C3FBB82A_2/fl9Mr0P5VEAWJWNX5NO7vB3OJT60baUmu2gm2Hk4yWAz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/363097B3-CACC-418C-9146-0ACEFB61AB07_2/FUYvwPG6b62T8Hr3DTJFFjqTrjveSwwmxIjMVc7GNxEz/Image.png)

**Flow-很少用**

### **ParentDataWidget**

**Positioned绝对定位布局**

固定view位置通常与stack搭配使用

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/345BE87A-CF30-42A8-8D48-AB996A007151_2/qfGvIyeZxoQHjDIcDbbxyMh7tGcnLKtep83fWH6yq6sz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/738E1056-54A5-4644-975D-5342458392BC_2/pmx9yPGUubFE87CU8g5dKPP34vU5SmMYNJgG1J3vRJYz/Image.png)

**Flexible-Expanded 流式布局**
可以展开布局大小的组件

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/CBE3F5A1-98AA-4F16-AE74-C7E0A5B78579_2/lrFVAvPA6pQkDDe5E36Mcmjy6gAqiDZxQJgtDu0qeMAz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/02658190-76D6-47BC-816A-A1F90B973A65/84531613-25BA-4CE7-8413-74320CBEDBAC_2/cQheuY6XXxE9GqMyWQgGlvRvM1rbza0ta93fc4KDqGQz/Image.png)

代码示例：
```other
import 'package:flutter/material.dart';
//使用flutter布局组件
class FlutterLayoutPage extends StatefulWidget {
  @override
  State<FlutterLayoutPage> createState() => _FlutterLayoutPage();
}

class _FlutterLayoutPage extends State<FlutterLayoutPage> {
  int _currentIndex = 0;//初始化当前选中页面 默认为0
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Stateful基础组件',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: const Text("Stateful基础组件"),//标题
        ),
        //底部导航栏
        bottomNavigationBar: BottomNavigationBar(
          currentIndex: _currentIndex,//当前选中页面 默认选中初始化的值
          onTap: (index){//接收一个index，点击的时候会自动切换到该索引
            setState(() {//使用setState改变初始化的当前索引的值
              _currentIndex = index;
            });
          },
          items: const [
            //items参数列表，有多少个BottomNavigationBarItem就会有多少个按钮，最少需要设置两个
            BottomNavigationBarItem(//第一个item
                icon: Icon(Icons.home,color: Colors.grey,),//第一个item的图标默认状态
                activeIcon: Icon(Icons.home,color: Colors.green,),//第二个item的图标激活状态
                label: '首页'//第一个item的显示名称
            ),
            BottomNavigationBarItem(//第二个item
                icon: Icon(Icons.list,color: Colors.grey,),//第二个item的图标默认状态
                activeIcon: Icon(Icons.list,color: Colors.green,),//第二个item的图标激活状态
                label: '列表'//第二个item的显示名称
            ),
          ],),

        floatingActionButton: const FloatingActionButton(
          onPressed: null,
          child: Text('点我'),
        ),
        body: _currentIndex==0
            ?
        RefreshIndicator(
            child:
            ListView(
              children: <Widget>[
                Container(//容器组件 //_currentIndex==0?如果等于0则显示Container内容
                  decoration: const BoxDecoration(color: Colors.white10),//装饰器
                  alignment: Alignment.center,//居中显示
                  child: Column(//上下排列组件
                    children: <Widget>[//子节点组件
                      Row(//从左到右布局
                        children: <Widget>[//Row的子节点
                          ClipOval(//裁剪圆形
                            child: SizedBox(//约束子节点大小
                              width: 100,//宽100
                              height: 100,//高100
                              child: Image.network('https://blog.suflive.com/2022/04/21/Typora%E6%B5%81%E7%A8%8B%E5%9B%BE%E4%BB%A3%E7%A0%81%E5%AE%9E%E4%BE%8B/hello.jpeg'),
                              //显示网络图片
                            ),
                          ),
                          Padding(
                            padding: EdgeInsets.all(10),//设置所有边距为10
                            child: ClipRect(//裁剪成方形
                              child: Opacity(//为子节点设置透明度
                                opacity: 0.5,//50%透明度
                                child: Image.network(
                                    'https://blog.suflive.com/2022/04/21/Typora%E6%B5%81%E7%A8%8B%E5%9B%BE%E4%BB%A3%E7%A0%81%E5%AE%9E%E4%BE%8B/hello.jpeg',
                                    width: 100,
                                    height: 100,
                                ),
                              ),
                            ),
                          ),
                        ],
                      ),
                      // Image.network(//插入网络图片
                      //   'https://blog.suflive.com/2022/04/21/Typora%E6%B5%81%E7%A8%8B%E5%9B%BE%E4%BB%A3%E7%A0%81%E5%AE%9E%E4%BE%8B/hello.jpeg',
                      //   //设置图片url
                      //   height: 300,//高
                      //   width: 250,//宽
                      // ),//加载网络图片
                      const TextField(//文本输入框
                        decoration: InputDecoration(
                          contentPadding: EdgeInsets.fromLTRB(5, 0, 0, 0),//边距：左5上0右0下0
                          hintText: '请输入',//hintText提示文案
                          hintStyle: TextStyle(
                            fontSize: 20,
                          ),//设置提示文案的样式
                        ),//使用decoration装饰器 定义文本输入框样式
                      ),
                      //PageView页面预览的使用
                      //使用Container约束大小
                      Container(
                        height: 100,
                        margin: EdgeInsets.only(top: 10),//使用EdgeInsets.only上边距为10
                        child: PhysicalModel(//显示不同形状组件
                          color: Colors.transparent,//透明显示颜色 透明
                          borderRadius: BorderRadius.circular(20),//裁剪成圆角半径
                          clipBehavior: Clip.antiAlias,//抗锯齿
                          child: PageView(
                            children: <Widget>[
                              _item('Page1',Colors.purple),//接收两个参数（标题，颜色）
                              _item('Page2',Colors.yellow),//接收两个参数（标题，颜色）
                              _item('Page3',Colors.green),//接收两个参数（标题，颜色）
                            ],
                        ),
                        ),
                      ),
                    ],
                  ),
                ),
                Column(//增加一行布局
                  children: <Widget>[//添加子节点
                    FractionallySizedBox(//约束水平方向-垂直方向组件
                      widthFactor: 1,//默认宽度为1
                        child: Container(//设置子节点容器
                          decoration: BoxDecoration(color: Colors.greenAccent),//设置容器背景颜色
                          child: Text('宽度撑满'),//设置容器内子节点
                        ),
                    ),
                  ],
                ),
                Stack(//实现叠加效果组件
                  children: <Widget>[//添加子节点
                    Image.network(
                      'https://blog.suflive.com/2022/04/21/Typora%E6%B5%81%E7%A8%8B%E5%9B%BE%E4%BB%A3%E7%A0%81%E5%AE%9E%E4%BE%8B/hello.jpeg',
                      width: 100,
                      height: 100,
                    ),//子节点组件1
                    Positioned(//定位布局
                      right: 0,
                      bottom: 0,
                        //如上写法：Positioned设置定位在做下方
                        child: Image.network(
                          'https://blog.suflive.com/2022/04/21/Typora%E6%B5%81%E7%A8%8B%E5%9B%BE%E4%BB%A3%E7%A0%81%E5%AE%9E%E4%BE%8B/hello.jpeg',
                          width: 100,
                          height: 100,
                        )//子节点组件2
                    ),
                  ],
                ),
                Wrap(//从左到右排列 自动换行
                  spacing: 6,//水平j安居
                  runSpacing: 10,//垂直间距
                  children: <Widget>[
                    _chip('flutter'),//调用_chip方法（传入label）
                    _chip('i'),
                    _chip('love'),
                    _chip('you'),
                    _chip('too much!'),
                  ],
                )
              ],
            ),
            onRefresh: _handleRefresh)
            :
        Column(
          children: <Widget>[
            Text('列表'),//第一行显示内容
            Expanded(
              child:
              Container(//设置Container的decoration装饰器
                decoration: BoxDecoration(color: Colors.greenAccent),
                //使用BoxDecoration约束背景颜色
                child: Text('拉伸高度填满'),
                //第二行显示内容 使用Expanded后第二行延伸Y轴进行填满
              ),
            )
          ],
        )//_currentIndex==0?如果不等于0 显示:后面的内容
      ),
    );
  }
  Future<Null> _handleRefresh() async{ //asyc设置异步运行
    await Future.delayed(Duration(milliseconds: 200));//计时器 200毫秒
    return null;//返回一个空值
  }
}

_chip(String label) {//创建_chip方法，接收参数label
  return Chip(label: Text(label),//返回格式化后的label
    avatar: CircleAvatar(//添加圆角头像
      backgroundColor: Colors.blue.shade900,//设置透明度900
      child: Text (
        label.substring(0,1),//取label的第一个字符
        style: const TextStyle(fontSize: 10,),//样式：文本样式（字体大小10）
      ),
    ),
  );
}

_item(String title, Color color) {
  return Container(//返回一个Container装饰器包裹住
    alignment: Alignment.center,//设置居中方式 居中
    decoration: BoxDecoration(
      color: color,//装饰器背景色等于传入的color参数
    ),//设置装饰器样式
    child: Text(title, style: TextStyle(fontSize: 20,color: Colors.white),),
  );
}

```

