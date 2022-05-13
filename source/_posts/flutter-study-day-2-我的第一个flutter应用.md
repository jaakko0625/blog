---
title: flutter study day 2 我的第一个flutter应用
date: 2022-04-24 18:03:49
tags: [flutter]
categories: flutter
---
![我的第一个flutter应用](https://tva2.sinaimg.cn/large/0072Vf1pgy1foxkjdzgusj31hc0u0nfc.jpg)
<!-- more -->

day 2 我的第一个flutter应用
=========================

今天花了几个小时时间终于将flutter环境处理好了  
于是开始动手写我的一个flutter项目
[参照flutter中文官网](https://flutter.cn/docs/get-started/codelab)  

### 首先
在android studio创建项目  
create new flutter project -> flutter -> 填写fluttersdk地址 -> 填写项目名字 -> next -> finish 创建完成
### 修改main.dart
    import 'package:flutter/material.dart';
    //引入flutter下的material包

    void main() {
    runApp(const MyApp());
    }
    //声明入口文件

    //创建myapp类并继承自StatlessWidget组件
    class MyApp extends StatelessWidget {
    const MyApp({Key? key}) : super(key: key);
    //进行函数构造 Flutter 框架中 Widget 構造函數都提供了Key 作為可選參數。

    //重写部件 build
    @override
    Widget build(BuildContext context) { //传入参数BuildContext context
        return MaterialApp(//返回 重写后的app
        title: 'Welcome to Flutter',
        home: Scaffold(
            appBar: AppBar(//App顶栏：
            title: const Text('my_app'),//标题：文本（"my_app"）
            ),
            body: const Center(//修改body元素：常量 居中
            child: Text('Hello World'),//子元素：文本("Hello World")
            ),
        ),
        );
    }
    }

实现如下效果：
![](https://flutter.cn/assets/images/docs/get-started/ios/hello-world.png)

### 导入包
包介绍：english_words  
包含数千个最常用的英文单词以及一些实用功能。  
在项目目录执行:  
    flutter pub add english_words

android studio打开pubspec.yml会提示pub get  
类似nodejs的npm install安装依赖

导入  
打开main.dart  

    import 'package:english_words/english_words.dart';
    //导入english_words包 未使用的包呈现灰色字体

**调用pair_words  **

    //重写部件 build
    @override
    Widget build(BuildContext context) { //传入参数BuildContext context
        final word_Pair = WordPair.random();//声明变量 word Pair = wordpaird的random函数随机生成英文
        return MaterialApp(//返回 重写后的app
        title: 'Welcome to Flutter',
        home: Scaffold(
            appBar: AppBar(//App顶栏：
            title: const Text('my_app'),//标题：文本（"my_app"）
            ),
            body: Center(//修改body元素：居中显示
            child: Text(word_Pair.asPascalCase),//文本(word_paird的随机英文并使用pascalcase进行大驼峰命名法重命名)
            ),
        ),
        );
    }

实现如下效果：
![](https://flutter.cn/assets/images/docs/get-started/ios/step2.png)

### 添加一个statefull widget  

**dart.main末尾添加以下代码**

    //新建类randomwords 继承自statefullwidget
    class RandomWords extends StatefulWidget {
        const RandomWords({ Key? key }) : super(key: key);
        //函数初始化 Flutter 框架中 Widget 構造函數都提供了Key 作為可選參數。

        //重写_RandomWordState类的createState函数 = _RandomWordsState()函数；
        @override
        _RandomWordsState createState() => _RandomWordsState();
    }
    //新建类——randomwordsstate 继承自 state<泛型 RandomWords>
    class _RandomWordsState extends State<RandomWords> {
    //重写 build函数
    @override
    Widget build(BuildContext context) {
            final wordPair = WordPair.random();//wordPair = 随机生成英文单词
            return Text(wordPair.asPascalCase);//返回文本 随机生成单词并使用大驼峰命名法
        }
    }

### 创建一个无限滚动的 ListView  

**修改dart.main**
**向 _RandomWordsState 类中添加一个 _suggestions 列表以保存建议的单词对，同时，添加一个 _biggerFont 变量来增大字体大小**

        class _RandomWordsState extends State<RandomWords> {
            final _suggestions = <WordPair>[];//新增数组_suggestions数据 泛型为WordPair
            final _biggerFont = const TextStyle(fontSize: 18.0);//新建变量 _biggerFont 定义 文本样式（字体大小 18.0）
            // ···
        }

    向 _RandomWordsState 类的 build 方法添加 ListView.builder
    在 _RandomWordsState 中的 itemBuilder 里添加 ListTile 函数
    class _RandomWordsState extends State<RandomWords> {
    final _suggestions = <WordPair>[];//新增数组_suggestions数据 泛型为WordPair
    final _biggerFont = const TextStyle(fontSize: 18.0);//新建变量 _biggerFont 定义 文本样式（字体大小 18.0）
    //重写 build函数
    @override
    Widget build(BuildContext context) {
        final wordPair = WordPair.random();//wordPair = 随机生成英文单词
        // return Text(wordPair.asPascalCase);//返回文本 随机生成单词并使用大驼峰命名法
        return ListView.builder(//返回列表显示
        padding: const EdgeInsets.all(16.0),//边距16.0
        //EdgeInsets对象：为四个方向设定固定的边距 .all为所有方向设置边距
        itemBuilder: /*1*/ (context, i){//参数：连接,迭代器i（从0开始);每调用一次会自增
            //每次建议的单词对都会让其递增两次，一次是 ListTile，另一次是 Divider。它用于创建一个在用户滚动时候无限增长的列表。
            //ListView 类提供了一个名为 itemBuilder 的 builder 属性，这是一个工厂匿名回调函数，接受两个参数
            if (i.isOdd) return const Divider();/*2*/
            //如果 i增加了：返回divider
            /*
            Divider是一个分割线控件
                height：是控件的高，并不是线的高度，绘制的线居中。
                thickness：线的高度。
                indent：分割线前面空白区域。
                endIndent：分割线后面空白区域。
            默认为浅灰色分隔线
            */

            final index = i ~/ 2; /*3*/
            //定义 索引 = i / 2 向下取整 计算出 ListView 中减去分隔线后的实际单词对数量。
            if (index >= _suggestions.length){//如果 索引小于等于 _suggestions的长度
            _suggestions.addAll(generateWordPairs().take(10));/*4*/
            //生成10个单词并增加到_suggestions数据内
            }
            return ListTile(//返回列表
            title: Text(//标题为文本
                _suggestions[index].asPascalCase,
                //_suggestions[索引].大驼峰命名
                style: _biggerFont,
                //样式为 定义好的 16.0
            )
            );
        },
        );
    }
    }

    //新建类randomwords 继承自statefullwidget
    class RandomWords extends StatefulWidget {
    const RandomWords({ Key? key }) : super(key: key);
    //函数初始化 Flutter 框架中 Widget 構造函數都提供了Key 作為可選參數。

    //重写_RandomWordState类的createState函数 = _RandomWordsState()函数；
    @override
    _RandomWordsState createState() => _RandomWordsState();
    }

**更新 _RandomWordsState 的 build() 方法以使用_buildSuggestions()**

    //新建类——randomwordsstate 继承自 state<泛型 RandomWords>
    class _RandomWordsState extends State<RandomWords> {
    final _suggestions = <WordPair>[];//新增数组_suggestions数据 泛型为WordPair
    final _biggerFont = const TextStyle(fontSize: 18.0);//新建变量 _biggerFont 定义 文本样式（字体大小 18.0）
    //重写 build函数
    @override
    Widget build(BuildContext context) {
        // final wordPair = WordPair.random();//wordPair = 随机生成英文单词
        // return Text(wordPair.asPascalCase);//返回文本 随机生成单词并使用大驼峰命名法
        return Scaffold(
        appBar: AppBar(
            title: const Text('Startup Name Generator'),
        ),
        body: ListView.builder(//返回列表显示
        padding: const EdgeInsets.all(16.0),//边距16.0
        //EdgeInsets对象：为四个方向设定固定的边距 .all为所有方向设置边距
        itemBuilder: /*1*/ (context, i){//参数：连接,迭代器i（从0开始);每调用一次会自增
            //每次建议的单词对都会让其递增两次，一次是 ListTile，另一次是 Divider。它用于创建一个在用户滚动时候无限增长的列表。
            //ListView 类提供了一个名为 itemBuilder 的 builder 属性，这是一个工厂匿名回调函数，接受两个参数
            if (i.isOdd) return const Divider();/*2*/
            //如果 i增加了：返回divider
            /*
            Divider是一个分割线控件
                height：是控件的高，并不是线的高度，绘制的线居中。
                thickness：线的高度。
                indent：分割线前面空白区域。
                endIndent：分割线后面空白区域。
            默认为浅灰色分隔线
            */

            final index = i ~/ 2; /*3*/
            //定义 索引 = i / 2 向下取整 计算出 ListView 中减去分隔线后的实际单词对数量。
            if (index >= _suggestions.length){//如果 索引小于等于 _suggestions的长度
            _suggestions.addAll(generateWordPairs().take(10));/*4*/
            //生成10个单词并增加到_suggestions数据内
            }
            return ListTile(//返回列表
            title: Text(//标题为文本
                _suggestions[index].asPascalCase,
                //_suggestions[索引].大驼峰命名
                style: _biggerFont,
                //样式为 定义好的 16.0
            )
            );
        },
        ),
        );
    }
    }

### 更新 MyApp 的 build() 方法，修改 title 的值来改变标题，修改 home 的值为 RandomWords widget

    //创建myapp类并继承自StatlessWidget组件
    class MyApp extends StatelessWidget {
    const MyApp({Key? key}) : super(key: key);
    //进行函数构造 Flutter 框架中 Widget 構造函數都提供了Key 作為可選參數。

    //重写部件 build
    @override
    Widget build(BuildContext context) { //传入参数BuildContext context
        return const MaterialApp(//返回 重写后的app
        title: 'Startup Name Generator',
        home: RandomWords(),
        );
    }
    }

最终效果如下：
![](https://flutter.cn/assets/images/docs/get-started/ios/step4-infinite-list.png)