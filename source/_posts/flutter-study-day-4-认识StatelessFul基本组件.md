---
title: flutter study day 4 认识StatelessFul基本组件
date: 2022-04-27 18:19:57
tags: [flutter]
categories: flutter
---
![认识StatelessFul基本组件](https://tva1.sinaimg.cn/large/a15b4afegy1fmvj3g29fbj21hc0u0akh.jpg)

StatelessFul基本组件
======================

可以改变页面状态 这是statelesswidget无状态的组件做不到的

**MaterialApp 材料设计的App组件**

通常放在根节点

title:标题

theme:主题

home：整个页面

**Scaffold**

flutter封装的带有AppBar&底部导航栏&侧边栏等效果的组件

**BottomNavigationBar底部导航栏**

至少接收两个item(icon默认图标状态,activeicon激活图标状态)

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/5C5AFAF6-3C50-4B79-A31B-BF00987ADF49_2/ixeOFWrNjl1CMsFUVDoFEtbRz7rd4F2g1YnAsqRuMS8z/Image.png)

**FloatingActionButton 悬浮按钮**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/28479537-363C-4B23-AFFB-16FBA2546DF5_2/SxXXTDgnxNeMrHyic6atxQ0FcTiRYmTzNhX72Q4f8xMz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/E322A796-D3AC-405E-8BC0-E300B1ACB44F_2/nUJt5JokjAtgctZRK9eu2nQTUkxLvy89WFOs5BHu3qkz/Image.png)

**RefreshIndicator 下拉刷新组件**

必须配合列表使用

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/A2AA3F35-2E46-4EF4-8CF4-02A7FAEC2EA8_2/kaSnxoMGetGdsUAcirNC3cTpWG9gxMLPrvtX8yLigiQz/Image.png)

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/761F63C9-6EF5-45BB-B9FD-56E408A4BC0A_2/7HFFgW7xn2KEgj3qJdfhCZyKtJ64WomsHOeF6XECyvoz/Image.png)

**Image 图片组件**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/3A59317B-753B-4904-BAEB-DA9FF3EEFE6E_2/jbQwyjFbxprsuWO7fsmN5YsDzVCdQuv2vWVFMqQ3bwsz/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/5B581BBE-1EF2-4627-9576-D22C6B74AAB9_2/V8hCinl5NBDrTKWzSm4aHmSLdkDYsQEwwJmizJkdJkIz/Image.png)

**TextField 输入框组件**

(可用作登录注册页面)

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/D54EAE6D-EBCD-4812-A67C-CF374DF3536F_2/MQiRwyRKbNQx5pyexA8wNZJd56qtAFXxYpG8XOHI4u0z/Image.png)

实现效果

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/9C32BC32-47B4-4EFC-8FA2-EA9E9F1399EB_2/vYhq6QqQxYPBkI0xvOgJx69SlUeo8aWtxxR449E5FwAz/Image.png)

**PageView页面预览**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/33E3DE50-E5A0-416C-8C54-AF5033E76FDC_2/Iuu9kMPfHlPZrHPXEnhyRvgBRadutInC52IdBzfKt5cz/Image.png)

实现效果（可左右华东切换）

可用作首页通知公告栏

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/F7D6F96E-C45E-4DB2-9453-B0D08225D23C/D7B6B634-DBC4-4DC6-A093-98EBB14F12F8_2/TyksPI6mGTg0ksM67jphOayq0fWNzzir1UPj98aRCVEz/Image.png)

完整代码：
```other
import 'package:flutter/material.dart';

class StatefulGroup extends StatefulWidget {
  @override
  State<StatefulGroup> createState() => _StatefulGroupState();
}

class _StatefulGroupState extends State<StatefulGroup> {
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
                      child: Column(
                        children: <Widget>[
                          Image.network(//插入网络图片
                            'https://blog.suflive.com/2022/04/21/Typora%E6%B5%81%E7%A8%8B%E5%9B%BE%E4%BB%A3%E7%A0%81%E5%AE%9E%E4%BE%8B/hello.jpeg',
                            //设置图片url
                            height: 300,//高
                            width: 250,//宽
                          ),//加载网络图片
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
                            //设置装饰器
                            decoration: BoxDecoration(color: Colors.lightBlueAccent),//BoxDecoration设置装饰器背景
                            //child节点设置pageview
                            child: PageView(
                              children: <Widget>[
                                _item('Page1',Colors.purple),//接收两个参数（标题，颜色）
                                _item('Page2',Colors.yellow),//接收两个参数（标题，颜色）
                                _item('Page3',Colors.green),//接收两个参数（标题，颜色）
                              ],
                            ),
                          ),
                        ],
                      ),
                    ),
                  ],
                ),
                onRefresh: _handleRefresh)
            :
        Text('列表'),//_currentIndex==0?如果不等于0 显示:后面的内容
      ),
    );
  }
  Future<Null> _handleRefresh() async{ //asyc设置异步运行
    await Future.delayed(Duration(milliseconds: 200));//计时器 200毫秒
    return null;//返回一个空值
  }
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

