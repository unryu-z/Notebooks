# Typora For Markdown 语法

[![img](https://upload.jianshu.io/users/upload_avatars/1182605/cb450aa4dd48?imageMogr2/auto-orient/strip|imageView2/1/w/96/h/96/format/webp)](https://www.jianshu.com/u/e27ca08288ba)

[大道至简峰](https://www.jianshu.com/u/e27ca08288ba)关注

32016.03.02 12:27:04字数 1,026阅读 101,808

Typora是一个功能强大的Markdown编辑器，使用GFM风格（即大名鼎鼎的github flavored markdown），Typora目前支持Mac OS和Windows，Linux版本尚未发布。Typora可以插入数学表达式，插入表情，表格，支持标准的Markdown语法，可以使用标注....，功能强悍！！！还可以导出PDF文件和HTLM文件。实时预览！！！非常牛逼！

![img](https://upload-images.jianshu.io/upload_images/1182605-dab41e61b9c18d4f.png?imageMogr2/auto-orient/strip|imageView2/2/w/1200/format/webp)

Typora界面

### 数学表达式

要启用这个功能，首先到`Preference`->`Editor`中启用。然后使用`$`符号包裹Tex命令，例如：`$lim_{x \to \infty} \ exp(-x)=0$`将产生如下的数学表达式：

![img](https://upload-images.jianshu.io/upload_images/1182605-6de962030ea181b8.png?imageMogr2/auto-orient/strip|imageView2/2/w/245/format/webp)

### 下标

下标使用`~`包裹，例如：`H~2~O`将产生水的分子式。

### 上标

上标使用`^`包裹，例如：`y^2^=4`将产生表达式

![img](https://upload-images.jianshu.io/upload_images/1182605-ee74782ebfa4a275.png?imageMogr2/auto-orient/strip|imageView2/2/w/49/format/webp)

### 插入表情

使用`:happy:`输入高兴的表情，使用`:sad:`输入悲伤的表情，使用`:cry:`输入哭的表情等。以此类推！

![img](https://upload-images.jianshu.io/upload_images/1182605-c90c6fa33f424942.png?imageMogr2/auto-orient/strip|imageView2/2/w/100/format/webp)

表情

### 下划线

用HTML的语法`<u>Underline</u>`将产生下划线<u>Underline</u>.

### 删除线

GFM添加了删除文本的语法，这是标准的Markdown语法木有的。使用`~~`包裹的文本将会具有删除的样式，例如`~删除文本~`将产生~~删除文本~~的样式。

### 代码

- 使用`包裹的内容将会以代码样式显示，例如



```bash
使用`printf()`
```

则会产生`printf()`样式。

- 输入`~~~`或者```然后回车，可以输入代码块，并且可以选择代码的语言。例如：



```java
 public Class HelloWorld{
   System.out.println("Hello World!");
 }
```

### 强调

使用两个*号或者两个_包裹的内容将会被强调。例如



```undefined
**使用两个*号强调内容**
__使用两个下划线强调内容__
```

将会输出

**使用两个\*号强调内容**
**使用两个下划线强调内容**
Typroa 推荐使用两个*号。

### 斜体

在标准的Markdown语法中，*和_包裹的内容会是斜体显示，但是GFM下划线一般用来分隔人名和代码变量名，因此我们推荐是用星号来包裹斜体内容。如果要显示星号，则使用转义：



```undefined
\*
```

### 插入图片

我们可以通过拖拉的方式，将本地文件夹中的图片或者网络上的图片插入。

![img](https://upload-images.jianshu.io/upload_images/1182605-1cbd9bb6f1ed0be4.gif?imageMogr2/auto-orient/strip|imageView2/2/w/662/format/webp)

drag and drop image

### 插入URL连接

使用尖括号包裹的url将产生一个连接，例如：`<www.baidu.com>`将产生连接:[www.baidu.com](https://link.jianshu.com/?t=http://www.baidu.com).

如果是标准的url，则会自动产生连接，例如:[www.google.com](https://link.jianshu.com/?t=http://www.google.com)

### 目录列表Table of Contents（TOC）

输入[toc]然后回车，将会产生一个目录，这个目录抽取了文章的所有标题，自动更新内容。

### 水平分割线

使用`***`或者`---`，然后回车，来产生水平分割线。

------

### 标注

我们可以对某一个词语进行标注。例如



```css
某些人用过了才知道[^注释]
[^注释]:Somebody that I used to know.
```

将产生：

![img](https://upload-images.jianshu.io/upload_images/1182605-e18b795ff66e841b.png?imageMogr2/auto-orient/strip|imageView2/2/w/317/format/webp)

注释

把鼠标放在`注释`上，将会有提示内容。

### 表格



```ruby
|姓名|性别|毕业学校|工资|
|:---|:---:|:---:|---:|
|杨洋|男|重庆交通大学|3200|
|峰哥|男|贵州大学|5000|
|坑货|女|北京大学|2000|
```

将产生:

| 姓名 | 性别 |   毕业学校   | 工资 |
| :--- | :--: | :----------: | ---: |
| 杨洋 |  男  | 重庆交通大学 | 3200 |
| 峰哥 |  男  |   贵州大学   | 5000 |
| 坑货 |  女  |   北京大学   | 2000 |

其中代码的第二行指定对齐的方式，第一个是左对齐，第二个和第三个是居中，最后一个是右对齐。

### 数学表达式块

输入两个美元符号，然后回车，就可以输入数学表达式块了。例如：



```csharp
 $$\mathbf{V}_1 \times \mathbf{V}_2 =  \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\\frac{\partial X}{\partial u} &  \frac{\partial Y}{\partial u} & 0 \\\frac{\partial X}{\partial v} &  \frac{\partial Y}{\partial v} & 0 \\\end{vmatrix}$$
```

将会产生:

![img](https://upload-images.jianshu.io/upload_images/1182605-d0283749ffa69612.png?imageMogr2/auto-orient/strip|imageView2/2/w/315/format/webp)

数学表达式块

### 任务列表

使用如下的代码创建任务列表，在[]中输入x表示完成，也可以通过点击选择完成或者没完成。



```css
- [ ] 吃饭
- [ ] 逛街
- [ ] 看电影
- [ ] 约泡
```

![img](https://upload-images.jianshu.io/upload_images/1182605-cd9c1b5edb6b83a8.png?imageMogr2/auto-orient/strip|imageView2/2/w/141/format/webp)

任务列表

### 列表

输入+, -, *,创建无序的列表，使用任意数字开头，创建有序列表，例如：



```undefined
**无序的列表**
* tfboys
* 杨洋
* 我爱你
```

**无序的列表**

- tfboys
- 杨洋
- 我爱你



```undefined
**有序的列表**
1. 苹果
6. 香蕉
10. 我都不喜欢
```

**有序的列表**

1. 苹果
2. 香蕉
3. 我都不喜欢

### 块引用

使用>来插入块引用。例如：



```undefined
>这是一个块引用！
```

将产生：

> 这是一个块引用！

### 标题

使用#表示一级标题，##表示二级标题，以此类推，有6个标题。

**这篇文章的下载地址**:链接: [https://pan.baidu.com/s/1miwkB4c](https://link.jianshu.com/?t=https://pan.baidu.com/s/1miwkB4c) 密码: h3fb