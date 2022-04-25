# 安装hexo
npm install hexo -g
# 升级hexo
npm update hexo -g

# 新建文章
hexo n "paper name"

# 生成静态文件
hexo g

# 启动服务
hexo s
hexo server -s # 冷部署
hexo server -p 5000 # 更改监听端口
hexo server -i 192.168.xx.xx #自定义IP启动

# 清除缓存
hexo clean

# 部署git
hexo d

# 随机二刺螈图片
http://www.dmoe.cc/random.php