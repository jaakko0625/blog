---
title: 如何为Ubuntu20设置开机自启动
date: 2023-03-04 13:02:38
tags: [技术备忘录]
categories:
thumbnail:
---
<!-- more -->
1. 创建system服务

	nano /etc/systemd/system/app.service


2. 键入system服务内容

    ```json
    [Unit]
    Description=My Command
    After=network.target
    
    [Service]
    ExecStart=/path/to/your/command
    
    [Install]
    WantedBy=multi-user.target
    ```


	其中：


	- Description：服务的描述，可以根据您的需求更改。
	- After：定义服务应该在哪个目标之后启动。在本例中，我们将其设置为 network.target。
	- ExecStart：定义要在启动服务时运行的命令的完整路径。
	- WantedBy：定义服务应该启动的目标。在本例中，我们将其设置为 multi-user.target。
3. 重载system配置

	systemctl daemon-reload


4. 启动创建的服务

	systemctl start app.service


5. 检查服务是否运行正常

	systemctl status app.service


6. 开机自启动服务

	systemctl enable app.service

