## Javascript 输入输出语句

| 方法             | 说明                           | 归属   |
| ---------------- | ------------------------------ | ------ |
| alert(msg)       | 浏览器弹出显示框               | 浏览器 |
| console.log(msg) | 浏览器控制台打印输出信息       | 浏览器 |
| prompt(into)     | 浏览器弹出输入框，用户可以输入 | 浏览器 |



## 变量



### 变量概述

本质：变量是程序在内存中申请的一块用来存放数据的空间，类似我们酒店房间，一个房间就可以看作是一个变量



### 变量的使用

变量在使用分为两步：

1、声明变量：

```html
var age;  //声明一个名称为 age 的变量
```

2、赋值：

```html
age = 18  //给变量 age 赋值 18，即变量的初始化
```



### 变量命名规范

由字母（A-Z,a-z）、数字（0，9）、下划线（_）、美元符号（$）组成，如userAge，num001，name

严格区分大小写，var app 和 var App，是两个变量

不能以数字开头，18age 是错误的

不能是关键字、保留字，例如var、for、while

变量名必须有意义。MMD、BBD

遵守驼峰命名法，首字母小写，后面单词的首字母需要大写，myfirstName



## 数据类型



### Number

Infinity 无穷大；-Infinity 无穷小

isNaN() 这个方法用来判断非数字，并且返回一个值，如果是数字返回的是 false，如果不是数字返回的是 true



### String

![image-20211025161457557](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211025161457557.png)

检测字符串的长度 length

```html
var str = 'my name is andy';
console.log(str.length);
console.log('沙漠'+'骆驼') //加号是字符串的拼接
```



### Boolean

如果一个变量声明为赋值就是 undefined 未定义数据类型

undefined 和数字相加，最后的结果就是 NaN

null 和数字相加等于数字本身

![image-20211025162403637](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211025162403637.png)



### 数据类型转换

获取数据类型的方法：

```html
var num = 12;
console.log(typeof num);   //number
```

**转换为字符串**

| 方式                         | 说明                         | 案例                                  |
| ---------------------------- | ---------------------------- | ------------------------------------- |
| toString()                   | 转换字符串                   | var num = 1; alert(num.toString());   |
| String()强制转换             | 转换字符串                   | var num = 1;alert(String(num));       |
| 加号拼接字符串（隐式住转换） | 和字符串拼接的结果都是字符串 | var num = 1;alert(num+"我是字符串")； |

**转换为数字型**

| 方式                   | 说明                         | 案例                |
| ---------------------- | ---------------------------- | ------------------- |
| parseInt(String)函数   | 将string类型转成整数数值型   | parseInt("78")      |
| parseFloat(string)函数 | 将string类型转成浮点数数值型 | parseFloat("78.23") |
| Number()强制转换为函数 | 将string类型转为数值型       | Number("12")        |
| js 隐式转换（- * /）   | 利用算术运算隐式转换为数值型 | "12"-0              |

**转换布尔型**

| 方式          | 说明               | 案例             |
| ------------- | ------------------ | ---------------- |
| Boolean()函数 | 其他类型转成布尔型 | Boolean("true"); |

代表空、否定的值会被转换为 false ，如 ''、0、NaN、null、undefined，其余值都会被转换为 true。

**关键字**

![image-20211025164631755](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211025164631755.png)

**保留字**

![image-20211025164650471](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211025164650471.png)



## 运算符



### 逻辑运算符

短路运算（逻辑中断）

短路运算的原理：当有多个表达式（值）时，左边的表达式值可以确定结果时，就不再继续运算右边的表达式的值

1、逻辑与(短路运算)

语法：表达式1 && 表达式2

如果第一个表达式的值为真，则返回表达式2。console.log(123 &&456)   //  456

如果第一个表达式的值为假，则返回表达式1。console.log(0 && 456) //  0

2、逻辑或（短路运算）

语法：表达式1 || 表达式2

如果第一个表达式的值为真，则返回表达式1。

如果第一个表达式的值为假，则返回表达式2。

案例：

```html
var num = 0;
console.log(123 || num++)  //123
console.log(num)  //0
```



### 运算符优先级

![image-20211025222218727](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211025222218727.png)



## Javascript 流程控制



### if  的语法结构与 if - else 语法结构

```html
if(条件表达式){
//执行语句
}
else{
//执行语句
}
```

案例：判断闰年

算法：能被4整除且不能整除100的为闰年（如2004年就是闰年，1901年不是闰年）或者能够被400整除的就是闰年。

```html
<script>
    var year = prompt('请输入你的年份')
    if（year % 4 ==0 && year % 100 != 0 || year % 400 == 0){
        alert('你输入的年份是闰年')；
    }
    else{
        alert('你输入的年份是平年')；
    }
</script>
```



### 三元表达式

三元表达式  表达式 ？ 表达式1 ：表达式2；

var num = 10;    var result = num > 5 ? '是的' : '不是的'；

案例：数字补0

```html
var time = prompt('请你输入一个0~59之间的一个数字');
time < 10 ? '0'+ time : time;
```



### switch 语句多分支

```html
<script>
switch(表达式){
    case value1:
        执行语句1;
        break;
    case value2:
        执行语句2;
        break;
    ...
    default:
        执行最后的语句;       
}
</script>
```

switch 注意事项：

switch 里的表达式经常写成变量，且该变量的值和 case 里面的值匹配的时候是全等，必须是值和数据类型一致才可以。num === 1。

switch 语句和 if else if 语句的区别

switch 语句通常处理 case 要确定值，if 语句一般可以处理一定范围的判断。



## 循环语句



### for 循环语句

```html
for(初始化变量;条件表达式;操作表达式){
//循环体
}
for(var i = 0; i <= 100; i++){
        var sum = 0;
        sum += i;
}
```

### while 循环语句

```html
while(条件表达式){
//循环体
}
```

### do - while 循环语句

```html
do{
//循环体
}while(条件表达式)
```

### continue 关键字

continue 关键字用于立即跳出本次循环，继续下一次循环。

### break 关键字

break 关键字用于立即跳出整个循环（循环结束）。



## 数组



### 数组的概念

数组（Array）。数组可以把一组数据一起存放，并提供方便的访问（获取）方式。数组是指一组数据的集合，其中的每个数据被称作元素，在数组中可以存放任意类型的元素。数组是一种将一组数据存储在单个变量名下的优雅方式。

### 创建数组

```javascript
var 数组名 = [];
var 数组名 = new Array();
var arr = [2,6,3,7,4];
var sum = 0;
var average = 0;
for(var i = 0; i < arr.length; i++){
    sum += i;
}
average = sum / arr.length;
console.log(sum,average);//x想要输出多个变量，用逗号分隔即可。
```

### 筛选数组

```javascript
var arr = [2,3,45,5,677,897,9,73,4,11];
var newArr = [];
for(var i = 0; i < arr.length; i++){
    if(arr[i] >= 10){
        newArr[newArr.length] = arr[i];
    }
}
console.log(newArr);
```

### 冒泡排序

```javascript
var srr = [5,4,3,2,1];
for(var i = 0; i < arr.length - 1; i++){
    for(var j = 0; j < arr.length - i - 1; j++){
        if(arr[j] > arr[j + 1]){
            var temp = arr[j];
            arr[j] = arr[j + 1];
            arr[j + 1] = temp;
        }
    }
}
```



## 函数



### 函数的创建

函数使用分为两步：声明函数和调用函数

1、声明函数

```javascript
function 函数名(){
    //函数体
}
function sayHi(){
    console.log("Hello");
}
var 变量名 = function(){
    //函数体
}
```

2、调用函数

```javascript
//函数名();
sayHi();   //函数调用一定要加小括号
```



### 函数的参数

```javascript
function 函数名(形参1，形参2...){
}
函数名(实参1，实参2...);
```

1、如果实参的个数和形参的个数一致，则正常输出结果。

2、如果实参的个数多于形参的个数，会取到形参的个数。

3、如果实参的个数少于形参的个数，形参可以看作是不用声明的变量，是一个变量但是没有接受值，结果为 undefined。



### 函数的返回值

```javascript
function fn(num1,num2){
    return num1,num2; //返回的结果是最后一个值
}
```

想返回多个值，用逗号分隔的话，则返回的结果是最后一个值。如果函数没有返回值，则会返回 undefined。



### arguments 的使用

当我们不确定有多少个参数传递的时候，可以用 arguments 来获取。在 JavaScript 中，arguments 实际上它是当前函数的一个内置对象。所有函数都内置了一个arguments 对象中存储了传递的所有实参。

```javascript
function fn(){
    console.log(arguments);
}
fn(1,2,3);
```

arguments 展示形式是一个伪数组，因此可以进行遍历。伪数组并不是真正意义上的数组，伪数组具有以下特点：

1、具有 length 属性。

2、按索引方式储存数据。

3、不具有数组的 push，pop 等方法。



## 作用域



### 全局作用域

整个 script 标签或者是一个单独的 js 文件。

### 局部作用域

局部作用域（函数作用域）在函数内部就是局部作用域这个代码的名字只在函数内部起效果和作用。



### 变量的作用域

全局变量：在全局作用域下的变量在全局下都可以用。

局部变量：在局部作用域下的变量，后者在函数内部的变量就是局部变量。注意，函数的形参也是可以看作是局部变量。

从执行效率来看全局变量和局部变量：

全局变量只有浏览器关闭的时候才会销毁，比较占内存资源。

局部变量是当我们程序执行完毕就会销毁，比较节约内存资源。

**Js 在 es6 的时候新增了块级作用域**



### 作用域链

根据在内部函数可以访问外部函数变量的这种机制，用链式查找决定哪些数据能被内部函数访问，就称作作用域链。即离它最近的开始向外层查找，可以说是就近原则。



## 预解析

我们 js 引擎运行 js 分为两步：预解析和代码执行。

预解析 js 引擎会把 js 里面所有的 var 还有 function 提升当前作用域的最前面。

预解析分为变量预解析（变量提升）和函数预解析（函数提升）。

变量提升就是把所有的变量声明提升到当前的作用域最前面，不是提升操作。

```javascript
console.log(num);
var num = 10;
//相当于执行了以下代码
var num;
console.log(num);
num = 10;
>>>>>>>>>>>>>>>>>>>>>>
var fun;
fun();
fun = function(){
    console.log(22);
}
```



函数提升就是把所有的函数声明提升到当前的作用域最前面。不调用函数。

代码执行按照代码书写的额顺序从上往下执行。



## 对象

在 JavaScript 中，对象是一组无序的相关属性和方法的集合，所有的事物都值对象，例如字符串、数值、数组、函数等。

对象是由属性和方法组成的

属性：事物的特征，在对象中用属性来表示（常用名词）。

方法：事物的行为，在对象中用方法来表示（常用动词）。



### 创建对象的三种方式

1、利用字面量创建对象

```javascript
var obj = {} //创建了一个空的对象
var obj = {
    uname:"张三疯",
    age:18,
    sex:'男',
    sayHi: function(){
        console.log('hi~');
    }
}
//(1)里面的属性或者方法我们采取键值对的形式，即键-属性名：值-属性值
//(2)多个属性或者方法中间用逗号隔开的
//(3)方法冒号后面跟的是一个匿名函数
console.log(obj.uname);
console.log(obj['age']);
obj.sayHi();
```

**变量、属性、函数、方法的区别**

（1）变量和属性的相同点是他们都是用来存储数据的

变量，单独声明并赋值，使用的时候直接写变量名，单独存在。

属性，在对象里面的不需要生命的，使用的时候必须是对象.属性。

（2）函数和方法的相同点，都是实现某种功能，做某件事。

函数，单独声明，并且调用的函数名()，单独存在的

方法，在对象里面调用的时候，对象.方法()

2、利用 new Object 创建对象

```javascript
var obj = new Object();
obj.uname = '张三疯';
obj.age = 18;
obj.sex = '男';
obj.sayHi = function(){
    console.log('hi~');
}
```

3、利用构造函数创建对象

构造函数就是把我们对象里面一些相同的属性和方法抽象出来封装到函数里面。构造函数（明星）泛指的某一大类，它类似 Java 语言里面的类（class）。对象特指是一个具体的事物。我们利用构造函数创建对象的过程我们也称为对象的实例化。

```javascript
function 构造函数名(){
    this.属性 = 值;
    this.方法 = function(){
        //函数体
    }
}
function Star(uname,age,sex){
    this.name = uname;
    this.age = age;
    this.sex = sex;
    this.sing = function(sang){
        console.log(sang);
    }
}
new 构造函数名();
var ldh = new Star('刘德华',18,'男');//调用函数返回的是一个对象
(1)构造函数名字首字母要大写
(2)我们构造函数不需要 return 就可返回结果
(3)我们调用构造函数必须使用 new
(4)我们只要 new Star() 调用函数就创建一个对象 ldh{}
(5)我们的属性和方法前面必须添加 this
```



### new 关键字执行过程

（1）new 构造函数可以在内存中创建了一个空的对象。

（2）this 就会指向刚才创建的空对象。

（3）执行构造函数里面的代码给这个空对象添加属性和方法。

（4）返回这个对象。



### 遍历对象

遍历对象使用（for in）

```javascript
var obj = {
    name:'pink 老师',
    age:18,
    sex:'男',
    fn:function(){
        //函数体
    }
}
//for(变量 in 对象){}
for(var k in obj){
    console.log(k);  // k变量输出得到的是属性名
    console.log(obj[k])  // obj[k]得到是属性值
}
```



## 内置对象

Javascript 中的对象分为三种：自定义对象、内置对象、浏览器对象。

前面两种是 JS 基础内容，属于 ECMAScript ；第三个浏览器对象属于我们独有的，我们 JS API 讲解。

内置函数就是指 JS 语言自带的一些对象，这些对象供开发者使用，并提供了一些常用的或是最基本而必要的功能（属性和方法）。

内置对象最大的优点就是帮助我们快速开发。

Javascript 提供了多个内置对象：Math、Date、Array、String等。



### 查文档

**MDN**

Mozilla 开发者网络（MDN）提供了有关网络技术（Open Web）的信息，包括 HTML、CSS 和万能网及 HTML 应用的 API。



### Math 对象

Math 对象不是构造函数它具有数学常数和函数的属性和方法。跟数学相关的运算（求绝对值，取整，最大值等）可以使用 Math 中的成员。

```javascript
Math.PI//圆周率
Math.floor()//向下取整
Math.ceil()//向上取整
Math.round()//四舍五入，就近取整，注意-3.5，结果是-3
Math.abs()//绝对值
Math.max()/Math.min()//求最大和最小值
```

**random()返回一个随机的小数**

这个方法里面不跟参数

```javascript
console.log(Math.random());
//我们想要得到两个数之间的随机整数，并且包含这两个整数
//Math.floor(Math.random()*(max-min+1))+min;
function getRandom(max,min){
    return Math.floor(Math.random()*(max-min+1))+min;
}
console.log(getRandom(1,10));
```



### 日期对象

日期格式化

| 方法名        | 说明                       | 代码               |
| ------------- | -------------------------- | ------------------ |
| getFullTear() | 获取当年                   | dObj.getFullYear() |
| getMonth()    | 获取当月（0-11）           | dObj.getMonth()    |
| getDate()     | 获取当天日期               | dObj.getDate()     |
| getDay()      | 获取星期几（周日0到周六6） | dObj.getDay()      |
| getHours()    | 获取当前小时               | dObj.getHours()    |
| getMinutes()  | 获取当前分钟               | dObj.getMinutes()  |
| getSeconds()  | 获取当前秒钟               | dObj.getSeconds()  |

**格式化年月日时分秒**

```javascript
var date = new Date();
var year = data.getFullYear();
var month = date.getMonth();
var dates = date.getDate();
var arr = ['星期日','星期一','星期二','星期三','星期四','星期五','星期六']；
var day = date.getDay();
var hours = date.getHours();
hours = hours < 10 ? '0' + hours : hours;
var minutes = date.getMinutes();
minutes = minutes < 10 ? '0' + minutes : minutes;
var Seconds = date.getSeconds();
seconds = seconds < 10 ? '0' + seconds : seconds;
console.log('当前时间：'+year+'年'+month+'月'+dates+'日'+arr[day]+'的'+hours+'时'+minutes+'分'+seconds+'秒');
```

获取 Date 总的毫秒数，不是当前时间的毫秒数，而是距离1970年1月1日过了多少毫秒数

```javascript
//1、通过 valueOf()、getTime()
var date = new Date();
console.log(date.valueOf());//就是我们现在时间距离1970.1.1总的毫秒数
console.log(date.getTime());
//2、简单的写法
var date1 = +new Date();// +new Date() 返回的就是总的毫秒数
console.log(date1);
//3、H5 新增的获得总的毫秒数
console.log(Date.now());
```

**倒计时案例分析**

核心算法：输入的时间减去现在的时间就是剩余的时间，即倒计时，但是不能拿着时分秒相减，比如05分减去25分，结果会是负数的。

用时间戳来做，用户输入时间的总的毫秒数减去现在的时间的总的毫秒数，得到的就是剩余时间的毫秒数。

把剩余时间总的毫秒数转换为天、时、分、秒（时间戳转换为时分秒）

```javascript
d = parseInt(总秒数/60/60/24);//计算天数
h = parseInt(总秒数/60/60%24);//计算小时
m = parseInt(总秒数/60%60);//计算分数
s = parseInt(总秒数%60);//计算当前秒数
function countDown(time){
    var nowTime = +new Date();//返回的是当前时间的总的毫秒数
    var inputTime = +new Date(time);//返回的是用户输入时间总的毫秒数
    var times = (inputTime - nowTime)/1000;//time 是剩余时间总的秒数
    var d = parseInt(times/60/60/24);
    d = d < 10 ? '0' + d : d;
    var h = parseInt(times/60/60%24);
    h = h < 10 ? '0' + h : h;
    var m = parseInt(times/60%60);
    m = m < 10 ? '0' + m : m;
    var s = parseInt(times%60);
    s = s < 10 ? '0' + s : s;
}
console.log(countDown('2019-5-1 18:00:00'));
var date = new Date();
console.log(date);
```



## 数组

### 创建数组的两种方式

```javascript
//1、利用数组的字面量
var arr = [1,2,3];
console.log(arr);
//2、利用 new Array()
var arr1 = new Array();//创建了一个空的数组
var arr2 = new Array(2);//这个2表示数组的长度为2，里面有2个空的数组元素
var arr3 = new Array(2,3);//等价于[2,3]，这样写表示里面有2个数组元素是2和3
console.log(arr3);
```

### 检测是否为数组的方法

