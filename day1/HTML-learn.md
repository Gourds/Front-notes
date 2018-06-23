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


