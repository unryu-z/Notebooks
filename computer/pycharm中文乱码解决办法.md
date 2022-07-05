https://blog.csdn.net/niedongri/article/details/72142401

# PyCharm----中文显示乱码的解决方法总结

 在使用pycharm时，经常会碰到中文会显示为乱码，比如:输出控制台、代码内容、左边项

 

目路径等。下面把我自己平时碰到的情况怎么解决的方法总结了一下。

 

 

## 一、pycharm左边项目路径栏目中文有乱码

这是因为pycharm默认没有设置支持中文显示的字体。所以我们只有设置一下支持中文的字体就可以了。

进入settings---Appearance & Behavior，勾选Override default fonts by并选择一个支持中文的字体，

我这里选择了微软雅黑(Microsoft YaHei)，自己根据喜欢的字体来设定。保存后，再来看看就真正显示了

## 二、输出控制台显示为乱码

这种情况下，我们到settings----Editor----File Encodings里设置IDEEncoding(全局编码)、Project Encoding(项目编码)、Default encoding for properties(属性文件的默认编码)都设置为UTF-8.

或者，在文件的第一行注释：

```
# -*- coding: utf-8 -*-
```

上述代码也可加入到文件模板，File->Settings->Editor->File and Code Templates(文件和代码模板)

设置后运行即可.

------------------------------------------------
版权声明：本文为CSDN博主「n_laomomo」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/niedongri/article/details/72142401