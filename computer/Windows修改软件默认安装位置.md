# 简单介绍

由于每次安装软件都要修改软件的安装路径，避免软件都装在C盘、占用C盘空间，于是找到通过修改注册表的方法修改默认安装位置。

==注意==：通过此方法修改默认安装位置后，部分软件在安装后可能无法打开，如Google Chrome浏览器，对于这些软件，可以<u>参考Windows修改Chrome浏览器安装位置</u>修改安装位置。

# 修改方法

1、通过快捷键win+R，打开`运行`窗口；

2、输入`regedit`，打卡注册表编辑器；

3、在左边依次打开文件夹HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft \ Windows\ CurrentVersion，选中CurrentVersion文件夹；

4、在右边找到“ProgramFilesDir”和“ProgramFilesDir(x86)”，进行下面操作；

5、双击“ProgramFilesDir”、可以发现在弹出的窗口中`数值数据(V):`下的路径为`C:\Program Files`，将这个路径修改为你想要安装软件的默认位置，如`D:\Program Files`，修改完成后点击`确认`；双击“ProgramFilesDir(x86)”，路径修改为`D:\Program Files`或`D:\Program Files(x86)`都可以；

6、对于注册表“ProgramFilesPath”，可以不用修改，因为它指定的路径为`%ProgramFiles%`是一个相对路径，也是一个环境变量。若要修改，请修改为和“ProgramFilesDir”同路径；

7、关闭注册表编辑器，完成修改。



