前端笔记-HTML



#### HTML/HMTL5/XHTML

HMTL即（Hyper Text Markup Language），是一种标记型语言

##### HTML元素

html文档是通过HTML元素进行定义的,HTML元素指从`开始标签(egg:<p>)`到`结束标签（egg：</p>)`的所有代码

```html
<html>

<body>
<p>This is my first paragraph.</p>
</body>

</html>
```

如上包含三个HTML元素，其中
- `<P>`元素定义了HTML文档中的一个段落
- `<body>`元素定义了HTML文档的主体，元素内容是另一个HTML元素`<p>`
- `<html>`元素定义了整个HTML文档

##### HTML属性

属性可以为HTML元素提供附加信息，属性在**开始标签中定义**以`key=value`的形式出现，如下其中`bgcolor`和`href`都是定义的属性
```html
<html>
<body bgcolor="yellow">
<!-- 注释 -->
<a href="http://www.w3school.com.cn">
This is a link</a>

</body>
</html>
```

##### HTML标题

html标题通过`<h1> - <h6>`进行定义（依次减小`<h1>`标题最大）。要确认该标签只用作标题，不能因为需要粗体或大号字体而使用标题

```html
<h1>This is a heading</h1>
<h2>This is a heading</h2>
<hr/> <!-- 这是个水平线-->
<h3>This is a heading</h3>
```

##### HTML段落

段落即将HTML文档分割为若干段落，使用`<p>`标签

```html
<p> 这是第一个段落 <\p>
<P> 这是第二个段落 <\p>
<p>This is<br />a para<br />graph with line breaks</p> 
```

以上使用`<br />`元素在不产生新段落的情况下进行换行，这个元素是一个空的HTML元素，因此关闭标签没有任何意义，所以它没有结束标签

##### HTML样式

使用`style`属性可以改变HTML元素的样式，如，使用`;`可以进行多个属性的定义

```html
<html>

<body style="background-color:yellow" >
<h1 style="background-color:red;font-family:verdana;text-align:center">标题一字体黑色居中</h1>
<p style="background-color:green;font-family:arial;color:red;font-size:30px;">一个定义了字体颜色大小的段落</p>
<h2 style="background-color:blue">标题二背景蓝色</h2>
</body>


</html>
```

##### HTML文本格式化

