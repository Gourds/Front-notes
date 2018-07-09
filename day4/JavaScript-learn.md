**简介：** 学习前端知识，JavaScript的学习肯定是必不可少的，目前按照百度前端学院的推荐，依然从[【MDN】](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript)上的教程开始学起。

JavaScript是一门跨平台、面向对象的轻量级脚本语言。在宿主环境中（如浏览器）中，JavaScript能够通过其所连接的环境提供的编程接口进行控制。JavaScrpt内置了一些对象的标准库，如**数组（array），日期（date），数学（math）以及一套核心语句，包括运算符、流程控制符以及申明方式等。JavaScript的核心部分可以通过添加对象语言以适应不同用途，例如：
- 客户端的 JavaScript 通过提供控制浏览器及其文档对象模型（DOM）的对象来扩展语言核心。例如：客户端版本直接支持应用将元素放在HTML表单中并且支持响应用户事件比如鼠标点击、表单提交和页面导航
- 服务端的 JavaScript 则通过提供有关在服务器上运行 JavaScript 的对象来可扩展语言核心。例如：服务端版本直接支持应用和数据库通信，提供应用不同调用间的信息连续性，或者在服务器上执行文件操作

JavaScript 和 Java 有一些共性但是在另一些方面有着根本性区别。JavaScript语言类似 Java 但是并没有 Java 的静态类型和强类型检查特性。JavaScript 遵循了 Java 的表达式语法，命名规范以及基础流程控制，这也是 JavaScript 从 LiveScript 更名的原因。JavaSctipt从java中借用了大部分语法，但也受到Awk，perl以及python的影响。

新世界大门`Hello world`
```javascript
fuction greetMe(user){
    alert('Hello ' + user);
}
greetMe('arvon')
```

### Chapter1：基础

几点语言特性
- 区分大小写，使用Unicode字符集
- 使用`;`号分割指令语句
- 注释风格与`c++`相同，使用`\\`进行单行注释

JavaScript有三种声明方式
- var：声明一个变量，可赋一个初始化值
- let：声明一个块作用域的局部变量，可赋一个初始化值
- const：声明一个块作用域的只读的命名变量


JavaScript数据结构和类型
- Boolean：布尔值，`true | false`
- null: 一个声明`null`值的特殊关键字，注意是区分大小写的
- undefined：变量未定义时的属性
- Number：数字
- String：字符串
- Symbol：一种数据类型，它的实例时唯一且不可改变的
- Object对象

由于JavaScript是动态类型语言，所以声明变量时不必指定数据类型，数据类型会在脚本执行的时候根据需要自动转换。

**字面量（Literals）：** 字面量是由语法表达式定义的常量；或者通过由一定字词组成的语词表达式定义的常量。在JavaScript中可以使用各种字面量，这些字面量是脚本中按字面意思给出的固定的值，而不是变量。常见的字面量如下
- 数组字面量（Array literals）
- 布尔字面量（Boolean literals）
- 浮点数字面量（Floating-point literals）
- 整数（Integers）
- 对象字面量（Object literals）
- RegExp literals
- 字符串字面量（String literals）

### Chapter2:流程控制

JavaScript提供一套灵活的语句集，特别是控制流语句，可以使用这个控制语句在应用程序中实现大量的交互功能。

语句块由一对大括号进行分割，常用的流程控制有`if/for/while`等

```javascript
var x = 1;

{
  let x = 2;  //结果输出1
  //var x = 2; //结果输出2
}
alert(x);
```

条件判断语句如：
```javascript
var x =1;
if (x > 2) {
  console.log(x + ">2");
}
else if (x < 2) {
  console.log(x + "<2");
 }
else{
  console.log(x +"is equal 2");
 }
 //推荐使用严格的语句块模式，语句else可选
```

switch语句:允许程序求一个表达式的值并且尝试去匹配表达式的值到一个`case`标签，匹配成功就执行变迁下相关指令。

```javascript
var input = 'orange';

switch (input){
  case "apple":
    console.log("is apple ");
    break;
  case "banana":
    console.log("is banana");
    break;
  case "orange":
    console.log("is orange");
    break;
  default:
    console.log("other food");
    
}
```

### Chapter3：异常处理

