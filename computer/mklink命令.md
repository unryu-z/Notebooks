# 一、mklink介绍

使用快捷键`win+R`，打开`运行`窗口；
输入`cmd`，打开命令提示符窗口；

## 1.1、帮助

```
mklink /?
```


查看mklink命令帮助：

    创建符号链接。
    MKLINK [[/D] | [/H] | [/J]] Link Target
       /D      创建目录符号链接。默认为文件
                符号链接。
        /H      创建硬链接而非符号链接。
        /J      创建目录联接。
        Link    指定新的符号链接名称。
        Target  指定新链接引用的路径
                (相对或绝对)。

## 1.2

```
mklink d:\link\te1.txt e:\target\test1.txt
```

创建test1.txt文件的符号链接te1.txt

创建前：test1.txt文件要存在、若不存在也可创建但符号链接无法打开，**而te1.txt文件要不存在**。

创建后：文件实际存储在text1.txt中，te1.txt大小为0kb。在两个位置都可以打开、修改，且两位置修改同步删除text1.txt后te1.txt还在但无法打开，**删除te1.txt后text1.txt无影响**。

该命令**只用于文件，不可用于文件夹**。

## 1.3 /d 目录符号链接

```
mklink /d d:\link\te e:\target\test
```

创建test文件夹的目录符号链接te文件夹。

创建前后同上，只是将上述”文件“替换为”文件夹“。打开te文件夹标题栏真实路径在E盘，地址栏虚假路径在D盘。实际存储在E盘。

该命令**只用于文件夹，不可用于文件**。

## 1.4 /j 硬链接

```
mklink /j d:\link\te e:\target\test
```

创建test文件夹的目录链接te文件夹。

创建前后同上。打开te文件夹标题栏路径和地址栏路径在D盘。实际存储在E盘。

该命令**只用于文件夹，不可用于文件**。无法用于坚果云备份

## 2.5 /h 目录链接

```
mklink /h d:\link\te1.txt d:/test1.txt
```

创建test1.txt文件的硬链接te1.txt。

创建前：test1.txt文件要存在、若不存在也可创建但符号链接无法打开，而te1.txt文件要不存在。
创建后：两者都存储文件，打开路径为真实路径。修改同步。删除一个文件后另一个无影响。

该命令**只用于同一磁盘的文件**，不可用于文件夹或不同磁盘的文件。

# 二、修改Chrome默认安装位置

1、首先查找软件默认安装位置，确定自己想安装的位置，例如Chrome默认安装在"C:\Program Files (x86)\Google"，而我想将Chrome安装在“D:\Program Files\Google"下；

2、在"D:\Program Files"文件夹下新建`Google`文件夹，确保"C:\Program Files (x86)"下没有`Google`文件夹；

3、运行命令：

```
mklink /j "C:\Program Files (x86)\Google" "D:\Program Files\Google"
```

由于路径中有空格，因此要加双引号；若路径中没有空格，可不加双引号。

创建成功后可以看到"C:\Program Files (x86)"下有一个`Google`文件夹，并且这个文件夹有一个快捷方式小箭头（建议不要利用一些软件如dism++去除这个小箭头，避免你不知道那个是文件存储位置，删除文件时删错文件）；

4、完成上述操作后就可以安装软件了，软件的实际存储位置已经更改。