# JavaScirpt教程

## 快速入门

1. __如何运行JavaScript代码__

* 直接嵌入

```
<html>
<head>
  <script>
    alert('Hello, world');
  </script>
</head>
<body>
  ...
</body>
</html>

```

&emsp; 由<script>...</script>包含的代码就是JavaScript代码，它将直接被浏览器执行。

* 引用`.js`文件

```
<html>
<head>
  <script src="/static/js/abc.js"></script>
</head>
<body>
  ...
</body>
</html>
```
&emsp; 把JavaScript代码放到一个单独的`.js`文件，然后在HTML中通过`<script src="..."></script>`引入这个文件,`/static/js/abc.js`就会被浏览器执行。

2. __如何编写JavaScript代码__

可以用任何文本编辑器来编写JavaScript代码。推荐以下几种文本编辑器：

* Visual Studio Code

微软出的Visual Studio Code，可以看做迷你版Visual Studio，免费！跨平台！内置JavaScript支持。

* Sublime Text

Sublime Text是一个好用的文本编辑器，免费。

* Notepad++

Notepad++也是免费的文本编辑器，但仅限Windows下使用。


>注意：不可以用Word或写字板来编写JavaScript或HTML，因为带格式的文本保存后不是纯文本文件，无法被浏览器正常读取。也尽量不要用记事本编写，它会自作聪明地在保存UTF-8格式文本时添加BOM头。

3. __如何调试JavaScript代码__

* 使用Google Chrome浏览器调试

要查看一个变量的内容：

查看(View)-开发者(Developer)-开发者工具(Developer Tools) 在Console中输入console.log(内容);

回车后显示的值就是变量的内容。

### 基本语法

1. __语法__

&emsp; JavaScript的语法和Java语言类似，每个语句以`;`结束，语句块用`{...}`。但是，JavaScript并不强制要求在每个语句的结尾加`;`，浏览器中负责执行JavaScript代码的引擎会自动在每个语句的结尾补上`;`。

&emsp; 花括号`{...}`内的语句具有缩进，通常是4个空格。缩进不是JavaScript语法要求必须的，但缩进有助于我们理解代码的层次，所以编写代码时要遵守缩进规则。很多文本编辑器具有“自动缩进”的功能，可以帮助整理代码。

>`{...}`还可以嵌套，形成层级结构

2. __注释__


&emsp; 以`//`开头直到行末的字符被视为行注释，注释是给开发人员看到，JavaScript引擎会自动忽略。

&emsp; 另一种块注释是用`/*...*/`把多行字符包裹起来，把一大“块”视为一个注释。

3. __大小写__

&emsp; JavaScript严格区分大小写。

### 数据类型和变量

1. __Number__

JavaScript不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型：

```
123; // 整数123
0.456; // 浮点数0.456
1.2345e3; // 科学计数法表示1.2345x1000，等同于1234.5
-99; // 负数
NaN; // NaN表示Not a Number，当无法计算结果时用NaN表示
Infinity; // Infinity表示无限大，当数值超过了JavaScript的Number所能表示的最大值时，就表示为Infinity
```

Number可以直接做四则运算，规则和数学一致：

```
1 + 2; // 3
(1 + 2) * 5 / 2; // 7.5
2 / 0; // Infinity
0 / 0; // NaN
10 % 3; // 1
10.5 % 3; // 1.5
```

注意%是求余运算。

2. __字符串__

字符串是以单引号`'`或双引号`"`括起来的任意文本，比如`'abc'`，`"xyz"`等等。

3. __布尔值__

布尔值和布尔代数的表示完全一致，一个布尔值只有`true`、`false`两种值。

```
true; // 这是一个true值
false; // 这是一个false值
2 > 1; // 这是一个true值
2 >= 3; // 这是一个false值
```
`&&`运算是与运算，只有所有都为`true`，`&&`运算结果才是`true`:

```
true && true; // 这个&&语句计算结果为true
true && false; // 这个&&语句计算结果为false
false && true && false; // 这个&&语句计算结果为false
```
`||`运算是或运算，只要其中有一个为`true`，`||`运算结果就是`true`：

```
false || false; // 这个||语句计算结果为false
true || false; // 这个||语句计算结果为true
false || true || false; // 这个||语句计算结果为true
```

`!`运算是非运算，它是一个单目运算符，把`true`变成`false`，`false`变成`true`：

```
! true; // 结果为false
! false; // 结果为true
! (2 > 5); // 结果为true
```
布尔值经常用在条件判断中，比如：

```
var age = 15;
if (age >= 18) {
    alert('adult');
} else {
    alert('teenager');
}
```
4. __比较运算符__

JavaScript允许对任意数据类型做比较：

```
false == 0; // true
false === 0; // false
```

要特别注意相等运算符`==`。JavaScript在设计时，有两种比较运算符：

* 第一种是`==`比较，它会自动转换数据类型再比较，很多时候，会得到非常诡异的结果；

* 第二种是`===`比较，它不会自动转换数据类型，如果数据类型不一致，返回`false`，如果一致，再比较。

由于JavaScript这个设计缺陷，不要使用`==`比较，始终坚持使用`===`比较。