可以使用`throw`抛出异常并使用`try .. catch`进行捕获。
推荐使用以下异常类型,参照[【MDN】](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
- `ECMAScript exceptions`
- `DoMException` and `DOMError`

简单例子
```JavaScript
function f(){
  try {
    console.log(0);
    throw "bogus";
  }  
  catch(e){
    console.log(1);
    alert(e);
    return true;
  }
  finally {
    console.log('Eng');
  }

}
f()
```

关于`Promises`：从ECMAScript 6开始支持，允许对延时和异步操作流进行控制。`Promoises`的几种状态如下：
- pending：初始化状态，正在执行
- fulfilled：成功的完成了操作
- rejected：失败，没有完成操作
- settled：处于fulfilled或rejected任意一个状态


### ChapterX：通过XHR加载图片

没试出来，不过也贴下来
```javascript
function imgLoad(url) {
  return new Promise(function(resolve, reject) {
    var request = new XMLHttpRequest();
    request.open('GET', url);
    console.log(url);
    request.responseType = 'blob';
    request.onload = function() {
      if (request.status === 200) {
        resolve(request.response);
      } else {
        reject(Error('Image didn\'t load successfully; error code:' 
                     + request.statusText));
      }
    };
    request.onerror = function() {
      reject(Error('There was a network error.'));
    };
    request.send();
  });
}

imgLoad('http://oqfz9mxmq.bkt.clouddn.com/20180413-gitlab-1.jpeg');
```

### Chapter4: 循环和迭代

包括以下几种
- `for`
- `do...while`
- `while`
- `labeled`
- `break`
- `continue`
- `for...in`
- `for...of`

**Ex1:** for 语句简单例子

```javascript
var step;
//for ([initialExpression]; [condition]; [incrementExpression])
for (step =0; step < 5; step++) {
  console.log('Walking' + step);
}
```

**Ex2:** do while语句

```javascript
let abc = 0;
do{
  abc += 1;
  console.log('is' + abc);
}while (abc < 5);
```

**Ex3:** while 语句

```javascript
var a = 0;
var b = 0;

while (a < 3){
  b++;
  a += b;
  c = a + b;
  console.log(a + '+' + b + '=' + c );
}
```

**Ex4:** break语句

需要注意的是`lable`标签，当break退出不带`lable`的循环时，会跳出整个循环，而使用带`lable`的进行退出，只会退出指定标记的语句。
```javascript
var a='arvon'

for (i=0; i< a.length; i++){
  console.log('hello' + i)
  labelTest:
  if (a[i] == 'v'){
    console.log('Now' + i)
    break labelTest;
    //break;
  }
}
```

**Ex5：** continue语句

continue语句可以用来继续执行下一个循环跟break类似，也可以指定`lable`进行匹配执行
```javascript
var a = 0;
var b = 0;
while (a < 5){
  a++;
  if (a == 3){
    continue;
  }
  console.log(a);
}
```

**Ex6:** for...in语句

```javascript

function hahaha(obj, obj_name){
  var result = "";
  for (var i in obj){
    result += obj_name + "." + i + "=" + obj[i] + "<br>";
  }
  result += "<hr>";
  return result;
}
console.log(hahaha('hello', 'world'));
```

**Ex7：**for..of语句

在可迭代的对象上创建了一个循环
```javascript
let arr = [3, 5, 7];
arr.foo = "hello";

for (let i in arr) {
   console.log(i); // logs "0", "1", "2", "foo"
}

for (let i of arr) {
   console.log(i); // logs "3", "5", "7" // 注意这里没有 hello
}
```

### Chapter5: 定义函数

函数定义由一系列`function`关键字组成（函数的名称、函数的参数列表、函数的javascript语句），如
```javascript
function cheng(haha){
  console.log(haha + " * " + haha + " = " + haha * haha)
}

cheng(3) //结果 3 * 3 = 9
```

**闭包：**简单理解，闭包就是能够读取其他函数内部变量的函数。由于在Javascript语言中，只有函数内部的子函数才能读取局部变量，因此可以把闭包简单理解成"定义在一个函数内部的函数"。闭包的最大用处有两个，一个是前面提到的可以读取函数内部的变量，另一个就是让这些变量的值始终保持在内存中。
```javascript
function f1(){
  var n = 99;
  njia = function(){n+=1}
  function f2(){
    alert(n);
  }
  return f2;
}

var result=f1();

result(); // 输出99
njia();
result(); //输出100
```

还是不大理解，参照[【阮一峰的Blog】](http://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html)

**使用arguments对象：** 可以给函数加参数

```javascript
function cece(myvar){
  var result = '';
  var i;
  for (i =1; i < arguments.length; i++){
    result += arguments[i] + myvar;
  }
  return console.log(result);
}


cece('aaa', 'bbb', 'ccc') //结果bbbaaacccaaa
```

**默认参数和剩余参数及箭头函数：** 看例子

```javascript
function multiply(a, b = 1) {
  return a*b;
}

multiply(5); // 5

```

### Chapter6: 



### Chapter7: