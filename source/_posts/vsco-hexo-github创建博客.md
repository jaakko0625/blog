---
title: vsco+hexo+github创建博客
date: 2022-04-20 14:14:38
tags: [hexo,blog,github]
categories: 技术分享
---
![vsco+hexo+github创建博客](https://tva2.sinaimg.cn/large/0072Vf1pgy1foxki70guwj31kw0w0qpu.jpg)
通过Vsco+Hexo+Github创建个人博客
=============================
环境准备
<!-- more -->

-----
#### 本地mac = node12 + vscode + hexo + icarus  
#### linux服务端 = ndoe12 + npm + pm2 + crontab

**github创建项目储存博客内容  
使用GithubDesktop打开项目**

### 本地环境搭建
**node使用了pkg方式安装**
<https://nodejs.org/download/release/v12.22.7/>

**安装 hexo-cli**  
npm i -g hexo-cli 
执行以下命令初始化hexo
hexo init

**编辑 _config.yml**

    title: Jaakko的365天 #网站标题
    subtitle: ''
    description: ''
    keywords: null #搜索关键字
    author: Jaakko #作者名称
    language: zh-CN #显示语言

执行以下命令拉起hexo  
hexo s

**安装 icarus主题**  
npm install hexo-theme-icarus  
hexo config theme icarus

上述环境搭建好后使用GitHubDesktop  
将内容Push到github

linux安装好环境后使用pm2后台挂起hexo  
run_pm2.js  

    //run
    const { exec } = require('child_process')
    exec('hexo server',(error, stdout, stderr) => {
    if(error){
    console.log('exec error: ${error}')
    return
    }
    console.log('stdout: ${stdout}');
    console.log('stderr: ${stderr}');
    })

pm2 start run_pm2.js  pm2挂载hexo  
pm2 startup  开机自启动  

linux使用crontab定时git pull

    nano /etc/crontab
    */10 * * * * root /root/blog/auto_git_pull.sh >> /root/blog.log 2>&1
    /etc/init.d/crontab restart

auto_git_pull.sh

    #!/bin/bash

    cd /root/blog/
    git pull

**linux服务端部署完毕**

**mac本地**
hexo创建文章
hexo new "我的第一篇博客"
编写文章
push到github
自动同步到网站