```javascript
//1、instanceof 运算符，它可以用来检测是否为数组
var arr = [];
var obj = {};
console.log(arr instanceof Array);
console.log(obj instanceof Array);
//2、Array.isArray(参数);H5新增的方法，ie9以上版本支持
console.log(Array.isArray(arr));
console.log(Array.isArray(obj));
```

### 添加删除数组元素方法

| 方法名             | 说明                                                  | 返回值               |
| ------------------ | ----------------------------------------------------- | -------------------- |
| push(参数1....)    | 末尾添加一个或多个元素，注意修改原数组                | 并返回新的长度       |
| pop()              | 删除数组最后一个元素，把数组长度减1无参数、修改原数组 | 返回它删除的元素的值 |
| unshift(参数1....) | 向数组的开头添加一个或更多元素，注意修改原数组        | 并返回新的长度       |
| shift()            | 删除数组的第一个元素，数组长度减1无参数、修改原数组   | 并返回第一个元素的值 |

```javascript
//1、push() 在我们数组的末尾添加一个或者多个数组元素
var arr = [1,2,3];
console.log(arr.push(4,'pink'));
console.log(arr);
//(1)push 是可以给数组追加新的元素
//(2)push() 参数直接写数组元素就可以了
//(3)push 完毕之后，返回的结果是新数组的长度
//(4)原数组也会发生变化
//2、unshift()在我们数组的开头，添加一个或者多个数组元素
console.log(arr.unshift('red','purple'));
console.log(arr);
//(1)unshift是可以给数组前面追加新的数组
//(2)unshift() 参数直接写数组元素就可以了
//(3)unshift 完毕之后，返回的结果是新数组的长度
//(4)原数组也会发生变化
//3、pop() 是可以删除数组的最后一个元素
console.log(pop());
console.log(arr);
//(1)pop是可以删除数组的最后一个元素，记住一次只能删除一个元素
//(2)pop()没有参数
//(3)pop完毕之后，返回的结果是删除那个元素
//(4)原数组也会发生变化
//4、shift() 是可以删除数组的最后一个元素
console.log(shift());
console.log(arr);
//(1)shift是可以删除数组的第一个元素，记住一次只能删除一个元素
//(2)shift()没有参数
//(3)shift完毕之后，返回的结果是删除那个元素
//(4)原数组也会发生变化
```



### 数组排序

| 方法名    | 说明                           | 是否修改原数组                   |
| --------- | ------------------------------ | -------------------------------- |
| reverse() | 颠倒数组中的元素的顺序，无参数 | 该方法改变原来的数组，返回新数组 |
| sort()    | 对数组的元素进行排序           | 该方法改变原来的数组，返回新数组 |

```javascript
//数组排序
//1、翻转数组
var arr = ['pink','red','blue'];
arr.reverse();
console.log(arr);
//2、数组排序（冒泡排序）
var arr1 = [13,4,77,1,7];
arr1.sort(function(a,b){
    return a - b;//升序的顺序排序
    return b - a;//降序的顺序排序
})
console.log(arr1);
```



### 数组索引方法

| 方法名        | 说明                           | 返回值                                    |
| ------------- | ------------------------------ | ----------------------------------------- |
| indexOf()     | 数组中查找给定元素的第一个索引 | 如果存在返回索引号，如果不存在，则返回-1. |
| lastIndexOf() | 在数组中的最后一个的索引       | 如果存在返回索引号，如果不存在，则返回-1. |

案例分析

目标：把就数组里面不重复的元素选取出来放到新数组中，重复的元素只保留一个，放到新数组中去重。

核心算法：我们遍历数组，然后拿着旧数组元素去查询新数组，如果该数组里面没有出现时，我们就添加，否则不添加。

```javascript
var arr = ['c','s','a','a','e','c'.'k']
function unqiue(arr){
    var newArr = [];
    for(var i = 0; i < arr.length; i++){
        if(newArr.indexOf(arr[i]) === -1){
            newArr.push(arr[i]);
        }
    }
    return newArr;
}
```



### 数组转换为字符串

| 方法名         | 说明                                       | 返回值         |
| -------------- | ------------------------------------------ | -------------- |
| toString()     | 把数组转换成字符串，逗号分隔每一项         | 返回一个字符串 |
| join('分隔符') | 方法用于把数组中的所有元素转换为一个字符串 | 返回一个字符串 |

```javascript
//数组转换为字符串
//1、toString()将我们的数组转换为字符串
var arr = [1,2,3];
console.log(arr.toString());
//2、join('分隔符');
var arr1 = ['green','blue','pinnk'];
console.log(arr1.join());
console.log(arr1.join('-'));
console.log(arr1.join('&'));
```

| 方法名   | 说明                                     | 返回值                                         |
| -------- | ---------------------------------------- | ---------------------------------------------- |
| concat() | 连接两个或多个数组，不影响原数组         | 返回一个新的数组                               |
| slice()  | 数组截取slice(begin,end)                 | 返回被截取项目的新数组                         |
| splice() | 数组删除splice（第几个开始，要删除个数） | 返回被删除项目的新数组，注意，这个会影响原数组 |



## 字符串对象



### 基本包装类型

为了方便操作基本数据类型，Javascript 还提供了三个特殊的引用类型：String、Number 和 Boolean。

基本包装类型就是把简单数据类型包装成为复杂数据类型，这样基本数据类型就有了属性和方法。

```javascript
var str = 'andy';
console.log(str.length);
```

按道理基本数据类型是没有属性和方法的，而对象才有属性和方法，但上面代码却可以执行，这是因为 js 会把基本数据类型包装为复杂数据类型，其执行过程下：

```javascript
//1、生成临时变量，把简单类型包装为复杂数据类型
var temp = new String('andy');
//2、赋值给我们声明的字符变量
str = temp;
//3、销毁临时变量
temp = null;
```



### 字符串的不可变

指的是里面的值不可变，虽然看上去可以改变内容，但其实是地址变了，内存中新开辟了一个内存空间。

```javascript
var str = 'abc';
str = 'hello';
//当重新给 str 赋值的时候，常量 'abc' 不会修改，依然在内存中
//重新给字符串赋值，会重新在内存中开辟空间，这个特点就是字符串的不可变
//由于字符串的不可变，在大量拼接字符串的时候会有效率问题
var str = '';
for (var i = 0; i <100000; i++){
    str += i;
}
console.log(str);//这个结果需要花费大量时间来显示，因为需要不断地开辟新的空间
```

字符串对象，根据字符返回位置，str.indexOf('要查找的字符',[起始的位置])

```javascript
var str = '改革春风吹满地，春天来了';
console.log(str.indexOf('春'));
console.log(str.indexOf('春',3));//从索引号时3的位置开始往后查找
```

案例：查找字符串中某个字符出现的次数

```javascript
var str = "oanfjshiwfsnal";
var num = 0;
var index = str.indexOf('o');
while(index !== -1){
    console.log(index);
    num++;
    index = str.indexOf('o',index + 1);
}
console.log('o出现的次数是：'+num);
```



### 根据位置返回字符（重点）

| 方法名            | 说明                                       | 使用                          |
| ----------------- | ------------------------------------------ | ----------------------------- |
| charAt(index)     | 返回指定位置的字符（index 字符串的索引号） | str.charAt(0)                 |
| charCodeAt(index) | 获取指定位置处字符的ASCLL码（index索引号） | str.charCodeAt(0)             |
| str[index]        | 获取指定位置处字符                         | HTML5，IE8支持和charAt() 等效 |

```javascript
//根据位置返回字符
//1、charAt(index) 根据位置返回字符
var str = 'andy';
console.log(str.charAt(3));
//遍历所有的字符
for(var i = 0; i < str.length; i++){
    console.log(str.charAt(i));
}
//2、charCodeAt(index) 返回相应索引号的字符ASCLL值，目的：判断用户按下了那个键
console.log(str.charCodeAt(0));//97
//3、str[index] H5 新增的
console.log(str[0]);//a
```

案例：判断一个字符串 'nkfahgfkladgkalg' 中出现次数最多的字符，并统计其次数。

（1）核心算法：利用charAt() 遍历这个字符串

（2）把每个字符都存储给对象，如果对象没有该属性，就为1，如果存在了就+1

（3）遍历对象，得到最大值和该字符

```javascript
var str = 'nkfahgfkladgkalg';
var o ={};
for(var i = 0; i < str.length; i++){
    var chars = str.charAt(i);//chars 是字符串的每一个字符
    if(o[chars]){
        o[chars]++
    }
    else{
        o[chars] = 1;
    }
}
```



| 方法名               | 说明                                                         | 返回值                 |
| -------------------- | ------------------------------------------------------------ | ---------------------- |
| concat()             | 连接两个或多个数组，不影响原数组                             | 返回一个新的数组       |
| slice()              | 数组截取slice(begin,end)                                     | 返回被截取项目的新数组 |
| substr(start,length) | 从 start 位置开始（索引号），length 取的个数，重点记住这个   |                        |
| substring(start,end) | 从 start 位置开始，截取到 end 位置，end 取不到基本和 slice 相同，但是不接受负值 |                        |

```javascript
//字符串操作方法
//1、concat('字符串1','字符串2'，...);
var str = 'andy';
console.log(str.concat('red'));
//2、substr('截取的起始位置','截取几个字符');
var str1 = '改革春风吹满地';
console.log(str1.substr(2,2));//第一个2是索引号的2，从第几个开始。第二个2是取几个字符。
//3、替换字符 replace('被替换的字符','替换为的字符'),它只是替换第一个字符
var str = 'andyandy';
console.log(str.replace('a','b'));
var str1 ='najgakgnalefnwef';
while(str1.indexOf('n')!==-1){
    str1 = str1.replace('o','*');
}
console.log(str1);
//4、字符转换为数组 split('分隔符')，前面我们学过 join 把数组转换为字符串
var str2 = 'red,pink,blue';
console.log(str2.split(','));
var str3 = 'red&pink&blue';
console.log(str3.split('&'));
```



### 简单类型与复杂类型

简单类型又叫做基本数据类型或者值类型，复杂类型又叫做引用类型。

值类型：简单数据类型/基本数据类型，在存储时变量中存储的是值本身，因此叫做值类型，string，number，boolean，undefined，null

引用类型：复杂数据类型，在存储时变量中存放的仅仅是地址（引用），因此叫做引用数据类型通过 new 关键字创建的对象（系统对象、自定义对象），如Object、Array、Date等。

```javascript
//简单数据类型 null 返回的是一个空的对象 object
var timer = null;
console.log(typeof timer);
//如果有个变量我们以后打算存储为对象，暂时没想好放啥，这个时候给 null
```



## 简单类型和复杂类型的内存分配和传参



### 简单类型和复杂类型的内存分配

![image-20211028223754351](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028223754351.png)

![image-20211028223844341](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028223844341.png)

![image-20211028223918532](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028223918532.png)

![image-20211028224205270](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028224205270.png)



### 简单类型和复杂类型的传参

**简单类型传参**

函数的形参也可看作是一个变量，当我们把一个值类型变量作为参数传给函数的形参时，其实是把变量在栈空间里的值复制了一份给形参，那么在方法内部对形参做任何修改，都不会影响到的外部变量。

```javascript
function fn(a){
    a++;
    console.log(a);
}
var x = 10;
fn(x);
console.log(x);
```

![image-20211028225256732](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028225256732.png)

**复杂类型传参**

函数的形参也可以看作是一个变量，当我们把引用类型变量传给形参时，其实是把变量在栈空间里保存的堆地址复制给了形参，形参和实参其实保存的是同一个堆地址，所以操作的是同一个对象。

```javascript
function Person(name){
    this.name = name;
}
function f1(x){         //x = p
    console.log(x.name);//2.这个输出什么  刘德华
    x.name = "张学友";
    console.log(x.name);//3.这个输出什么  张学友
}
var p = new Person("刘德华");
console.log(p.name);    //1.这个输出什么  刘德华
f1(p);
console.log(p.name)；   //4.这个输出什么  张学友
```

![image-20211028225318316](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028225318316.png)



## DOM 页面文档对象模型



### Web APIs 和 JS 基本关联性



![image-20211028225501637](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028225501637.png)

![image-20211028225536054](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028225536054.png)

![image-20211028225554906](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028225554906.png)



### DOM 简介

文档对象模型（Document Object Model，简称 DOM），时W3C组织推荐的处理可扩展标记语言（HTML 或者 XML）的标准编辑接口。

W3C 已经定义了一系列的 DOM 接口，通过这些 DOM 接口可以改变网页的内容、结构和样式。

![image-20211028225926880](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211028225926880.png)



### 获取元素

DOM 在我们实际开发中主要用来操作元素

获取页面中的元素可以使用以下几种方式

（1）根据 ID 获取

```html
<div id="time">2019-9-9</div>
<script>
    //1、因为我们文档页面从上往下加载，所以先得有标签，所以我们 script 写到标签的下面
    //2、get 获取 element 元素 by 通过驼峰命名法
    //3、参数 id 是大小写敏感的字符串
    //4、返回的是一个元素对象
    var timer = document.getElementById('time');
    console.log(timer);
    console.log(typeof timer);
    //5、console.dir 打印我们返回的元素对象，更好的查看里面的属性和方法
    console.dir(timer);
</script>
```

（2）根据标签名获取，使用 getElementsByTagName() 方法可以返回带有指定标签名的对象的集合。

```html
<ul>
    <li>知否知否</li>
    <li>知否知否</li>
    <li>知否知否</li>
    <li>知否知否</li>
    <li>知否知否</li>
</ul>
<script>
    //1、返回的是获取过来的元素对象的集合，以伪数组的形式存储的
     var lis = document.getElementsByTagName('li');
    console.log(lis);
    console.log(lis[0]);
    //2、我们想要依此打印里面的元素对象我们可以采取遍历的方式
    for(var i = 0; i < lis.length; i++){
        console.log(lis[i]);
    }
    //3、如果页面中只有一个 li，返回的还是伪数组的形式
    //4、如果页面中没有这个元素返回的空的伪数组的形式
    //5、element.getElementsByTagName('标签名');父元素必须是指定的单个元素
    var ols = document.getElementsByTagName('ol'); //[ol]
    console.log(ols[0].getElementsByTagName('li'));
    var ol = document.getElementById('ol');
    console.log(ol.getElementsByTagName('li'));
</script>
```

**注意：**因为得到的是一个对象的集合，所以我们想要操作里面的元素就需要遍历。得到元素对象是动态的。

（3）通过 HTML5 新增的方法获取

```javascript
document.getElementsByClassName('类名');//根据类名返回元素对象集合
document.querySelector('选择器');//根据指定选择器返回第一个元素对象
document.querySelectorAll('选择器');//根据指定的选择器返回返回指定选择器的所有元素集合
//案例
document.getElementsByClassName('box');
document.querySelector('.box');
document.querySelector('#nav');
document.querySelector('li');
document.querySelectorAll('.box');
document.querySelectorAll('li');
```

![image-20211029173742145](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211029173742145.png)

（4）特殊元素获取（body，html）

```javascript
document.body//返回 body 元素对象
document.documentElement//返回 html 元素对象
//1、获取 body 元素
var bodyEle = document.body;
console.log(bodyEle);
sonsole.dir(bodyEle);
//2、获取 html 元素
var htmlEle = document.documentElement;
console.log(htmlEle);
```



### 事件

事件三要素

1、事件是由三部分组成事件源、事件类型和事件处理程序，我们也称为事件三要素。

```html
<button id="btn">唐伯虎</button>
<script>
     //1、事件源，事件被触发的对象（按钮）
    var btn = document.getElementById('btn');
    //2、事件类型，如何触发什么事件，比如鼠标点击（onclick）还是鼠标经过，还是键盘按下
    //3、事件处理程序，通过一个函数赋值的方式完成
    btn.onclick = function(){
        alert('点秋香');
    }
</script>
```



### 常见的鼠标事件

| 鼠标事件    | 触发事件         |
| ----------- | ---------------- |
| onclick     | 鼠标点击左键触发 |
| onmouseover | 鼠标经过事件     |
| onmouseout  | 鼠标离开事件     |
| onfoucs     | 获得鼠标焦点触发 |
| onblur      | 失去鼠标焦点触发 |
| onmousemove | 鼠标移动触发     |
| onmouseup   | 鼠标弹起触发     |
| onmousedown | 鼠标按下触发     |



### 改变元素的内容

```javascript
element.innerText
//从起始位置到终止位置的内容，但它去除 html 标签，同时空格和换行也会去掉
element.innerHTML
//起始位置到终止位置的全部内容，包括 html 标签，同时保留空格和换行
```

innerText 和 innerHTML 的区别

```html
<p>
    我是文字
    <span>123</span>
</p>
<script>
//innerText 不识别 html 标签，非标准,去除空格和换行
var div = document.querySelector('div');
var p = document.querySelector('p');
div.innerText = '<strong>今天是：</strong>2019';
console.log(p.innerText);
//innerHTML 识别 html 标签，W3C 标准。保留空格和换行
div.innerText = '<strong>今天是：</strong>2019';
console.log(p.innerHTML);
</script>
```



### 改变元素的属性

操作元素之修改元素属性

```html
<button id="ldh">刘德华</button>
<button id="zxy">张学友</button>
<img src="1.jpg" alt="">
<script>
   var ldh = document.getElementById('ldh');
   var zxy = document.getElementById('zxy');
   var img = document.querySelector('img');
    zxy.onclick = function(){
        img.src = "2.jpg";
        img.title = "张学友"
    }
    ldh.onclick = function(){
        img.src = "1.jpg";
        img.title = "刘德华"
    }
</script>
```

操作元素之表单属性设置，如表单的属性 type、value、checked、seleced、disabled

```html
<button>按钮</button>
<input type="text" value="输入内容">
<script>
    var btn = document.querySelector('button');
    var input = document.query.Selector('input');
    btn.onclick = function(){
        //input.innerHtml = "被点击了"; 这个是普通盒子比如 div 标签里面的内容
        //表单里面的值文字内容是通过 value 来修改的
        input.value = "被点击了";
        //如果想要某个表单被禁用，不能再点击 disabled，我们想要这个按钮 button 禁用
        this.diabled = true;
        this 指向的是事件函数的调用者 btn
    }
</script>
```

**仿京东密码显示案例：**

```html
<style>
    .box{
        width:400px;
        border-bottom:1px solid #ccc;
        margin:100px auto;
        position:relative;
    }
    .box input{
        width:370px;
        height:30px;
        border:0;
        ontline:none;
    }
    .box img{
        width:24px;
        position:absolute;
        right:2px;
        top:2px
    }
</style>
<div class="box">
<label for="">
    <img src="choseeye.jpg" alt="" id="eye">
</label>
<input type="password" name="" id="pwd">
</div>
<script>
    //1、获取元素
    var eye = document.getElemnetById('eye');
    var pwd = document.getElementById('pwd');
    //2、注册事件
    eye.onclick = function(){
        //点击一次之后，flag 一定要变化
        if(flag == 0){
            pwd.type = 'text';
            eye.src = 'openeye.jpg'
            flag = 1;
        }else{
            pwd.type = 'password';
            eye.src = 'closeeye.jpg'
            flag = 0;
        }
    }
</script>
```



