---
title: flutter study day 10 获取flutter应用的生命周期
date: 2022-05-18 16:02:30
tags: [flutter]
categories: flutter
thumbnail:
---

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/00741F1F-1715-4A21-A4E6-AE8CDA091219/6EB5EFD9-C299-4534-87C8-BC9E1C4EF2C0_2/NRAV6WqyKy8ygrNWs6vWxnjjdSur2AYc6E1RdwWrMu0z/Image.png)
<!-- more -->
使用WidgetsBindingObserver检测用户操作

```other
WidgetsBindingObserver :监测页面生命周期

组件添加 with WidgetsBindingObserver {
//重写initState
	@override
	WidgetsBinding.instance.addObserver(this);//添加观察者
	super.initState();
}

```


didChangeAppLifecycleState()  
接收两个参数：页面State组件 state

state存储了app应用的当前状态

通过监测用户操作执行相关命令

```other
@override
  void didChangeAppLifecycleState(AppLifecycleState state) {
    //父类调用
    super.didChangeAppLifecycleState(state); //可有可无 因为本身就没有任何内容
    //打印当前state状态
    print('state状态 ：$state');

    //判断当前状态 执行操作
    //生命周期变化时回调
    //  resumed:应用可见并可响应用户操作
    //  inactive:用户可见，但不可响应用户操作
    //  paused:已经暂停了，用户不可见、不可操作
    if (state == AppLifecycleState.paused) {
      print('已经暂停了，用户不可见、不可操作:App进入后台');
    } else if (state == AppLifecycleState.resumed) {
      print('应用可见并可响应用户操作：App进去前台');
    } else if (state == AppLifecycleState.inactive) {
      //不常用
      print('应用处于被打断状态');
    }
  }
```

