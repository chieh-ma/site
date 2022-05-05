---
title: 网站搭建
date: 2022-01-20 10:38:03
---
# 创建GitHub仓库
点击GitHub中的`New repository`创建新仓库，仓库名应该为：`用户名.github.io` 这个用户名使用你的GitHub帐号名称代替，这是固定写法。
<!--more-->
# 安装Git
Git官网：[https://git-scm.com/](https://git-scm.com/ "点击访问Git官网")
安装完成后，在命令行里输入git测试是否安装成功。

# Git与GitHub帐号绑定
鼠标右击打开`Git Bash Here`，设置`user.name`和`user.email`配置信息
```
git config --global user.name "你的GitHub用户名"
git config --global user.email "你的GitHub注册邮箱"
```
生成ssh密钥文件
```
ssh-keygen -t rsa -C "你的GitHub注册邮箱"
```
然后直接三个回车即可，默认不需要设置密码。
然后在用户\你的账户文件夹下找到生成的.ssh的文件夹中的`id_rsa.pub`密钥，将内容全部复制
打开`GitHub_Settings_keys`页面，新建`new SSH Key`
Title为标题，任意填即可，将刚刚复制的id_rsa.pub内容粘贴进去，最后点击`Add SSH key`。
在Git Bash中检测GitHub公钥设置是否成功

```
ssh git@github.com
```
如下显示表示成功。
```
PTY allocation request failed on channel 0
Hi majiepage/majiepage.github.io! You've successfully authenticated, but GitHub does not provide shell access.
Connection to github.com closed.
```

# 安装Node.js
Node.js官网：[https://nodejs.org/zh-cn/](https://nodejs.org/zh-cn/ "点击访问Node.js官网")
安装后，检测Node.js是否安装成功，在命令行中输入`node -v`，出现版本号表示Node.js安装成功。
检测npm是否安装成功，在命令行中输入`npm -v`，出现版本号表示npm安装成功。

# 安装Hexo
在D盘创建blog文件夹，进入文件夹中，右键选择`Git Bash Here`，使用npm命令安装Hexo，输入
```
npm install -g hexo-cli 
```
安装完成后，关闭命令行窗口。在D:\blog文件夹中右键选择`Git Bash Here`，输入`hexo -v`，出现版本号表示安装成功。
然后初始化我们的博客，输入：

```
hexo init blog
```
会看到在D:\blog文件夹中生成很多文件，接着生成网页输入：
```
hexo g
```
本地预览输入：
```
hexo s
```
完成后，打开浏览器输入地址：[localhost:4000](localhost:4000)

# 推送网站
打开站点的配置文件`_config.yml`，翻到最下修改为：
```
deploy:
type: git
repo: git@github.com:username/username.github.io.git
branch: main
```
保存站点配置文件。然后安装Git部署插件，输入命令：
```
npm install hexo-deployer-git --save
```
最后输入如下命令完成发布：
```
hexo clean && hexo g && hexo d
```