### 样式属性操作

```html
<style>
    div{
        width:200px;
        height:200px;
        background-color:pink;
    }
</style>
<div></div>
<script>
    var div = document.querySelector('div');
    div.onclick = function(){
        //div.style里面的样式采取驼峰命名法
        this.style.backgroundColor = 'purple';
        this.style.width = '300px';
        //JS 修改 style 样式操作，产生的是行内样式，css 权重比较高
    }
</script>
```

**仿淘宝关闭二维码案例**

核心算法：利用样式的显示和隐藏完成，display:none 隐藏元素 display:block 显示元素

点击按钮，就让这个二维码盒子隐藏起来即可

```html
<style>
    .box{
        position:relative;
        width:74px;
        height:88px;
        border:qpx solid #ccc;
        margin:100px auto;
        font-size:12px;
        text-align:center;
        color:#f40;
    }
    .box img{
        width:60px;
        margin-top:5px;
    }
    .close-btn{
        position:absolute;
        top:-1px;
        left:-16px;
        width:14px;
        height:14px;
        border:1px solid #ccc;
        line-height:14px;
        font-family:Arial,Helvetica,sans-serif;
        cursor:pointer;
    }
</style>
<div class="box">
    <img src="taobao.jpg" alt="">
    <i class="close-btn">x</i>
</div>
<script>
    var btn = document.querySelector('.close-btn');
    var box = document.querySelector('.box');
    btn.onclick = function(){
        box.style.display = 'none';
    }
</script>
```

**循环精灵图案例**

```html
<style>
    .box{
        width:250px;
        margin:100px auto;
    }
    .box li{
        float:left;
        width:24px;
        height:24px;
        background-color:pink;
        margin:15px;
        background-url(images/sprite.png) no-repeat;
    }
</style>
<div>
    <ul>
       <li></li><li></li><li></li><li></li><li></li><li></li><li></li><li></li><li></li><li></li><li></li><li></li>
    </ul>
</div>
<script>
    var lis = document.querySelectorAll('li');
    for(var i = 0;i < lis.length; i++){
        var index = i * 44;
        lis[i].style.backgroundPosition = '0 -' + index + 'px';
    }
</script>
```

**案例：显示隐藏文本框内容**

案例分析

（1）首先表单需要2个新事件，获取焦点onfocus，失去焦点 onblur。

（2）如果获取焦点，判断表单里面内容是否为默认文字，如果是默认文字，就清空表单内容。

（3）如果失去焦点，判断表单内容是否为空，如果为空，则表单内容改为默认文字。

```html
<style>
    input{
        color:#999;
    }
</style>
<input type="text" value="手机">
<script>
    var text = document.querySelector('input');
    text.onfocus = function(){
        if(this.value === '手机'){
            this.value = '';
        }
        this.style.color = '#333';
    }
    text.onblur = function(){
        if(this.value === ''){
            this.value = '手机';
        }
        this.style.color = '#999';
    }
</script>

```

我们可以通过 JS 修改元素的大小、颜色、位置等样式

```javascript
element.style//行内样式操作
element.className//类名样式操作
```

**注意：**

1、如果样式修改较多，可以采取操作类名方式更改元素样式

2、class 因为是个保留字，因此使用 className 来操作元素类名属性

3、className 会直接更改元素的类名，会覆盖原先的类名

```javascript
//1、使用 element.style 获取修改元素样式，如果样式较少或者功能简单的情况下使用
var test = document.querySelector('div');
test.onclick = function(){
    //this.style.color = '#fff';
    //this.style.fontSize = "25px";
    //...
    //多类选择器,需要我们实现写好类
    this.className = "first change";
}
```

**案例：仿新浪注册页面**

```html
<style>
    div{
        width:600px;
        margin:100px auto;
    }
    .message{
        display:inline-block;
        font-size:12px;
        color:#999;
        background:url(images/mess.png) no-repeat left center;
        padding-left:20px;
    }
    .wrong{
        color:red;
        background-image:url(images/wrong.png);
    }
</style>
<div class="register">
    <input type="password" class="ipt">
    <p class="message">请输入6~16位密码</p>
</div>
<script>
    var ipt = document.querySelector('.ipt');
    var message = document.querySelector('.message');
    ipt.onblur = function(){
        if(this.value.length <6 || this.value.length > 16){
            message.className = 'message wrong';
            message.innerHTML = '你输入的位数不对要求6~16位';
        }
        else{
            message.className = 'message right';
            message.innerHTML = '你输入的正确';
        }
    }
</script>
```

![image-20211030191906040](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211030191906040.png)



### 操作元素（排他思想）

如果有同一组元素，我们想要某一个元素实现某种样式，需要用到循环的排他思想算法：

1、所有元素全部清除样式（干掉其他人）

2、给当前元素设置样式（留下我自己）

3、注意顺序不能颠倒，首先干掉其他人，再设置自己

```html
<button>按钮1</button><button>按钮2</button><button>按钮3</button><button>按钮4</button><button>按钮5</button>
<script>
    var btns = document.getElementTagName('button');
    //btns 得到的是伪数组，里面的每一个元素 btns[i]
    for(var i = 0; i < btns.length; i++){
        btns[i].onclick = function(){
            //(1)我们先把所有的按钮背景颜色去掉，干掉所有人
            for(var i = 0; i < btns.length; i++){
                btns.[i].style.backgroundColor = '';
            }
            //(2)然后才让当前的元素背景颜色为 pink，留给我自己
            this.style.backgroundColor = 'pink';
        }
    }
</script>
```

**案例：百度换肤**

```html
<style>
    *{
        margin:0;
        pading:0;
    }
    body{
        background:url(images/1.jpg) no-repeat center top;
    }
    li{
        list-style:none;
    }
    .baidu{
        overflow:hidden;
        margin:100px auto;
        background-color:#fff;
        width:410px;
        padding-top:3px;
    }
    .baidu li{
        float:left;
        margin:0 1px;
        cursor:pointer;
    }
    .baidu img{
        width；100px;
    }
</style>
<ul class="baidu">
    <li><img src="images/1.jpg"></li>
    <li><img src="images/2.jpg"></li>
    <li><img src="images/3.jpg"></li>
    <li><img src="images/4.jpg"></li>
</ul>
<script>
    var imgs = document.querySelector('.baidu').querySelectAll('img');
    for(var i = 0; i < imgs.length; i++){
        imgs[i].onclick = function(){
            document.body.style.backgroundImage = 'url(' + this.src + ')';
        }
    }
</script>
```

案例：表格隔行变色

案例分析：

（1）用到新的鼠标事件经过 onmouseover 鼠标离开 onmouseout

（2）核心思想：鼠标经过 tr 行，当前的行变色背景颜色，鼠标离开去掉当前背景颜色

（3）注意：第一行（thead 里面的行）不需要变换颜色，因此我们获取的是 tbody 里面的行

```javascript
var trs = document.querySelector('tbody').querySelectorAll('tr');
for(var i = 0; i < trs.length; i++){
    trs[i].onmouseover = function(){
        this.className = 'bg';
    }
    trs[i].onmouseout = function(){
        this.className = '';
    }
}
```

**案例：表单全选取消全选**

![image-20211030195249373](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211030195249373.png)

案例分析

（1）全选和取消全选做法：让下面所有复选框的 checked 属性（选中状态）跟随全选按钮即可

（2）下面复选框需要全部选中，上面全选才能选中做法：给下面所有复选框绑定点击事件，每次点击，都要循环查看下面所有的复选框是否有没选中的，如果有一个没选中的，上面全选就不选中

（3）可以设置一个变量，来控制全选是否选中

```javascript
var j_cbAll = document.getElementById('j_cbAll');//全选按钮
var j_tbs = document.getElementById.getElementByTagName('input');//下面所有的复选框
j_cbAll.onclick= function(){
    //this.checked它可以得到当前复选框的选中状态如果是true就是选中，如果是false就是未选中
    console.log(this.checked);
    for(var i = 0; i <j_tbs.length; i++){
        j_tbs[i].checked = this.checked;
    }
}
//下面复选框需要全部选中，上面全选才能选中做法，给下面所有复选框绑定点击事件，每次点击，都要循环查看是否有未选中的
for(var i = 0; i < j_tbs.length; i++){
    j_tbs[i].onclick = function(){
        var flag = true;
        for(var i = 0; i < j_tbs.length; i++){
            if(!j_tbs[i].checked){
                flag = false;
                break;//退出 for 循环，这样可以提高执行效率，因为只要有一个没有选中，剩下的就无需循环判断了
            }
        }
        j_cbAll.checked = flag;
    }
}
```



### 自定义属性的操作

获取属性值

```html
element.属性//获取属性值,区别：获取内置属性值（元素本身自带的属性）
element.getAttribute('属性');//主要获得自定义的属性（标准）我们程序员自定义的属性
<div id="demo" index="1"></div>
<script>
    var div = document.querySelector('div');
    console.log(div.id);
    console.log(div.getAttribute('id'));
    console.log(div.getAttribute('index'));
</script>
```

设置属性值

```html
element.属性 = '值'//设置内置属性值,区别：设置内置属性值（元素本身自带的属性）
element.getAttribute('属性','值');//主要设置自定义的属性（标准）我们程序员自定义的属性
<div id="demo" index="1"></div>
<script>
    var div = document.querySelector('div');
    div.id = 'demos';
    div.setAttribute('index',2);
</script>
```

移除属性

```html
element.removeAttribute('属性');
<script>
    var div = document.querySelector('div');
    div.removeAttribute('index');
</script>
```

**案例：tab 栏切换（重点案例）**

当鼠标点击上面相应的选项卡（tab），下面内容跟随变化

案例分析：

（1）Tab栏切换由2个大的模块

（2）上的模块选项卡，点击某一个，当前这个底色会是红色，其余不变（排他思想）修改类名的方式

（3）下面的模块的内容，会跟随上面的选项卡变化，所以下面模块变化写到点击事件里面

（4）规律：下面的模块显示内容和上面的选项卡一一对应，相匹配

（5）核心思想：给上面的 tab_list 里面的某个小 li ，让 tab_con 里面对应序号的内容显示，其余隐藏（排他思想）

```html
<style>
    .tab_list li{
        float:left;
        height:39px;
        line-height:39px;
        padding:0 20px;
        text-align:center;
        cursor:pointer;
    }
    .tab_list .current{
        background-color:#c81623;
        color:#fff;
    }
    .item_info{
        padding:20pxx 0 0 20px;
    }
</style>
<div>
    <div>
        <ul>
            <li class="current">商品介绍</li>
            <li>规格与包装</li>
            <li>售后保障</li>
            <li>商品评价</li>
            <li>手机社区</li>
        </ul>
    </div>
    <div>
        <div class="item" style="display:block;">商品介绍模块内容</div>
        <div class="item">规格与包装模块内容</div>
        <div class="item">售后保障模块内容</div>
        <div class="item">商品评价模块内容</div>
        <div class="item">手机社区模块内容</div>
    </div>
</div>
<script>
    var tab_list = document.querySelector('.tab_list');
    var lis = tab_list.querySelectorAll('li');
    for(var i = 0; i < lis.length; i++){
        lis[i].setAttribute('index',i);
        lis[i].onclick = function(){
            //干掉所有人，其余的 li 清除 class 这个类
            for(var i = 0; i < lis.length; i++){
                lis[i].className = '';
            }
            //留下我自己
            this.className = 'current';
            //下面显示内容模块
            var index = this.getAttribute('index');
            console.log(index);
            //干掉所有人，让其余的item这些div隐藏
            for(var i = 0; i < item.length; i++){
                item[i].style.display = 'none';
            }
            //留下我自己，让对应的item显示出来
            item[index].style.display = 'block';
        }
    }
</script>
```

H5 自定义属性

自定义属性目的：是为了保存并使用数据。有些数据可以保存到页面中而不用保存到数据库中。

自定义属性获取是通过 getAttribute('属性')获取。

但是有些自定义属性很容易引起歧义，不容易判断是元素的内置属性还是自定义属性。

H5给我们新增了自定义属性，规定自定义属性 data- 开头做为属性名并且赋值。

比如<div data-index = "1"></div> 或者element.setAttribute('data-index',2)

H5新增 element.dataset.index 或者 element.dataset['index']，ie11 才开始支持

```html
<div getTime="20" data-index="2" data-list-name="andy"></div>
<script>
    var div = document.querySelector('div');
    console.log(div.getAttribute('getTime'));
    console.log(div.getAttribute('data-list-name'));
    div.setAttribute('data-time',20);
    //dataset 是一个集合里面存放了所有以 data 开头的自定义属性
    console.log(div.dataset);
    console.log(div.dataset.listName);
    console.log(div.dataset['listName']);
</script>
```

![image-20211030231025911](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211030231025911.png)



### 节点操作

节点概述

一般地，节点至少拥有 nodeType（节点类型）、nodeName（节点名称）和nodeValue（节点值）这三个基本属性

元素节点 nodeType 为 1

属性节点 nodeType 为 2

文本节点 nodeType 为 3 （文本节点包括文字、空格、换行等）

我们在实际开发中，节点操作主要操作的是元素节点

节点层级

利用 DOM 树可以把节点划分为不同的层级关系，常见的事父子兄层级关系。

父级节点

```javascript
var erweima = document.querySelector('.erweima');
//得到的是离元素最近的父级节点（亲爸爸）如果找不到父节点就返回为 null
console.log(erweima.parentNode);
```

子节点

parentNode.childNodes（标准） 返回包含指定节点的子节点的集合，该集合为即时更新的集合

**注意：**返回值里面包含了所有的子节点，包括元素节点，文本节点等。

如果只想获得里面的元素节点，则需要专门处理。所以我们一般不提倡使用 childNodes

```javascript
var ul = document.querySelector('ul');
for(var i = 0; i < ul.childNodes.length; i++){
    if(ul.childNodes[i].nodeType ==1){
        //ul.childNodes[i] 是元素节点
        console.log(ul.childNodes[i]);
    }
}
```

parentNode.children（非标准）是一个只读属性，返回所有的字元素节点。它只返回子元素节点，其余节点不返回（这个是我们重点掌握的）。

虽然 children 是非标准，但是得到了各个浏览器的支持，因此我们可以放心使用

```javascript
parentNode.firstChild//firstChild 返回第一个子节点，找不到则返回 null。同样，也是包含所有的节点。
parentNode.lastChild
//以下两个方法有兼容性问题，IE9以上才支持
parentNode.firstElementChild//firstElementChild 返回第一个子元素节点，找不到则返回 null
parentNode.lastElementChild//lastElementChild 返回最后一个子元素节点，找不到则返回 null
```

实际开发中，firstChild 和 lastChild 包含其他节点，操作不简单，而 firstElementChild 和 lastElementChild 又有兼容性问题，那么我们如何获取第一个子元素节点或最后一个子元素节点呢？解决方案：

```javascript
var ol = document.querySelector('ol');
//1、firstChild 第一个子节点，不管是文本节点还是元素节点
console.log(ol.firstChild);
console.log(ol.lastChild);
//2、firstElementChild 返回第一个子元素节点
console.log(ol.firstElementChild);
console.log(ol.lastElementChild);
//3、实际开发的写法，既没有兼容性问题有返回第一个子元素
console.log(ol.children[0]);
console.log(ol.children[ol.children.length = 1]);
```

**案例：新浪下拉菜单**

案例分析：

导航栏里面的 li 都要有鼠标经过效果，所以需要循环注册鼠标事件

核心原理：当鼠标经过 li 里面的第二个孩子 ul 显示，当鼠标离开，则 ul 隐藏

```html
<style>
    .nav>li>a:hover{
        background-color:#eee;
    }
    .nav ul{
        display:none;
        position:absolute;
        top:41px;
        left:0;
        width:100%;
        border-left:1px solid #FECC5B;
        border-rigth:1px solid #FECC5B;
    }
    .nav ul li{
        border-bottom:1px solid #FECC5B;
    }
    .nav ul li a:hover{
        background-color:#FFF5DA;
    }
</style>
<div>
    <ul>
        <li>
            <a href="#">微博</a>
            <ul>
                <li><a href="私信"></a></li>
                <li><a href="评论"></a></li>
                <li><a href="@我"></a></li>
            </ul>
        </li>
        <li>
            <a href="#">微博</a>
            <ul>
                <li><a href="私信"></a></li>
                <li><a href="评论"></a></li>
                <li><a href="@我"></a></li>
            </ul>
        </li>
        <li>
            <a href="#">微博</a>
            <ul>
                <li><a href="私信"></a></li>
                <li><a href="评论"></a></li>
                <li><a href="@我"></a></li>
            </ul>
        </li>
    </ul>
</div>
<script>
    var nav = document.querySelector('.nav');
    var lis = nav.children;//得到4个小 li
    for(var i = 0; i < lis.length; i++){
        lis[i].onmouseover = function(){
            this.children[1].style.display = "block";
        }
        lis[i].onmouseout = function(){
            this.children[1].style.display = 'none';
        }
    }
</script>
```

兄弟节点

```javascript
node.nextSibling//nextSibling 返回当前元素的下一个兄弟节点，找不到则返回 null ，也是包含所有的节点
node.previousSibling//previousSibling 返回当前元素的上一个兄弟节点，找不到则返回 null ，也是包含所有的节点
//以下两个方法有兼容性问题，IE9以上才支持
node.nextElementSibling//nextElementSibling 返回当前元素的下一个兄弟节点，找不到则返回 null
node.previousElementSibling//previousElementSibling 返回当前元素的上一个兄弟节点，找不到则返回 null
```

如何解决兼容性问题？及自己封装一个兼容性的函数

```javascript
function getNextElementSibling(element){
    var el = element;
    while(el = el.nextSibling){
        if(el.nodeType === 1){
            return el;
        }
    }
    return null;
}
```

创建节点

```javascript
document.createElement('tagName');
//document.createElement()方法创建由 tagName 指定的 HTML 元素。因为这些元素原先不存在，是根据我们的需求动态生成的，所以我们也称为动态创建元素节点。
//1、创建节点元素节点
var li = document.createElement('li');
//2、添加节点 node.appendChild(child) node 父级，child 是子级后追加元素，类似于数组中的push
var ul = document.querySelector('ul');
ul.appendChild(li);
//3、添加节点 node.insertBefore(child,指定元素);
var lili = document.createElement('li');
ul.insertBefore(lili,ul.children[0]);
//4、我们想要页面添加一个新的元素：创建元素，添加元素。
```

