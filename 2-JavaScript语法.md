##### 2.1 准备工作

编写JavaScript脚本不需要任何特殊软件，一个普通的文本编辑器和一个Web浏览器就足够了。

必须通过HTML/XHTML文档才能执行。

两种方式可以做到。

* 将JavaScript代码放到文档<head>标签中的<script>标签之间。
* 更好的方式是把JavaScript代码存为一个扩展名为.js的独立文件。
  * 典型的作法是在文档的<head>部分放一个<script>标签，并把它的src属性指向该文件。
  * 最好的作法是把<script>标签放到HTML文档的最后，</body>标签之前。这样能使浏览器更快的加载页面。

程序设计语言分为解释型和编译型两大类。

* 解释型不需要编译器，仅需要解释器。如果有错误，只能等到解释器执行到有关代码时才能被发现。（JavaScript）
* 编译型需要一个编译器，把高级语言编写出来的源代码翻译为直接在计算机上执行的文件。如果有错误，在编译阶段就能被发现。相比于解释型语言，速度更快，可移植性更好。（Java或C++）

#### 2.2 语法

##### 2.2.3 变量

JavaScript允许直接对变量赋值不需事先声明。如果在对某个变量赋值之前未声明，赋值操作将自动声明该变量。

变量和其他语法元素的名字是区分字母大小写的。

JavaScript变量名允许包含美元符号。

##### 2.2.4 数据类型

有些其他的语言要求在声明变量的同时还必须同时声明变量的数据类型，这种做法称为类型声明。必须明确类型声明的语言称为强类型语言。

JavaScript不需要进行类型声明，它是一种弱类型语言。可在任何阶段改变变量的数据类型。

1. 字符串
   
   字符串必须包在引号里，单引号或双引号都可以。

##### 2.2.5 数组

字符串、数值和布尔值都是标量（scalar）。标量在任意时刻只能有一个值。

数组用`Array`声明。

声明数组的同时还可以指定数组初始元素个数。`var beatles = Array(4);`

也可以不给出元素个数。`var beatles = Array();`

`var beatles = Array("John", "Paul", "George", "Ringo");`

可以用方括号创建数组。`var beatles = ["John", "Paul", "George", "Ringo"];`

存放数据的首选方式：将数据保存为对象。

**关联数组**

``` objective-c
var lennon = Array();
lennon["name"] = "John";
lennon["year"] = 1940;
lennon["living"] = false;
```

这种用法不是一个好习惯，不推荐使用。

##### 2.2.6 对象

创建对象使用`Object`。

``` objective-c
var lennon = Object();
lennon.name = "John";
lennon.year = 1940;
lennon.living = false;
```

也可用花括号语法创建对象。`{propertyName:value, propertyName:value}`。

`var lennon = {name:"John", year:1940, living:false};`

##### 2.3 操作

**算术操作符**

加号既可以用于数值，也可以用于字符串。把多个字符串首尾相连，这种操作叫拼接。

可以把数值和字符串拼接在一起。此时，数值将自动被转为字符串。

#### 2.4 条件语句

##### 2.4.1 比较操作符

`==`并不表示严格想等。比较false与一个空字符串，`==`会认为它们想等。

``` objective-c
var a = false;
var b = "";
if (a == b) {
  alert("a equals b");
}
```

这个求值结果是true。

`===`进行严格比较，不仅比较值还比较变量类型。

``` objective-c
var a = false;
var b = "";
if (a === b) {
  alert("a equals b");
}
```

这个求值结果是false。

`!=`，`!==`也是如此。

##### 2.4.2 逻辑操作符

