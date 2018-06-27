CSS-learn

### CSS 介绍

CSS(层叠式样式表)用于指定文档如何呈现给用户（包括样式、布局等）。

CSS的规则组成：
- 一组属性，属性的值指定HTML内容的显示方式
- 一个选择器，指定CSS规则想要应用到哪里，如一个标题或段落等。

CSS如何工作
- 浏览器将HTML和CSS转化成DOM（文档对象模型）。DOM在计算机内存中表示文档，它把文档内容和其样式结合在一起
- 浏览器显示DOM内容

关于DOM：DOM是一种树形结构，标记语言中的每个元素、属性、文本片段都是一个DOM节点

将CSS应用到HTML文档上
- 外部样式表
```html
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>
<!--or follow-->
h1 {
  color: blue;
  background-color: yellow;
  border: 1px solid black;
}
```
- 内部样式表
```html
<html>
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }

      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>
```
- 内联样式
```html
<html>
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
  </head>
  <body>
    <h1 style="color: blue;background-color: yellow;border: 1px solid black;">Hello World!</h1>
    <p style="color:red;">This is my first CSS example</p>
  </body>
</html>
```

#### CSS语法

基本来看CSS由两块内容构成：属性（Property）及属性值（Value）。给CSS属性设置特定的值是CSS语言的核心功能。

一个元素可以被多个选择器匹配，CSS定义了哪个规则比其他规则具有更高的优先级，这就是层叠算法（cascade algorithm）。

CSS规则时样式表的主要组成块，CSS规则只是被称为CSS语句中的一种。其他类型如下：
-  `@-rule`(At-rules)在CSS中被用来传递元数据、条件信息或其他描述性信息
- `嵌套语句`语法是CSS规则的嵌套块，只有在特定条件（`@media/@supports/@document`）匹配时才会应用到文档

#### 使CSS更具可读性

浏览器会忽略多余的空格，不过可以使用空格是代码更具可读性。
在HTML中使用`/*注释内容*/`进行注释

使用合适的简写，一些属性支持简写如`font`/`background`/`padding`/`margin`被称为简写属性，如
```css
padding-top: 10px;
padding-right: 15px;
padding-bottom: 15px;
padding-left: 5px;
/* 等同于 下面的简写 */
padding: 10px 15px 15px 5px;
/* 再譬如 */
background-color: red;
background-image: url(bg-graphic.png);
background-position: 10px 10px;
background-repeat: repeat-x;
background-scroll: fixed;
/* 可简写为 */
background: red url(bg-graphic.png) 10px 10px repeat-x fixed;
```

#### CSS选择器

CSS选择器分为多种：
- 简单选择器（Simple selectors）：通过元素类型、`class`或者`id`匹配一个或多个元素
- 属性选择器（Attribute selectors）：通过属性或属性值匹配一个或多个元素
- 伪类（Pseudo-classes）：匹配处于确定状态的一个或多个元素，比如被鼠标指针悬停的元素，或当前被选中或未选中的复选框，或元素是DOM树中一父节点的第一个子节点。
- 伪元素（Pseudo-elements）:匹配处于相关的确定位置的一个或多个元素，例如每个段落的第一个字，或者某个元素之前生成的内容
- 组合器（Combinators）：这里不仅仅是选择器本身，还有以有效的方式组合两个或更多的选择器用于非常特定的选择的方法。例如，你可以只选择divs的直系子节点的段落，或者直接跟在headings后面的段落
- 多用选择器（Multiple selectors）：将以逗号分隔开的多个选择器放在一个CSS规则下面，从而将一组声明应用于由这些选择器所选择的所有元素

##### 类型选择器（元素选择器）

如
```html
<h1>No1</h1>
<p> haha </p>
<div></div>
<p> done </p>
<h1 class="second type">No2</h1>
<h2 id="hahaha"> dadada</h2>
```
选择器为
```css
/* 普通选择器 */
p {
  color: black;
}
div {
  color: green
}
/* 类选择器 */
.second type {
  font-weight: bold;
}
/* ID选择器 */
#hahah {
  font-family: cursive;
}
/* 通用选择器就是字符“*” 一般不使用，会影响全局拖慢速度 */
```

##### 属性选择器

属性选择器根据元素的属性和属性值来匹配元素，通用语法由`[]`组成，其中包含属性名称后跟可选条件以及匹配属性的值。分为存在和值（Presence and Value）属性选择器和子串值（Substring value）选择器

参照[【MDN】](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Attribute_selectors)

好玩的子串值选择器
```html
<ol>
  <li lang="en-GB" data-perf="inc-pro">Manchester United</li>
  <li lang="es" data-perf="same-pro">Barcelona</li>
  <li lang="de" data-perf="dec">Bayern Munich</li>
  <li lang="es" data-perf="same">Real Madrid</li>
  <li lang="de" data-perf="inc-rel">Borussia Dortmund</li>
  <li lang="en-GB" data-perf="dec-rel">Southampton FC</li>
</ol>
```
```css
li[lang="en-GB"] {
   background: url("http://mdn.github.io/learning-area/css/introduction-to-css/css-selectors/en-GB.png") 5px center no-repeat;
}

li[lang="de"] {
   background: url("http://mdn.github.io/learning-area/css/introduction-to-css/css-selectors/de.png") 5px center no-repeat;
}

li[lang="es"] {
   background: url("http://mdn.github.io/learning-area/css/introduction-to-css/css-selectors/es.png") 5px center no-repeat;
}

li[data-perf*="inc"] {
   background-color: rgba(0,255,0,0.7);
}

li[data-perf*="same"] {
   background-color: rgba(0,0,255,0.5);
}

li[data-perf*="dec"] {
   background-color: rgba(255,0,0,0.7);
}

li[data-perf*="pro"] {
   font-weight: bold;
}

li[data-perf*="rel"] {
   font-style: italic;
   color: #666;
}

ol {
   padding: 0;
}

li {
   padding: 3px 3px 3px 34px;
   margin-bottom: 5px;
   list-style-position: inside;
}
```

##### 伪类和伪元素

伪选择器实际上不是选择元素而是元素的某些部分或在特定上下文中存在的元素，分两种：伪类及伪元素

一个CSS伪类是一个以冒号`:`卓伟前缀被添加到一个选择器末位的关键字。参照[【MDN】](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Pseudo-classes_and_pseudo-elements)

##### 组合器及多个选择器

参考[【MDN】](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Combinators_and_multiple_selectors)

#### CSS的值和单位

CSS的值的类型有很多，常见的有，具体参考[【MDN】](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Values_and_units)
- 数值
- 百分比
- 颜色
- 坐标位置
- 函数

#### 层叠和继承

元素的最终的样式可以在多个地方定义，这些定义通过复杂的形式互相影响。具体参考[【MDN】](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Cascade_and_inheritance)

**层叠：** 那个选择器优先级最高取决于三个因素
1. 重要性（Importance）
2. 专用性（Specificity）
3. 源代码次序（Source order）

#### 框模型

CSS框模型是网页布局的基础，每一个元素被表示为一个矩形的方框，框的内容、内边距、边界和外边距像洋葱一样，一层包一层的构建起来。具体查看[【MDN】](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Box_model)