添加元素

```javascript
node.appendChild(child)//将一个节点添加到指定父节点的子节点列表末尾
node.insertBefore(child，指定元素)//将一个节点添加到指定父节点的子节点列表前面
```

**案例：简单发布留言**

案例分析：

核心算法：点击按钮之后，就动态创建一个 li，添加到 ul 里面

创建 li 的同时，把文本与里面的值通过 li.innerHTML 复制给 li

如果想要新的留言后面显示就用 appendChild 如果想要前面显示就用 insertBefore

```javascript
var btn = document.querySelector('button');
var text = document.querySelector('textarea');
var ul = document.querySelector('ul');
var as = document.querySelector('a');
btn.onclick = function(){
    if(text.value == ''){
        alert('你没有输入内容');
        return false;
    }
    else{
        //创建元素
        var li = document.createElement('li');
        //阻止链接跳转需要添加javascript:void(0); 或者 javascript:;
        li.innerHTML = text.value + "<a href='javascript:;'>删除</a>";
        //2、添加元素
        //ul.appendChild(li);
        ul.insertBefore(li,children[0]);
        //3、删除元素，删除的是当前链接的 li 它的父亲
        for(var i = 0; i < as.length; i++){
            as[i].onclick = function(){
               // node.removeChild(child);删除的是 li 当前 a 所在的 li this.parentNode;
                ul.removeChild(this.parentNode)
            }
        }
    }
}
```

删除节点

```html
<botton>删除节点</botton>
<ul>
    <li>熊大</li>
    <li>熊二</li>
    <li>光头强</li>
</ul>
<script>
node.removeChild(child);//node.removeChild(child)方法从 DOM 中删除一个子节点，返回删除的节点
var ul = document.querySelector('ul');
var btn = document.querySelector('button');
btn.onclick = function(){
    if(ul.children.length == 0){
        this.disabled = true;
    }
    else{
        ul.removeChild(ul.children[0]);
    }
}
</script>
```

复制节点（克隆节点）

```javascript
node.choneNode()//node.choneNode()方法返回调用该方法的节点的一个副本。也称为克隆节点/拷贝节点
```

**注意：**如果括号参数为空或者为 false，则是浅拷贝，即只克隆复制节点本身，不克隆里面的子节点。如果括号参数为 true，则是深度拷贝，会复制节点本身以及里面所有的子节点。

```html
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
</ul>
<script>
    var ul = document.querySelector('ul');
    //1.node.choneNode();//括号参数为空或者为 false，则是浅拷贝，即只克隆复制节点标签。不复制内容
    //2.括号参数为 true，则是深度拷贝，会复制节点本身以及里面所有的内容。
    var lili = ul.children[0].choneNode(true);
    ul.appendChild(lili);
</script>
```

**案例：动态生成表格**

案例分析：

因为里面的学生数据都是动态的，我们需要 js 动态生成。这里我们模拟数据，自己定义好数据。数据我们采取对象形式存储。

所有的数据都是放到 tbody 里面的行里面。

因为行很多，我们需要循环创建多个行（对应都少人）。

每个行里面又有很多单元格（对应里面的数据），我们还继续使用循环创建多个单元格，并且把数据存入里面（双重 for 循环）。

最后一列单元格是删除，需要单独创建单元格。

```html
<style>
    table{
        width:500px;
        border-collapse:collapse;
        margin:100px auto;
        text-align:center;
    }
    td,th{
        border:1px solid #333;
    }
    thead tr{
        height:40px;
        background-color:#ccc;
    }
</style>
<table>
    <thead><tr></tr></thead>
    <tbody><tr></tr></tbody>
</table>
<script>
    var datas = [{
        name:'张三疯';
        subject:'Javascript';
        score:100;
    }];
    //往 tbody 里面创建行：有几个人（通过数组的长度）我们就创建几行
    var tbody = document.querySelector('tbody');
    for(var i = 0; i <datas.length; i++){
        // 创建 tr 行
        var tr = document.createElement('tr');
        tbody.appendChild(tr);
        // 行里面创建单元格 td 单元格的数量取决于每个对象里面的属性个数 for 循环遍历对象 datas[i]
        for(var k in datas[i]){
            //创建单元格
            var td = document.createElement('td');
            //把对象里面的属性值 datas[i][k] 给 td
            // console.log(datas[i][k]);
            td.innerHTML = datas[i][k]
            tr.appendChild(td);
        } 
        //3、创建有删除 2 个字的单元格
        var td document.createElement('td');
        td.innerHTML = '<a href="javascript:;">删除</a>';
        tr.appendChild(td);
    }
    //4、删除操作开始
    var as = document.querySelectorAll('a');
    for(var i = 0; i < as.length; i++){
        as[i].onclick = function(){
            // 点击 a 删除当前 a 所在的行
            tbody.removeChild(this.parentNode.parentNode);
        }
    }
</script>
```

三种创建元素方式的区别

```html
<button>点击</button>
<p>abc</p>
<div class="inner"></div>
<div class="create"></div>
<script>
//1、document.write() 创建元素，如果页面文档流加载完毕，再调用这句话会导致页面重绘
window.onload = function(){
    document.write('<div>123</div>');
}
var btn = document.querySelector('button');
btn.onclick = function(){
    document.write('<div>123</div>');
}
//2、innerHTML 创建元素
    var inner = document.querySelector('.inner');
    for(var i = 0; i <= 100; i++){
        inner.innerHTML += '<a href="#">百度</a>';
    }
//3、document.createElement() 创建元素
    var create = document.createElement('a');
    create.appendChild(a);
</script>
```

三种动态创建元素区别

document.write() 是直接将内容写入页面的内容流，但是文档流执行完毕，则它会导致页面全部**重绘**

element.innerHTML 是将内容写入某个 DOM 节点，不会导致页面全部重绘，采取拼接的方式，如下。

```javascript
function fn(){
    var d1 = +new Date();
    var str = '';
    for(var i = 0; i <= 1000; i++){
        document.body.innerHTML += '<div style="width:100px; height:2px; border qpx solid blue;"></div>';
    }
    var d2 =+new Date();
    console.log(d2 - d1);
}
fn();
```

创建多个元素效率更高（不要拼接字符串，采取数组形式拼接），结构稍微复杂，如下。

```javascript
function fn(){
    var d1 = +new Date();
    var array = [];
    for(var i = 0; i <= 1000; i++){
        array.push('<div style="width:100px; height:2px; border qpx solid blue;"></div>');
    }
    document.body.innerHTML = array.join('');
    var d2 =+new Date();
    console.log(d2 - d1);
}
fn();
```

createElement() 创建多个元素效率稍微低一点点，但是结构更清晰

```javascript
function fn(){
    var d1 = +new Date();
    for(var i = 0; i < 1000; i++){
        var div = document.createElement('div');
        div.style.width = '100px';
        div.style.height = '2px';
        div.style.border = '1px solid red';
        document.body.appecdChild(div);
    }
    var d2 = +new Date();
    console.log(d2 - d1);
}
fn();
```

总结：不同浏览器下，innerHTML 效率要比 createElement 高

![image-20211031182147921](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211031182147921.png)

关于 dom 操作，我们主要针对于元素的操作。主要有创建、增、删、改、查、属性操作、事件操作。



## 事件



### 注册事件概述

![image-20211031182442585](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211031182442585.png)



### 事件监听方式

**addEventListener 事件监听方式**

```javascript
eventTarget.addEventListener(type,listener[,useCapture])
```

eventTarget.addEventListener() 方法将指定的监听器注册到 eventTarget（目标对象）上，当该对象触发指定的事件时，就会执行事件处理函数。该方法接收三个参数：

type：事件类型字符串，比如 click、mouseover，注意这里不要带 on

listener：事件处理函数，事件发生时，会调用该监听函数

useCapture：可选参数，是一个布尔值，默认是 false。学完 DOM 事件流后，我们再进一步学习



**attachEvent 事件监听方式**

```javascript
eventTarget.attachEvent(eventNameWithOn,callback)
```

eventTarget.attachEvent() 方法将指定的监听器注册到 eventTarget（目标对象）上，当该对象触发事件指定的事件时，指定的回调函数就会被执行。该方法接收两个参数：

eventNameWithOn：事件类型字符串，比如 onclick、onmouseover，这里要带 on

callback：事件处理函数，当目标触发事件时回调函数被调用

```html
<button>按钮</button>
<button>按钮</button>
<button>按钮</button>
<script>
    var btn = document.querySelectorAll('button');
    //1、传统方式注册事件
    btns[0].onclick = function(){
        alert('hi');
    }
    btns[0].onclick = function(){
        alert('hao a u');
    }
    //2、事件监听注册事件 addEventListener
    //(1)里面的事件类型是字符串，必定加引号，而且不带 on
    //(2) 同一个元素，同一个事件可以添加多个监听器（事件处理程序）
    btn[1].addEventListener('click',function(){
        alert(22);
    })
    btn[1].addEventListener('click',function(){
        alert(33);
    })
    //3、attachEvent ie9以前的版本支持
    btn[2].attachEvent('onclick',function(){
        alert(11);
    })
</script>
```

**注册事件兼容性解决方案**

```javascript
function addEventListener(element,eventName,fn){
    //判断当前浏览器是否支持 addEventListener 方法
    if(element.addEventListener){
        element.addEventListener(eventName,fn);
    }
    else if(element.attachEvent){
        element.attachEvent('on' + eventName,fn);
    }
    else{
        //相当于 element.onclick = fn;
        element['on' + eventName] = fn;
    }
}
```

兼容性处理的原则：首先照顾大多数浏览器，再处理特殊浏览器



### 事件删除

```html
<div>1</div>
<div>2</div>
<div>3</div>
<script>
    var divs = document.querySelectorAll('div');
    divs[0].onclick = function(){
        alert(11);
        //传统方式删除事件
    }
    //2、removeEventListener 删除事件
    divs[1].addEventListener('click',fn);//里面的 fn 不需要调用加小括号
    function fn(){
        alert(22);
        divs[1].removeEventListener('click',fn);
    }
    //3、
    divs[2].attachEvent('onclick',fn1);
    function fn1(){
        alert(33);
        divs[2].detachEvent('onclick',fn1);
    }
</script>
```

删除事件兼容性解决方案

```javascript
function removeEventLietener(element,eventName,fn){
    //判断当前浏览器是否支持 removeEventListener 方法
    if(element.removeEventListener){
        element.removeEventListener(eventName,fn);//第三个参数默认是 false
    }
    else if(element.detachEvent){
        element.detachEvent('on' + eventName,fn);
    }
    else{
        element['on' + eventName] = null;
    }
}
```



### DOM 事件流

![image-20211031195505816](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211031195505816.png)

![image-20211031195614062](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211031195614062.png)

事件发生会在元素节点之间按照特定的顺序传播，这个传播过程即 DOM 事件流。

**注意：**

（1）JS 代码中只能执行捕获或者冒泡其中的一个阶段。

（2）onclick 和 attachEvent 只能得到冒泡阶段。

（3）addEventListener(type,listener[,useCapture]) 第三个参数如果是 true，表示在事件捕获阶段调用事件处理程序；如果是 false（不写默认就是 false），表示在事件冒泡阶段调用事件处理程序。

（4）实际开发中我们很少使用事件捕获，我们更关注事件冒泡。

（5）有些事件是没有冒泡的，比如 onblur、onfocus、onmouseenter、onmouseleave

（6）事件冒泡有时候会带来麻烦，有时候又会帮助很巧妙的做某事件，我们后面讲解。

```html
<div class="father">
    <div class="son"></div>
</div>
<script>
    //dom 事件流三个阶段
    //1、Js 代码中只能执行捕获或者冒泡其中的一个阶段
    //2、 onclick 和 attachEvent（ie） 只能得到冒泡阶段
    //3、捕获阶段，如果 addEventListener 第三个参数是 true，那么则处于捕获阶段 document -> html -> body -> father -> son
    var son = document.querySelector('.son');
    son.addEventListener('click',function(){
        alert('son');
    },true);
    var father = document.querySelector('.father');
    father.addEventListener('click',function(){
        alert('father');
    },true);
    //4、冒泡阶段，如果 addEventListener 第三个参数是 false 或者 省略，那么则处于冒泡阶段
    //son -> father -> body -> html -> document
    var son = document.querySelector('.son');
    son.addEventListener('click',function(){
        alert('son');
    },false);
    var father = document.querySelector('.father');
    father.addEventListener('click',function(){
        alert('father');
    },false);
    document.addEventListener('click',function(){
        alert('document');
    })
</script>
```



### 事件对象

```javascript
eventTarget.onclick = function(event){}
eventTarget.addEventListener('click',function(event){})
//这个 event 就是事件对象，我们还喜欢的写成 e 或者 evt
```

官方解释：event 对象代表事件的状态，比如键盘按键的状态、鼠标的位置、鼠标按钮的状态。

简单解释：事件发生后，跟事件相关的一系列信息数据的集合都放这个对象里面，这个对象就是事件对象 event，他有很多属性和方法。比如：

1、谁绑定了这个事件。

2、鼠标触发事件的话，会得到鼠标的相关信息，如鼠标位置。

3、键盘触发事件的话，会得到键盘的相关信息，如按了哪个键。

**事件对象的使用语法**

```javascript
eventTarget.onclick = function(event){
    //这个event 就是 事件对象，我们还喜欢的写成 e 或者 evt
}
eventTarget.addEventListener('click',function(event)){
     //这个 event 就是事件对象，我们还喜欢的写成 e 或者 evt                        
}
```

这个 event 是个形参，系统帮我们设定为事件对象，不需要传递实参过去。

当我们注册事件时，event 对象就会被系统自动创建，并依次传递给事件监听器（事件处理函数）。

```javascript
var div = document.querySelector('div');
div.onclick = function(e){
    //console.log(window.event);
    e = e || window.event;
    console.log(e);
}
div.addEventListener('click',function(e)){
    console.log(e);
}
//1、event 就是一个事件对象，写到我们侦听函数的小括号里面当形参来看。
//2、事件对象只有有了事件才会存在，它是系统给我们创建的，不需要我们传递参数。
//3、事件对象是我们事件的一系列相关数据的集合，跟事件相关，比如鼠标点击里面就包含了鼠标的相关信息，鼠标坐标，如果是键盘事件里面就包含的键盘事件的信息，比如，判断用户按下了那个键。
//4、这个事件对象我们可以自己命名，比如 event、evt、e
//5、事件对象也有兼容性问题 ie789 通过 window.event 兼容性的写法 e = e || window.event;
```

**事件对象的常见属性和方法**

![image-20211103152729767](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211103152729767.png)

```html
<div style="width:100px;height:100px"></div>
<ul>
    <li>abc</li>
    <li>abc</li>
    <li>abc</li>
</ul>
<script>
    //常见事件对象的属性和方法
    //1、 e.target 返回的是触发事件的对象（元素），this 返回的是绑定事件的对象（元素）
    //区别： e.target 点击了那个元素，就返回那个元素 this 那个元素绑定了这个点击事件，那么就返回谁
    var div = document.querySelector('div');
    div.addEventListener('click',function(e){
        console.log(e.target);
        console.log(this);
    })
    var ul = document.querySelector('ul');
    ul.addEventListener('click',function(e){
        //我们给 ul 绑定了事件，那么 this 就指向 ul
        console.log(this);
        //e.taregt 只想我们点击的那个对象，谁触发了这个事件，我们点击的是 li e.target 指向的就是 li
        console.log(e.target);
    })
    // 了解兼容性
    div.onclick = function(e){
        e = e || window.event;
        var target = e.taregt || e.srcElement;
        console.log(target);
    }
    //2、了解跟 this 有个非常相似的属性 currentTarget，ie678 不认识
</script>
```

1、返回事件类型；2、阻止默认行为

```html
<div>123</div>
<a href="http://www.baidu.com">百度</a>
<form action="http://www.baidu.com">
    <input type="submit" value="提交" name="sub">
</form>
<script>
    //返回事件类型
    var div = document.querySelector('div');
    div.addEventListener('click',fn);
    div.addEventListener('mouseover',fn);
    div.addEventListener('mouseout',fn);
    function fn(e){
        console.log(e.type);
    }
    //2、阻止默认行为（事件）让链接不跳转或者让提交按钮不提交
    var a = addEventListener('click',function(e){
        e.preventDefault();//dom 标准写法
    })
    a.onclick = function(e){
        //普通浏览器 e.preventDefalut();方法
        //e.preventDefalut();
        //低版本浏览器 ie678 returnValue 属性
        //e.returnValue;
        //我们可以利用 return false 也能阻止默认行为，没有兼容性问题，特点：return 后面的代码不执行了，而且只限于传统的注册方式
        return false;
        alert(11);
    }
</script>
```

**组织事件冒泡**

组织事件冒泡的两种方式

事件冒泡：开始时由最具体的元素接收，然后逐级向上传播到DOM最顶层节点。

事件冒泡本身的特性，会带来的坏处，也会带来的好处，需要我们灵活掌握。

阻止事件冒泡

标准写法：利用事件对象里面的 stopPropagation() 方法

```javascript
e.stopPropagation()
```

非标准写法：IE 6-8 利用事件对象 cancelBubble属性

```html
<div class="father">
    <div class="son">son 儿子</div>
</div>
<script>
     //阻止冒泡 dom 推荐的标准 stopPropagation()
    var son = document.querySelector('.son');
    son.addEventListener('click',function(e){
        alert('son');
        e.stopPropagation();//stop 停止 Propagation 传播
        e.cancelBubble = true;// 非标准 cancel 取消 bubble 泡泡
    }，false);
    var father = document.querySelector('.father');
    father.addEventListener('click',function(){
        alert('father');
    },false);
    document.addEventListener('click',function(){
        alert('document');
    })
</script>
```

组织事件冒泡的兼容性解决方法

```javascript
if( e && e.stopPropagation){
    e.stopPropagation();
}
else{
    window.event.cancelBubble = true;
}
```



### 事件委托（代理、委派）

事件冒泡本身的特性，会带来的坏处，也会带来的好处，需要我们灵活掌握。生活中有如下场景：

咱们班有100个学生，快递员有100个快递，如果一个个的送花费的时间较长。同时每个学生领取的时候，也需要排队领取，也花费时间较长，何如？

**解决方案：**快递员把100个快递，委托给班主任，班主任，班主任把这些快递放到办公室，同学们下课自行领取即可。

**优势：**快递员省事，委托给班主任就可以走了。同学们领取也方便，因为相信班主任。

**事件委托**

事件委托也称事件代理，在 jQuery 里面称为事件委派。

**事件委派的原理**