这节太长了，具体参照[《w3school》](http://www.w3school.com.cn/html/html_formatting.asp),简单记录下，主要包括以下
- 文本格式化（定义字体类型、字体大小、是否倾斜、上下角标）
- 预格式文本（不对空格换行进行解释，适合代码块）
- 计算机输出标签（通常用户显示计算机编程代码）
- 地址
- 缩进和首写字母缩写
- 文字方向
- 块引用
- 删除字效果和插入字效果

##### HTML引用

HTML` <q> `元素定义短的引用。浏览器通常会为` <q> `元素包围引号。

##### HTML计算机代码

通常，HTML 使用可变的字母尺寸，以及可变的字母间距。在显示计算机代码示例时，并不需要如此。`<kbd>, <samp>, 以及 <code> `元素全都支持固定的字母尺寸和间距。

##### HTML CSS

通过使用 HTML4.0，所有的格式化代码均可移出 HTML 文档，然后移入一个独立的样式表。当浏览器读到一个样式表，它就会按照这个样式表来对文档进行格式化。有以下三种方式来插入样式表
- 外部样式表(适合页面样式需要重复利用)
- 内部样式表（适用于单个文件需要特别样式）
- 内联样式表（适用于文件内个别元素需要特别的样式）

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
<!-- 以上就是外部样式的例子-->
<head>

<style type="text/css">
body {background-color: red}
p {margin-left: 20px}
</style>
</head>
<!-- 以上就是内部样式表 -->

<p style="color: red; margin-left: 20px">
This is a paragraph
</p>
<!-- 以上是内联样式表 -->
```

##### HTML链接

HTML使用超级链接与其他文档进行相连，可以点击跳转那种。链接文本不必一定是文本。图片或其他 HTML 元素都可以成为链接。

使用`<a>`标签在HTML中创建链接，有两种使用标签的方式
- 通过使用 href 属性 - 创建指向另一个文档的链接
- 通过使用 name 属性 - 创建文档内的书签

```html
<html>

<body>

<a href="http://arvon.top/" target="_blank">我的博客!</a>

<p>如果把链接的 target 属性设置为 "_blank"，该链接会在新窗口中打开。</p>

</body>

</html>
```

##### HMTL图片

在HTML中，图像由`<img>`标签定义,它只包含属性，并且没有闭合标签。更详细查阅[【w3school】](http://www.w3school.com.cn/html/html_images.asp)
- 背景图片
- 排列图片
- 浮动图片
- 调整图片尺寸
- 为图片显示替换文本
- 制作图像链接
- 创建图像映射
- 把图像转换成图像映射

##### HTML表格

表格由`<table>`标签来定义。每个表格均有若干行（由` <tr> `标签定义），每行被分割为若干单元格（由` <td>` 标签定义）。字母` td `指表格数据（table data），即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。更详细的可以查看[【w3school】](http://www.w3school.com.cn/html/html_tables.asp)

如下例子

```html
<!--table -->
<table border="1" cellpadding="10" cellspacing="2" background="/i/eg_bg_07.gif">
<caption>我的标题</caption>
<tr>
<th>Heading</th>
<th colspan="2" align="left">Another Heading </th>
</tr>
<tr>
<td>row 1, cell 1</td>
<td>row 1, cell 2</td>
<td>row 1, cell 3</td>

</tr>
<tr>
<td align="left">row 2, cell 1</td>
<td>row 2, cell 2</td>
<td bgcolor="yellow">&nbsp;</td>
</tr>
</table>
```

##### HTML列表

列表分为有序列表和无序列表，有序列表可以单独指定起始标签值

```html
<html>
<body>

<ul>
  <li>咖啡</li>
  <li>茶</li>
  <li>牛奶</li>
</ul>

<ol>
  <li>咖啡</li>
  <li>牛奶</li>
  <li>茶</li>
</ol>

<ol start="50">
  <li>咖啡</li>
  <li>牛奶</li>
  <li>茶</li>
</ol>
 
</body>
</html>

</html>
```

##### HTML块

大多数HTML元素被定义为块级元素（block level element）或内联元素（inline element）。块级元素在浏览器显示时通常会以新行开始和结束（如`<h1>,<p>,<ul>,<table>`)，内联元素通常不会以新行开始（如`<b>,<td>,<a>,<img>`)。

可以通过`<div>`和`<span>`将HTML元素组合起来
- `<div>`元素：属于块级元素，是用于组合其他HTML元素的容器。如果与CSS一同使用，`<div>`元素可用于对大的内容块设置样式属性。另一种常见用途是文档布局
- `<span>`元素：属于内联元素，可用作文本容器。当与CSS一同使用时，用于为部分文本设置属性。

##### HTML类

对HTML进行分类，让我们能够对同类的元素定义CSS样式。

```html
<html>
<head>
<style>
.myblog {
    background-color:black;
    color:white;
    margin:20px;
    padding:20px;
}
span.red {color:red;}	
</style>
</head>

<body>

<div class="myblog">
<h2><span class="red">Arvon</span> Info</h2>

<p>Arvon Blog: <a href="http://arvon.top/" target="_blank">Blog</a></p>

<p>Arvon Github: <a href="https://github.com/Gourds">Github</a></p>
</div> 

</body>
</html>
```

##### HTML布局

参展[【w3c】](http://www.w3school.com.cn/html/html_layout.asp)

##### HTML响应式web设计

响应式设计即RWD（Responsive Web Design）。参考[【w3c】](http://www.w3school.com.cn/html/html_responsive.asp)
- 能够以可变尺寸传递网页
- 对于平板和移动设备是必须的

常见的实现方式有两种：
- 自己设计 
- 使用Bootstrap

##### HTML框架

使用框架可以再同一个浏览器窗口中显示多个页面，每份HTML文档称为一个框架。参照[【w3c】](http://www.w3school.com.cn/html/html_frames.asp)
- 垂直框架
- 水平框架

两种框架可以组合使用。假如一个框架有可见边框，用户可以拖动边框来改变它的大小。为了避免这种情况发生，可以在 `<frame>`标签中加入：noresize="noresize"。

#### HTML内联框架（HTML Iframe）

内联框架（Ifram）用于在网页内显示网页。参照参照[【w3c】](http://www.w3school.com.cn/html/html_iframe.asp)

```html
<html>
<body>

<iframe src="/example/html/demo_iframe.html" name="iframe_a"></iframe>

<p><a href="http://arvon.top" target="iframe_a">Arvon Blog</a></p>

<p><b>注释：</b>由于链接的目标匹配 iframe 的名称，所以链接会在 iframe 中打开。</p>

</body>
</html>
```

##### [HTML背景](http://www.w3school.com.cn/html/html_backgrounds.asp)

设置背景可以美化站点，背景可以设置为颜色或者图像。

当设置为颜色时，支持3中方式（十六进制数字、RGB值、或颜色名）
```html
<body bgcolor="#000000">
<body bgcolor="rgb(0,0,0)">
<body bgcolor="black">
```

当设置为图像时，使用图像的URL（可以为相对地址，也可以为绝对地址），如果图像尺寸小于窗口大小，那么图像将被浏览器敞口复制。使用图像时注意点如下：
- 背景图片文件不应超过10k，不能影响页面的加载时间
- 背景图像是否与页面中的图像搭配良好
- 背景图像是否与页面中的文字搭配良好
- 图像平铺后是否依然美观
- 要避免背景比文字有吸引力

##### HTML脚本

使用JavaScript可以使HTML页面具有更强的动态和交互性，常用于图片操作、表单验证、内容动态更新等。参照[【w3c】](http://www.w3school.com.cn/html/html_scripts.asp)

##### [HTML头部](http://www.w3school.com.cn/html/html_head.asp)

HTML头部包括以下几部分
- 文档标题。不会在文章中显示，`<head>` 元素是所有头部元素的容器,可以添加的标签包括`<title>、<base>、<link>、<meta>、<script> 以及 <style>`
- 链接目标。可以指定默认是否打开新窗口
- 文档描述。可以记录作者、描述等
- 文档关键词。就是TAG的意思
- 重定向用户。可以将用户引导到新的页面

##### HTML字符实体

在HTML中有些字符是预留的不能直接使用，所以当需要使用这些字符时需要使用字符实体。如大于小于号会被认为是标签
，字符实体可参考[【w3c】](http://www.w3school.com.cn/tags/html_ref_entities.html)

##### HTML统一资源定位器

URL（Uniform Resource Locator）即统一资源定位器

##### HTML [URL字符编码](http://www.w3school.com.cn/tags/html_ref_urlencode.html)

URL编码会将字符转换为可通过因特网传输的格式。
- URL只能使用`ASCII`字符集来通过因特网发送
- URL编码使用`%`后面的两位16进制数字来替换非`ASCII`字符
- URL不能包含空格，通常使用`+`来替换空格

##### [HTML颜色](http://www.w3school.com.cn/html/html_colors.asp)

##### [HTML颜色名](http://www.w3school.com.cn/html/html_colornames.asp)

##### [HTML速查手册](http://www.w3school.com.cn/html/html_quick.asp)
