---
title: flutter study day 6 创建和使用flutter路由与导航
date: 2022-05-09 18:02:41
tags: [flutter]
categories: flutter
---
![flutter study day 6 创建和使用flutter路由与导航](https://tva2.sinaimg.cn/large/a15b4afegy1fnmws7fac1j21hc0u0hak.jpg)
示例：

	**在app首页添加路由**

	**在MyApp的MaterialApp内添加routes：**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/AA02EC32-F038-419E-82BE-5F3525F47B99/2F8CA006-52D9-4C66-B618-81E3694D20E1_2/JB4J9VfZhsgJizd8XWJKZ0uyXYOW7cFIenHiYuelnDAz/Image.png)

	别名:(BuilderContext context)=>需要指向的页面

	**创建RouteNavigator组件**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/AA02EC32-F038-419E-82BE-5F3525F47B99/3098E73C-3F03-4B2B-9ECF-7B82449AAAEF_2/WxcWFj7wuoUrLWSw25ey76L1DG6Bl76jIsn7ziIQv3Ez/Image.png)

	**重写_NavigatorState组件**

	bool byName = false;

	//添加一个布尔值变量byName默认值为false

	return Container

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/AA02EC32-F038-419E-82BE-5F3525F47B99/B1C3D842-4CC9-4377-A9E7-088CCA1838D0_2/fcF0869cKs3xtG0JUizCfnwCIy2yKPfvyUngFCxbWeAz/Image.png)

	**_item方法**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/AA02EC32-F038-419E-82BE-5F3525F47B99/79DC0950-B883-492D-A763-CE2FA62C22BD_2/PwxyApeCESzGMEwdYoFD6YMxx7IyNBUIxxhY366rrkwz/Image.png)

	**实现效果**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/AA02EC32-F038-419E-82BE-5F3525F47B99/77551A53-2565-4985-9DC2-6408D1ACEA94_2/V2orFCOQf9atZZq2KLSI11d0Bwu0p6SJh0rS8zu18Tcz/Image.png)

	点击后跳转到对应的页面

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/AA02EC32-F038-419E-82BE-5F3525F47B99/F89B9423-D922-444B-B849-6953D4350C4A_2/b3Qg8WwlbCEkzXGLoyFyuY7KnxfRkBNy6JGdgRjyHkoz/Image.png)

	**左上角的返回按钮需要手动在对应页面内添加一个Navigator.pop方法（跳出指定页面）**

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/AA02EC32-F038-419E-82BE-5F3525F47B99/0BA1F93D-5312-48B9-9D1B-CB40EB178A06_2/iAYarL8I8oyJqyP7pXswYhwLydCy1pbuNxsKGiAa08Mz/Image.png)

	每一个页面都需要添加此按钮才能参与返回上一页否则只能沿左侧右滑返回上一页

	**示例代码：**

    ```other
    import 'package:flutter/material.dart';
    import 'package:study_project1/statfull_grooup_page.dart';
    import './less_group_page.dart';
    import 'flutter_layout_page.dart';
    
    void main() {
      runApp(MyApp());
    }
    
    class MyApp extends StatelessWidget {
      const MyApp({Key? key}) : super(key: key);
    
      @override
      Widget build(BuildContext context) {
        return MaterialApp(
          title: 'Flutter Demo',
          theme: ThemeData(
            primarySwatch: Colors.blue,
          ),
          home: Scaffold(//实现一个页面
            appBar: AppBar(//顶部栏
              title: Text('如何创建和使用路由与导航'),//标题
            ),
            body: RouteNavigator(),//页面：使用路由组件
          ),
          routes: <String,WidgetBuilder>{//创建路由：接收两个参数Stirng&WidgetBuilder
            'less': (BuildContext context)=>LessGroupPage(),//指向LessGroupPage
            'ful': (BuildContext context)=>StatefulGroup(),//指向StatefulGroup
            'layout': (BuildContext context)=>FlutterLayoutPage(),//指向FlutterLayoutPage
          }
        );
      }
    }
    
    class RouteNavigator extends StatefulWidget {
      @override
      _RouteNavigatorState createState() => _RouteNavigatorState();
    }
    
    class _RouteNavigatorState extends State<RouteNavigator> {
      bool byName = false;
      @override
      Widget build(BuildContext context) {
        return Container(//容器
          child: Column(//布局
            children: <Widget>[
              SwitchListTile(//添加一个开关组件
                title: Text('${byName?'':'不'}通过路由名跳转'),//显示是否通过路由名跳转
                  value: byName,//byName控制true或false
                  onChanged: (value){//传入byName的值
                setState(() {
                  byName = value;
                });
              }),
              _item('StatelessWidget基础组件',LessGroupPage(),'less'),//第一个路由按钮
              _item('StatefullWidget基础组件',StatefulGroup(),'ful'),//第二个路由按钮
              _item('Layout基础组件',FlutterLayoutPage(),'layout'),//第三个路由按钮
              //_item为自定义方法，接收三个参数：title，页面，路由名称
            ],
          )
        );
      }
    
      _item(String tittle, page, String routeName) {//自定义item方法 接收三个参数
        return Container(//返回一个ring器
            child: RaisedButton(//点击按钮
              onPressed: (){
                if(byName) {//如果包含byName
                  Navigator.pushNamed(context, routeName);//跳转到对应的页面
                } else {//不包含byName
                  Navigator.push(//跳转到传入的page页面
                      context,
                      MaterialPageRoute(builder: (context) => page));
                }
              },
            child: Text(tittle),//容器标题为传入的标题
        ),
        );
      }
    }
    
    ```