不是没个子节点单独设置事件监听器，而是事件监听器设置在其父节点上，然后利用冒泡原理影响设置每个子节点。

以上案例：给 ul 注册点击事件，然后利用事件对象的 target 来找到当前点击的 li，因为点击 li，时间会冒跑到 ul 上，ul 有注册事件，就会触发事件监听器。

**事件委托的作用**

我们只操作了一次 DOM，提高了程序的性能。

```html
<ul>
    <li>知否知否，点我应有弹框在手！</li>
    <li>知否知否，点我应有弹框在手！</li>
    <li>知否知否，点我应有弹框在手！</li>
    <li>知否知否，点我应有弹框在手！</li>
</ul>
<script>
    //事件委托的核心思想：给父节点添加侦听器，利用事件冒泡影响每一个子节点
    var ul = document.querySelector('ul');
    ul.addEventListener('click',function(e){
        // alert('知否知否，点我应有弹框在手！');
        //e.taregt 这个可以得到我们点击的对象
        e.target.style.background = 'pink';
    })
</script>
```

1、禁止鼠标右键菜单

contextmenu 主要控制应该何时显示上下文菜单，主要用于程序员取消默认的上下文菜单

```javascript
document.addEventListner('contextmenu',funciton(e){
    e.preventDefault();
})
```

2、禁止鼠标选中（selectstart 开始选中）

```javascript
document.addEventListener('selectstart',function(e){
    e.preventDefault();
})
```

```html
<body>
    我是一段不愿意分享的文字
    <script>
        //1、 contextmenu 我们可以禁用右键菜单
        document.addEventListener('contextmenu',function(e){
            e.preventDefault();
        })
        //2、禁止选中文字 selectstart
        document.addEventListener('selectstart',function(e){
            e.preventDefault();
        })
    </script>
</body>
```



### 鼠标事件对象

event 对象代表事件的状态，跟时间相关的一系列信息的集合。现阶段我们主要是用鼠标事件对象 MouseEvent 和键盘事件对象 KeyboardEvent。

![image-20211103215221132](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211103215221132.png)

```javascript
document.addEventListener('click',function(e){
    //1、client 鼠标在可视区的x和y坐标
    console.log(e.clientX);
    console.log(e.clientY);
    console.log('-----------');
    //2、page 鼠标在页面文档的x和y坐标
    console.log(e.pageX);
    console.log(e.pageY);
    console.log('-----------');
    //3、screen 鼠标在电脑屏幕的x和y坐标
    console.log(e.screenX);
    console.log(e.screenY);
})
```

**案例：跟踪鼠标的天使**

案例分析：

（1）鼠标不断的移动，使用鼠标移动事件：mousemove

（2）在页面中移动，给 document 注册事件

（3）图片要移动距离，而且不占位置，我们使用绝对定位即可

（4）核心原理：每次鼠标移动，我们都会获得最新的鼠标坐标，把这个x和y坐标做为图片的 top 和 left 值就可以移动图片

```html
<img src="images/ange1.gif" alt="">
<script>
    var pic = document.querySelector('img');
    document.addEventListener('mousemove',function(e){
        //1、mousemove 只要我们鼠标移动1px，就会触发这个事件
        //2、核心原理：每次鼠标移动，我们都会获得最新的鼠标坐标，把这个x和y坐标做为图片的top 和 left 值就可以移动图片
        var x = e.pageX;
        var y = e.pageY;
        console.log('x的坐标是：'+ x , 'y的坐标是：' + y);
        pic.style.left = x;
        pic.style.top = y;
        //3、千万不要忘记给 left 和 top 添加 px 单位
        pic.style.left = x + 'px';
        pic.style.top = y - 40 + 'px';
    })
</script>
```



### 常用键盘事件

![image-20211103222745257](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211103222745257.png)

```javascript
//1、keyup 按键弹起的时候触发
document.onkeyup = function(){
    console.log('我弹起了');
}
document.addEventListener('keyup',function(){
    console.log('我弹起了');
})
//2、keydown 按键按下的时候触发，能识别功能键，比如 ctrl shift 左右箭头
document.addEventListener('keydown',function(){
    console.log('我按下了down');
})
//3、keypress 按键按下的时候触发，不能识别功能键，比如 ctrl shift 左右箭头
document.addEventListener('keypress',function(){
    console.log('我按下了press');
})
```

**注意：**

1、如果使用 addEventListener 不需要加 on

2、onkeypress 和前面2个的区别是，它不识别功能键，比如左右箭头，shift等。

3、三个事件的执行顺序是：keydown->keypress->keyup



### 键盘事件对象

![image-20211103223753821](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211103223753821.png)

```javascript
//键盘事件对象中的 keyCode 属性可以得到相应键的 ASCII 码值
//1、我们的 keyup 和 keydown 事件不区分字母大小写 a 与 A 得到的都是 65
//2、我们的 keyup 和 keydown 事件区分字母大小写 a 97 和 A 得到的是 65
document.addEventListener('keyup',function(e){
    console.log('up:'+e.keyCode);
    // 我们可以利用 keyCode 返回的 ASCII 码值来判断用户按下了那个键
    if(e.keyCode === 65){
        alert('您按下了a键');
    }else{
        alert('您没有按下了a键')；
    }
})
document.addEventListener('keypress',function(e){
    console.log('press:'+e.keyCode);
})
```

**案例：模拟京东按键输入内容**

案例分析：

（1）核心思路：检测用户是否按下了 s 键，如果按下 s 键，就把光标定位到搜索框里面

（2）使用键盘事件对象里面的 keyCode 判断用户按下的是否是 s 键

（3）搜索框获得焦点：使用 js 里面的 focus() 方法

```html
<input type="text">
<script>
    var search = document.querySelector('input');
    document.addEventListener('keyup',function(){
        if(e.keyCode === 83){
            search.focus();
        }
    })
</script>
```

**案例：模拟京东快递单号查询**

案例分析：

（1）快递单号输入内容时，上面的大号字体盒子（con）显示（这里面的字号更大）

（2）表单检测用户输入：给表单添加键盘事件

（3）同时把快递单号里面的值（value）获取过来赋值给 con 盒子（innerText）作为内容

（4）如果快递单号里面内容为空，则隐藏大号字体盒子（con）盒子

（5）注意：keydown 和 keypress 在文本框里面的特点：他们两个事件触发的时候，文字还没有落入文本框。

（6）keyup 事件触发的时候，文字已经落入文本框里面了

```javascript
var con = document.querySelector('.con');
var jd_input = document.querySelector('.jd');
jd_input.addEventListener('keyup',function(){
    if(this.value == ''){
        con.style.display = 'none';
    }else{
        con.style.display = 'block';
        con.innerText = this.value;
    }
})
//当我们失去焦点，就隐藏这个 con 盒子
jd_input.addEventListener('blur',function(){
    con.style.display = 'none';
})
//当我们获得焦点，就显示这个 con 盒子
jd_input.addEventListener('focus',function(){
    if(this.value !== ''){
        con.style.display = 'block';
    }    
})
```



## BOM（浏览器对象模型）

![image-20211103231201732](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211103231201732.png)



### BOM的构成

![image-20211103231214027](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211103231214027.png)

window 对象是浏览器的顶级对象，它具有双重角色。

1、它是 JS 访问浏览器窗口的一个接口

2、它是一个全局对象。定义在全局作用域中的变量、函数都会变成 window 对象的属性和方法。

在调用的时候可以省略 window，前面学习的对话框都属于 window 对象方法，如 alert()、prompt()等。

**注意：**window 下的一个特殊属性 window.name



### 窗口加载事件

```javascript
window.onload = function(){}
//或者
window.addEventListener('load',function(){});
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
document.addEventListener('DOMContentLoaded',function(){})
```

window.onload 是窗口（页面）加载事件，当文档内容完全加载完成会触发该事件（包括图像、脚本文件、CSS文件等），就调用的处理函数。

DOMContentLoaded 事件触发时，仅当 DOM 加载完成，不包括样式表，图片，flash等等。ie9以上才支持

如果页面的图片很多的话，从用户访问到 onload 触发可能需要较长的时间。交互效果就不能实现，必须影响用户的体验，此时用 DOMContentLoaded 事件比较合适。

**注意：**

1、有了 window.onload 就可以把 JS 代码写到页面元素的上方，因为 onload 是等页面内容全部加载完毕，再去执行处理函数。

2、window.onload 传统注册事件方式只能写一次，如果有多个，会以最后一个 window.onload 为准。

3、如果使用 addEventListener 则没有限制。

```javascript
window.addEventListener('load',function(){
    var btn = document.querySelector('button');
    btn.addEventListener('click',function(){
        alert('点击我');
    })
})
window.addEventListener('load',function(){
    alert(22);
})
window.addEventListener('DOMContentLoaded',function(){
    alert(33);
})
//load 等页面内容全部加载完毕，包含页面dom元素，图片 flash css等等
// DOMContentLoaded 是 DOM 加载完毕，不包含图片 flash css 等就可以执行，加载速度比 load更快一些
```



### 调整窗口大小事件

```javascript
window.onresize = function(){}
window.addEventListener('resize',function(){});
```

window.onresize 是调整窗口大小加载事件，当触发时就调用的处理函数

**注意：**

1、只要窗口大小发生像素变化，会触发这个事件。

2、我们经常利用这个时间完成响应式布局。window.innerWidth 当前屏幕的宽度

```javascript
window.addEventListener('load',function(){
    var div = document.querySelector('div');
    window.addEventListener('resize',function(){
        console.log(window.innerWidth);
        console.log('变化了');
        if(window.innerWidth <= 800){
            div.style.display = 'none';
        }else{
            div.style.display = 'block';
        }
    })
})
```



### 两种定时器

window 对象给我们提供了2个非常好用的方法-定时器。

**setTimeout() 定时器**

```javascript
window.setTimeout(调用函数，[延迟的毫秒数]);
```

setTimeout() 方法用于设置一个定时器，该定时器在定时器到期后执行调用函数。

**注意：**

1、window 可以省略。

2、这个调用函数可以直接写函数，或者写函数名或者采取字符串‘函数名()’三种形式。第三种不推荐

3、延迟的毫秒数省略默认是0，如果写，必须是毫秒。

4、因为定时器可能有很多，所以我们经常给定时器赋值一个标识符。

```javascript
setTimeout(function(){
    console.log('时间到了');
},2000);
function callback(){
    console.log('爆炸了');
}
setTimeout(callback,3000);
//setTimeout('callback()',3000);我们不提倡这个写法
```

setTimeout() 这个调用函数我们也称为回调函数 callback。普通函数是按照代码顺序直接调用。而这个函数，需要等待时间，时间到了才去调用这个函数，因此称为回调函数。简单理解：回调，就是回头调用的意思。上一件事干完，再回来再调用这个函数。以前我们讲的element.onclick = function(){} 或者 element.addEventListener('click',fn); 里面的函数也是回调函数。

**案例：回调函数以及5秒之后自动关闭广告**

案例分析：

（1）核心思路：5秒之后，就把这个广告隐藏起来

（2）用定时器 setTimeout

```html
<img src="images/ad.jpg" alt="">
<script>
    var ad = document.querySelector('.ad');
    setTimeout(function(){
        ad.style.display = 'none';
    },5000);
</script>
```



**setInterval() 定时器**

```javascript
window.setInterval(回调函数,[间隔的毫秒数]);
```

setInterval() 方法重复调用一个函数，每隔这个时间，就去调用一次回调函数。

**注意：**

（1）window 可以省略。

（2）这个调用函数可以直接写函数，或者写函数名或者采取字符串‘函数名()’三种形式。

（3）间隔的毫秒数省略默认是0，如果写，必须是毫秒，表示每隔多少毫秒就自动调用这个函数。

（4）因为定时器可能有很多，所以我们经常给定时器赋值一个标识符。

```javascript
// 语法规范：window.setInterval(调用函数,延时时间);
setInterval(function(){
    console.log('继续输出');
},1000);
//setTimeout 延时时间到了，就去调用这个回调函数，只调用一次，就结束了这个定时器
//setInterval 每隔这个延时时间，就去调用这个回调函数，会调用很多次，重复调用这个函数
```

**案例：倒计时效果**

案例分析：

（1）这个倒计时是不断变化的，因此需要定时器来自动变化（setInterval）

（2）三个黑色盒子里面分别存放时分秒

（3）三个黑色盒子利用 innerHTML 放入计算的小时分钟秒数

（4）第一次执行也是间隔毫秒数，因此刚刷新页面会有空白

（5）最好采取封装函数的方式，这样可以先调用一次这个函数，防止刚开始刷新页面有空白问题。

```html
<div>
    <span class="hour">1</span>
    <span class="minute">2</span>
    <span class="second">3</span>
</div>
<script>
    //1、获取元素
    var hour = document.querySelector('.hour');//小时的黑色盒子
    var minute = document.querySelector('.minute');//分钟的黑色盒子
    var second = document.querySelector('.second');//秒数的黑色盒子
    var inputTime = +new Date('2019-5-5 18:00:00');//返回的是用户输入时间总的毫秒数
    countDown();//我们先调用一次这个函数，防止刚开始刷新页面有空白问题。
    //2、开启定时器
    setInterval(countDown,1000);
    function countDown(){
        var nowTime = +new Date();//返回的是当前时间总的毫秒数
        var times = (inputTime - nowTime) / 1000;// times是剩下时间总的毫秒数
        var h = parseInt(times / 60 /60 % 24);//时
        h = h < 10 ? '0' + h : h;
        hour.innerHTML = h;
         var m = parseInt(times / 60 % 60 );//分
        m = m < 10 ? '0' + m : m;
        minute.innerHTML = m;
         var s = parseInt(times % 60);//秒
        s = s < 10 ? '0' + s : s;
        second.innerHTML = s;
    }
</script>
```



### 停止两个定时器

**停止 setTimeout() 定时器**

```javascript
window.clearTimeout(timeoutID)
```

clearTimeout() 方法取消了先前通过调用 setTimeout() 建立的定时器

**注意：**1、window 可以省略。2、里面的参数就是定时器的标识符。

```html
<button>点击停止定时器</button>
<script>
    var btn = document.querySelector('button');
    var timer = setTimeout(function(){
        console.log('爆炸了');
    },5000);
    btn.addEventListener('click',function(){
        clearTimeout(timer);
    })
</script>
```

**停止 setInterval() 定时器**

```javascript
window.clearTnterval(intervalID);
```

clearInterval() 方法取消了先前通过调用 setInterval() 建立的定时器。

**注意：**1、window 可以省略。2、里面的参数就是定时器的标识符。

```html
<button class="begin">点击开启定时器</button>
<button class="stop">点击停止定时器</button>
<script>
    var begin = document.querySelector('.begin');
     var stop = document.querySelector('.stop');
    var timer = null;
    begin.addEventListener('click',function(){
        timer = setTimeout(function(){
            console.log('爆炸了');
        },1000);
    })
    stop.addEventListener('click',function(){
        clearTimeout(timer);
    })
</script>
```

**案例：发送短信**

点击按钮后，该按钮60秒之内不能再点击，防止重复发送短信

案例分析：

（1）按钮点击之后，会禁用 disabled 为 true

（2）同时按钮里面的内容会变化，注意 button 里面的内容通过 innerHTML 修改

（3）里面秒数是有变化的，因此需要用到定时器

（4）定义一个变量，在定义其里面，不断递减

（5）如果变量为0说明到了时间，我们需要停止定时器，并且赋予按按钮初始状态

```html
<input type="number"><button>发送</button>
<script>
    var btn = document.querySelector('button');
    btn.addEventListener('click',function(){
        btn.disbled = true;
        var timer = setInterval(function(){
            if(time == 0){
                clearInterval(timer);
                btn.disabled = false;
                btn.innerHTML = '发送';
            }
            else{
                btn.innerHTML = '还剩下' + time + '秒';
            }
        },1000);
    })
</script>
```



### this 指向问题

this 指向问题，一般情况下 this 的最终指向的是那个调用它的对象。

```javascript
//1、全局作用域或者普通函数中 this 指向全局对象 window（注意定时器里面的 this 指向 window）
console.log(this);
function fn(){
    console.log(this);
}
window.fn();
window.setTimeout(function(){
    console.log(this);
},1000);
//2、方法调用中谁调用 this 指向谁
var o = {
    sayHi:function(){
        console.log(this);//this 指向的是 o 这个对象
    }
}
o.sayHi();
var btn = document.querySelector('button');
btn.addEventListener('click',function(){
    console.log(this);//this 指向的是 btn 这个按钮对象
})
//构造函数中 this 指向构造函数的实例
function Fun(){
    console.log(this);//this 指向的是 fun
}
var fun = new Fun();
```



### JS 是单线程

Javascript 语言的一大特点就是单线程，也就是说，同一个时间只能做一件事。这是因为 Javascript 这门脚本语言诞生的使命所致——Javascript 是为处理页面中用户的交互，以及操作 DOM 而诞生的，比如我们对某个 DOM 元素进行添加和删除操作，不能同时进行。应该先进行添加，之后再删除。

单线程就意味着，所有任务需要排队，前一个任务，才会执行后一个任务。这样所导致的问题是：如果 JS 执行的时间过长，这样就会造成页面的渲染不连贯，导致页面渲染加载阻塞的感觉。



### 同步和异步

以下代码执行的结果是什么？

```javascript
console.log(1);
setTimeout(function(){
    console.log(3);
},1000);
console.log(2);
```

为了解决这个问题，利用多核 CPU 的计算能力，HTML5 提出 Web Worker 标准，允许 Javascript 脚本创建多个线程。于是，JS 中出现了同步和异步。

![image-20211104154114516](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211104154114516.png)

![image-20211104154125144](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211104154125144.png)

![image-20211104154136934](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211104154136934.png)

![image-20211104154208917](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211104154208917.png)

那么以下代码执行的结果又是什么？

```javascript
console.log(1);
setTimeout(function(){
    console.log(3)
},0);
console.log(2);
//>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
console.log(1);
document.onclick = function(){
    console.log('click');
}
concole.log(2);
setTimeout(function(){
    console.log(3);
},3000);
```

![image-20211104164719846](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211104164719846.png)

![image-20211104164740846](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211104164740846.png)



### location 对象

window 对象给我们提供了一个 location 属性用于获取或设置窗体的 URL，并且可以用于解析 URL。因为这个属性返回的是一个对象，所以我们将这个属性也称为 location 对象。

![image-20211104171612895](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211104171612895.png)

**location 对象的属性**

| location 对象属性 | 返回值                           |
| ----------------- | -------------------------------- |
| location.href     | 获取或者设置整个 URL             |
| location.host     | 返回主机（域名）www.itheima.com  |
| location.port     | 返回端口号，如果未写返回空字符串 |
| location.search   | 返回参数                         |
| location.partname | 返回路径                         |
| location.hash     | 返回片段#后面内容常见于链接锚点  |

重点记住：href 和 search

**案例：5秒钟之后自动跳转页面**

案例分析：

（1）利用定时器做倒计时效果

（2）时间到了，就跳转页面。使用 location.href

```html
<button>点击</button>
<div></div>
<script>
    var btn = document.querySelector('button');
    var div = document.querySelector('div');
    btn.addEventListener('click',function(){
        location.href = 'http://www.itcast.cn';
    })
    var timer = 5;
    setInterval(function(){
        if(timer == 0){
            location.href = 'http://www.itcast.cn';
        }
        else{
            div.innerHTML = '您将在' + timer + '秒钟之后跳转到首页';
            timer--;
        }
    },1000);
</script>
```

**案例：获得 URL 参数**

案例分析：

（1）第一个登录页面，里面有提交表单，action 提交到 index.html 页面

（2）第二个页面，可以使用第一个页面的参数，这样实现了一个数据不同页面之间的传递效果

（3）第二个页面之所以可以使用第一个页面的数据，是利用了 URL 里面的 location.search 参数

（4）在第二个页面中，需要把这个参数提取

（5）第一步去掉？利用 substr

（6）第二步利用 = 号分割键和值 split('=')

```html
<!--login.html-->
<form action="index.html">
    用户名：<input type="text" name="uname">
    <input type="sumbit" value="登录">
</form>
<!--index.html-->
<div></div>
<script>
    console.log(location.search);//?uname = andy
    //1、先去掉？ substr('起始的位置',截取几个字符);
    var params = location.search.substr(1);//uname = andy
    coonsole.log(params);
    //2、利用 = 字符串分割为数组 split('=');
    var arr = params.spilt('=');
    console.log(arr);//["uname","ANDY"]
    var div = document.querySelector('div');
    //3、把数据写入 div 中
    div.innerHTML = arr[1] + '欢迎您';
</script>
```

**location 对象的方法**

| location 对象方法  | 返回值                                                       |
| ------------------ | ------------------------------------------------------------ |
| location.assgin()  | 跟 href 一样，可以跳转页面（也称为重定向页面）               |
| location.replace() | 替换当前页面，因为不记录历史，所以不能后退页面               |
| location.reload()  | 重新加载页面，相当于刷新按钮或者 f5 如果参数为 true 强制刷新 ctrl + f5 |

```html
<button>点击</button>
<script>
    var btn = document.querySelector('button');
    btn.addEventListener('click',function(){
        //记录浏览历史，所以可以实现后退功能
        //location.assign('http://www.itcast.cn')
        //不记录浏览历史，所以不可以实现后退功能
        location.replace('http://www.itcast.cn');
        location.reload();
    })
</script>
```



### navigator 对象

navigator 对象包含有关浏览器的信息，它有很多属性，我们最常用的是 userAgent，该属性可以返回有客户及发送服务器的 user-agent 头部的值。

下面前端代码可以判断用户那个终端打开页面，实现跳转。

```javascript
if((navigator.userAgent.match(/(phone|pad|pod|iPhone|iPod|ios|iPad|Android|Mobile|BlackBerry|IEMobile|MQQBowser|JUC|Fennec|wOSBrowser|BrowserNG|WebOS|Symbian|Windows Phone)/i))){
    window.location.href = "";//手机
}
else{
    window.location.href = "";//电脑
}
```



### history 对象

window 对象给我们提供了一个 history 对象，与浏览器历史记录进行交互。该对象包含用户（在浏览器窗口中）访问过的 URL。

| history 对象 | 作用                                                        |
| ------------ | ----------------------------------------------------------- |
| back()       | 可以后退功能                                                |
| forward()    | 前进功能                                                    |
| go(参数)     | 前进后退功能，参数如果是1，前进1个页面，如果是-1后退1个页面 |

history 对象一般在实际开发中比较少用，但是会在一些 OA 办公系统中见到。

```html
<a href="index.html">点击我去网上首页</a>
<button>后退</button>
<script>
    var btn = document.querySelector('button');
    btn.addEventListener('click',function(){
        //history.back();
        history.go(-1);
    })
</script>
```



## PC 端网页特效



### 元素偏移量 offset 系列

**offset 概述**

offset 翻译过来就是偏移量，我们使用 offset 系列相关属性可以动态的得到该元素的位置（偏移）、大小等。

（1）或的元素距离带有定位父元素的位置

（2）获得元素自身的大小（宽度高度）

（3）注意：返回的数值都不带单位

offset 系列常用属性：

| offset 系列属性      | 作用                                                         |
| -------------------- | ------------------------------------------------------------ |
| element.offsetParent | 返回作为该元素带有定位的父级元素，如果父级元素都没有定位则返回 body |
| element.offsetTop    | 返回元素相对有定位父元素上方的偏移                           |
| element.offsetLeft   | 返回元素相对有定位父元素左边框的偏移                         |
| element.offsetWidth  | 返回自身包括 padding，边框、内容区的宽度，返回数值不带单位   |
| element.offsetHeight | 返回自身包括 padding，边框、内容区的高度，返回数值不带单位   |

```html
<div class="father">
    <div class="son"></div>
</div>
<script>
    //offset系列
    var father = document.querySelector('.father');
    var son = document.querySelector('.son');
    //可以得到元素的偏移，位置，返回的不带单位的数值
    console.log(father.offsetTop);
    console.log(father.offsetLeft);
    //它以带有定位的父亲为准，如果么有父亲或者父亲没有定位，则以 body 为准
    console.log(son.offsetLeft);
    //可以得到元素的大小、宽度和高度是包括padding + border +width
    var w.document.querySelector('.w');
    console.log(w.offsetWidth);
    console.log(w.offsetHeight);
    //返回带有定位的父亲，否则返回的是 body
    console.log(son.offsetParent);//返回带有定位的父亲，否则返回的是 body
    console.log(son.parentNode);// 返回父亲是最近一级的父亲，亲爸爸，不管父亲有没有定位
</script>
```

![image-20211105164708597](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211105164708597.png)

**案例：获取鼠标在盒子内的位置**

案例分析：

（1）我们在盒子内点击，想要得到鼠标距离盒子左右的距离

（2）首先得到鼠标在页面中的坐标（e.pageX,e.pageY）

（3）其次得到盒子在页面中的距离（box.offsetLeft,box.offsetTop）

（4）用鼠标距离页面的坐标减去盒子在页面中的距离，得到鼠标在盒子内的坐标

（5）如果想要移动一下鼠标，就要获取最新的坐标，使用鼠标移动事件 mousemove

```html
<div class="box"></div>
<script>
    var box = document.querySelector('.box');
    box.addEventListener('mousemove',function(e){
        var x = e.pageX - this.offsetLeft;
        var y = e.pageY - this.offsetTop;
        this.innerHTML = 'x的坐标是' + x + 'y的坐标是' + y;
    })
</script>
```

**案例：模态框拖拽**

弹出框，我们也称为模态框。

案例分析：

（1）点击弹出层，会弹出模态框，并且显示灰色半透明的遮挡层。

（2）点击关闭按钮，可以关闭模态框，并且同时关闭灰色半透明遮挡层。

（3）鼠标放到模态框最上面一行。可以按住鼠标拖拽模态框在页面中移动。

（4）鼠标松开，可以停止拖动模态框移动。

（5）触发事件是鼠标按下 mousedown，鼠标移动 mousemove 鼠标松开 mouseup

（6）拖拽过程，鼠标移动过程中，获得最新的值赋值给模态框的 left 和 top 值，这样模态框可以跟着鼠标走了

（7）鼠标按下触发的事件源是最上面一行，就是 id 为 title

（8）鼠标的坐标减去鼠标在盒子内的坐标，才是模态框真正的位置

（9）鼠标按下，我们要得到鼠标在盒子的坐标

（10）鼠标移动，就让模态框的坐标设置为：鼠标坐标减去盒子坐标即可，注意移动事件写到按下事件里面

（11）鼠标松开，就停止拖拽，就是可以让鼠标移动事件解除

```javascript
var login = document.querySelector('.login');
var mask = document.querySelector('.login-bg');
var link = document.querySelector('#link');
var choseBtn = document.querySelector('.#choseBtn');
//点击弹出层这个链接 link，让 mask 和 login 显示出来
link.addEventListener('click',function(){
    mask.style.display = 'block';
    login.style.display = 'block';
})
//点击 closeBtn 就隐藏 mask 和 login
closeBtn.addEventListener('click',function(){
    mask.style.display = 'none';
    login.style.display = 'none';
})
//开始拖拽
//(1)当我们鼠标按下，就获得鼠标在盒子内的坐标
title.addEventListener('mousedown',function(e){
    var x = e.pageX - login.offsetLeft;
    var y = e.pageY - login.offsetTop;
    //(2)鼠标移动的时候，把鼠标在页面中的坐标，减去鼠标在盒子内的坐标就是模态框的 left 和 top 值
    document.addEventListener('mousemove',move)
        function move(e){
            login.style.left = e.pageX - x + 'px';
            login.style.top = e.pageY - y + 'px';
    }
    //(3)鼠标弹起，就让鼠标移动事件移除
    document.addEventListener('mouseup',function(){
        document.removeEventListener('mousemove',move);
    })
})
```

**案例：仿京东放大镜效果**

（整体）案例分析：

1、整个案例可以分为三个功能模块。

2、鼠标经过小图片盒子，黄色的遮挡层和大图片盒子显示，离开隐藏2个盒子功能。

（1）鼠标经过小图片盒子，黄色的遮挡层和大图片盒子显示，离开隐藏2个盒子功能。

（2）就是显示与隐藏。

3、黄色的遮挡层跟随鼠标功能。

（1）黄色的遮挡层跟随鼠标功能。

（2）把鼠标坐标给遮挡层不合适，因为遮挡层坐标以父盒子为准。

（3）首先是获得鼠标在盒子的坐标。

（4）之后把数值给遮挡层作为 left 和 top 值

（5）此时用到鼠标移动事件，但是还是在小图片盒子内移动。

（6）发现，遮挡层位置不对，需要再减去盒子自身高度和宽度的一半。

（7）遮挡层不能超出小图片盒子范围。

（8）如果小于零，就打坐标设置为0。

4、移动黄色遮挡层，大图片跟随移动功能。

（1）移动黄色遮挡层，大图片跟随移动功能。

（2）求大图片的移动距离公式。

![image-20211105214341836](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211105214341836.png)

```html
<style>
    .small-box {
        position: relative;
        width: 400px;
        height: 400px;
        float: left;
    }

    .small-box img {
        width: 400px;
        height: 400px;
    }

    .big-box {
        position: relative;
        width: 500px;
        height: 500px;
        float: left;
        display: none;
        overflow: hidden;
    }

    .big-box .bigImg {
        position: absolute;
        top: 0;
        left: 0;
        width: 800px;
        height: 800px;
    }

    .glass {
        position: absolute;
        top: 0;
        left: 0;
        width: 300px;
        height: 300px;
        background-color: yellow;
        opacity: 0.5;
        display: none;
    }
</style>

<body>
    <div class="small-box">
        <img src="imgs/02.jpg">
        <span class="glass"></span>
    </div>
    <div class="big-box">
        <img src="imgs/02.jpg" class="bigImg">
    </div>
    <script>
        window.addEventListener('load', function () {
            var small_box = document.querySelector('.small-box');
            var glass = document.querySelector('.glass');
            var big_box = document.querySelector('.big-box');
            //1、当我们鼠标经过 small_box 就显示和隐藏 glass 遮挡层 和 big_box 大盒子
            small_box.addEventListener('mouseover', function () {
                glass.style.display = 'block';
                big_box.style.display = 'block';
            })
            small_box.addEventListener('mouseout', function () {
                glass.style.display = 'none';
                big_box.style.display = 'none';
            })
            //2、鼠标移动的时候，让黄色的盒子跟着鼠标来走
            small_box.addEventListener('mousemove', function (e) {
                //(1)先计算出鼠标在盒子内的坐标
                var x = e.pageX - this.offsetLeft;
                var y = e.pageY - this.offsetTop;
                //(2)减去盒子的高度 300的一半是150 就是我们 glass 的最终 left 和 top 值
                //(3)我们 glass 移动的距离
                var glassX = x - glass.offsetWidth / 2
                var glassY = y - glass.offsetHeight / 2
                //(4)如果 x 坐标小于0就让它停在0的位置
                glassMax = small_box.offsetWidth - glass.offsetWidth;
                if (glassX <= 0) {
                    glassX = 0;
                } else if (glassX >= glassMax) {
                    glassX = glassMax;
                }
                if (glassY <= 0) {
                    glassY = 0;
                } else if (glassY >= glassMax) {
                    glassY = glassMax;
                }
                glass.style.left = glassX + 'px';
                glass.style.top = glassY + 'px';
                //3、大图片的移动距离 = 遮挡层移动距离*大图片最大移动距离/遮挡层的最大移动距离
                //大图
                var bigIMg = document.querySelector('.bigImg');
                //大图片最大移动距离
                var bigMax = bigIMg.offsetWidth - big_box.offsetWidth;
                //大图片的移动距离 X Y
                var bigX = glassX * bigMax / glassMax;
                var bigY = glassY * bigMax / glassMax;
                bigIMg.style.left = -bigX + 'px';
                bigIMg.style.top = -bigY + 'px';
            })
        })
    </script>
</body>
```



### 元素可视区 client 系列

client 翻译过来就是客户端，我们使用 client 系列的相关属性来获得元素可视区的相关信息。通过 client 系列的相关属性可以动态的得到该元素的边框大小、元素大小等。

| client 系列属性      | 作用                                                         |
| -------------------- | ------------------------------------------------------------ |
| element.clientTop    | 返回元素上边框的大小                                         |
| element.clientLeft   | 返回元素左边框的大小                                         |
| element.clientWidth  | 返回自身包括 padding、内容区的宽度，不含边框，返回数值不带单位 |
| element.clientHeight | 返回自身包括 padding、内容区的高度，不含边框，返回数值不带单位 |

```html
<div></div>
<script>
    var div = document.querySelector('div');
    console.log(div.clientWidth);
</script>
```

![image-20211105215148100](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211105215148100.png)



**立即执行函数写法**

立即执行函数 (function(){})(); 或者 (function(){}());

主要作用：创建一个独立的作用域。避免了命名冲突问题。

```javascript
//1、立即执行函数：不需要调用，立马能够自己执行的函数
function fn(){
    console.log(1);
}
fn();
//2、写法，也可以传递参数进来
//(function(){})(); 或者 (function(){}());
(function(a,b){
    console.log(a + b);
}(2,3));
```

**案例：淘宝 flexible.js 源码分析**

```javascript
(function flexible(window,document){
    //获取的 html 的根元素
    var dprEl =document.documentElement;
    //dpr 物理像素化
    var dpr = window.devicePixelRatio || 1;
    //adjust body font size 设置我们 body 的字体大小
    function setBodyFontSize(){
        if(document.body){
            document.body.style.fontSize = (12 * dpr) + 'px';
        }
        else{
            document.addEventListener('DOMContentLoaded',setBodyFontSize);
        }
    }
    setBodyFontSize();
    //set 1rem = viewWidth / 10
    function setRemUnit(){
        var rem = docEl.clientWidth / 10;
        docEl.style.fontSize = rem + 'px';
    }
    setRemUnit();
    // reset rem unit on page resize 当我们页面尺寸大小发生变化的时候，要重新设置下 rem 的大小
    window.addEventListener('resize',setRemUnit);
    //pageshow 是我们重新加载页面触发的事件
    window.addEventListener('pageshow',function(e){
        //e.persisted 返回的是 true 就是说如果这个页面是从缓存取过来的页面，也需要从新计算一下 rem 的大小
        if(e.persisted){
            setRemUnit();
        }
    })
    //detect 0.5px supports 有些移动端的浏览器不支持0.5像素的写法
    if(dpr >= 2){
        var fakeBody = document.createElement('body');
        var testElement = document.createElement('div');
        testElement.style.border = '5px solid transparent';
        fakeBody.appendChild(testElement);
        docEl.appendChild(fakeBody);
        if(testElement.offsetHeight ===1){
            docEl.classList.add('hairlines');
        }
        docEl.removeChild(fakeBody);
    }
}(window,document))
```

![image-20211105220429772](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211105220429772.png)



### 元素 scroll 系列属性

scroll 翻译过来是滚动的，我们使用 scroll 系列的相关属性可以动态的得到该元素的大小、滚动距离等。

| scroll 系列属性      | 作用                                               |
| -------------------- | -------------------------------------------------- |
| element.scrollTop    | 返回被卷曲的上侧距离，返回数值不带单位             |
| element.scrollLeft   | 返回被卷曲的左侧距离，返回数值不带单位             |
| element.scrollWidth  | 返回自身实际的宽度，不含边框，返回的数值都不带单位 |
| element.scrollHeight | 返回自身实际的高度，不含边框，返回的数值都不带单位 |

```html
<style>
    div{
        width:200px;
        height:200px;
        background-color:pink;
        border:10px solid red;
        padding:10px;
    }
</style>
<div>我是内容我是内容我是内容我是内容我是内容我是内容我是内容我是内容</div>
<script>
    var div = document.querySelector('div');
    console.log(div.scrollHeight);
    console.log(clientHeight);
    //scroll 滚动事件当我们滚动条发生变化会触发的事件
    div.addEventListener('scroll',function(){
        console.log(div.scrollTop);
    })
</script>
```

![image-20211105222245224](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211105222245224.png)



**案例：仿淘宝固定右侧侧边栏**

1、原先侧边栏是绝对定位

2、当页面滚动到一定位置，侧边栏改为固定定位

3、页面继续滚动，会让返回顶部显示出来

![image-20211105222628794](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211105222628794.png)

案例分析：

（1）需要用到页面滚动事件 scroll 因为是页面滚动，所以事件源是 document

（2）滚动到某个位置，就是判断页面被卷去的上部值

（3）页面被卷去的头部：可以通过 window.pageYOffset 获得，如果是被卷去的左侧 window.pageXOffset

（4）注意，元素被卷去的头部是 element.scrollTop，如果是页面被卷去的头部则是 window.pageYOffset

