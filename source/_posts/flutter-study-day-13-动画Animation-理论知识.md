---
title: flutter study day 13 动画Animation-理论知识
date: 2022-05-23 18:19:03
tags: [flutter]
categories: flutter
thumbnail:
---
![](https://tva4.sinaimg.cn/large/0072Vf1pgy1fodqpadh6zj31kw14nnpe.jpg)
<!-- more -->
**动画Animation使用户界面更直观、流畅**

**补间Tween**：定义了开始与结束点、时间线与时间和速度的曲线。由框架计算从开始过度到结束。

**基于物理的动画：**基于物理的动画中，运动被模拟为与真实世界的行为相似，投掷一颗球从地上弹起与用绳子帮助一个球自由落下的方式是不同的。

**使用基础类添加widget动画：**

  
**Animation：核心类，指导动画的值**  
Animation<double>,此外还会生成<Size>、<Color>。  
Animation有状态，可以通过value获取动画的当前值  
Animation本身和UI渲染没有关系

**CurvedAnimation：Animation的子类，将过程抽象为非线性曲线**  


**AnimationController：Animation的子类，管理Animation。**  
forward()：启动动画  
reverse({double frome})：倒放动画  
reset()：重置动画播放位置  
stop({bool canceled = true})：停止动画  
创建Controller需要传递vsync参数，存在vsync则会防止屏幕外动画消耗不必要资源，可以将statful作为vsync的值

**Tween：执行动画的对象使用的数据范围之间的生成值(例如：[0, 255])。**

例 生成一个数据范围：final Tween doubleTween = new Tween<double>(begin: -200, end:0);（此范围值不是必须的，可以是Colors中的颜色 例：Colors.transparent, Colors.black54）
