---
title: 创建文章和页面
date: 2022-01-25 14:17:12
---
# 创建本地文章文件
在D:\blog文件夹右键Git Bash Here，输入：
```
hexo new "example"
```
example.md文件会建在目录D:\blog\source\\_posts下，使用Markdown编辑器编辑文档。

# Markdown编辑器：
* typora v0.11.18 [Download (Windows x64)](https://download.typora.io/windows/typora-update-x64-1117.exe) 🙂
* marktext [官网](https://marktext.app/)
* Sublime Text [官网](https://www.sublimetext.com/)

# 常用Markdown语法
1. 标题
   \# 一级标题
   \## 二级标题
   \### 三级标题
   \#### 四级标题
   \##### 五级标题
   \###### 六级标题
2. 字体
   \*\***example**\*\*
   \**example*\*
   \*\*\****example***\*\*\*
   \~\~~~example~~\~\~
3. 链接
   \[an example](https://example.com/ "Optional Title")
4. 图片
   \!\[Alt text](https://example.com/img.jpg "Optional title")
5. 列表
* 无序列表
​	\- example
​	\+ example
​	\* example
* 有序列表
​	1\. example
​	2\. example
​	3\. example

# 推送至GitHub
编辑保存关闭文档，输入命令：
```
hexo clean && hexo g && hexo d
```
之后就可以在网站上看到该文章。

# 创建本地页面文件
在D:\blog文件夹右键Git Bash Here，输入：
```
hexo new page "example"
```
目录D:\blog\source会出现example文件夹，使用Markdown编辑器编辑文件夹中index.md文档。

# 将页面添加至导航栏
修改主题配置文件_config.yml
```
navbar:
    # 导航栏菜单，可自行增减.
    # Navigation bar menu.
    menu:
        首页: /
        归档: /archives/
        分类: /categories/
        标签: /tags/
        # 说说: /talk/
        友链: /links/
        赞赏: /appreciate/
        关于: /about/
        举例: /example/
        # ...
```

# 推送至GitHub
编辑保存关闭文档，输入命令：
```
hexo clean && hexo g && hexo d
```
之后就可以在网站的导航栏看到“举例”，点击即可看到该页面。