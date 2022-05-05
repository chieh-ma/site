---
title: 网站在线监控
date: 2022-02-15 16:54:02
---
# UptimeRobot
1. 注册UptimeRobot [官网](https://uptimerobot.com/)
2. 点击`Add New Monitor`创建新的监控器
3. 输入监控器相关信息，点击`Create Monitor`
4. 在`My Settings`页面获取API Key(以下两种获取一种即可)
# uptime-status
1. 下载最新版[uptime-status](https://github.com/yb/uptime-status/releases)，解压缩压缩包
2. 打开`config.js`文件，修改你的`ApiKeys`和其它配置
3. 把修改好的文件夹放到博客根目录的`source`文件夹并重命名为`status`
4. 修改博客根目录`_config.yml`中`skip_render: [status/**]`跳过渲染
5. 部署到GitHub `hexo clean && hexo g && hexo d`
6. 打开`域名/status/`[Demo](https://machieh.com/status/)
<iframe width="854" height="480" src="https://www.youtube.com/embed/TIbZDRXM-Tg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<img src="https://hexojs.github.io/hexo-theme-landscape/assets/wallpaper-2572384.jpg"/> 