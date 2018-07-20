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

**箭头函数**

```javascript
var a = [
 "arvon",
  "and",
  "mo"
];
var a2 = a.map(function(s){ return s.length });
console.log(a2); // logs [ 8, 6, 7, 9 ]
var a3 = a.map( s => s.length );
console.log(a3); // logs [ 8, 6, 7, 9 ]
```

### Chapter6: 表达式和运算符

具体参照[【MDN】](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_Operators),这里只写一些学习的例子。

```javascript
​​​var a = 2
var b = 6
var count_type = [
  a + b,
  a - b,
  a * b,
  a / b,
  a ** b,
]
function test(){
  for (i of count_type){
    console.log(i);
  }
}
test()
```

**解构：** 对于更复杂的赋值，解构赋值语法是一个能从数组或对象对应的数组结构或对象字面量里提取数据的 Javascript 表达式。

```javascript
var foo = ["hi", "arvon", "mo", "hahah"];

/*
//不使用解构
var one = foo[0];
var two = foo[1];
var three = foo[2];
*/
//使用解构
var [one, two, three] = foo;
console.log(one, two, three);
```

**比较运算符：** 

```javascript
var a = 1;
var aa = "1";
var b = 2;
var bb = "2";

console.log(a > b); //false
console.log(bb > a); //true
console.log(a != aa); //false
console.log(a == aa); //true
console.log(a === aa); //false
console.log(a !== aa);  //true
```

