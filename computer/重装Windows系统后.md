# 一、重装Windows系统

根据B站up主`硬件茶谈`的[视频](https://www.bilibili.com/video/BV1DJ411D79y)重装系统。

激活、对磁盘进行分区。可能有一些电脑要重新安装驱动。

# 二、更改Windows系统一些文件夹位置

# 2.1、系统临时文件夹

1、系统临时文件夹C:\Windows\Temp
2、用户临时文件夹C:\Users\用户名\AppData\Local\Temp
3、浏览器缓存C:\Users\用户名\ AppData\Local\Microsoft\Windows\Temporary Internet Files

根据`mklink`命令更改文件夹位置，最好更改后的文件夹和系统在同一硬盘下，防止系统调用数据时影响电脑速度。

## 2.2、个人文件夹

个人文件夹如：下载、图片、音乐、文档、视频等文件夹。文件夹位置：C:\Users\用户名

同样利用`mklink`转移文件夹位置，我将上述文件夹转移到机械硬盘，而系统在固态硬盘。

# 3、本人使用的软件

由于以前使用的是机械硬盘，在固态硬盘重装系统后要将软件迁移到固态硬盘。我是直接重装所有软件。

## 3.1、Windows基本软件

1、系统更新、清理垃圾、防护：Dism++、CCleaner、火绒
2、办公软件：Office、Adobe Acrobat DC（查看pdf）、DeepL（翻译）
3、下载工具：IDM、BitComit、EagleGet、迅雷、百度网盘、硕鼠、哔哩哔哩唧唧、Aria2 Tools（支持RPC协议）
4、其他软件：Chrome浏览器、坚果云（文件同步）、网易云、foobar2000（本地音乐）、potplayer（视频）、bandizip（解压文件）、Typora（笔记）、Snipaste（截图）、Everything（快速搜索本地文件）

## 3.2、专业软件

Matlab、MathType、Mathpix、SPSS、SAS

## 3.3、隔离软件

在虚拟机、android、网页版运行的软件

微信、QQ、腾讯会议、网易云音乐、百度网盘、迅雷等国产软件，避免其扫描数据

## 3.4、其他软件

foxmail邮箱、steam、Pixiv反向代理软件、Bitvise SSH Client、Clash for Windows、bandicam（视频录制）

