**SiteRule** 具有三个主要组件：**Site**，**Rule**和**Selector**。两者之间的关系是逐层包含的，即**站点site包含多个规则rule**，而**规则rule包含各种选择器selector**。

我们需要了解的第一件事是选择器，通过它我们可以找到并找到所需的数据。规则是一个包含各种选择器的集合。不同的选择器可以获得不同的数据。每个规则的最终组合是一个站点！

好了，现在让我们开始学习SiteRule的语法规则。

## 选择器selector

------

选择器是整个SiteRule中最重要的部分，因为选择器定义的行为是告诉Yealico如何获取指定的数据。能够熟练使用Selector的前提是您应该了解[HTML](https://www.w3schools.com/html/)，[CSS](https://www.w3schools.com/css/)和[正则表达式](https://www.w3schools.com/js/js_regexp.asp)。

选择器包含5个参数：**选择器**，**函数**，**参数**，**正则表达式**，**替换**。

#### 选择器selector

可以选择特定HTML标记（以下称为“元素”）的CSS3语法选择器。

特殊语法– **this**代表当前选择的元素（以下称为“当前元素”）。

#### 功能function

将在当前元素上执行的方法。函数支持以下值：

- **html**：获取当前元素内的所有HTML字符串；
- **text**：获取当前元素内的所有纯字符串（删除所有HTML标记）；
- **attr**：将获取当前元素的属性值。必须通过设置param参数来确定要具体获取哪个属性值；
- 空白字符或nil：获取包含当前元素本身的所有HTML字符串。

支持多种功能，以逗号分隔。

#### 参数param

当选择的功能设置为“ATTR”帕拉姆指定将获得属性值的属性的名称。

支持多个属性，以逗号分隔。

#### 正则表达式regex

是在上述选择器获得的字符串上使用的正则表达式，包含至少一个Group。匹配的值使用占位符**$ 1**，**$ 2**，**$ 3表示**...占位符可用于替换。

#### 替代replace

使用替换的先决条件是已设置regex参数。单独使用替换无效。

当替换为空时，默认值为**$ 1**占位符，这是使用正则表达式匹配的第一个组值。

如果没有任何匹配项，并且您想使用原始字符串，则可以使用**| {source：}**占位符。

通过使用正则表达式匹配的占位符，您可以合并所需的最终字符串结果。当然，它也可以是数学表达式，通常用于获得评级。

## 规则

------

Rule是各种选择器的集合，不同的选择器可以获取不同的数据。Rule进一步细分为三种类型的特定页面：**SeriesRule系列页**，**ListRule列表页**，**DetailRule详细页**和**GalleryRule通用规则**。

### SeriesRule系列页，ListRule列表页

------

SeriesRule主要应用于ListRule的顶层页面。例如，某些网站不仅具有“列表”页面，而且还具有“系列”页面。单击系列，您可以输入相应的列表。

当然，如果您需要将每个Tag链接写为Page，则直接使用SeriesRule获取Tag页面的所有内容是一个很好的选择。
这样，您可以将所有标签统一为一页，然后单击“标签”以方便地获取相应的列表。

ListRule主要应用于列表页面，例如常规列表页面，标签链接页面和搜索页面。

ListRule包含以下选择器：

#### 项目

选择列表中的每个项目，获得的结果应该是一个包含多个相同类型项目的集合。

例如，网站的最新文章页面通常是列表页面，并且该页面将按日期顺序列出最新文章。我们通过选择器项获得的集合应该是此页面上所有最新文章的集合。

获取项目后，我们如何获取每个项目中包含的详细数据？例如，文章的标题，作者，更新时间，评分等。这时，我们需要使用以下选择器来获取相应的数据。

以下所有选择器的选择仅限于上面检索的每个项目。

#### idCode

商品的唯一标识符。idCode替换URL模式中的{idCode：}占位符。

#### 标题

项目标题。

#### 盖

商品的封面图片网址。

#### coverWidth

项目封面图像的宽度。

#### coverHeight

项目封面图像的高度。

#### largeImage

商品的大图片网址。

#### 类别

项目的类别。

#### 作者

项目的作者。

#### 上载者

项目的上传者。

#### 已发表

商品发布的时间。

#### 约会时间

项目的时间，通常是指更新时间。

#### 评分

项目的等级。

#### totalImages

图像总数。

设置此参数并将DetailRule容器中pictureRule的url用作分页占位符{page：}时，Yealico将根据分页规则自动获取所有大图像的url。



### 详细规则

------

DetailRule主要用于详细页面。通常，它是指单击ListRule中的项目后的链接页面。Selector的定义：标题，封面，类别，作者，上传者，已发布，日期时间和等级与ListRule中描述的相同。

此外，DetailRule还包含几个微型规则，包括：**tagRule**， **pictureRule**， **ChapterRule** 和**commentRule**。

#### totalImages

详细信息页面中的图像总数。

设置此参数并将pictureRule的url容器用作分页占位符{page：}时，Yealico将根据分页规则自动获取所有大图像的url。

#### photoAlbumLink

某些网站的专辑或视频不在详细页面上，您需要单击第二级页面的链接以获取专辑或视频的详细信息。

设置photoAlbumLink时，pictureRule将作用于与photoAlbumLink对应的链接页面，videoRule将相同。

### tagRule

在详细信息页面中获取所有标签数据。

tagRule包含以下选择器：

#### 项目

获取包含所有标签的集合。

以下所有选择器选择都限于检索到的每个项目。

#### 名称

标签的名称。

#### 网址

标签的页面链接。

### pictureRule

在详细信息页面中获取所有图像数据。

pictureRule包含以下选择器：

#### 项目

获取包含所有图片的集合。

以下所有选择器选择都限于检索到的每个项目。

#### 缩图

图片的缩略图。

#### 网址

图片的大图片网址。定义链接选择器后，将在链接所指向的页面上执行此URL选择器。

#### 链接

获取页面链接以获取大图片网址。

### videoRule

与pictureRule相同。

### 规则

在详细信息页面中获取所有章节数据。

ChapterRule包含以下选择器：

#### 项目

获取包含所有章节的集合。

以下所有选择器选择都限于检索到的每个项目。

#### idCode

本章的唯一标识符。该部分的idCode必须与ListRule的idCode区分开。本章的idCode替换URL模式中的{cidCode：}占位符。

#### 标题

本章的标题。

#### 约会时间

本章的日期时间。

#### 网址

本章指向的页面链接。

### commentRule

在详细信息页面中获取所有评论数据。

commentRule包含以下选择器：

#### 项目

获取包含所有评论的集合。

以下所有选择器选择都限于检索到的每个项目。

#### 头像

用户的头像图片。

#### 用户名

评论的用户名。

#### 约会时间

评论的日期时间。

#### 内容

评论内容。

### 画廊规则

------

GalleryRule主要用于图片浏览页面。

GalleryRule包含以下选择器：

#### 总页数

图片浏览页面上的总页数。

#### 项目

获取当前页面的所有图片数据的集合。

#### 图片

项目的网址。

### videoRule

与pictureRule相同。



## 现场

------

网站是整个网站规则的最外层，它包含网站的基本设置，页面设置，各个页面的默认URL模式以及页面规则。

网站包含以下参数：

#### 名称

网站名称。

#### 显示模式

列表页面的默认显示模式，支持：**text**，**table**，**collection**，**Waterfall，tag**。Waterfall需要在ListRule中获取图片的宽度和高度，否则它将自动切换回集合显示模式。

#### loginUrl

登录页面链接地址。

#### indexUrl，detailUrl，galleryUrl，searchUrl

这些是列表页面，详细信息页面，图片浏览页面和搜索页面的链接URL模式。这些页面的链接URL模式可以包含以下类型的占位符：

**{page：**起始页码**：**增量页码**}**

分页占位符。例如，{page：1：1}表示分页开始页号为1，并且每个分页页均增加1。如果每个增量页号为1，则可以将其缩短为{page：1}。

如果第一页不需要分页信息，请使用以下占位符：

**{pageFormat：{page：**起始页码**：**递增页码**}}**

#### {idCode：}

表示ListRule中项目的唯一标识符。主要用于detailUrl。

#### {cidCode：}

代表章节的唯一标识符。主要用于galleryUrl。

#### {关键词：}

搜索页面的关键字占位符。当用户搜索时，输入的关键字将首先替换该占位符，然后向服务器发起搜索请求。

### 系列规则

默认的系列页面规则。这是一个ListRule。

### indexRule

默认列表页面规则。这是一个ListRule。

### detailRule

默认的详细信息页面规则。这是一个DetailRule。

### galleryRule

默认图片浏览页面规则。这是一个GalleryRule。

### 页数

网站可以设置多个页面。每个页面还可以针对自己的**displayMode**，**flags，indexUrl**，**detailUrl**，**galleryUrl**，**listRule**，**detailRule**和**galleryRule**进行自定义。

当需要为当前页面设置关联的**ListRule时**，需要将**relListRuleIndex**设置为相应**ListRule**的索引。

同样，您可以设置**detailRule**和**galleryRule**。

### 标志

使用标记在网站上设置更多详细信息。

支持的标志是：

#### 需要登录

请注意，站点必须先登录才能获取正常数据。

#### 重复的缩略图

所获取的缩略图是大图像，然后按背景位置进行移动。

#### ignoreDetail

使用该应用程序时，直接从列表页面转到图片浏览页面，而忽略详细信息页面。通常用于图像板站点，例如mbooru。

#### jsNeededIndex，jsNeededDetail，jsNeededGallery，jsNeededSearch，jsNeededPhotoAlbum，jsNeededAll

标记列表页面，详细信息页面和图片浏览页面分别需要Web浏览器加载页面以正常获取数据，因为需要执行JavaScript。

#### postSearch，postIndex，postDetail，postGallery，postPhotoAlbum，postAll

请注意，搜索需要通过POST发送。这些参数以及GET方法都放入searchUrl中。

#### big5CharsetIndex，big5CharsetDetail，big5CharsetGallery，big5CharsetSearch，gbkCharsetIndex，gbkCharsetDetail，gbkCharsetGallery，gbkCharsetSearch

指定页面的HTML字符集。

#### userAgentMobile

模拟移动设备对网站的访问。

### seriesRules，listRules，detailRules，galleryRules

提供附加的**seriesRule**，**listRule**，**detailRule**和**galleryRule，**以方便使用不同的Pages。