**位运算符：** 用于直接对二进制位进行计算，会将操作数转化为由0和1组成的32bit的整数。具体可以看[【这里】](http://javascript.ruanyifeng.com/grammar/operator.html#toc19)

**移位运算符：** 参照上面的链接吧，感觉不会很常用，暂时粗略看下，不深入学习。

**逻辑运算符：** 

```javascript
var a = 2 >1 && 'a' != 'b';
var b = 2 < 1 || 'a' == 'b';
var c = ! 2 < 1
console.log(a); //true
console.log(b); //false
console.log(c); //true
```

**条件运算符：**

```javascript
// 条件 ？ value1 ： value2；
function haha(age){
  var status = (age >= 18) ? "adult" : "child";
  console.log(status);
}

haha('17'); //child
haha('27'); //adult
```

**逗号操作符：**

逗号操作符对两个操作数进行求值并返回最终操作数的值，常用在for循环中，在每次循环时对多个变量进行更新。

```javascript
var a = [1, 2, 3, 4, 5];
var b = ['a', 'b', 'c'];

for (var i = 0, j = 6; i <= j; i++, j--){
  console.log(i, j, a[i]);
}
```

**一元操作符：**

一元操作符仅对应一个操作数
- `delete`
- `typeof`
- `void`

**关系操作符：**

关系操作符对操作数进行比较，根据比较结果返回相应的布尔值
- `in`：判断指定属性是否属于指定对象
- `instanceof`:判断对象类型

**运算符优先级：**

具体参考[【JavaScript 参考手册】](https://developer.mozilla.org/zh-CN/docs/JavaScript/Reference/Operators/Operator_Precedence#Table)

### Chapter7: 表达式

表达式是一组代码的集合，它返回一个值。每一个合法的表达式都可以计算成某个值。Javascript有以下几种表达式类型
- 算数
- 字符串
- 逻辑值
- 基本表达式
- 左值表达式

#### 基本表达式

**this** 关键字被用于指代当前的对象
```html
<p>Enter a number between 18 and 99:</p>
<input type="text" name="age" size=3 onChange="validate(this, 18, 99);">
```

```javascript
function validate(obj, lowval, hival){
  if ((obj.value < lowval) || (obj.value > hival))
    console.log("Invalid Value!");
}
```

### 数字和日期

具体参照[【这里】](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Numbers_and_dates)

#### 数字对象

数字主要有以下几种：
- 十进制数字：可以以0开头但是接着的数如果小于8这个数字会被识别为8进制
- 二进制数字：以`0b`or`0B`开头
- 八进制数字：
- 十六进制：以`0x`or`0X`开头

内置的Number对象有一些关于数字的常量属性，如最大值、不是一个数字和无穷大等，不能改变这些属性，但可以按以下方式使用
```javascript
var biggestNum = Number.MAX_VALUE;
var smallestNum = Number.MIN_VALUE;
var infiniteNum = Number.POSITIVE_INFINITY;
var negInfiniteNum = Number.NEGATIVE_INFINITY;
var notANum = Number.NaN;
```

#### 日期对象

```javascript
var dateObjectName = new Date();
console.log(dateObjectName); //Date 2018-07-18T09:38:29.884Z
```

### 字符串

除非必要，不然应该尽量使用String字面量，因为String对象的某些行为与直觉上并不一致，如
```javascript
var s1 = "2" + "2";
var s2 = new String("2" + "2");

console.log(s1); //22
console.log(s2); // String { "22" }
```

### 国际化

**日期和时间格式化**
```javascript
var msPerDay = 24 * 60 * 60 * 1000;
 
// July 17, 2014 00:00:00 UTC.
var july172014 = new Date(msPerDay * (44 * 365 + 11 + 197));//2014-1970=44年
//这样创建日期真是醉人。。。还要自己计算天数。。。11是闰年中多出的天数。。。
//197是6×30+16(7月的16天)+3(3个大月)-2(2月少2天)

var options = { year: "2-digit", month: "2-digit", day: "2-digit",
                hour: "2-digit", minute: "2-digit", timeZoneName: "short" };
var americanDateTime = new Intl.DateTimeFormat("en-US", options).format;
 
console.log(americanDateTime(july172014)); // 07/16/14, 5:00 PM PDT
```

**数字格式化**

```javascript
var gasPrice = new Intl.NumberFormat("en-US",
                        { style: "currency", currency: "USD",
                          minimumFractionDigits: 3 });
 
console.log(gasPrice.format(5.259)); // $5.259

var hanDecimalRMBInChina = new Intl.NumberFormat("zh-CN-u-nu-hanidec",
                        { style: "currency", currency: "CNY" });
 
console.log(hanDecimalRMBInChina.format(1314.25)); // ￥ 一,三一四.二五
```

**定序**

`Collator`对象在字符串比较和排序方面很好用

```javascript
var names = ["Hochberg", "Hönigswald", "Holzman"];
 
var germanPhonebook = new Intl.Collator("de-DE-u-co-phonebk");
var germanDictionary = new Intl.Collator("de-DE-u-co-dict");
 
console.log(names.sort(germanPhonebook.compare).join(", "));//Hochberg, Hönigswald, Holzman
console.log(names.sort(germanDictionary.compare).join(", "));//Hochberg, Holzman, Hönigswald

```

### 正则表达式（Regular_Expressions)

一个正则表达式字面量由包含在斜杠之间的模式组成，如`/abc/`或者使用`RegExp`对象构建。具体参照[【文档】](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Regular_Expressions)

```javascript
var myRe = /d(b+)d/g;
var myArray = myRe.exec("cdbbdbsbz");

console.log(myArray); //Array [ "dbbd", "bb" ]
```

### 数组对象（Array object）

数组（Array）是一个有序的数据集合，可以通过数组名称和索引进行访问。具体参照[【文档】](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Indexed_collections)

```javascript
var create_array1 = new Array('a1', 'a2', 'a3');
var create_array2 = Array('b1', 'b2', 'b3');
var create_array3 = ['c1', 'c2', 'c3'];

console.log(create_array1); //Array(3) [ "a1", "a2", "a3" ]
console.log(create_array2[1]); // b2
console.log(create_array3);
```

### 映射


[【具体参照】](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Keyed_Collections)
**Map对象** ：一个map对象就是一个简单的键值对映射集合，可以按照数据插入时候的顺序遍历所有的元素。

```javascript
var test = new Map();
test.set('arovn', 'me');
test.set('mo', 'you');
test.set('dog', 'haha');
console.log(test.size); //3
for (var [key, value] of test){
  console.log(key + '===' + value);
  /*
  arovn===me 
  mo===you 
  dog===haha
  */
}
test.clear();
console.log(test.size); //0
```

**Object和Map的比较：** 
- Object的键必须是String，在Map里键可以为任意类型
- 只能手动获取Object的长度，Map的长度可以轻松获得
- Map的遍历会按照元素的插入顺序
- Object有原型有一些缺省的值（map=Object.create(null))

