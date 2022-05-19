---
title: 'flutter study day 11 part 2 拍照app开发:获取图片与展示图片'
date: 2022-05-19 18:20:06
tags: [flutter]
categories: flutter
thumbnail:
---

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/9B4E28F6-E814-4E56-B831-24DC83D37590/8B105975-D1BF-4E94-A276-BCEBD7D225A0_2/RW2mhTspkdXV6XEK4Mp9Qx4FYQMPQEnNYQUev4Jh39wz/Image.png)
<!-- more -->
需求：点击拍照按钮-》弹出选项（拍照/照片图库）

点击拍照图库：可以选择照片，

点击拍照：调用相机自带功能

app内部页面内显示/删除：已经添加的照片

照片布局：自动换行


1.设置页面布局

```other
@override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('【实战尝鲜】拍照APP开发'),
        leading: GestureDetector(
          onTap: () {
            Navigator.pop(context);//离开当前页面
          },
          child: const Icon(Icons.arrow_back),//返回按钮图标
        ),
      ),
      body: Center(//页面居中布局
        child: Wrap(//flex平滑布局
          spacing: 5,//X轴间距
          runSpacing: 5,//Y轴jian距
          children: _genImages(),//子节点：获取照片
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _pickImage,
        tooltip: '选择图片',
        child: const Icon(Icons.add_a_photo),
      ),
    );
```

2.编辑_pickImage函数方法

showModalBottomSheet：一个由下往上弹框

接收两个参数：context builder()

```other
_pickImage() {//选择照片的方法
    showModalBottomSheet(
        context: context,
        builder: (context) => Container(//设置容器储存按钮
          height: 160,//设置容器高度
          child: Column(//组件上下排列
            children: <Widget>[
              //排列一下两个组件
              _item('拍照',true),
              _item('照片图库',false),
            ],
          ),
    ));
  }
```

3.自定义_item方法

```other
//自定义item方法 接收两个参数：标题 & 是否获取图片
  _item(String title, bool isTakePhoto) {
    return GestureDetector(//设置按钮监听器
      child: ListTile(//子节点：排列列表
        leading: Icon(
            isTakePhoto ?
            Icons.camera_alt : Icons.photo_library
                //展示按钮图标
        ),
        title: Text(title),//展示对应item的文字标题
        onTap: () => getImage(isTakePhoto),//点击后执行拍照 或 图库
      ),
    );
  }
```

4.设置选择照片后平滑排列照片并自动换行以及删除选中照片

```other
//设置选择照片后平滑排列照片并自动换行以及删除选中照片
  _genImages(){
    //该返回选中的照片
    return _images.map((file){
      return Stack(//让照片进行层叠布局排列
        children: <Widget>[//排列子组件
          ClipRRect(//让每一张照片进行圆角处理
            borderRadius: BorderRadius.circular(5),//设置圆角边距5px
            child: Image.file(
                File(file.path),//文件路径
              height: 160,//设置高度
              width: 90,//设置宽度
              fit: BoxFit.fill,//填满容器
            ),
          ),
          Positioned(//设置定位按钮
            right: 5,//右5
            top: 5,//上5
            //右上角
            child: GestureDetector(//设置按钮监听器
              //设置点击按钮
              onTap: () {
                setState((){//点击按钮执行的动作
                  _images.remove(file);//删除指定的文件/图片
                });
              },
              child: ClipOval(//设置一个圆角的删除按钮
                child: Container(//使用容器包裹
                  padding: const EdgeInsets.all(3),//四周围间距3
                  //设置装饰器
                  decoration: const BoxDecoration(color: Colors.black26),//半透明颜色
                  child: const Icon(
                    Icons.close,//图标 关闭图标
                    size: 18,//图标大小
                    color: Colors.white,//图标颜色 白色
                  ),
                ),
              ),
            ),
          ),
        ],
      );
    }).toList();//将map转换为列表排列
  }
```


最终实现效果：

![image](https://res.craft.do/user/full/95b613cb-a607-3458-0fba-b0ca77de5993/doc/9B4E28F6-E814-4E56-B831-24DC83D37590/FA4E3202-2F0E-48DC-8EFA-3951ED60FB39_2/aVkawdYA3vV13D9UKkV5DQCH5hTJ9T4FrTEyMAVznqsz/Image.png)

