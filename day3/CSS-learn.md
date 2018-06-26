CSS-learn

#### CSS 介绍

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
