---
title: Office 365安装后变成2016专业增强版,显示产品激活失败的解决方案
date: 2022-02-28 10:18:56
---
今天用了很久的Office突然显示产品激活失败，打开Excel文档能看就是不能编辑，我反复退出登录账号也不行，我想我开了一年的Microsoft 365家庭会员，还没到期，怎么就不能用了呢？打开账户一看显示的是Office 2016 增强版，于是又开始卸载重装Office，还是显示产品激活失败，最后百度一下解决了。
这种情况发生的原因可能就是之前安装的office版本已经被识别为未激活版本，卸载不完全仍然保留了未激活的信息。解决方法就是删除之前的密钥。
步骤：
1. 搜索cmd，右键以管理员身份运行
2. 执行命令： `cd C:\Program Files\Microsoft Office\Office16`，进入Office2016文件夹
3. 执行命令：`cscript ospp.vbs /dstatus`，获取Office激活信息，得到`Last 5 characters of installed product key: KHGM9`(已安装产品密钥的最后5个字符)
4. 执行命令：`cscript ospp.vbs /unpkey:KHGM9`，删除激活的信息
5. 以管理员身份打开Office，重新登录即可。