```html
<style>
    .slider-bar{
        position:absolute;
        left:50%;
        top:300px;
        margin-left:600px;
        width:45px;
        height:130px;
        background-color:pink;
    }
    .w{
        width:1200px;
        margin:10px auto;
    }
    .header{
        height:150px;
        background-color:purple;
    }
    .banner{
        height:250px;
        background-color:skyblue;
    }
    .main{
        height:1000px;
        background-color:yellowgreen;
    }
    span{
        display:none;
        position:absolute;
        bottom:0;
    }
</style>
<div class="slider-bar">
    <span class="goback">返回顶部</span>
</div>
<div class="header w">头部区域</div>
<div class="banner w">banner区域</div>
<div class="main w">主体部分</div>
<script>
    //获取元素
    var sliderbar = document.querySelector('.slider-bar');
    var banner = document.querySelector('.banner');
    //banner.offsetTop 就是被卷去头部的大小，一定要写到滚动到外面
    var bannerTop = banner.offsetTop;
    //当我们侧边栏固定定位之后应该变化的数值
    var sliderbarTop = sliderbar.offsetTop - bannerTop;
    // 获取 main 主体元素
    var main = document.querySelector('.main');
    var goBack = document.querySelector('goBack');
    var mainTop = main.offsetTop;
    //页面滚动事件 scroll
    document.addEventListener('scroll',function(){
        //console.log(11);
        //window.pageYOffset 页面被卷去的头部
        //console.log(window.pageYOffset);
        //当我们页面被卷去的头部大于等于了172 (即bannerTop) 此时，侧边栏就要改为固定定位
        if(window.pageYOffset >= bannerTop){
            sliderbar.style.position = 'fixed';
            sliderbar.style.top = sliderTop + 'px';
        }
        else{
            sliderbar.style.position = 'absolute';
            sliderbar.style.top = '300px';
        }
        //当我们页面滚动到 main 盒子，就显示 goback 模块
        if(window.pageYOffset >= mainTop){
            goBack.style.display = 'block';
        }
        else{
            goBack.style.display = 'none';
        }
    })
</script>
```

**页面被卷去的头部兼容性解决方案**

需要注意的是，页面被卷去的头部，有兼容性问题，因此被卷去的头部通常有如下几种写法：

1、声明DTD，使用 document.documentElement.scrollTop

2、未声明DTD，使用 document.body.scrollTop

3、新方法 window.pageYOffset 和 window.pageXOffset，IE9开始支持

```javascript
function getScroll(){
    return{
        left:window.pageXOffset || documentElement.scrollLeft || document.body.scrollLeft || 0,top:window.pageYOffset || documentElement.scrollTop || document.body.scrollTop || 0
    };
}
//使用的时候 getScroll().left
```



### 三大系列大小对比

![image-20211105230557197](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211105230557197.png)

他们主要用法：

1、offset 系列经常用于获得元素位置 offsetLeft，offsetTop

2、client 经常用于获取元素大小 clientWidth，clientHeight

3、scroll 经常用于获取滚动距离 scrollTop，scrollLeft

4、注意页面滚动的距离通过 window.pageXOffset 获得



### mouseenter 鼠标事件

当鼠标移动到元素上时就会触发 mouseenter 事件

类似 mouseenter，他们两者之间的差别是

mouseover鼠标经过自身盒子会触发，经过子盒子还会触发。mouseenter只会经过自身盒子触发

之所以这样，就是因为 mouseenter 不会冒泡

跟 mouseenter 搭配鼠标离开 mouseleave 同样不会冒泡

```html
<div class="father">
    <div class="son"></div>
</div>
<script>
    var father = document.querySelector('.father');
    var son = document.querySelector('.son');
    //father.addEventListener('mouseover',function(){
    //    console.log(11);
    //})
    father.addEventListener('mouseenter',function(){
        console.log(11);
    })
</script>
```



### 动画实现原理

核心原理：通过定时器 setInterval() 不断移动盒子位置。

实现步骤：

1、获得盒子当前位置

2、让盒子在当前位置加上1个移动距离

3、利用定时器不断重复这个操作

4、加一个结束定时器的条件

5、注意此元素需要添加定位，才能使用 element.style.left

```html
<style>
    div{
        position:absolute;
        left:0;
        width:100px;
        height:100px;
        background-color:pink;
    }
</style>
<div></div>
<script>
    //动画原理
    var div = document.querySelector('div');
    var timer = setInterval(function(){
        if(div.offsetLeft >= 400){
            //停止动画，本质是停止定时器
            clearInterval(timer);
        }
        div.style.left = div.offsetLeft + 1 +'px';
    },30);
</script>
```

**简单动画函数封装**

```javascript
//简单动画函数封装 obj 目标对象 target 目标位置
function animate(obj,target){
    var timer = setInterval(function(){
        if(obj.offsetLeft >= target){
            //停止动画，本质是停止定时器
            clearInterval(timer);
        }
        obj.style.left = obj.offsetLeft + 1 + 'px';
    },30);
}
var div = document.querySelector('div');
//调用函数
animate(div,300);
```

```html
<style>
    div{
        position:absolute;
        left:0;
        width:100px;
        height:100px;
        background-color:pink;
    }
    span{
        position:absolute;
        left:0;
        top:200px;
        width:150px;
        height:150px;
        background-color:purple;
    }
</style>
<button>前进</button>
<button>后退</button>
<div></div>
<span></span>
<script>
//简单动画函数封装 obj 目标对象 target 目标位置
    //var obj = {};
    //obj.name = 'andy';
    //给不同的元素指定了不同的定时器
function animate(obj,target){
    //当我们不断的点击按钮，这个元素的速度会越来越快，因为开启了太多的定时器
    //解决方案就是让我们元素只有一个定时器执行
    //先清除以前的定时器，只保留当前的一个定时器执行
    clearInterval(obj.timer);
    obj.timer = setInterval(function(){
        if(obj.offsetLeft == target){
            //停止动画，本质是停止定时器
            clearInterval(obj.timer);
        }
        obj.style.left = obj.offsetLeft + 1 + 'px';
    },30);
}
var div = document.querySelector('div');
var span = document.querySelector('span');
var btn = document.querySelector('button');
//调用函数
animate(div,300);
btn.addEventListener('click',function(){
    animate(span,200);
})
</script>
```

**缓动效果原理**

缓动效果就是让元素运动速度有所变化，最常见的是让速度慢慢停下来。思路：

1、让盒子每次移动的距离慢慢变小，速度就会慢慢落下来。

2、核心算法：（目标值 - 现在的位置）/ 10 做为每次移动的距离步长

3、停止的条件是：让当前盒子位置等于目标位置就停止定时器

```html
<style>
    span{
        position:absolute;
        left:0;
        top:200px;
        width:150px;
        height:150px;
        background-color:purple;
    }
</style>
<button class="advance">前进</button>
<button class="retreat">后退</button>
<span></span>
<script>
function animate(obj,target){
    //先清除以前的定时器，只保留当前一个定时器执行
    clearInterval(obj.timer);
    obj.timer = setInterval(function(){
        //步长值写到定时器的里面
        //var step = (target - obj.offsetLeft) / 10;
        //把我们步长值改为整数，不要出现小数的问题
        //var step = Math.ceil((target - obj.offsetLeft) / 10);
        var step = (target - obj.offsetLeft) / 10;
        step = step > 0 ? Math.ceil(step) : Math.floor(step);
        if(obj.offsetLeft == target){                       //(我倒退出错的重点问题)
            //停止动画，本质是停止定时器
            clearInterval(obj.timer);
        }
        //把每次加1，这个步长值改为一个慢慢变小的值，步长公式：(目标值 - 现在的位置) / 10
        obj.style.left= obj.offsetLeft + step + 'px';
    },15);
}
    //匀速动画就是盒子是当前的位置 + 固定的值 10
    //缓动动画就是盒子当前的位置 + 变化的值(目标值 - 现在的位置) / 10
    var btn500 = document.querySelector('.advance');
    var btn800 = document.querySelector('.retreat');
    var span = document.querySelector('span');
    btn500.addEventListener('click',function(){
    animate(span,500);
    })
    btn800.addEventListener('click',function(){
    animate(span,500);
        span.style.background = 'red';
    })
</script>
```

![image-20211106001619610](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211106001619610.png)

**完善缺点：**

1、步长取整；2、条件：obj.offsetLeft == target，才能倒退顺畅。**(我练习倒退出错的重点问题)**

```javascript
//把我们步长值改为整数，不要出现小数的问题
//var step = Math.ceil((target - obj.offsetLeft) / 10);
var step = (target - obj.offsetLeft) / 10;
step = step > 0 ? Math.ceil(step) : Math.floor(step);
```

**动画函数添加回调函数**

回调函数原理：函数可以作为一个参数。将这个函数作为参数传到另一个函数里面，当那个函数执行完之后，再执行传进去的这个函数，这个过程就叫做回调。

**回调函数写的位置：定时器结束的位置。**

```javascript
function animate(obj,target,callback){
    //console.log(callback);callback = function(){} 调用的时候 callback()
    //先清除以前的定时器，只保留当前一个定时器执行
    clearInterval(obj.timer);
    obj.timer = setInterval(function(){
        //步长值写到定时器的里面
        //var step = (target - obj.offsetLeft) / 10;
        //把我们步长值改为整数，不要出现小数的问题
        //var step = Math.ceil((target - obj.offsetLeft) / 10);
        var step = (target - obj.offsetLeft) / 10;
        step = step > 0 ? Math.ceil(step) : Math.floor(step);
        if(obj.offsetLeft == target){                       //(我倒退出错的重点问题)
            //停止动画，本质是停止定时器
            clearInterval(obj.timer);
            //回调函数写到定时器结束里面
            //if(callback){
            //    callback();
            //}
            callback && callback();
        }
        //把每次加1，这个步长值改为一个慢慢变小的值，步长公式：(目标值 - 现在的位置) / 10
        obj.style.left= obj.offsetLeft + step + 'px';
    },15);
}
    //匀速动画就是盒子是当前的位置 + 固定的值 10
    //缓动动画就是盒子当前的位置 + 变化的值(目标值 - 现在的位置) / 10
    var btn500 = document.querySelector('.advance');
    var btn800 = document.querySelector('.retreat');
    var span = document.querySelector('span');
    btn500.addEventListener('click',function(){
    animate(span,500);
    })
    btn800.addEventListener('click',function(){
    animate(span,500,function(){
        span.style.background = 'red';
    });
    })
```

**引用动画函数**

```html
<style>
        .sliderbar {
            width: 50px;
            height: 50px;
            position: relative;
            left: 85%;
            top: 300px;
            background-color: brown;
            /* overflow: hidden; */
        }

        .con {
            width: 200px;
            height: 50px;
            position: absolute;
            left: 0;
            top: 0;
            background-color: pink;
            overflow: hidden;
            line-height: 50px;
            z-index: -1;
            text-align: center;
        }

        span {
            display: block;
            text-align: center;
            width: 50px;
            height: 50px;
            line-height: 50px;
        }
    </style>
<div class="sliderbar">
    <span>☚☛</span>
    <div class="con">问题反馈</div>
</div>
<script>
    var sliderbar = document.querySelector('.sliderbar');
    var con = document.querySelector('.con');
    //当我们鼠标经过 sliderbar 就会让 con 这个盒子滑动到左侧
    //当我们鼠标离开 sliderbar 就会让 con 这个盒子滑动到右侧
    sliderbar.addEventListener('mouseover',function(){
        animate(obj,target,callback);
        animate(con,-160,function(){
            //当我们动画执行完毕，就把 ☚ 改为 ☛
            sliderbar.children[0].innerHTML = '☛';
        });
    })
    sliderbar.addEventListener('mouseleave',function(){
        animate(obj,target,callback);
        animate(con,0,function(){
            sliderbar.children[0].innerHTML = '☚';
        })
    })
</script>
```



### 案例：网页轮播图

轮播图也称焦点图，是网页中比较常见的网页特效。

功能需求：

1、鼠标经过轮播图模块，左右按钮显示，离开隐藏左右按钮。

2、点击右侧按钮一次，图片往左播放一张，以此类推，左侧按钮同理。

3、图片播放的同时，下面小圆圈模块跟随一起变化。

4、点击小圆圈，可以播放相应图片。

5、鼠标不经过轮播图，轮播图也会自动播放图片。

6、鼠标经过，轮播图模块，自动播放停止。

案例分析：

（1）此时需要添加 load 事件。

（2）鼠标经过轮播图模块，左右按钮显示，离开隐藏左右按钮。

（3）显示隐藏 display 按钮。

```javascript
window.addEventListener('load',function(){
    //1、获取元素
    var arrow_l = document.querySelector('.arrow-l');
    var arrow_r = document.querySelector('.arrow-r');
    var focus = document.querySelector('.focus');
    //2、鼠标经过 focus 就显示隐藏左右按钮
    focus.addEventListener('mouseenter',function(){
        arrow_l.style.display = 'block';
        arrow_r.style.display = 'block';
    })
    focus.addEventListener('mouseleave',function(){
        arrow_l.style.display = 'none';
        arrow_r.style.display = 'none';
    })
})
```

案例分析：

（1）动态生成小圆圈

（2）核心思路：小圆圈的个数要跟图片张数一致

（3）所以首先先得到 ul 里面图片的张数（图片放入 li 里面，所以就是 li 得个数）

（4）利用循环动态生成小圆圈（这个小圆圈要放入 ol 里面）

（5）创建节点 createElement('li');

（6）插入节点 ol。appendChild('li');

（7）第一个小圆圈需要添加 current 类（小圆圈的排他思想）

（8）其余的小圆圈就移除这个 current 类

（9）注意：我们在刚才生成小圆圈的同时，就可以直接绑定这个点击事件了。

```javascript
//3、动态生成小圆圈，有几张图片，我就生成几个小圆圈
var ul = focus.querySelector('ul');
var ol = focus.querySelector('.circle');
//console.log(ul.children.length);
for(var i = 0; i < ul.children.length; i++){
    //创建一个小 li
    var li = document.createElement('li');
    //把小 li 插入到 ol 里面
    ol.appendChild(li);
    //4、小圆圈的排他思想，我们可以直接在生成小圆圈的同事直接绑定点击事件
    li.addEventListener('click',function(){
        //干掉所有人，把所有的小 li 清除 current 类名
        for(var i = 0; i < ol.children.length; i++){
            ol.children[i].className = '';
            //留下自己，当前的小 li 设置 current 类名
            this.className = 'current';
        }
    })
}
把 ol 里面的第一个小 li 设置类名为 current
ol.children[0].className = 'current';
```

案例分析：

（1）点击小圆圈滚动图片

（2）此时使用到 animate 动画函数，将 js 文件引入（注意，因为 index.js 依赖 animate.js，所以，animate.js 要写到 index.js 上面）

（3）使用动画函数的前提，该元素必须有定位

（4）注意是 ul 移动，而不是小 li

（5）滚动图片的核心算法：点击某个小圆圈，就让图片滚动，小圆圈的索引号乘以图片的宽度作为 ul 移动的距离

```javascript
//3、动态生成小圆圈，有几张图片，我就生成几个小圆圈
var ul = focus.querySelector('ul');
var ol = focus.querySelector('.circle');
//console.log(ul.children.length);
for(var i = 0; i < ul.children.length; i++){
    //创建一个小 li
    var li = document.createElement('li');
    //记录当前小圆圈的索引号，通过自定义属性来做
    li.setAttribute('index',i);
    //把小 li 插入到 ol 里面
    ol.appendChild(li);
    //4、小圆圈的排他思想，我们可以直接在生成小圆圈的同事直接绑定点击事件
    li.addEventListener('click',function(){
        //干掉所有人，把所有的小 li 清除 current 类名
        for(var i = 0; i < ol.children.length; i++){
            ol.children[i].className = '';
            //留下自己，当前的小 li 设置 current 类名
            this.className = 'current';
            //5、点击，注意是 ul 移动，而不是小 li
            //小圆圈的索引号乘以图片的宽度作为 ul 移动的距离 注意是负值
            //要拿到当前小 li 小圆圈的索引号
            var index = this.getAttribute('index');
            var focusWidth = focus.offsetWidth;
            console.log(focusWidth);
            console.log(index);
            animate(ul,-index * focusWidth);
        }
    })
    ol.children[0].className = 'current';
}
```

案例分析：

（1）点击右侧按钮一次，就让图片滚动一张。

（2）声明一个变量 num，点击一次，自增1，让这个变量乘以图片宽度，就是 ul 的滚动距离。

（3）图片无缝滚动原理

（4）把 ul 第一个 li 复制一份，放到 ul 的最后面

（5）当图片滚动到克隆的最后一张图片时，让 ul 快速的、不做动画的跳到最左侧：left 为 0

（6）同时 num 赋值为 0，可以从新开始滚动图片了

```javascript
//6、点击右侧按钮一次，图片滚动一张
var num = 0;
arrow_r.addEventListener('click',function(){
    //如果走到了最后复制的一张图片，此时，我们的 ul 要快速复原 left 改为 0
    if(num == ul.children.length - 1){
        ul.style.left = 0;
        num = 0;
    }
    num++;
    animate(ul,-num * focusWidth);
});
```

案例分析：

（1）克隆第一张图片

（2）克隆 ul 第一个 li choneNode() 加 true 深克隆复制里面的子节点 false 浅克隆

（3）添加到 ul 最后面 appendChild

```javascript
//6、克隆第一张图片(li)放到 ul 最后面
var first = ul.children[0].choneNode(true);
ul.appendChild(first);
//7、点击右侧按钮一次，图片滚动一张
var num = 0;
arrow_r.addEventListener('click',function(){
    //如果走到了最后复制的一张图片，此时，我们的 ul 要快速复原 left 改为 0
    if(num == ul.children.length - 1){
        ul.style.left = 0;
        num = 0;
    }
    num++;
    animate(ul,-num * focusWidth);
});
```

案例分析：

（1）点击右侧按钮，小圆圈跟随变化

（2）最简单的做法是再声明一个变量 circle，每次点击自增1，注意，左侧按钮也需要这个变量，因此要声明全局变量

（3）但是图片有5张，我们小圆圈只有4个少一个，必须加一个判断条件

（4）如果 circle == 4 就从新复原为 0