另一个例外是`NaN`这个特殊的Number与所有其他值都不相等，包括它自己：

`NaN === NaN; // false`

唯一能判断`NaN`的方法是通过`isNaN()`函数：

`isNaN(NaN); // true`


最后要注意浮点数的相等比较：

`1 / 3 === (1 - 2 / 3); // false`

这不是JavaScript的设计缺陷。浮点数在运算过程中会产生误差，因为计算机无法精确表示无限循环小数。要比较两个浮点数是否相等，只能计算它们之差的绝对值，看是否小于某个阈值：

`Math.abs(1 / 3 - (1 - 2 / 3)) < 0.0000001; // true`

5. __null和undefined__

`null`表示一个“空”的值，它和0以及空字符串`''`不同，`0`是一个数值，`''`表示长度为0的字符串，而`null`表示“空”。

在JavaScript中，还有一个和null类似的undefined，它表示“未定义”。

>JavaScript的设计者希望用null表示一个空的值，而undefined表示值未定义。事实证明，区分两者的意义不大。大多数情况下，我们都应该用null。undefined仅仅在判断函数参数是否传递的情况下有用。

6. __数组__

* 数组用`[]`表示

数组是一组按顺序排列的集合，集合的每个值称为元素。JavaScript的数组可以包括==任意数据==类型。例如：

```
[1, 2, 3.14, 'Hello', null, true];
```

上述数组包含6个元素。数组用`[]`表示，元素之间用`,`分隔。

* 通过`Array()`函数实现

另一种创建数组的方法是通过Array()函数实现：

`new Array(1, 2, 3); // 创建了数组[1, 2, 3]`

然而，出于代码的可读性考虑，强烈建议直接使用`[]`。

数组的元素可以通过索引来访问。请注意，索引的起始值为0：

```
var arr = [1, 2, 3.14, 'Hello', null, true];
arr[0]; // 返回索引为0的元素，即1
arr[5]; // 返回索引为5的元素，即true
arr[6]; // 索引超出了范围，返回undefined
```
7. __对象__

JavaScript的对象是一组由键-值组成的无序集合，例如：

```
var person = {
    name: 'Bob',
    age: 20,
    tags: ['js', 'web', 'mobile'],
    city: 'Beijing',
    hasCar: true,
    zipcode: null
};
```

JavaScript==对象的键都是字符串类型，值可以是任意数据类型==。上述person对象一共定义了6个键值对，其中每个键又称为对象的属性，例如，person的name属性为'Bob'，zipcode属性为null。

要获取一个对象的属性，我们用对象变量.属性名的方式：

```
person.name; // 'Bob'
person.zipcode; // null
```

8. __变量__

变量在JavaScript中就是用一个变量名表示，变量名是大小写英文、数字、$和_的组合，且==不能用数字==开头。变量名也不能是JavaScript的关键字，如`if`、`while`等。申明一个变量用`var`语句，比如：

```
var a; // 申明了变量a，此时a的值为undefined
var $b = 1; // 申明了变量$b，同时给$b赋值，此时$b的值为1
var s_007 = '007'; // s_007是一个字符串
var Answer = true; // Answer是一个布尔值true
var t = null; // t的值是null
```
在JavaScript中，使用等号`=`对变量进行赋值。可以把任意数据类型赋值给变量，同一个变量可以反复赋值，而且可以是不同类型的变量，但是要注意只能用`var`申明一次，例如：

```
var a = 123; // a的值是整数123
a = 'ABC'; // a变为字符串
```

这种变量本身类型不固定的语言称之为动态语言，与之对应的是静态语言。静态语言在定义变量时必须指定变量类型，如果赋值的时候类型不匹配，就会报错。例如Java是静态语言，赋值语句如下：

```
int a = 123; // a是整数类型变量，类型用int申明
a = "ABC"; // 错误：不能把字符串赋给整型变量
```

和静态语言相比，动态语言更灵活，就是这个原因。

>要显示变量的内容，可以用`console.log(x)`，打开Chrome的控制台就可以看到结果。使用`console.log()`代替`alert()`的好处是可以避免弹出烦人的对话框。

9. __strict模式__


JavaScript在设计之初，为了方便初学者学习，并不强制要求用`var`申明变量。这个设计错误带来了严重的后果：如果一个变量没有通过`var`申明就被使用，那么该变量就自动被申明为全局变量：

```
i = 10; // i现在是全局变量
```

在同一个页面的不同的JavaScript文件中，如果都不用`var`申明，恰好都使用了变量`i`，将造成变量i互相影响，产生难以调试的错误结果。

使用`var`申明的变量则不是全局变量，它的范围被限制在该变量被申明的函数体内（函数的概念将稍后讲解），同名变量在不同的函数体内互不冲突。

为了修补JavaScript这一严重设计缺陷，ECMA在后续规范中推出了strict模式，在strict模式下运行的JavaScript代码，强制通过var申明变量，未使用var申明变量就使用的，将导致运行错误。

启用strict模式的方法是在JavaScript代码的第一行写上：

`'use strict';`

这是一个字符串，不支持strict模式的浏览器会把它当做一个字符串语句执行，支持strict模式的浏览器将开启strict模式运行JavaScript。

