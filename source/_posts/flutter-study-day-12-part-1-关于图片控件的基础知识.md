---
title: flutter study day 12 part 1 关于图片控件的基础知识
date: 2022-05-20 15:31:06
tags:
categories:
thumbnail:
---

![关于图片控件的基础知识](https://tva4.sinaimg.cn/large/a15b4afegy1fmvju3msuyj21hc0u04pt.jpg)

<!-- more -->
- Image widget
	- Flutter中用来展示图片的widget
	- 如果需要使图片根据屏幕分辨率自动适配需要使用AssetImaget指定图像，并确保Image widget存在MaterialApp或MediaQuery下方
- 如何加载网络图片？ 
	- Image.network( ‘url’ )
- 如何加载静态图片？ 
	- pubspec.yml 写入图片src
	- Image.asset( 'src' )
- 如何加载本地图片？ 
	- pubspec.yml 添加path_provider插件
	- 导入头文件（插件包）
	- 调用FlutterBuilder()函数加载图片

    ```other
    import 'dart:io';
    import 'package:path_provider/path_provider.dart';
    
    //Image.file(File('/sdcard/Download/Stack.png')),
    FutureBuilder(future: _getLocalFile("Download/Stack.png"),
      builder:  (BuildContext context, AsyncSnapshot<File> snapshot) {
        return snapshot.data != null ? Image.file(snapshot.data) : Container();
      })
    )
    //获取SDCard的路径：
     Future<File> _getLocalFile(String filename) async {
        String dir = (await getExternalStorageDirectory()).path;
        File f = new File('$dir/$filename');
        return f;
      }
    ```

- 如何设置Placeholder？ 
	- 安装Transparent_Image插件
	- 在组件中导入插件包
	- 使用FadeInImage.assetNetworl
		- placeholder:kTransparentImage 透明图层，在图片加载前会现在placeholder

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/064D53BE-8CEA-4704-A08D-324A34C54B53/CA2541AC-1373-4AE1-BBB8-BC38C0DA8B29_2/sYguK8kYJlC5RfRNQjPiqRs4E0QszgFs6WvA7QfxKSIz/Image.png)


		- 加载本地资源中自定义的placeholder

			- 安装插件包

			- 导入插件包

			- placeholder加载本地资源图片

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/064D53BE-8CEA-4704-A08D-324A34C54B53/14C2F0D7-B1D3-4B9D-A2FC-03A44250BD04_2/pnbl1CmAw2jilt87ZnJfZIsWhOwPKExT45FISBbBNOQz/Image.png)


- 如何配置图片缓存？ 
	- 图片只需要加载过一次之后第二次即使无网络也能够加载图片
	- 安装cache_network_image插件
	- 导入插件包

    ```other
    child: CachedNetworkImage(
                placeholder: (context, url) => new CircularProgressIndicator(),
                imageUrl:
                    'https://picsum.photos/250?image=9',
              ),
    ```

- 如何加载自定义Icon？ 
	- material.dart的Material_fonts函数库中有大量的flutter官方图标可以直接调用
	- 构造自定义图标函数

	const IconData(

	this.codePoint,//必填参数，fonticon对应的16进制Unicode {

	this.fontFamily,//字体库系列

	this.fontPackage,//字体在那个包中，不填仅在自己程序包中查找

	this.matchTextDirection: false,图标是否按照图标绘制方向显示

	});


	- 配置字体与自定义Icon字体一致

    ```other
    fonts:
    	- family: devio
    	  fonts:
    	    - asset: fonts/devio.ttf
    ```

	- 使用

    ```other
    child: new Icon(
    	new IconData(
    		0xf5566,//图标代码
    		fontFamily: "devio"//图标字体
    	),
    	size: 100.0,//图标大小
    	color: Colors.blueAccent,//图标颜色
    )
    ```