```javascript
//3、动态生成小圆圈，有几张图片，我就生成几个小圆圈
var ul = focus.querySelector('ul');
var ol = focus.querySelector('.circle');
//console.log(ul.children.length);
for(var i = 0; i < ul.children.length; i++){
    //创建一个小 li
    var li = document.createElement('li');
    //记录当前小圆圈的索引号，通过自定义属性来做
    li.setAttribute('index',i);
    //把小 li 插入到 ol 里面
    ol.appendChild(li);
    //4、小圆圈的排他思想，我们可以直接在生成小圆圈的同事直接绑定点击事件
    li.addEventListener('click',function(){
        //干掉所有人，把所有的小 li 清除 current 类名
        for(var i = 0; i < ol.children.length; i++){
            ol.children[i].className = '';
            //留下自己，当前的小 li 设置 current 类名
            this.className = 'current';
            //5、点击，注意是 ul 移动，而不是小 li
            //小圆圈的索引号乘以图片的宽度作为 ul 移动的距离 注意是负值
            //要拿到当前小 li 小圆圈的索引号
            var index = this.getAttribute('index');
            //当我们点击了某个小 li 就要把这个 li 的索引号给 num
            num = index;
            //当我们点击了某个小 li 就要把这个 li 的索引号给 circle
            circle = index;
            var focusWidth = focus.offsetWidth;
            console.log(focusWidth);
            console.log(index);
            animate(ul,-index * focusWidth);
        }
    })
    ol.children[0].className = 'current';
}
//6、克隆第一张图片(li)放到 ul 最后面
var first = ul.children[0].choneNode(true);
ul.appendChild(first);
//7、点击右侧按钮一次，图片滚动一张
var num = 0;
arrow_r.addEventListener('click',function(){
    //如果走到了最后复制的一张图片，此时，我们的 ul 要快速复原 left 改为 0
    if(num == ul.children.length - 1){
        ul.style.left = 0;
        num = 0;
    }
    num++;
    animate(ul, -num * focusWidth);
    //8、点击右侧按钮，小圆圈跟随一起变化，可以再声明一个变量控制小圆圈的播放
    circle++;
    //如果 circle == 4，说明走到最后我们克隆的这张图片了，我们就复原
    if(circle == ol.children.length){
        circle = 0;
    }
    //先清除其余小圆圈的 current类名
    for(var i = 0; i < ol.children.length; i++){
        ol.children[i].className = '';
    }
    //留下当前的小圆圈的 current 类名
    ol.children[circle].className = 'current';
});
arrow_l.addEventListener('click',function(){
    //如果走到了最后复制的一张图片，此时，我们的 ul 要快速复原 left 改为 0
    if(num == 0){
        ul.style.left = -num * focusWidth + 'px';
        num = ul.children.length - 1;
    }
    num--;
    animate(ul, -num * focusWidth);
    //8、点击右侧按钮，小圆圈跟随一起变化，可以再声明一个变量控制小圆圈的播放
    circle--;
    //如果 circle < 0，说明第一张图片，则小圆圈要改为第4个小圆圈
    if(circle < 0){
        circle = ol.children.length - 1;
    }
    //先清除其余小圆圈的 current类名
    for(var i = 0; i < ol.children.length; i++){
        ol.children[i].className = '';
    }
    //留下当前的小圆圈的 current 类名
    ol.children[circle].className = 'current';
});
```

我们可以把小圆圈排他思想封装为一个函数

```javascript
function circleChange(){
    //先清除其余小圆圈的 current类名
    for(var i = 0; i < ol.children.length; i++){
        ol.children[i].className = '';
    }
    //留下当前的小圆圈的 current 类名
    ol.children[circle].className = 'current';
}
```

案例分析：

（1）自动播放功能

（2）添加一个定时器

（3）自动播放轮播图，实际就类似于点击了右侧按钮

（4）此时我们使用手动调用右侧按钮点击事件 arrow_r.click()

（5）鼠标经过 focus 就停止定时器

```javascript
window.addEventListener('load',function(){
    //1、获取元素
    var arrow_l = document.querySelector('.arrow-l');
    var arrow_r = document.querySelector('.arrow-r');
    var focus = document.querySelector('.focus');
    //2、鼠标经过 focus 就显示隐藏左右按钮
    focus.addEventListener('mouseenter',function(){
        arrow_l.style.display = 'block';
        arrow_r.style.display = 'block';
        clearInterval(timer);
        timer = null;//清除定时器变量
    });
    focus.addEventListener('mouseleave',function(){
        arrow_l.style.display = 'none';
        arrow_r.style.display = 'none';
        timer = setInterval(function(){
            //手动调用点击事件
            arrow_r.click();
        },2000);
    });
    //9、自动播放轮播图
    var timer = setInterval(function () {
    //手动调用点击事件
         arrow_r.click();
    }, 2000);
})
```

**完整轮播图代码**

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        .focus {
            width: 720px;
            height: 500px;
            margin: 100px auto;
            position: relative;
            background-color: brown;
            overflow: hidden;
        }

        .arrow-l,
        .arrow-r {
            display: none;
            position: absolute;
            top: 50%;
            margin-top: -20px;
            width: 24px;
            height: 40px;
            background: rgba(0, 0, 0, .3);
            text-align: center;
            line-height: 40px;
            color: #fff;
            font-family: 'icomoon';
            font-size: 18px;
            text-decoration: none;
        }

        .arrow-r {
            right: 0;
            z-index: 2;
        }

        .arrow-l {
            left: 0;
            z-index: 2;
        }

        .focus ul {
            width: 600%;
            position: absolute;
            left: 0;
            top: 0;
        }

        .focus ul li {
            float: left;
            list-style: none;
        }

        .focus ul li img {
            width: 720px;
            height: 500px;
        }

        .circle {
            position: absolute;
            bottom: 10px;
            left: 50px;
        }

        .circle li {
            float: left;
            width: 8px;
            height: 8px;
            border: 2px solid rgba(255, 255, 255, 0.5);
            margin: 0 3px;
            border-radius: 50%;
            cursor: pointer;
            list-style: none;
        }

        .current {
            background-color: #fff;
        }
    </style>
</head>

<body>
    <div class="focus">
        <!-- 左按钮 -->
        <a href="javascript:;" class="arrow-l">&lt;</a>
        <!-- 右按钮 -->
        <a href="javascript:;" class="arrow-r">&gt;</a>
        <!-- 核心滚动区域 -->
        <ul>
            <li><img src="imgs/01.jpg" alt=""></li>
            <li><img src="imgs/02.jpg" alt=""></li>
            <li><img src="imgs/03.jpg" alt=""></li>
            <li><img src="imgs/04.jpg" alt=""></li>
        </ul>
        <!-- 小圆圈 -->
        <ol class="circle">
        </ol>
    </div>
</body>

</html>
<script>
    function animate(obj, target, callback) {
        //console.log(callback);callback = function(){} 调用的时候 callback()
        //先清除以前的定时器，只保留当前一个定时器执行
        clearInterval(obj.timer);
        obj.timer = setInterval(function () {
            //步长值写到定时器的里面
            //var step = (target - obj.offsetLeft) / 10;
            //把我们步长值改为整数，不要出现小数的问题
            //var step = Math.ceil((target - obj.offsetLeft) / 10);
            var step = (target - obj.offsetLeft) / 10;
            step = step > 0 ? Math.ceil(step) : Math.floor(step);
            if (obj.offsetLeft == target) {                  //(我倒退出错的重点问题)
                //停止动画，本质是停止定时器
                clearInterval(obj.timer);
                //回调函数写到定时器结束里面
                if (callback) {
                    callback();
                }
                // callback || callback();
            }
            //把每次加1，这个步长值改为一个慢慢变小的值，步长公式：(目标值 - 现在的位置) / 10
            obj.style.left = obj.offsetLeft + step + 'px';
        }, 15);
    }
    window.addEventListener('load', function () {
        //1、获取元素
        var arrow_l = document.querySelector('.arrow-l');
        var arrow_r = document.querySelector('.arrow-r');
        var focus = document.querySelector('.focus');
        flag = true
        //2、鼠标经过 focus 就显示隐藏左右按钮
        focus.addEventListener('mouseenter', function () {
            arrow_l.style.display = 'block';
            arrow_r.style.display = 'block';
            clearInterval(timer);
            timer = null;//清除定时器变量
        });
        focus.addEventListener('mouseleave', function () {
            arrow_l.style.display = 'none';
            arrow_r.style.display = 'none';
            timer = setInterval(function () {
                //手动调用点击事件
                arrow_r.click();
            }, 2000);
        });
        //3、动态生成小圆圈，有几张图片，我就生成几个小圆圈
        var ul = focus.querySelector('ul');
        var ol = focus.querySelector('.circle');
        var focusWidth = focus.offsetWidth;
        var num = 0;
        var circle = 0;
        var flag = true;
        //console.log(ul.children.length);
        for (var i = 0; i < ul.children.length; i++) {
            //创建一个小 li
            var li = document.createElement('li');
            //记录当前小圆圈的索引号，通过自定义属性来做
            li.setAttribute('index', i);
            //把小 li 插入到 ol 里面
            ol.appendChild(li);
            //4、小圆圈的排他思想，我们可以直接在生成小圆圈的同事直接绑定点击事件
            li.addEventListener('click', function () {
                //干掉所有人，把所有的小 li 清除 current 类名
                for (var i = 0; i < ol.children.length; i++) {
                    ol.children[i].className = '';
                    //留下自己，当前的小 li 设置 current 类名
                    this.className = 'current';
                    //5、点击，注意是 ul 移动，而不是小 li
                    //小圆圈的索引号乘以图片的宽度作为 ul 移动的距离 注意是负值
                    //要拿到当前小 li 小圆圈的索引号
                    var index = this.getAttribute('index');
                    //当我们点击了某个小 li 就要把这个 li 的索引号给 num
                    num = index;
                    //当我们点击了某个小 li 就要把这个 li 的索引号给 circle
                    circle = index;
                    console.log(focusWidth);
                    console.log(index);
                    animate(ul, -index * focusWidth);
                }
            })
            ol.children[0].className = 'current';
        }
        //6、克隆第一张图片(li)放到 ul 最后面
        var first = ul.children[0].cloneNode(true);
        ul.appendChild(first);
        //7、点击右侧按钮一次，图片滚动一张
        var num = 0;
        arrow_r.addEventListener('click', function () {
          if(flag){
            flag = false;
            //如果走到了最后复制的一张图片，此时，我们的 ul 要快速复原 left 改为 0
            if (num == ul.children.length - 1) {
                ul.style.left = 0;
                num = 0;
            }
            num++;
            animate(ul, -num * focusWidth,function(){
                flag = true;
            });
            //8、点击右侧按钮，小圆圈跟随一起变化，可以再声明一个变量控制小圆圈的播放
            circle++;
            //如果 circle == 4，说明走到最后我们克隆的这张图片了，我们就复原
            if (circle == ol.children.length) {
                circle = 0;
            }
            //先清除其余小圆圈的 current类名
            for (var i = 0; i < ol.children.length; i++) {
                ol.children[i].className = '';
            }
            //留下当前的小圆圈的 current 类名
            ol.children[circle].className = 'current';
            }
        });
        arrow_l.addEventListener('click', function () {
          if(flag){
            flag = false;
            //如果走到了最后复制的一张图片，此时，我们的 ul 要快速复原 left 改为 0
            if (num == 0) {
                ul.style.left = -num * focusWidth + 'px';
                num = ul.children.length - 1;
            }
            num--;
            animate(ul, -num * focusWidth,function(){
                flag = true;
            });
            //8、点击右侧按钮，小圆圈跟随一起变化，可以再声明一个变量控制小圆圈的播放
            circle--;
            //如果 circle < 0，说明第一张图片，则小圆圈要改为第4个小圆圈
            if (circle < 0) {
                circle = ol.children.length - 1;
            }
            //先清除其余小圆圈的 current类名
            for (var i = 0; i < ol.children.length; i++) {
                ol.children[i].className = '';
            }
            //留下当前的小圆圈的 current 类名
            ol.children[circle].className = 'current';
        }
        });
        //9、自动播放轮播图
            var timer = setInterval(function () {
                //手动调用点击事件
                arrow_r.click();
            }, 2000);
    })
</script>
```



### 节流阀

防止轮播图按钮连续点击造成播放过快。

节流阀目的：当上一个函数动画内容执行完毕，再去执行下一个函数动画，让事件无法连续触发。

核心实现思路：利用回调函数，添加一个变量来控制，锁定函数和解锁函数。

开始设置一个变量 var flag = true;

if(flag){flag = false; do something} 关闭水龙头。

利用回调函数动画执行完毕，flag = true 打开水龙头。

```javascript
arrow_l.addEventListener('click', function () {
    if(flag){
            flag = false;
            //如果走到了最后复制的一张图片，此时，我们的 ul 要快速复原 left 改为 0
            if (num == 0) {
                ul.style.left = -num * focusWidth + 'px';
                num = ul.children.length - 1;
            }
            num--;
            animate(ul, -num * focusWidth,function(){
                flag = true;
            });
            //8、点击右侧按钮，小圆圈跟随一起变化，可以再声明一个变量控制小圆圈的播放
            circle--;
            //如果 circle < 0，说明第一张图片，则小圆圈要改为第4个小圆圈
            if (circle < 0) {
                circle = ol.children.length - 1;
            }
            //先清除其余小圆圈的 current类名
            for (var i = 0; i < ol.children.length; i++) {
                ol.children[i].className = '';
            }
            //留下当前的小圆圈的 current 类名
            ol.children[circle].className = 'current';
    }
});
```

**案例：返回顶部**

滚动窗口至文档中的特定位置。window.scroll(x,y)。

（1）带有动画的返回顶部

（2）此时可以继续使用我们封装的动画函数

（3）只需要把所有的 left 相关的值改为跟页面垂直滚动距离相关就可以了

（4）页面滚动了多少，可以通过 window.pageYOffset 得到

```javascript
//3、当我们点击了返回顶部模块，就让窗口滚动的页面的最上方
goBack.addEventListener('click',function(){
    //里面的x和y不跟单位的，直接写数字即可
    //window.scroll(0,0)
    //因为是窗口滚动，所以对象是 window
    animate（window,0,callback);
})
//动画函数
function animate(obj, target, callback) {
        //console.log(callback);callback = function(){} 调用的时候 callback()
        //先清除以前的定时器，只保留当前一个定时器执行
        clearInterval(obj.timer);
        obj.timer = setInterval(function () {
            //步长值写到定时器的里面
            //var step = (target - obj.offsetLeft) / 10;
            //把我们步长值改为整数，不要出现小数的问题
            //var step = Math.ceil((target - obj.offsetLeft) / 10);
            var step = (target - window.pageYOffset) / 10;
            step = step > 0 ? Math.ceil(step) : Math.floor(step);
            if (window.pageYOffset == target) {          //(我倒退出错的重点问题)
                //停止动画，本质是停止定时器
                clearInterval(obj.timer);
                //回调函数写到定时器结束里面
                if (callback) {
                    callback();
                }
                // callback || callback();
            }
            //把每次加1，这个步长值改为一个慢慢变小的值，步长公式：(目标值 - 现在的位置) / 10
            window.scroll(0, window.pageYOffset + step);
        }, 15);
    }
```

**案例：筋斗云案例**

1、鼠标经过某个小 li，筋斗云跟这到当前小 li 位置

2、鼠标离开这个小 li，筋斗云复原为原来的位置

3、鼠标点击了某个小 li，筋斗云就会留点点击这个小 li 的位置

案例分析：

（1）利用动画函数做动画效果

（2）原先筋斗云的起始位置是0

（3）鼠标经过某个小 li，把当前小 li 的 offsetLeft 位置做为目标值即可

（4）鼠标离开某个小 li，就把目标值设为0

```javascript
window.addEventListener('load',function(){
    //1、获取元素
    var cloud = document.querySelector('.cloud');
    var c_nav = document.querySelector('.c-nav');
    var lis = c_nav.querySelectorAll('li');
    //这个 current 做为筋斗云的起始位置
    var current = 0;
    //2、给所有的小 li 绑定事件
    for(var i = 0; i < lis.length; i++){
        //(1)鼠标经过把当前小 li 的位置做为目标值
        lis[i].addEventListener('mouseenter',function(){
            animate(cloud,this.offsetLeft);
        })
        //(2)鼠标离开就复原为0
        lis[i].addEventListener('mouseLeave',function(){
            animate(cloud,0);
        })
        //(3)当我们鼠标点击，就把当前位置做为目标值
        lis[i].addEventListener('click',function(){
            current = this.offsetLeft;
        })
    }
})
```



## 本地存储



### 本地存储

随着互联网的快速发展，基于网页的应用越来越普遍，同时也变得越来越复杂，为了满足各种各样的需求，会经常性在本地存储大量的数据，HTML5 规范提出了相关解决方案。

**本地存储特性**

1、数据存储在用户浏览器中

2、设置、读取方便、甚至页面刷新不丢失数据

3、容量较大，sessionStorage 约5M、localStorage 约20M

4、只能存储字符串，可以将对象 JSON.stringify() 编码后存储

![image-20211117130835670](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117130835670.png)



### window.sessionStorage

1、生命周期为关闭浏览器窗口

2、在同一个窗口（页面）下数据可以共享

3、以键值对的形式存储使用

**存储数据：**

```javascript
sessionStorage.setItem(key,value)
```

**获取数据：**

```javascript
session.Storage.getItem(key)
```

**删除数据：**

```javascript
sessionStorage.removeItem(key)
```

**删除所有数据：**

```javascript
sessionStorage.clear()
```

**使用案例：**

```html
<input type="text">
<button class="set">存储数据</button>
<botton class="get">获取数据</botton>
<botton class="remove">删除数据</botton>
<botton class="del">清空所有数据</botton>
<script>
    var ipt = document.querySelector('input');
    var set = document.querySelector('.set');
    var get = document.querySelector('.get');
    var remove = document.querySelector('.remove');
    var del = document.querySelector('.del');
    set.addEventListener('click',function(){
        //当我们点击了之后，就可以把表单里面的值存储起来
        var val = ipt.value;
        sessionStorage.setItem('uname',val);
    });
    get.addEventListener('click',function(){
        //当我们点击了之后，就可以把表单里面的值获取过来
        console.log(sessionStorage.getItem('uname'););
    });
    remove.addEventListener('click',function(){
        //当我们点击了之后，就可以把表单里面的uname键值对清除
        sessionStorage.removeItem('uname');
    })
    del.addEventListener('click',function(){
        //当我们点击了之后，清除所有的
        sessionStorage.clear();
    })
</script>
```

**案例：记住用户名**

如果勾选记住用户名，下次用户打开浏览器，就在文本框里面自动显示上次登陆的用户名

案例分析：

（1）把数据存储起来，用到本地存储

（2）关闭页面，也可以显示用户名，所以用到 localStorage

（3）打开页面，先判断是否有这个用户名，如果有，就在表单里面显示用户名，并且勾选复选框

（4）当复选框发生改变的时候 change 事件

（5）如果勾选，就存储，否则就移除

```html
<input type="text" id="username"><input type="checkbox" name="" id="remember">记住用户名
<script>
    var username = document.querySelector('#username');
    var remember = document.querySelector('#remember');
    if(localStorage.getItem('username')){
        username.value = localStorage.getItem('username');
        remember.checked = true;
    }
    remember.addEventListener('change',function(){
        if(this.checked){
            localStorage.setItem('username',username.value)
        }
        else{
            localStorage.removeItem('username');
        }
    })
</script>
```

