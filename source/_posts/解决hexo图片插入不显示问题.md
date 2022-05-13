---
title: 解决hexo图片插入不显示问题
date: 2022-04-25 16:46:33
tags: [hexo, icarus]
categories: 技术分享
---
![](https://tva2.sinaimg.cn/large/0072Vf1pgy1foxln98mdaj31hc0u018i.jpg)
<!-- more -->

说明：
---
  **在这之前使用hexo写东西上传照片总是不太方便，所以今天查了一下hexo图片上传以及显示的解决方案。**

1. 在hexo目录执行  

        npm install hexo-asset-img --save
2. 修改_config.yml  
将post_asset_folder: false 修改为true  

        post_asset_folder: true
3. 通过hexo n "文档文章"新建文章  
会在source的post下自动生成一个 文章.md 以及一个文章同名目录  
那么文章同名目录下就可以存放我们需要引用的图片了  
调用方法：

        ![](文章目录/your_img.jpg)
经测试：通过以上方式插入图片，在VSCODE的Preview能够正常显示图片  
在网站的文章内会自动转换成：{% asset_img img.jpg %}格式  
这样即不影响我们编辑文章也不影响文章图片正常显示  
我们需要的做的就只是正常生成文章  
将需要的图片上传到目录中
正常插入图片

如果使用typora只需要设置文章根目录，上传图片可以直接拖拽或者粘贴会更加便捷。

今天的技术分享到此结束！！
