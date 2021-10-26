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

创建数组

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

筛选数组

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

冒泡排序

```javascript
var srr = [5,4,3,2,1];
for(var i = 0; i < arr.length; i++){
    for(var j = 0; j < arr.length - i; j++){
        if(arr[j] > arr[j + 1]){
            var temp = arr[j];
            arr[j] = arr[j + 1];
            arr[j + 1] = temp;
        }
    }
}
```

