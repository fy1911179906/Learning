# 第三章       列表与元组



## 序列

Python 中所有序列都可以进行一些特定操作，包括索引、分片、序列相加、乘法、成员资格、长度、最小值和最大值。

（1）索引：即序列（数组）下标可访问元素

```py
>>> group_2='12345'  #定义变量group_2,并赋值12345
>>> group_2[2]  #根据编号取元素，使用格式为：在方括号中输入所取元素的编号值
'3'
>>> '56789'[0]
'5'
```



（2）分片：即对序列（数组）一个范围内的元素进行访问

```py
>>> student='0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20'
>>> student[10:19]  #取得第二组所有同学的序号，加上逗号分隔符，需要取得10个字符
'5,6,7,8,9'
>>> student[-17:-1]  #负数表明从右开始计数，取得最后一组所有6名同学的序号
'15,16,17,18,19,2'
>>> number=[1,2,3,4,5,6,7,8,9,10]
>>> number[0:10]
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> number[0:]
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
>>> number[::-1]  #第二个冒号后是参数——步长，默认为1，为0报错，为负数序列从相反方向开始提取元素
[10, 9, 8, 7, 6, 5, 4, 3, 2, 1]
>>> number[0:10:2]
[1, 3, 5, 7, 9]
```



（3）序列相加：使用加号可以进行序列的连接操作

```py
>>> [1,2,3]+[4,5,6]
[1, 2, 3, 4, 5, 6]
>>> a=[1,2]
>>> b=[5,6]
>>> a+b
[1, 2, 5, 6]
>>> s='hello'
>>> w='world'
>>> s+w
'helloworld'
```



（4）乘法：用一个数字n乘以一个序列会生成新的序列。在新的序列中，会将原来的序列将首尾相连n重复次，得到一个新的变量值，赋给新的序列，这就是序列中的乘法。

（5）成员资格：所谓成员资格，是指某个序列是否是另一个序列的子集，该序列是否满足成为另一个序列的成员的资格。

（6）长度、最小值和最大值：提供的快速获取序列长度、最小值和最大值的内建函数，对应的内建函数分别为len、max和min。



## 列表

### 更新列表

（1）元素赋值：通过下标对对应的数值进行更改。

（2）增加元素：通过append()方法在列表末尾添加新对象的方法。

（3）删除元素：通过del语句删除列表中的元素。

（4）分片赋值：list()方法会将字符串str转换为对应的列表，通过分片替换元素或插入新元素。

### 嵌套列表

即列表里的列表，可视为一维和二维（数组）的看法

### 列表方法

（1）append()方法的语法格式如下：

（2）extend()方法的语法格式如下：

（3）index()方法的语法格式如下：

（4）insert()方法的语法格式如下：

（5）sort()方法的语法格式如下：

（6）copy()方法的语法格式如下：

（7）remove()方法的语法格式如下：

（8）pop()方法的语法格式如下：

（9）reverse()方法的语法格式如下：

（10）clear()方法的语法格式如下：

（11）count()方法的语法格式如下：

（12）高级排序



## 元组

### tuple函数

tuple()函数是针对元组操作的，功能是把传入的序列转换为元组并返回得到的元组，若传入的参数序列是元组，就会将传入参数原样返回。tuple()函数把参数序列转换为元组，list()函数把参数序列转换为列表。

### 元组的基本操作

（1）访问元组：通过索引下标即可访问元组中的值

（2）修改元组：元组中的元素不允许修改，但是可以对元组进行连接组合。

（3）删除元组：通过del语句删除整个元组，删除后，若继续访问，程序会报错。

（4）元组的索引和截取：通过分片的方式得到序列结果的元组。

### 元组内置函数

（1）len(tuple)函数用于计算元组中元素的个数。

（2）max(tuple)函数用于返回元组中元素的最大值。

（3）min(tuple)函数用于返回元组中元素的最小值。



## 列表与元组的区别

列表与元组的区别在于元组的元素不能修改。元组一旦初始化就不能修改，而列表则不同，想要修改哪里就可以修改哪里。



## 牛刀小试——实现杨辉三角

杨辉三角，是二项式系数在三角形中的一种几何排列，出现于中国南宋数学家杨辉1261年所著的《详解九章算法》一书中。杨辉三角是中国数学史上的一个伟大成就。

**思考点拨：**

（1）每个数等于它上方两数之和。

（2）每行数字左右对称，由1开始逐渐变大。

（3）第n行的数字有n项。

（4）前n行共[(1+n)n]/2个数。

（5）第n行的m个数可表示为C(n-1,m-1)，即为从n-1个不同元素中取m-1个元素的组合数。

（6）第n行的第m个数和第n-m+1个数相等，为组合数性质之一。

（7）每个数字等于上一行的左右两个数字之和，可用此性质写出整个杨辉三角。

```py
def create_line(l_list):
  line_list=[1]
  for x in range(1,len(l_list)):
        line_list.append(l_list[x]+l_list[x-1])
  line_list.append(1)
  return line_list

def print_line(line_list,width_v):
  s=""
  for x in line_list:
        s+=str(x)+" "
  print(s.center(width_v))

lines=[1]
row=int(input("输入行数："))
width=row*4
for x in range(row):
  print_line(lines,width)
  lines=create_line(lines)
```





# 第四章       字符串



## 字符串的简单操作

在Python中，可以使用单引号(')或双引号(")创建字符串。



## 字符串格式化

### 经典的字符串格式化符号——百分号(%)

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\6bbfdd14f1c595ee4406429527530688902c9a19.jpg)

```py
>>> print('圆周率PI的值为：%f' % 3.14)
圆周率PI的值为：3.140000
>>> print('圆周率PI的值为：%.2f' % 3.14)
圆周率PI的值为：3.14
```



### 元组的字符串格式化

格式化操作符的右操作数可以是任何元素，如果右操作数是元组，元组中的每个元素都会被单独格式化，每个值都需要对应的一个占位符。

```py
>>> print('%s年的冬奥会将在%s举行，预测中国至少赢取%d枚金牌' % ('2022','北京',5))
2022年的冬奥会将在北京举行，预测中国至少赢取5枚金牌
>>> print('%s年的冬奥会将在%s举行，预测中国至少赢取%d枚金牌' % ('2022','北京')) #少一个值
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    print('%s年的冬奥会将在%s举行，预测中国至少赢取%d枚金牌' % ('2022','北京'))
TypeError: not enough arguments for format string
>>> print('%s年的冬奥会将在%s举行，预测中国至少赢取枚金牌' % ('2022','北京',5)) #少一个占位符
Traceback(most recent call last):
  File "<pyshell#5>", line 1, in <module>
    print('%s年的冬奥会将在%s举行，预测中国至少赢取枚金牌' % ('2022','北京',5))
TypeError: not enough arguments for format string
>>> print('%s年的冬奥会将在%s举行，预测中国至少赢取%d枚金牌' % ['2022','北京',5])
Traceback(most recent call last):
  File "<pyshell#7>", line 1, in <module>
    print('%s年的冬奥会将在%s举行，预测中国至少赢取%d枚金牌' % ['2022','北京',5])
TypeError: not enough arguments for format string
>>> print('%s年的冬奥会将在北京举行' % ['2022'])
['2022']年的冬奥会将在北京举行
>>> print('%s年的冬奥会将在北京举行' % '2022')
2022年的冬奥会将在北京举行
>>> print('%s年的冬奥会将在北京举行' % ['2022','北京'])
['2022', '北京']年的冬奥会将在北京举行
```



（1）简单字符串格式化

```py
>>> print('圆周率PI的值为：%.2f' % 3.14)
圆周率PI的值为：3.14
>>> print('石油价格为每桶：$%d' % 96)
石油价格为每桶：$96
```



（2）格式化时指定字段宽度和精度

```py
>>> print('圆周率PI的值为：%10f' % 3.141593)   #字段宽度为10
圆周率PI的值为：3.141593 	#字符串宽度为10，被字符串占据8个空格，剩余两个空格
>>> print('保留2位小数，圆周率PI的值为：%10.2f' % 3.141593)   #字段宽度为10
保留2位小数，圆周率PI的值为：3.14 	#字符串宽度为10，字符串占据4个，剩6个
```



（3）符号、对齐和0填充

```py
>>> print('圆周率PI的值为：%010.2f' % 3.141593)
圆周率PI的值为：0000003.14

>>> print('圆周率PI的值为：%10.2f' % 3.14)
圆周率PI的值为：      3.14
>>> print('圆周率PI的值为：%-10.2f' % 3.14)
圆周率PI的值为：3.14      #此处右侧为多出的空格

>>> print(('% 5d' % 10) + '\n' + ('% 5d' % -10))
   10
  -10
```



### format  字符串格式化

一种字符串格式化的方式，形式为str.format()。str.format()是对百分号(%)格式化的改进。

```py
>>> 'hello,{}'.format('world')
'hello,world'
>>> print('圆周率PI的值为：{0}'.format(3.141593))
圆周率PI的值为：3.141593
>>> print('圆周率PI的值为：{0:.2f}'.format(3.141593))
圆周率PI的值为：3.14
>>> print('圆周率PI的值为：{pi}'.format(pi=3.141593))
圆周率PI的值为：3.141593
>>> print('{}年的冬奥会将在{}举行，预测中国至少赢取{}枚金牌'.format('2022','北京',5))
2022年的冬奥会将在北京举行，预测中国至少赢取5枚金牌
>>> print('{0}年的冬奥会将在{1}举行，预测中国至少赢取{2}枚金牌'.format('2022','北京',5))
2022年的冬奥会将在北京举行，预测中国至少赢取5枚金牌
>>> print('{year}年的冬奥会将在{address}举行'.format(year='2022',address='北京'))
2022年的冬奥会将在北京举行
```



### f  字符串格式化

一种字符串格式化字符：_f-strings_,格式化字符串。

_f-strings_使用方式如下：

```py
>>> f'hello,{world}'
'hello,world'
>>> f'{2*10}'
'20'
>>> year = 2022
>>> address = '北京'
>>> gold = 5
>>> f'{year}年的冬奥会将在{address}举行，预测中国至少赢取{gold}枚金牌'
'2022年的冬奥会将在北京举行，预测中国至少赢取5枚金牌'
>>> print(f'{year}年的冬奥会将在{address}举行，预测中国至少赢取{gold}枚金牌')
2022年的冬奥会将在北京举行，预测中国至少赢取5枚金牌
```



### f-string  字符串格式化

添加了一些语法结构，使其能够用于调试。

在过去，f_string这样使用：

```py
>>> name='xiaomeng'
>>> number=1001
>>> print(f'name={name}, number={number}')
name=xiaomeng, number=1001
```



在Python3.8中，可以使用如下方式（更加简洁）：

```py
>>> name='xiaomeng'
>>> number=1001
>>> print(f'{name=}, {number=}')
name='xiaomeng', number=1001
```



## 字符串方法



### split()方法

### strip()方法

### join()方法

### find()方法

### lower()方法

### upper()方法

### replace()方法

### swapcase()方法

### translate()方法



## 牛刀小试——变形金刚

打印如下结果：

（1）hello 的字符串长度；（2）HELLO；（3）Hello；（4）hEllo；（5）HeLLO；（6）h,llo。

```py
>>> def str_transformers():
    old_str = 'hello'
    print('the length of old_str is:', len(old_str))
    print('upper old_str is:', old_str.upper())
    print('title old_str is:', old_str.title())
    new_str = old_str.replace('e', 'E')
    print('new_str is:', new_str)
    print('swap case new_str is:', new_str.swapcase())
    print('use \',\' join old_str is:',','.join(old_str.split('e')))
    
    打印结果如下：
>>> str_transformers()
the length of old_str is: 5
upper old_str is: HELLO
title old_str is: Hello
new_str is: hEllo
swap case new_str is: HeLLO
use ',' join old_str is: h,llo
```





# 第五章       字典和集合



## 字典的使用

在Python中，字典是一种数据据结构，这种结构的功能就如它的命名一样，可以像汉语字典一样使用。

现需要创建一个小型数据库，用于存储第一组五位同学的姓名和序号，下面我们先使用列表实现上述功能，并从列表中找到叫小智的同学的序号，示例如下：

```py
>>> students=['小萌','小智','小强','小张','小李']
>>> numbers=['000','001','002','003','004']
>>> index_num=students.index("小智")
>>> print(f'小智在students中的索引下标是：{index_num}')
小智在students中的索引下标是：1
>>> xiaozhi_num=numbers[index_num]
>>> print(f'小智在numbers中的序号是：{xiaozhi_num}')
小智在numbers中的序号是：001
```



## 创建和使用字典

在Python中，创建字典的语法格式如下：

```py
>>> d={key1:value1,key2:value2}
```

下面是一个简单的字典示例：

```py
>>> dict_define={'小萌': '000', '小智': '001', '小强': '002'} 
>>> dict_define
{'小萌': '000', '小智': '001', '小强': '002'}
```



### dict函数

在Python中，可以使用dict()函数将序列转换为字典，可以用dict()函数，通过其他映射（如其他字典）或键值对建立字典，示例如下：

````py
>>> student=[('name','小智'),('number','001')]
>>> student
[('name', '小智'), ('number', '001')]
>>> type(student)
<class 'list'>
>>> student_info=dict(student) 
>>> type(student_info)
<class 'dict'>
>>> print(f'学生信息：{student_info}')
学生信息：{'name': '小智', 'number': '001'}
>>> student_name=student_info['name']
>>> print(f'学生姓名：{student_name}')
学生姓名：小智
>>> student_num=student_info['number']   #从字典中轻松获取学生序号
>>> print(f'学生序号：{student_num}')
学生学号：001
````



### 字典的基本操作

（1）修改字典

（2）删除字典元素

（3）字典键的特性

（4）len函数

（5）type函数



### 字典和列表比较

假如给你一个任务，让你从一堆名字中查找某个名字，找到名字后再找到这个名字对应的序号，名字和序号是一一对应的，就如此时在字典屋的Python快乐学习班的全体同学都有一个唯一的序号。根据目前所学，可以有两种实现方式：list列表和dict字典。

**方式一：**使用list列表实现。如果用list实现，需要定义两个列表，一个列表存放名字，一个列表存放序号，并且两个列表中的元素有一一对应关系。使用列表的方式，要先在名字列表中找到对应的名字，再从序号列表中取出对应的序号，使用列表的方式会发现，当list列表越长时，好耗时越长。

**方式二：**使用dict字典。如果用dict字典实现，只需要一个名字和序号一一对应的字典，就可以直接根据名字查找序号，无论字典有多大，查找速度都不会变。



## 字典方法



### get()方法

### keys()方法

### values()方法

### key in dict  方法

### update()方法

### clear()方法

### copy()方法

### fromkeys()方法

### items()方法

### setdefault方法



## 集合



### 创建集合

创建集合有两种方法：一种是直接把元素用花括号（{}）括起来，花括号中的元素之间用英文模式下的逗号（,）分隔；另一种是用set(obj)方法定义，obj为一个元素、一个列表或元组。

```py
>>> numbers={1,2,3,4,5}
>>> print(f'numbers变量的类型为:{type(numbers)}')
numbers变量的类型为:<class 'set'>
>>> numbers
{1, 2, 3, 4, 5}
>>> name=set('abc')  #一个元素，仔细观察输出结果
>>> name
{'a', 'b', 'c'}
>>> print(f'name变量的类型为:{type(name)}')
name变量的类型为:<class 'set'>
>>> students=set(['小萌','小智'])   #一个列表
>>> students
{'小萌', '小智'}
>>> print(f'students变量的类型为:{type(students)}')
students变量的类型为:<class 'set'>
>>> stu=set(('小萌','小智'))    #一个元组
>>> stu
{'小萌', '小智'}
>>> print(f'stu变量的类型为:{type(stu)}')
stu变量的类型为:<class 'set'>
```



### 集合方法

（1）add()方法

（2）remove()方法

（3）in 和 not in



## 牛刀小试——字典合并与排序

有两个字典，先将字典合并，完成后合并的字典进行排序

**大体思路：**

（1）借助字典的 update 函数将字典合并。

（2）准备一个将字典转化为列表的函数（知识点：字典转化为列表）。

（3）将转化后的列表进行排序（知识点：列表排序）。

（4）将排序好的列表转化为字典（知识点：列表转化为字典）。

```py
>>> def merge_range():
    lan_ver = {"lan": "python", "v": "3.7"}
    rea_ai = {"why": "hobby", "how": "do"}
    d_merge = dict()
    d_merge.update(lan_ver)
    d_merge.update(rea_ai)
    desc_list = sorted(dt2ls(d_merge), key=lambda x:x[0], reverse=True)
    desc_dict = dict(desc_list)
    asc_list = sorted(dt2ls(d_merge), key=lambda x:x[0], reverse=False)
    asc_dict = dict(asc_list)
    print(f'合并后的结果：{d_merge}')
    print(f'按照第0个元素降序排列：{desc_dict}' )
    print(f'按照第0个元素升序排列：{asc_dict}' )

>>> def dt2ls(dic:dict):
    """ 将字典转化为列表 """
    keys = dic.keys()
    values = dic.values()
    lst = [(key, val) for key, val in zip(keys, values)]
    return lst
>>> merge_range()

合并后的结果： {'lan': 'python', 'v': '3.7', 'why': 'hobby', 'how': 'do'}
按照第0个元素降序排列： {'why': 'hobby', 'v': '3.7', 'lan': 'python', 'how': 'do'}
按照第0个元素升序排列： {'how': 'do', 'lan': 'python', 'v': '3.7', 'why': 'hobby'}
```





# 第六章       条件、循环和其他语句



## 使用文本编辑器

Sublime Text 和 Notepad++



## import 的使用



### import语句

```py
import math
r=5
print('半径为5的圆的面积为：%.2f' %(math.pi*r**2))
```



### 使用逗号输出

```py
>>> student='小智'
>>> print('学生称呼：',student)
学生称呼： 小智
>>> greeting='大家好！'
>>> intriduce='我叫小智，'
>>> comefrom='我来自智慧城市。'
>>> print(greeting,intriduce,comefrom)
大家好！ 我叫小智， 我来自智慧城市。
```



## 别样的赋值



### 序列解包

```py
>>> x,y,z=1,2,3
>>> x,y,z
(1, 2, 3)
>>> x,y,z=1,2
Traceback (most recent call last):   #解包序列中的元素数量必须和放置在赋值符号“=”左边的数量完全一致，否则会赋值时引发异常
  File "<stdin>", line 1, in <module>
ValueError: not enough values to unpack (expected 3, got 2)
```

解包序列中的元素数量必须和放置在赋值符号“=”左边的数量完全一致，否则会赋值时引发异常



### 链式赋值

```py
>>> x=y=z=10
>>> x
10
```



### 增值赋值

```py
>>> x=5
>>> x+=1   #加
>>> x
6
```



## 语句块

在Python中，冒号(:)用来标识语句块的开始，语句块并非一种语句，语句块是一组满足一定条件时执行一次或多次的语句。



## 条件语句



### 布尔变量的作用

下面的值在作为布尔表达式时，会被解释器看作假（False）：

False，None，0，""，()，[]，{}



### if语句

```py
greeting='hello'
if greeting=='hello':
   print('hello')
```



### else语句

```py
num=10
if num<=10:
   if num>=5:
      print('num的值介于5和10之间')
   else:
      print('num的值不介于5和10之间')
else:
   print('num的值不介于5和10之间')
```



### elif语句

```py
num=10
if num>10:
   print('num的值大于10')
elif 0<=num<=10:
   print('num的值介于0和10之间')
else:
   print('num的值小于0')
```



### 嵌套代码块

```py
num=10
if num>10:
   print('num的值大于10')
elif 0<=num<=10:
   print('num的值介于0和10之间')
else:
   print('num的值小于0')
```



### 更多操作

（1）is：同一性运算符

```py
>>> x=y=[1,2,3]
>>> z=[1,2,3]
>>> x==y
True
>>> x is y
True
>>> x is z
False
```



（2）比较字符串和序列

```py
>>> [1,2]<[2,1]
True
>>> [1,2]<[1,2]
False
>>> [1,2]==[1,2]
True
>>> [2,[1,2]]<[2,[1,3]]
True
```



（3）布尔运算符

```py
num=10
if num<=10:
   if num>=5:
      print('num的值介于5和10之间')
   else:
      print('num的值不介于5和10之间')
else:
   print('num的值不介于5和10之间')
```



### 断言

是使用关键字assert，当assert后面的条件为真时，程序正常运行；当assert后面的条件为假时，输出错误信息。错误的提示信息由我们自己定义，这个错误参数提示信息可以称为异常参数。这就可以理解为要求条件必须为真的。

```py
>>> x=3
>>> assert x>0,"x is not zero or negative"
>>> assert x%2==0, "x is not an even number"   #提示x不是偶数
Traceback (most recent call last):
  File "<stdin>",line 1,in <module>
AssertionError: x is not an even number
```



## 循环



### while 循环

```py
n = 1
while n <= 100:
    print(f'当前数字是：{n}')
    n += 1
```



### for 循环

```py
fields = ['a', 'b', 'c']
for f in fields:
    print(f'当前字母是：{f}')
```



### 循环遍历字典元素

```py
tups = {'name': '小智', 'number': '001'}
# for循环字典
for tup in tups:
    print(f'{tup}:{tups[tup]}')
    
tups = {'name': '小智', 'number': '001'}
for key, value in tups.items():
    print(f'{key}:{value}')
    
输出结果如下：
number:001
name:小智
```



### 迭代工具

（1）并行迭代

```py
student = ['xiaomeng', 'xiaozhi', 'xiaoqiang']
number = [1001, 1002, 1003]
for i in range(len(student)):
    print(f'{student[i]}的学号是：{number[i]}')
```



（2）翻转和排序迭代

```py
>>> sorted([5,3,1,7])
[1, 3, 5, 7]
>>> sorted('hello,world')
[',', 'd', 'e', 'h', 'l', 'l', 'l', 'o', 'o', 'r', 'w']
>>> list(reversed('hello,world'))
['d', 'l', 'r', 'o', 'w', ',', 'o', 'l', 'l', 'e', 'h']
>>> ''.join(reversed('hello,world'))
'dlrow,olleh'
```



### 跳出循环

（1）break

```py
# 示例1
for letter in 'hello':
    if letter == 'l':
        break
    print(f'当前字母为:{letter}')

# 示例2
num = 10
while num > 0:
    print(f'输出数字为:{num}')
    num -= 1
    if num == 8:
        break
```



（2）continue

```py
for letter in 'hello':     # 示例1
    if letter == 'l':
        continue
    print(f'当前字母 :{letter}')

num = 3                    # 示例2
while num > 0:              
    num -= 1
    if num == 2:
        continue
    print(f'当前变量值 :{num}')
```



### 循环中的else子句

（1）在while循环中使用else语句

```py
num = 0
while num < 3:
    print(f"{num} 小于 3")
    num += 1
else:
    print(f"{num} 大于或等于 3")
print("结束循环!")
```

（2）在for循环中使用else语句

```py
names = ['xiaomeng', 'xiaozhi']
for name in names:
    if name == "xiao":
        print(f"名称：{name}")
        break
    print(f"循环名称列表 {name}")
else:
    print("没有循环数据!")
print("结束循环!")
```



## pass语句

Python中的pass作用是作用是保持程序结构的完整性。

```py
错误：
name='xiaomeng'
if name == 'xiaomeng':
    print('hello')
elif name == 'xiaozhi':
    # 预留，先不做任何处理
else:
    print('nothing')
    
正确：
name = 'xiaomeng'
if name == 'xiaomeng':
    print('hello')
elif name == 'xiaozhi':
    # 预留，先不做任何处理
    pass
else:
    print('nothing')
```



## 牛刀小试——猜字游戏编写

游戏内容是这样的：随便给定在一个范围内的数字，让用户去猜这个数字是多少，并输入自己猜测的数字，系统判断是否为给定数字。如果输入的猜测数字大于给定值，提示你输入的值大于自己猜测的数字，如果输入的值小于给定值，就提示输入的值小了；如果等于给定值，就提示你猜对了，并展示总共才了多少次。

**思考点拨：**

先从最简单的方向思考，有3种情况：（1）输入值小于给定值；（2）输入值大于给定值；（3）输入值等于给定值；对于情况（1）和（2），需要继续输入；对于情况（3），输入结束。需要提供3个变量：一个变量用于记录给定值，一个变量用于记录输入值，还有一个变量用于记录输入了多少次，注意输入次数至少是一次。

```py
import random

number = random.randint(1, 100)
guess = 0
while True:
    num_input = input("请输入一个1到100的数字:")
    guess += 1
    if not num_input.isdigit():
        print("请输入数字。")
    elif int(num_input) < 0 or int(num_input) >= 100:
        print("输入的数字必须介于1到100。")
    else:
        if number == int(num_input):
            print(f"恭喜您，您猜对了，您总共猜了 {guess} 次")
            break
        elif number > int(num_input):
            print("您输入的数字小了。")
        elif number < int(num_input):
            print("您输入的数字大了。")
        else:
            print("系统发生不可预测问题，请联系管理人员进行处理。")
```





# 第七章      函数



## 调用函数

 https://docs.python.org/3.7/library/functions.html

```py
>>> int(12.1)
12
>>> abs(20)
20
>>> abs(-20)
20
```



## 定义函数

Python定义函数使用def关键字，一般格式如下：

```py
def <name> (arg1,arg2,... argN):
<statement>

示例：
def hello():
    print('hello,world')
hello()
```



## 函数的参数



### 必须参数

必须参数必须以正确的顺序传入函数。调用时数量必须和声明时一样。

```py
def param_one(val_str):
    print(f'the param is:{val_str}')
    print(f'我是一个传入参数，我的值是：{val_str}')
param_one('hello,world')
```



### 关键字参数

使用关键字参数允许调用函数时参数的顺序与声明时不一致，因为Python解释器能够用参数名匹配参数值。

```py
def person_info(age, name):
    print(f'年龄：{age}')
    print(f'名称：{name}')
    return


print('-------按参数顺序传入参数-------')
person_info(21, '小萌')
print('-------不按参数顺序传入参数，指定参数名-------')
person_info(name='小萌', age=21)
print('-------按参数顺序传入参数，并指定参数名-------')
person_info(age=21, name='小萌')
```



### 默认参数

使用默认参数，就是在定义函数时，给参数一个默认值。默认参数一定要放在非默认参数后面，无论有多少默认参数，都不能在必须参数之前。默认参数可以通过传入参数名更改参数值。

```py
错误示例：

def default_param_1(age=23, name, addr='shanghai'):
	print(f'hi，我叫：{name}')
	print(f'我今年：{age}')
	print(f'我现在在: {addr}')
	return

def default_param_2(age=23, addr='shanghai', name):
	print(f'hi，我叫：{name}')
	print(f'我今年：{age}')
	print(f'我现在在: {addr}')
	return

default_param_1(age=23, '小萌', addr='shanghai')
default_param_2(age=23, addr='shanghai', '小萌')



正确示例：

def default_param(name, age=23, addr='shanghai'):
    print(f'hi，我叫：{name}')
    print(f'我今年：{age}')
    print(f'我现在在: {addr}')
    return

print('-------传入必须参数-------')
default_param('小萌')
print('-------传入必须参数，更改第一个默认参数值-------')
default_param('小萌', 21)
print('-------传入必须参数，默认参数值都更改-------')
default_param('小萌', 21, 'beijing')
print('-------传入必须参数，指定默认参数名并更改参数值-------')
default_param('小萌', addr='beijing')
print('-------传入必须参数，指定参数名并更改值-------')
default_param('小萌', addr='beijing', age=23)
print('-------第一个默认参数不带参数名，第二个带-------')
default_param('小萌', 21, addr='beijing')
print('-------两个默认参数都带参数名-------')
default_param('小萌', age=23, addr='beijing')
print('-------第一个默认参数带参数名，第二个不带，报错-------')
# default_param('小萌',age=23,'beijing')  # 打开运行报错
```



### 可变参数

如果需要一个函数能够处理更多的声明参数，这些参数叫作可变参数。加了星号（*）的变量名会存放所有未命名的变量参数。如果变量参数在函数调用时没有指定参数，就是一个空元组。

````py
def person_info_var(arg, *vartuple):
    print(arg)
    for var in vartuple:
        print(f'我属于不定长参数部分:{var}')
    return

print('------------不带可变参数------------------')
person_info_var('小萌')
print('------------带两个可变参数------------------')
person_info_var('小萌', 21, 'beijing')
print('------------带5个可变参数----------------')
person_info_var('小萌', 21, 'beijing', 123, 'shanghai', 'happy')


难点：
other = {'城市': '北京', '爱好': '编程'}

def per_info(name, number, **kw):
    print(f'名称:{name},学号:{number},其他:{kw}')

per_info('小智', 1002, 城市=other['城市'], 爱好=other['爱好'])
per_info('小智', 1002, **other)

函数执行结果为：
名称：小智，学号：1002，其他：{'城市': '北京', '爱好': '编程'}
由函数执行结果看到，可以使用两个“*”号，即使用“**”处理关键字参数。函数调用时可以用更简单的方式调用，简单形式如下：
per_info('小智',1002,**other)
函数结果和前面的一样写法上却简单了不少。此处**other表示把other这个字典的所有key-value用关键字参数传入函数的**kw参数中，kw将获得一个字典，注意kw获得的字典是other复制的，对kw的改动不会影响函数外的other。
````



### 组合参数

在Python中定义函数可以用必须参数、关键字参数、默认参数和可变关键字参数，这4种参数可以组合使用。

```py
def exp(p1, p2, df=0, *vart, **kw):
    print(f'{p1 = }, {p2 = }, {df = }, {vart = }, {kw = }')

exp(1, 2)
exp(1, 2, c=3)
exp(1, 2, 3, 'a', 'b')
exp(1, 2, 3, 'abc', x=9)  #在调用函数时，Python解释器会自动按照参数位置和参数名把对应的参数传进去
```

此处还可以用tuple 和 dict 调用上述函数，使用方式如下：

```py
args=(1,2,3,4)
kw={'x':8,'y':'9'}
exp(*args,**kw)

执行结果如下：
p1=1,p2=2,df=3,vart=(4,),kw={'y':'9','x':8}
由执行结果看到，任意函数都可以通过类似func(*args,**kw)的形式调用，无论参数是如何定义的。
```



### 仅通过位置指定的参数

```py
def pow(x, y, z=None):
    r = x ** y
    if z is not None:
       r %= z
       return r
正确：
print(f'{pow(2, 10, 5)=}')
错误：
print(f'{pow(2, 10, z=5)=}')
```

在Python3.8的新语法中，符号/分隔了位置参数和关键字参数。在这个例子中，所有参数都是未知参数。在以前的版本的Python中，会被认为是关键字参数。但采用上述函数定义，pow(2,10,5)是正确的调用方式，而pow2(2,10,z=5)是不正确的。



也可以在变量之间插入/，正斜杠之前的变量按照纯粹的Python输入方法，而正斜杠之后的按照定义好的方法执行。

```py
def fun(a, b, /, c, d, *, e, f):
    print(f'{a=}, {b=}, {c=}, {d=}, {e=}, {f=}')


# 合法
fun(1, 2, 3, 4, e=5, f=6)
# 合法
fun(1, 2, 3, d=4, e=5, f=6)
# 合法
fun(1, 2, c=3, d=4, e=5, f=6)
# 不合法
fun(1, b=2, c=3, d=4, e=5, f=6)
# 不合法
fun(a=1, b=2, c=3, d=4, e=5, f=6)
```



## 形参和实参

Python函数的两种类型的参数，一种是函数定义里的形参，一种是调用函数时传入的实参。



## 变量的作用域



### 局部变量

在函数内定义的变量名只能被函数内部引用，不能在函数外引用，这个变量的作用域是局部的，也称为局部变量。

```py
正确：
def local_var():
    x = 100
    print(x)

错误：
def local_func():
    x = 100
    print(f'变量x：{x}')

print(f'函数体外访问变量x：{x}')
local_func()
```



### 全局变量

在函数外，一段代码最开始赋值的变量可以被多个函数引用，这就是全局变量。全局变量可以在整个程序范围内访问。

```py
# 这是一个全局变量
total_val = 0


def sum_num(arg1, arg2):
    # total_val在这里是局部变量.
    total_val = arg1 + arg2
    print(f"函数内是局部变量:{total_val}")
    return total_val


def total_print():
    print(f'total的值是:{total_val}')
    return total_val


print(f'函数求和结果:{sum_num(10, 20)}')
total_print()
print(f"函数外是全局变量:{total_val}")
```



## 有返回值和无返回值函数

```py
def no_return():
    print('no return函数不写return语句')


def just_return():
    print('just return函数只写return，不返回具体内容')
    return


def return_val():
    x = 10
    y = 20
    z = x + y
    print('return val函数写return语句，并返回求和的结果。')
    return z


print(f'函数no return调用结果：{no_return()}')
print(f'函数just return调用结果：{just_return()}')
print(f'函数return val调用结果：{return_val()}')
```



## 返回函数

返回值的函数：

```py
def calc_sum(*args):
    ax = 0
    for n in args:
        ax = ax + n
    return ax
```

返回函数的函数：

```py
def sum_late(*args):
    def calc_sum():
        ax = 0
        for n in args:
            ax = ax + n
        return ax
    return calc_sum


print(f'调用sum_late的结果：{sum_late(1, 2, 3, 4)}')
calc_sum = sum_late(1, 2, 3, 4)
print(f'调用calc_sum的结果：{calc_sum()}')
```

可以看到，此处返回了一个我们之前没有看过的类型的值，是返回了一个函数吗？是的，此处确实返回了一个函数。对于此处定义的函数，我们没有返回求和的结果，而是返回了一个求和函数。有一点需要注意，当调用sum_late()函数时，每次都会返回一个新的函数，即使传入相同的参数也是如此，例如：

```py
f1=sum_late(1,2,3)
f2=sun_late(1,2,3)
print('f1==f2的结果为：',f1==f2)
执行结果如下：
f1==f2的结果为：False
```

由执行结果看到，返回的函数f1 和 f2 不同。我们在此处提到了闭包，什么是闭包呢？

闭包的定义：如果在一个内部函数中对外部函数（不是在全局作用域）的变量进行引用，内部函数就被认为是闭包。

下面演示两种不同结果的函数：

```py
def func_count():
    fs = []
    for i in range(1, 4):
        def f():
             return i * i
        fs.append(f)
    return fs


f1, f2, f3 = func_count()
print(f'f1的结果是：{f1()}')
print(f'f2的结果是：{f2()}')
print(f'f3的结果是：{f3()}')

执行结果如下：
f1的结果是:9
f2的结果是:9
f3的结果是:9
原因在于返回的函数引用了变量i，但它并非立刻执行。等到3个函数都返回时，他们所引用的变量i已经变成了3，因此最终结果为9.
```

```py
def func_count_up():
    def f(j):
        def g():
            return j*j
        return g
    fs = []
    for i in range(1, 4):
        # f(i)立刻被执行，因此i的当前值被传入f()
        fs.append(f(i))
    return fs


f1, f2, f3 = func_count_up()
print(f'f1的结果是：{f1()}')
print(f'f2的结果是：{f2()}')
print(f'f3的结果是：{f3()}')

执行结果如下：
f1的结果是:1
f2的结果是:4
f3的结果是:9
```



## 递归函数

fact(n)用递归方式定义函数如下：

```py
def fact(n):
    if n == 1:
        return 1
    return n * fact(n - 1)

print(f'调用递归函数执行结果为：{fact(5)}')
```

由于上面的fact(n)函数 return n*fact(n-1) 引入了乘法表达式，因此不是尾递归。要改成尾递归方式需要多一点代码，主要是把每一步乘积传入递归函数中，看如下函数定义方式：

```py
# import sys
#
# sys.setrecursionlimit(10000) #例如这里设置深度为一万

def fact(n):
    return fact_iter(n, 1)

def fact_iter(num, product):
    if num == 1:
        return product
    return fact_iter(num - 1, num * product)

print(f'调用递归函数执行结果为：{fact(997)}')
```



## 匿名函数

lambda 函数的语法只包含一个语句，语句如下：

```py
lambda [arg1 [,arg2,......argn]]:expression
```

使用 def 语句：

```py
def func(x,y):
    return x+y
    
def func_filter(x):
    return x>3
f_list=filter(func_filter,[1,2,3,4,5])
print('列表中大于3的元素有：',[item for item in f_list])
```

使用 lambda 表达式：

```py
lambda x,y : x+y

print('列表中大于3的元素有：',[item for item in filter(lambda x : x>3,[1,2,3,4,5])])
```

item for item in filter 是 Python 3 中 filter 函数的取值方式，因为从Python 3起，filter 函数返回的对象从列表改为迭代器（filter object）。filter object 支持迭代器操作，比如for循环：

```py
for item in a_filter_object:
print(item)
```

如果还需要一个列表，就可以这样得到它：

```py
filter_list=[item for item in a_filter_object]
```

匿名函数有3个规则要记住：

（1）一般有一行表达式，必须有返回值。

（2）不能有return。

（3）可以没有参数，也可以有一个或多个参数。



## 偏函数

偏函数是将所要承载的函数作为 partial() 函数的第一个参数，原函数的各个参数依次作为 partial() 函数的后续参数，除非使用关键字参数。

```py
from functools import partial

def mod_partial(n, m):
  return n % m
  
mod_by_100 = partial(mod_partial, 100)
print(f'自定义函数，100对7取余结果为：{mod_partial(100, 7)}')
print(f'调用偏函数，100对7取余结果为：{mod_by_100(7)}')
```



## 牛刀小试——经典排序之快速排序实现

快速排序（quick sort）是一种分治排序算法。该算法首先选取一个划分元素（partition element，也称为pivot）；然后重排列表，将其划分为3部分，即 left （小于划分元素 pivot 的部分）、pivot（划分元素） right （大于划分元素 pivot 的部分），此时元素 pivot 已经在列表的最终位置上；最后分别对 left 和 right两部分进行递归排序。

其中，划分元素的选取直接影响快速排序算法的效率，通常选择列表的第一个元素。中间元素或最后一个元素作为划分元素，当然也有更复杂的选择方式。划分过程根据划分元素重排列表，是快速排序算法的关键所在。

快速排序算法的优点是原位排序（只使用很小的辅助栈），平均时间复杂度为O(n log n)。快速排序算法的缺点是不稳定，最坏情况下时间复杂度为O(n*2)。

```py
def quick_sort(num_list):
   q_sort(num_list, 0, len(num_list) - 1)

def q_sort(num_list, first, last):
    if first < last:
        split = partition(num_list, first, last)
        q_sort(num_list, first, split - 1)
        q_sort(num_list, split + 1, last)

def partition(num_list, first, last):
    # 选取列表中的第一个元素作为划分元素
    pivot = num_list[first]
    left_mark = first + 1
    right_mark = last
    while True:
        while num_list[left_mark] <= pivot:
            # 如果列表中存在与划分元素pivot相等的元素，让它位于left部分
            # 以下检测用于划分元素pivot是列表中的最大元素时
            # 防止left_mark越界
            if left_mark == right_mark:
                break
            left_mark += 1
        while num_list[right_mark] > pivot:
            # 这里不需要检测，划分元素pivot是列表中的最小元素时
            # right_mark自动停在first处
            right_mark -= 1
        if left_mark < right_mark:
            # 此时，left_mark处的元素大于pivot
            # right_mark处的元素小于等于pivot，交换两者
            num_list[left_mark], num_list[right_mark] = num_list[right_mark], num_list[left_mark]
        else:
            break
    # 交换first处的划分元素与right_mark处的元素
    num_list[first], num_list[right_mark] = num_list[right_mark], num_list[first]
    # 返回划分元素pivot的最终位置
    return right_mark

n_list = [5, -4, 6, 3, 7, 11, 1, 2]
print(f'排序之前: {str(n_list)}')
quick_sort(n_list)
print(f'排序之后: {str(n_list)}')
```





# 第八章       面向对象编程



## 理解面向对象

Python 是一门面向对象编程语言，对面向对象语言编码的过程叫作面向对象编程。



## 类的定义和使用



### 类的定义

类定义的语法格式如下：

```py
class ClassName(object):
      <statement-1>
      .
      .
      .
      <statement-N>
```

示例：

````py
class MyClass(object):
    i = 123

    def f(self):
        return 'hello world'
````



### 类的使用

````py
class MyClass(object):
    i = 123

    def f(self):
        return 'hello world'
        
use_class=MyClass()     #这一步叫作类的实例化
print(f'调用类的属性：{use_class.i}')
print(f'调用类的方法：{use_class.f()}')

执行结果如下：
调用类的属性：123
调用类的方法：hello world
````



## 深入类



### 类的构造方法

```py
class MyClass(object):
    i = 123

    def __init__(self, name):
        self.name = name

    def f(self):
        return 'hello,'+ self.name

use_class = MyClass('xiaomeng')
print(f'调用类的属性：{use_class.i}')
print(f'调用类的方法：{use_class.f()}')

程序执行结果如下：
调用类的属性：123
调用类的方法：hello,xiaomeng

若类的实例化语句写法和之前一样，即
use_class = MyClass()

程序执行结果如下：
Traceback (most recent call last):
  File "C:\Users\FY\Desktop\Python练习\python3.8sourcecode\chapter8\my_calss_search.py", line 15, in <module>
    use_class = MyClass()
TypeError: __init__() missing 1 required positional argument: 'name'
```

还有需要注意的是，一个类中可定义多个构造方法，但实例化类时只实例化最后的构造方法，即后面的构造方法会覆盖前面的构造方法，并且需要根据最后一个构造方法的形式进行实例化。建议一个类只定义一个构造函数。



### 类的访问权限

在类内部有属性和方法，外部代码可以通过直接调用实例变量的方法操作数据，这样就隐藏了内部的复杂逻辑。

```py
class Student(object):
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def info(self):
        print(f'学生：{self.name}；分数: {self.score}')

stu = Student('xiaomeng', 95)
print (f'修改前分数：{stu.score}')
stu.info()
stu.score=0
print (f'修改后分数：{stu.score}')
stu.info()
```

要让内部属性不被外部访问，可以在属性名称前加两个下划线_。在 Python 中，实例的变量名如果以 _ 开头，就会变成私有变量（private），只有内部可以访问，外部不能访问。

```py
class Student(object):
    def __init__(self, name, score):
        self.__name = name
        self.__score = score

    def info(self):
        print(f'学生：{self.__name}；分数: {self.__score}')


stu = Student('xiaomeng', 95)
print(f'修改前分数：{stu.__score}')
stu.info()
stu.__score = 0
print(f'修改后分数：{stu.__score}')
stu.info()

程序执行结果如下：
  File "C:\Users\FY\Desktop\Python练习\python3.8sourcecode\chapter8\student_calss_1.py", line 11, in <module>
    print(f'修改前分数：{stu.__score}')
AttributeError: 'Student' object has no attribute '__score'
```

如果外部代码要获取类中的私有变量或通过外部更改内部私有变量的值，可以为类增加 get_attr 和 set_attr 方法

```py
class Student(object):
    def __init__(self, name, score):
        self.__name = name
        self.__score = score

    def info(self):
        print(f'学生：{self.__name}；分数: {self.__score}')

    def get_score(self):
        return self.__score

    def set_score(self, score):
        self.__score = score


stu = Student('xiaomeng', 95)
print(f'修改前分数：{stu.get_score()}')
stu.info()
stu.set_score(0)
print(f'修改后分数：{stu.get_score()}')
stu.info()
```

类也有私有方法。类的私有方法也是以两个下划线开头。

```py
class PrivatePublicMethod(object):
    def __init__(self):
        pass

    def __foo(self):          # 私有方法
        print('这是私有方法')

    def foo(self):            # 公共方法
        print('这是公共方法')
        print('公共方法中调用私有方法')
        self.__foo()
        print('公共方法调用私有方法结束')

pri_pub = PrivatePublicMethod()
print('开始调用公共方法：')
pri_pub.foo()
print('开始调用私有方法：')
pri_pub.__foo()
```



## 继承

在面向对象程序设计中，当我们定义一个class时，可以从某个现有的class继承，定义的新class称为子类（Subclass），而被继承的class成为基类、父类或超类（Base class、Super class）。

继承的定义如下：

```py
class DerivedClassName(BaseClassName):
      <statememnt-1>
      .
      .
      .
      <statememt-N>
```

示例：

````py
class Animal(object):
      def run(self):
          print('Animal is running...')
class Dog(Animal):
      pass
class Cat(Animal):
      pass
dog=Dog()
dog.run()
cat=Cat()
cat.run()

程序执行结果如下：
Animal is running...
Animal is running...
````

还要注意的是，子类不能继承父类中的私有方法，也不能调用父类的私有方法。



## 多态

无论时 Dog 还是 Cat ，调用父类的 run() 方法时显示的都是 Animal is running...，如果想让结果显示为 Dog is running... 和 Cat is running...，该如何办呢？

```py
class Animal(object):
    def run(self):
        print('Animal is running...')

    def jump(self):
        print('Animal is jumpping....')

    def __run(self):
        print('I am a private method.')

class Dog(Animal):
    def run(self):
        print('Dog is running...')

class Cat(Animal):
    def run(self):
        print('Cat is running...')
        
dog = Dog()
print('实例化Dog类')
dog.run()

cat = Cat()
print('实例化Cat类')
cat.run()
```



## 封装

封装并不等同于多态。多态可以让用户对不知道类（或对象类型）的对象进行方法调用，而封装可以不用关心对象是如何构建的，直接使用即可。

```py
class Student0(object):
    def __init__(self, name, score):
        self.name = name
        self.score = score

    def info(self):
        print(f'学生：{self.name}；分数: {self.score}')

stu = Student0('xiaomeng', 95)
stu.info()
```



## 多重继承

Python 还支持多重继承。多重继承的类定义如下：

```py
class DerivedClassName(Base1,Base2,Base3):
      <statement-1>
      .
      .
      .
      <statement-N>
```



## 获取对象信息



（1）使用 type() 函数

```py
>>> type(124)
<class 'int'>
>>> type('abc')
<class 'str'>
>>> type(None)
<class 'NoneType'>
```



（2）使用 isinstance() 函数

要明确class的继承关系，使用 type() 很不方便，通过判断 class 的数据类型确定 class 的继承关系要方便得多，这个时候可以使用 isinstance() 函数。

```py
>>> isinstance(Dog,Animal)
True
>>> isinstance(Animal,Dog)
False
```



（3）使用 dir()

如果要获得一个对象的所有属性和方法，就可以使用 dir() 函数。dir() 函数返回一个字符串的 list。例如，获得一个 str 对象的所有属性和方法的方式如下：

````py
>>> dir('abc')
['__add__', '__class__', '__contains__', '__delattr__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__getitem__', '__getnewargs__', '__gt__', '__hash__', '__init__', '__init_subclass__', '__iter__', '__le__', '__len__', '__lt__', '__mod__', '__mul__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__rmod__', '__rmul__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', 'capitalize', 'casefold', 'center', 'count', 'encode', 'endswith', 'expandtabs', 'find', 'format', 'format_map', 'index', 'isalnum', 'isalpha', 'isascii', 'isdecimal', 'isdigit', 'isidentifier', 'islower', 'isnumeric', 'isprintable', 'isspace', 'istitle', 'isupper', 'join', 'ljust', 'lower', 'lstrip', 'maketrans', 'partition', 'removeprefix', 'removesuffix', 'replace', 'rfind', 'rindex', 'rjust', 'rpartition', 'rsplit', 'rstrip', 'split', 'splitlines', 'startswith', 'strip', 'swapcase', 'title', 'translate', 'upper', 'zfill']
````



## 类的专有方法

（1）__ str __

```py
class Student(object):
    def __init__(self, name):
        self.name = name

print(Student('xiaozhi'))

执行结果如下：
<__main__.Student object at 0x0000021B744E6040>

>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

class Student(object):
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return f'学生名称: {self.name}'

print(Student('xiaozhi'))

执行结果如下：
学生名称：xiaozhi
```

如果在交互式模式下输入如下：

```py
>>> s=Student=('xiaozhi')
>>> s
<__main__.Student object at 0x0000021B744E6040>
```

这是因为直接显示变量调用的不是__ str __ ()，而是 __ repr __ ()，两者的区别在于 __ str __ ()返回用户看到的字符串，而 __ repr __ ()返回程序开发者看到的字符串。也就是说， __ repr __ ()是为调试服务的。解决办法是再定义一个 __ repr __ ()。通常， __ str __ ()和 __ repr __ ()的代码是一样的，所以有一个偷懒的写法：

```py
class Student(object):
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return f'学生名称: {self.name}'
    __repr__ = __str__

print(Student('xiaozhi'))

如果在交互式模式下输入如下：
>>> s=Student=('xiaozhi')
>>> s
学生名称：xiaozhi
```



（2）__ iter __

如果想将一个类用于 for ... in 循环，类似 list 或 tuple 一样，就必须实现一个 __ iter __ ()方法。 该方法返回一个迭代对象，Python 的 for 循环会不断调用该迭代对象的 __ next __ ()方法，获得循环的下一个值，直到遇到 StopIteration 错误时退出循环。我们以斐波那契数列为例，写一个可以作用于 for 循环的 Fib 类。

```py
class Fib(object):
    def __init__(self):
        # 初始化两个计数器a、b
        self.a, self.b = 0, 1 

    def __iter__(self):
        # 实例本身就是迭代对象，故返回自己
        return self 

    def __next__(self):
        # 计算下一个值
        self.a, self.b = self.b, self.a + self.b
        # 退出循环的条件
        if self.a > 100000: 
            raise StopIteration()
        # 返回下一个值
        return self.a 

for n in Fib():
    print(n)
```



（3）__ getitem __

Fib 实例虽然能够作用于 for 循环，和 list 有点像，但是不能将它当成 list 使用。要像 list 一样按照下标取出元素，需要实现 __ getitem __()方法，代码如下：

```py
class Fib(object):
    def __getitem__(self, n):
        a, b = 1, 1
        for x in range(n):
            a, b = b, a + b
        return a

fib = Fib()
print(fib[3])
print(fib[10])
```



（4）__ getattr __

正常情况下，调用类的方法或属性时，如果类的方法或属性不存在就会报错。要避免这个错误，除了可以添加一个 score 属性外，Python 还提供了另一种机制，就是写一个 __ getattr __ ()方法，动态返回一个属性。

```py
class Student(object):

    def __init__(self):
        self.name = 'xiaozhi'

    def __getattr__(self, attr):
        if attr=='score':
            return 95

stu = Student()
print((stu.name))
print((stu.score))

在交互模式下输入如下：
>>> stu=Student()
>>> stu.name
xiaozhi
>>> stu.score
95
```



（5）__ call __

一个对象实例可以有自己的属性和方法，调用实例的方法时使用 instance.method() 调用。只需要定义一个 __ call  __ ()方法，就可以直接对实例进行调用。

```py
class Student(object):
    def __init__(self, name):
        self.name = name

    def __call__(self):
        print(f'名称：{self.name}')

stu = Student('xiaomeng')
print(stu())
print(callable(Student('xiaozhi')))

在交互模式下输入如下：
>>> stu=Student('xiaomeng')
>>> stu()
名称：xiaomeng
```

很多时候判断一个对象是否能被调用可以使用 callable() 函数，比如 max 函数和上面定义的带有 __ call __ ()的 Student 类实例。

```py
>>> callable(Student('xiaomeng'))
True
>>> callable(max)
True
>>> callable([1,2,3])
False
>>> callable(None)
False
>>> callable('a')
False
```



## 牛刀小试一——出行建议

小智今天想出去，但不清楚今天的天气是否适宜出行，需要一个帮他提供建议的程序，程序要求出入daytime 和 night，根据可见度和温度给出出行建议和使用的交通方式，需要考虑需求变更的可能。

定义天气查找类

```py
class WeatherSearch(object):
    def __init__(self, input_daytime):
        self.input_daytime = input_daytime

    def seach_visibility(self):
        visible_leave = 0
        if self.input_daytime == 'daytime':
            visible_leave = 2
        if self.input_daytime == 'night':
            visible_leave = 9
        return visible_leave

    def seach_temperature(self):
        temperature = 0
        if self.input_daytime == 'daytime':
            temperature = 26
        if self.input_daytime == 'night':
            temperature = 16
        return temperature
```

定义建议类

````py
from chapter8.weather_search import WeatherSearch

class OutAdvice(WeatherSearch):
    def __init__(self, input_daytime):
        WeatherSearch.__init__(self, input_daytime)

    def seach_temperature(self):
        vehicle = ''
        if self.input_daytime == 'daytime':
            vehicle = 'bike'
        if self.input_daytime == 'night':
            vehicle = 'taxi'
        return vehicle

    def out_advice(self):
        visible_leave = self.seach_visibility()
        if visible_leave == 2:
            print(f'The weather is good,suitable for use {self.seach_temperature()}.')
        elif visible_leave == 9:
            print(f'The weather is bad,you should use {self.seach_temperature()}.')
        else:
            print('The weather is beyond my scope,I can not give you any advice')

check = OutAdvice('daytime')
check.out_advice()
````



## 牛刀小试二——判断一棵树是否为二叉搜索树

**问题：**已知一个二叉树的根节点，验证该树是否为二叉搜索树。

**思考点拨：**一个二叉搜索树具有如下特征：

（1）节点的左子树只包括小于当前节点的数。

（2）节点的右子树只包括大于当前节点的数。

（3）所有左子树和右子树自身必须也是二叉搜索树。

````py
class SearchTree(object):
    def __init__(self, small, large):
        self.small = small
        self.large = large

    def valid_bst(self, root, small, large):
        """
        :param root:
        :param small:
        :param large:
        :return:
        """
        if root is None:
            return True
        if self.small >= root.val or self.large <= root.val:
            return False
        return self.valid_bst(root.left, self.small, root.val) and self.valid_bst(root.right, root.val, self.large)

    def is_valid_bst(self, root):
        """
        :param root:
        :return:
        """
        return self.valid_bst(root, self.small, self.large)


class TreeNode(object):
    def __init__(self, x):
        self.val = x
        self.left = None
        self.right = None


a = TreeNode(12)
b = TreeNode(5)
c = TreeNode(18)
d = TreeNode(2)
e = TreeNode(9)
f = TreeNode(15)
g = TreeNode(19)

a.left = b
a.right = c
b.left = d
b.right = e
c.left = f
c.right = g
m = SearchTree(d.val, g.val)
print(f'该树是否是二叉搜索树：{m.is_valid_bst(a)}')
print(f'该树是否是二叉搜索树：{m.is_valid_bst(f)}')
````





# 第九章       异常



## 什么是异常

在学习 Python 编程的过程中，经常会看到一些报错信息，使你编写的程序不能如期工作，如我们前面看到过的 NameError、SyntaxError、TypeError、ValueError 等，这些都是异常。

```py
>>> priint(a)
Traceback (most recent call last):
  File "<pyshell#0>", line 1, in <module>
    priint(a)
NameError: name 'priint' is not defined
```



## 异常处理

try 语句的基本形式为 try/except , try/except 语句用来检测 try 语句块中的错误，从而让 except 语句捕获异常信息并处理。如果你不想在发生异常时结束程序，只需在 try 语句块中捕获异常即可。捕获异常的语法如下：

````py
try:
<语句>     #运行别的代码
except <名字>:
<语句>     #如果在 try 部分引发了异常
````

示例：

````py
def exp_exception(x, y):
    try:
        a = x/y
        print('a=', a)
        return a
    except Exception:
        print('程序出现异常，异常信息：被除数为0')

exp_exception(2, 0)
````



## 抛出异常

Python 使用 raise 语句抛出一个指定异常。我们可以使用类（Exception 的子类）或实例参数调用 raise 语句引发异常。使用类时程序会自动创建实例。例如：

```py
>>> raise Exception
Traceback (most recent call last):
  File "<pyshell#1>", line 1, in <module>
    raise Exception
Exception
>>> raise NameError('This is NameError')
Traceback (most recent call last):
  File "<pyshell#2>", line 1, in <module>
    raise NameError('This is NameError')
NameError: This is NameError
```

Python 重要的内建异常类

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\src=http___upload-images.jianshu.io_upload_images_15892379-fb0d92275e5bf3b9.png&refer=http___upload-images.jianshu.jpg)



## 捕捉多个异常

Python 支持在一个 try/except 语句中处理多个异常，语法如下：

```py
try:
<语句>    #运行别的代码
except <名字1>:
<语句>    #如果在 try 部分引发了 name1 异常
except <名字2>，<数据>:
<语句>    #如果在 try 部分引发了 name2 异常,获得附加异常
```

示例：

```py
def mult_exception(x, y):
    try:
        a = x/y
        b = name
    except ZeroDivisionError:
        print('this is ZeroDivisionError')
    except NameError:
        print('this is NameError')

mult_exception(2, 0)
```



## 使用一个块捕捉多个异常

```py
def model_exception(x, y):
    try:
        b = name
        a = x/y
    except (ZeroDivisionError, NameError, TypeError):
        print('one of ZeroDivisionError or NameError or TypeError happened')

model_exception(2,0)
```



## 捕捉对象

如果希望在 except 子句中访问异常对象本身，也就是看到一个异常对象真正的异常信息，而不是输出自己定义的异常信息，可以使用         as e 的形式，我们称之为捕捉对象。示例如下：

```py
def model_exception(x, y):
    try:
        b = name
        a = x/y
    except (ZeroDivisionError, NameError, TypeError) as e:
        print(e)

model_exception(2, 0)
```



## 全捕捉

```py
def model_exception(x, y):
    try:
        a = x/y
        b = name
    except (ZeroDivisionError, NameError, TypeError) as e:
        print(e)

model_exception(2, '')

执行结果如下：
unsupported operand type(s) for /: 'int' and 'str'
```

由结果看到，这里抛出的信息并不像我们之前看到的那样，带有明显的 Error 关键字或异常词。此处只是告知不支持的操作类型。



## 异常中的 else

异常为我们提供了 try..except...else 语句实现该功能，语法如下：

```py
try:
<语句>       #运行别的代码
except <名字1>:
<语句>       #如果在 try 部分引发了异常1
except <名字2>，<数据>:
<语句>       #如果在 try 部分引发了异常2
else:
<语句>       #如果没有发生异常
```

示例：

````py
def model_exception(x, y):
    try:
        a = x/y
    except:
        print('Error happened')
    else:
        print('It went as expected')

model_exception(2, 1)
````



## 自定义异常

```py
class MyError(Exception):
    def __init__(self):
        pass

    def __str__(self):
       return 'this is self define error'


def my_error_test():
    try:
        raise MyError()
    except MyError as e:
        print('exception info:', e)

my_error_test()

执行结果如下：
exception info: this is self define error
```



## finally 子句

Python 中的 finally 子句需要和 try 子句一起使用，组成 try/finally 的语句形式，try/finally 语句无论发生异常与否都将执行最后的代码。

````py
def use_finally(x, y):
    try:
        a = x/y
    finally:
        print('No matter what happened,I will show in front of you')

use_finally(2, 0)

执行结果如下：
No matter what happened,I will show in front of you
Traceback (most recent call last):
  File "C:\Users\FY\Desktop\Python练习\python3.8sourcecode\chapter9\use_finally.py", line 8, in <module>
    use_finally(2, 0)
  File "C:\Users\FY\Desktop\Python练习\python3.8sourcecode\chapter9\use_finally.py", line 3, in use_finally
    a = x/y
ZeroDivisionError: division by zero
````

try、except、else 和 finally 可以组合使用，但要记得 else 在 except 之后，finally 在 except 和 else 之后。示例：

````py
def use_finally(x, y):
    try:
        a = x/y
    except ZeroDivisionError:
        print('Some bad thing happened:division by zero')
    finally:
        print('No matter what happened,I will show in front of you')

use_finally(2, 0)

执行结果如下：
Some bad thing happened:division by zero
No matter what happened,I will show in front of you
````



## 异常和函数

异常与函数能够很自然地一起工作。如果异常在函数内引发而不被处理，就会传播至函数调用的地方。如果异常在函数调用的地方也没有被处理，就会继续传播，一直到达主程序。如果在主程序也没有做异常处理，异常就会被 Python 解释器捕获，输出一个错误信息，然后退出程序。

```py
def division_fun(x, y):
    return x / int(y)

def exp_fun(x, y):
    return division_fun(x, y) * 10

def main(x, y):
    exp_fun(x, y)

main(2,0)

执行结果如下：
Traceback (most recent call last):
  File "C:\Users\FY\Desktop\Python练习\python3.8sourcecode\chapter9\division_fun.py", line 13, in <module>
    main(2,0)
  File "C:\Users\FY\Desktop\Python练习\python3.8sourcecode\chapter9\division_fun.py", line 10, in main
    exp_fun(x, y)
  File "C:\Users\FY\Desktop\Python练习\python3.8sourcecode\chapter9\division_fun.py", line 6, in exp_fun
    return division_fun(x, y) * 10
  File "C:\Users\FY\Desktop\Python练习\python3.8sourcecode\chapter9\division_fun.py", line 2, in division_fun
    return x / int(y)
ZeroDivisionError: division by zero
```



## 牛刀小试——正常数和异常数

**题目要求：**对给定的数组，前后两个数组相除，若被除数为0，则通过自定义异常打印出异常信息，并加入异常数数组中，若被除数不为0，则为正常数，加入正常数数组中。最后打印出正常数和异常数。

**思考点拨：**

（1）for 循环取得前后两个数。

（2）对除法做异常捕获。

（3）定义正常数数组，走正常逻辑通过的数组加入正常数数组中。定义异常数数组，被异常捕获后，调用自定义异常，返回异常数值和异常信息。

````py
num_list = [5, 0, 73, 0, 16]


class ExceptionNum(object):
    def __init__(self):
        pass

    @staticmethod
    def num_operation():
        # 正常数数组
        normal_num_list = list()
        # 异常数数组
        exp_num_list = list()
        for item in range(num_list.__len__()):
            if item == num_list.__len__() - 1:
                divisor_num, dividend_num = num_list[item], num_list[item]
            else:
                # divisor_num除数, dividend_num被除数
                divisor_num, dividend_num = num_list[item + 1], num_list[item]
            try:
                divisor_num / dividend_num
                rt_str = '第' + str(item + 1) + '个是正常数，值：' + str(num_list[item])
                normal_num_list.append(rt_str)
            except ZeroDivisionError as ex:
                exp_num = SelfDefineError(num_list[item]).__int__()
                rt_str = '第' + str(item + 1) + '个是异常数，值：' + str(exp_num)
                exp_num_list.append(rt_str)
                print(SelfDefineError(num_list[item]).__str__())

        return normal_num_list, exp_num_list


class SelfDefineError(Exception):
    def __init__(self, num):
        self.num = num

    def __str__(self):
        return 'error info:The dividend num equals zero.'

    def __int__(self):
        return self.num

if __name__ == "__main__":
    normal_num_list, exp_num_list = ExceptionNum().num_operation()
    print(f'正常数数组：{normal_num_list}')
    print(f'异常数数组：{exp_num_list}')
````





# 第十章      日期和时间



## 日期和时间



### 时间戳

通常，时间戳表示从1970年1月1日00时00分00秒开始按秒计算的偏移量，也就是从1970年01月01日00时00分00秒（北京时间 1970年01月01日08时00分00秒）起到现在的总毫秒数。



### 时间格式化符号

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\时间和日期.png)



### struct_time 元组

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\struct_time.png)



## time 模块



### time() 函数

time() 函数的语法格式如下：

```py
time.time()
```

time() 函数 用于返回当前时间的时间戳（北京时间 1970年01月01日08时00分00秒起到现在的总毫秒数）。

```py
import time
print(f'当前时间的时间戳：{time.time()}')
执行结果如下：
当前时间的时间戳：1632398919.1479697
```



### strftime() 函数

strftime() 函数的语法格式如下：

```py
time.strftime(format[,t])
```

strftime() 函数用于接收时间元组，并返回可读字符串表示的当地时间，格式由参数 format 决定。该函数的使用示例如下：

```py
import time
t = (2019, 9, 15, 19, 50, 38, 6, 48, 0)
t = time.mktime(t)
print(time.strftime('%b %d %Y %H:%M:%S', time.gmtime(t)))
执行结果如下：
Sep 15 2019 11:50:38
```



### strptime() 函数

strptime() 函数的语法格式如下：

````py
time.strptime(string[,format])
````

此语法中，time 指的是 time 模块，string 是指时间字符串，format 是指格式化字符串。strptime() 函数用于根据指定的格式把一个时间字符串解析为时间元组，strptime() 函数返回的是 struct_time 对象。该函数的使用示例如下：

````py
import time
struct_time = time.strptime("11 Mar 18", "%d %b %y")
print(f'returned tuple: {struct_time}')
执行结果如下：
returned tuple: time.struct_time(tm_year=2018, tm_mon=3, tm_mday=11, tm_hour=0, tm_min=0, tm_sec=0, tm_wday=6, tm_yday=70, tm_isdst=-1)
````



### localtime() 函数

localtime() 函数的语法格式如下：

```py
time.localtime([secs])
```

此语法中,time指的是 time 模块，secs 是指转换为 time.struct_time 类型的对象的秒数。localtime() 函数的作用是格式化时间戳为本地时间。如果 secs 参数为传入，就以当地时间为转换标准。该函数返回 time.struct_time 类型的对象（struct_time 是在 time 模块中定义的表示时间的对象）。该函数的使用示例如下：

```py
import time
print(f'time.localtime():{time.localtime()}')
执行结果如下：
time.localtime():time.struct_time(tm_year=2021, tm_mon=9, tm_mday=23, tm_hour=20, tm_min=52, tm_sec=12, tm_wday=3, tm_yday=266, tm_isdst=0)
```



### sleep() 函数

sleep() 函数的语法格式如下：

````py
time.sleep(secs)
````

此语法中，time 指的是 time 模块，secs 是指推迟执行的秒数。sleep() 函数用于推迟调用线程的运行，可通过参数 secs 指定进程挂起的时间。该函数没有返回值。

```py
import time
print(f'Start : {time.ctime()}')
time.sleep(5)
print(f'End : {time.ctime()}')
执行结果如下：
Start : Thu Sep 23 20:55:56 2021
End : Thu Sep 23 20:56:01 2021
```



### gmtime() 函数

gmtime() 函数的语法格式如下：

```py
time.gmtime([secs])
```

此语法中，time 指的是 time 模块，secs 是指转换为 time.struct_time 类型的对象的秒数。gmtime() 函数用于将一个时间戳转换为UTC时区（0时区）的 struct_time，可选的参数 secs 表示从1970年01月01日到现在的秒数。gmtime() 函数的默认值为 time.time()，函数返回 time.struct_time 类型的对象（struct_time 是在 time 模块中定义的表示时间的对象。该函数的使用示例如下：

````py
import time
print(f'time.gmtime():{time.gmtime()}')
执行结果如下：
time.gmtime():time.struct_time(tm_year=2021, tm_mon=9, tm_mday=23, tm_hour=13, tm_min=2, tm_sec=59, tm_wday=3, tm_yday=266, tm_isdst=0)
````



### mktime() 函数

mktime() 函数的语法格式如下：

````py
time.mktime(t)
````

此语法中，time 指的是 time 模块，t 是指结构化的时间或完整的9位元组元素。mktime() 函数用于执行与 gmtime() 、localtime() 相反的操作，接收 struct_time 对象作为参数，返回用秒数表示时间的浮点数。如果输入的值不是合法时间，就会触发OverflowError 或 ValueError 异常。该函数使用示例如下：

````py
import time
t = (2019, 9, 15, 17, 35, 38, 6, 48, 0)
print(f'time.mktime(t):{time.mktime(t)}')
执行结果如下：
time.mktime(t):1568540138.0
````



### asctime() 函数

asctime() 函数的语法格式如下：

````py
time.asctime([t])
````

此语法中， time 指的是 time 模块，t 是指完整的9位元组元素或通过函数 gmtime() 、localtime() 返回的时间值。asctime() 函数用于接收时间元组并返回一个可读的形式，例如，Sun Sep 15 16:15:23 2019（2019年09月15日  周日16时15分23秒），是一个由24个字符组成的字符串。该函数的使用示例如下：

```py
import time
t = time.localtime()
print(f'time.asctime(t):{time.asctime(t)}')
执行结果如下：
time.asctime(t):Thu Sep 23 21:26:19 2021
```



### ctime() 函数

ctime() 函数的语法格式如下：

````py
time.ctime([secs])
````

此语法中，time 指的是 time 模块，secs 是指要转换为字符串时间的秒数。ctime() 函数用于把一个时间戳（按秒计算的浮点数）转化为 time.asctime() 的形式。。如果未指定参数 secs 或参数为 None，就会默认将 time.time() 作为参数。ctime 的作用相当于 asctime(localtime(secs))。ctime() 函数返回一个时间字符串。该函数的使用示例如下：

````py
import time
print(f'time.ctime():{time.ctime()}')
执行结果如下：
time.ctime():Thu Sep 23 21:39:47 2021
````



### 三种时间格式转化

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\三种时间格式化转化.png)

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\三种时间格式转化2.png)



## datetime 模块

datetime 模块定义了以下5个类：

datetime.date：表示日期的类。常用的属性有year、month、day。

datetime.time：表示时间的类。常用的属性有hour、minute、second、microsecond。

datetime.datetime：表示日期时间。

datetime.timedelta：表示时间间隔，即两个时间点之间的长度。

datetime.tzinfo：与时区有关的信息。



datetime.datetime 类中有以下方法。

**（1）now()**

now() 方法的语法格式如下：

```py
datetime.datetime.now([tz])
```

此语法中，datetime.datetime 指的是 datetime.datetime 类，如果提供了参数 tz，就获取 tz 参数所指时区的本地时间。now() 方法返回一个 datetime 对象。now() 方法返回一个 datetime 对象。该方法的使用示例如下：

````py
import datetime
print(f'now is:{datetime.datetime.now()}')
执行结果如下：
now is:2021-09-23 22:08:37.524350
````



**（2）today()**

today() 方法的语法格式如下：

```py
datetime.datetime.today()
```

此语法中，datetime.datetime 指的是 datetime.datetime 类。today() 方法返回一个表示当前本地时间的 datetime 对象。该方法的使用示例如下：

````py
import datetime
print(f'today is:{datetime.datetime.today()}')
执行结果如下：
today is:2021-09-23 22:12:50.005579
````



**（3）strptime()**

strptime() 方法的语法格式如下：

````py
datetime.datetime.strptime(date_string,format)
````

此语法中，datetime.datetime 指的是 datetime.datetime 类，date_string 是指日期字符串，format 为格式化方式。strptime() 方法用于将格式字符串转换为 datetime 对象。strptime() 方法返回一个 datetime 对象。该方法的使用示例如下：

````py
import datetime
dt = datetime.datetime.now()
old_dt = str(dt)
new_dt = dt.strptime(old_dt, '%Y-%m-%d %H:%M:%S.%f')
print(f"old_dt is:{old_dt}")
print(f"old_dt type is:{type(old_dt)}")
print(f"new_dt is:{new_dt}")
print(f"new_dt type is:{type(new_dt)}")

执行结果如下：
old_dt is:2021-09-23 22:18:06.471858
old_dt type is:<class 'str'>
new_dt is:2021-09-23 22:18:06.471858
new_dt type is:<class 'datetime.datetime'>
````



**（4）strftime()**

strftime() 方法的语法格式如下：

```py
datetime.datetime.strftime(format)
```

此语法中，datetime.datetime 指的是 datetime.datetime 类，format为格式化方式。strftime() 方法用于将 datetime 对象转换为格式字符串。strftime() 方法返回一个字符串对象。该方法的使用示例如下：

```py
import datetime
dt = datetime.datetime.now()
new_dt = dt.strftime('%Y-%m-%d %H:%M:%S')
print(f"dt is: {dt}")
print(f"dt type is:{type(dt)}")
print(f"new_dt is:{new_dt}")
print(f"new_dt type is:{type(new_dt)}")

执行结果如下：
dt is: 2021-09-23 22:22:56.537122
dt type is:<class 'datetime.datetime'>
new_dt is:2021-09-23 22:22:56
new_dt type is:<class 'str'>
```



**（5）datetime.utcnow()**

utcnow() 方法的语法格式如下：

```py
datetime.datetime.utcnow()
```

此语法中，datetime.datetime 指的是 datetime.datetime 类。utcnow() 方法返回一个当前UTC时间的 datetime 对象。该方法的使用示例如下：

```py
import datetime
print(f'utcnow is:{datetime.datetime.utcnow()}')
执行结果如下：
utcnow is:2021-09-23 14:27:22.358282
```



**（6）fromtimestamp()**

fromtimestamp() 方法的语法格式如下：

````py
datetime.datetime.fromtimestamp(timestamp[,tz])
````

此语法中，datetime.datetime 指的是 datetime.datetime 类，参数 tz 指定时区信息。fromtimestamp() 方法用于根据时间戳创建一个 datetime 对象。fromtimestamp() 方法返回一个 datetime 对象。

```py
import datetime
import time

print(f'fromtimestamp is:{datetime.datetime.fromtimestamp(time.time())}')
执行结果如下：
fromtimestamp is:2021-09-23 22:33:09.501315
```



**（7）utcfromtimestamp()**

utcfromtimestamp() 方法的语法格式如下：

````py
datetime.datetime.utcfromtimestamp(timestamp)
````

datetime.datetime 指的是 datetime.datetime 类，timestamp 是指时间戳。utcfromtimestamp() 方法用于根据时间戳创建一个 datetime 对象。utcfromtimestamp() 方法返回一个 datetime 对象。

````py
import datetime, time

print(f'utcfromtimestamp is:{datetime.datetime.utcfromtimestamp(time.time())}')
执行结果如下：
utcfromtimestamp is:2021-09-23 14:37:24.831532
````



## 日历模块



**（1）calendar.calendar(year,w=2,l=1,c=6)**

该函数返回一个多行字符串格式的 year 年历，3一个月一行，间隔距离为 c，每日宽度间隔为 w 字符。每行长度为21 * w+18+2 * c。1是每星期的行数。

**（2）calendar.firstweekday()**

返回当前每周起始日期的设置。默认情况下，首次载入 calendar 模块时返回0，即星期一。

**（3）calendar.isleep(year)**

如果是闰年就返回 True，否则返回 False。

**（4）calendar.leapdays(y1,y2)**

返回在 y1,y2 两年之间的闰年总数

**（5）calendar.month(year,month,w=2,l=1)**

返回一个多行字符串格式的 year 年 month 月日历，两行标题，一周一行。每日宽度间隔为 w 字符。每行长度为 7*w+6。1是每星期的行数。

**（6）calendar.monthcalendar(year,month)**

返回一个整数的单层嵌套列表。每个子列表装载代表一个星期的整数。year 年 month 月外的日期都设为0；范围内的日期由该月第几日表示，从1开始。

**（7）calendar.monthrange(year,month)**

返回两个整数。第一个是该月星期几的日期码，第二个是该月的日期码。日从0（星期一）到6（星期日），月从1到12。

**（8）calendar.prcal(year,w=2,l=1,c=6)**

相当于print(calendar.calendar(year,w,l,c))。

**（9）calendar.promonth(year,month,w,=2,l=1)**

相当于print(calendar.calendar(year,month,w,l))。

**（10）calendar.setfirstweekday(weekday)**

设置每周的起始日期码，0（星期一）到6（星期日）。

**（11）calendar.timegm(tupletime)**

和 time.gmtime 相反，接收一个时间元组形式，返回该时刻的时间戳。

**（12）calendar.weekday(year,month,day)**

返回给定日期的日期码，0（星期一）到6（星期日）。月份为1（1月）到12（12月）。



## 牛刀小试——时间大杂烩

自定义函数，使用 Time、Calendar 和 datetime 模块获取当前日期前后 N 天或 N 月的日期

```py
import calendar
import datetime
import time

year = time.strftime("%Y", time.localtime())
mon = time.strftime("%m", time.localtime())
day = time.strftime("%d", time.localtime())
hour = time.strftime("%H", time.localtime())
min = time.strftime("%M", time.localtime())
sec = time.strftime("%S", time.localtime())


def today():
    """
    get today,date format="YYYY-MM-DD"
    :return:
    """
    return datetime.date.today()


def todaystr():
    """
    get date string, date format="YYYYMMDD"
    :return:
    """
    return year + mon + day


def date_time():
    """
    get datetime,format="YYYY-MM-DD HH:MM:SS"
    :return:
    """
    return time.strftime("%Y-%m-%d %H:%M:%S", time.localtime())


def datetimestr():
    """
    get datetime string
    date format="YYYYMMDDHHMMSS"
    :return:
    """
    return year + mon + day + hour + min + sec


def get_day_of_day(n=0):
    """
    if n>=0,date is larger than today
    if n<0,date is less than today
    date format = "YYYY-MM-DD"
    :param n:
    :return:
    """
    if n < 0:
        n = abs(n)
        return datetime.date.today() - datetime.timedelta(days=n)
    else:
        return datetime.date.today() + datetime.timedelta(days=n)


def get_days_of_month(year, mon):
    """
    get days of month
    :param year:
    :param mon:
    :return:
    """
    return calendar.monthrange(year, mon)[1]


def get_firstday_of_month(year, mon):
    """
    get the first day of month
    date format = "YYYY-MM-DD"
    :param year:
    :param mon:
    :return:
    """
    days = "01"
    if int(mon) < 10:
        mon = "0" + str(int(mon))
    arr = (year, mon, days)
    return "-".join("%s" % i for i in arr)


def get_lastday_of_month(year, mon):
    """
    get the last day of month
    date format = "YYYY-MM-DD"
    :param year:
    :param mon:
    :return:
    """
    days=calendar.monthrange(year, mon)[1]
    mon = addzero(mon)
    arr = (year, mon, days)
    return "-".join("%s" % i for i in arr)


def get_firstday_month(n=0):
    """
    get the first day of month from today
    n is how many months
    :param n:
    :return:
    """
    (y, m, d) = getyearandmonth(n)
    d = "01"
    arr = (y, m, d)
    return "-".join("%s" % i for i in arr)


def get_lastday_month(n=0):
    """
    get the last day of month from today
    n is how many months
    :param n:
    :return:
    """
    return "-".join("%s" % i for i in getyearandmonth(n))


def getyearandmonth(n=0):
    """
    get the year,month,days from today
    befor or after n months
    :param n:
    :return:
    """
    thisyear = int(year)
    thismon = int(mon)
    totalmon = thismon + n
    if n >= 0:
        if totalmon <= 12:
            days = str(get_days_of_month(thisyear, totalmon))
            totalmon = addzero(totalmon)
            return year, totalmon, days
        else:
            i = totalmon // 12
            j = totalmon % 12
            if j == 0:
                i -= 1
                j = 12
            thisyear += i
            days = str(get_days_of_month(thisyear, j))
            j = addzero(j)
            return str(thisyear), str(j), days
    else:
        if 0 < totalmon < 12:
            days = str(get_days_of_month(thisyear,totalmon))
            totalmon = addzero(totalmon)
            return year, totalmon, days
        else:
            i = totalmon // 12
            j = totalmon % 12
            if j == 0:
                i -= 1
                j = 12
            thisyear += i
            days = str(get_days_of_month(thisyear, j))
            j = addzero(j)
            return str(thisyear), str(j), days


def addzero(n):
    """
    add 0 before 0-9
    return 01-09
    :param n:
    :return:
    """
    nabs = abs(int(n))
    if nabs < 10:
        return "0" + str(nabs)
    else:
        return nabs


def get_today_month(n=0):
    """
    获取当前日期前后N月的日期
    if n>0, 获取当前日期前N月的日期
    if n<0, 获取当前日期后N月的日期
    date format = "YYYY-MM-DD"
    :param n:
    :return:
    """
    (y, m, d) = getyearandmonth(n)
    arr = (y, m, d)
    if int(day) < int(d):
        arr = (y, m, day)
    return "-".join("%s" % i for i in arr)


def get_firstday_month(n=0):
    (y, m, d) = getyearandmonth(n)
    arr = (y, m, '01')
    return "-".join("%s" % i for i in arr)


def main():
    print(f'today is:{today()}')
    print(f'today is:{todaystr()}')
    print(f'the date time is:{date_time()}')
    print(f'data time is:{datetimestr()}')
    print(f'2 days after today is:{get_day_of_day(2)}')
    print(f'2 days before today is:{get_day_of_day(-2)}')
    print(f'2 months after today is:{get_today_month(2)}')
    print(f'2 months before today is:{get_today_month(-2)}')
    print(f'2 months after this month is:{get_firstday_month(2)}')
    print(f'2 months before this month is:{get_firstday_month(-2)}')


if __name__ == "__main__":
    main()
```





# 第十一章       正则表达式



## 认识正则表达式

正则表达式是一个特殊的字符序列，它能帮助你方便的检查一个字符串是否与某种模式匹配。从而达到快速检索或替换符合某个模式、规则的文本。

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\正则表达式.png)

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\正则表达式1.png)

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\正则表达式2.png)



## re 模块



### re.match 函数

re.match 尝试从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match()就返回none。该函数语法如下：

```py
re.match(pattern,string,flags=0)
```

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\re.match.png)

示例如下：

```py
import re

# 在起始位置匹配
print(re.match('hello', 'hello world').span())
# 不在起始位置匹配
print(re.match('world', 'hello world'))
执行结果如下：
(0, 5)
None
```



### re.search 函数

re.search 扫描整个字符串并返回第一个成功的匹配。该函数语法如下：

```py
re.search(pattern,string,flags=0)
```

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\re.search.png)

示例如下：

```py
import re

# 在起始位置匹配
print(re.search('hello', 'hello world').span())
# 不在起始位置匹配
print(re.search('world', 'hello world').span())
执行结果如下：
(0, 5)
(6, 11)
```



### re.match 与 re.search 的区别

re.match只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回None；而re.search匹配整个字符串，直到找到一个匹配。



### re.compile 函数

compile 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用。语法格式为：

```py
re.compile(pattern[, flags])
```

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\re.compile.png)

示例如下：

```py
>>>import re
>>> pattern = re.compile(r'\d+')                    # 用于匹配至少一个数字
>>> m = pattern.match('one12twothree34four')        # 查找头部，没有匹配
>>> print m
None
>>> m = pattern.match('one12twothree34four', 2, 10) # 从'e'的位置开始匹配，没有匹配
>>> print m
None
>>> m = pattern.match('one12twothree34four', 3, 10) # 从'1'的位置开始匹配，正好匹配
>>> print m                                         # 返回一个 Match 对象
<_sre.SRE_Match object at 0x10a42aac0>
>>> m.group(0)   # 可省略 0
'12'
>>> m.start(0)   # 可省略 0
3
>>> m.end(0)     # 可省略 0
5
>>> m.span(0)    # 可省略 0
(3, 5)
```



### findall

在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果没有找到匹配的，则返回空列表。**注意：** match 和 search 是匹配一次 findall 匹配所有。语法格式为：

```py
findall(string[, pos[, endpos]])
```

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\findall.png)

示例如下：

```py
import re
 
pattern = re.compile(r'\d+')   # 查找数字
result1 = pattern.findall('runoob 123 google 456')
result2 = pattern.findall('run88oob123google456', 0, 10)
 
print(result1)
print(result2)
```



### re.finditer

和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回。

````py
re.finditer(pattern, string, flags=0)
````

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\re.finditer.png)

示例如下：

```py
import re
 
it = re.finditer(r"\d+","12a32bc43jf3") 
for match in it: 
    print (match.group() )
```



### re.split

split 方法按照能够匹配的子串将字符串分割后返回列表，它的使用形式如下：

```py
re.split(pattern, string[, maxsplit=0, flags=0])
```

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\re.split.png)

示例如下：

```py
>>>import re
>>> re.split('\W+', 'runoob, runoob, runoob.')
['runoob', 'runoob', 'runoob', '']
>>> re.split('(\W+)', ' runoob, runoob, runoob.') 
['', ' ', 'runoob', ', ', 'runoob', ', ', 'runoob', '.', '']
>>> re.split('\W+', ' runoob, runoob, runoob.', 1) 
['', 'runoob, runoob, runoob.']
 
>>> re.split('a*', 'hello world')   # 对于一个找不到匹配的字符串而言，split 不会对其作出分割
['hello world']
```



### 检索和替换

Python 的 re 模块提供了re.sub用于替换字符串中的匹配项。语法：

```py
re.sub(pattern, repl, string, count=0, flags=0)
```

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\re.sub.png)

示例如下：

```py
import re
 
phone = "2004-959-559 # 这是一个国外电话号码"
 
# 删除字符串中的 Python注释 
num = re.sub(r'#.*$', "", phone)
print "电话号码是: ", num
 
# 删除非数字(-)的字符串 
num = re.sub(r'\D', "", phone)
print "电话号码是 : ", num
```



## 牛刀小试——匹配比较

给定一个字符串，分别用各种不同的匹配方式对字符串进行匹配，比较各种匹配结果的异同。示例如下：

````py
import re


# 匹配目标
def target_match(content):
    result = re.match('^Hello\s(\d+)\sWorld', content)
    return result, result.group(), result.group(1), result.span()


# 通用匹配
def gena_match(content):
    result = re.match('^Hello.*Demo$', content)
    return result, result.group(), result.span()


# 贪婪匹配
def greed_match(content):
    result = re.match('^He.*(\d+).*Demo$', content)
    return result, result.group(1)


# 非贪婪匹配
def un_greed_match(content):
    result = re.match('^He.*(\d+).*Demo$', content)
    return result, result.group(1)


if __name__ == "__main__":
    con_match = 'Hello 1234567 World_This is a Regex Demo'
    target_match(con_match)
    gena_match(con_match)
    greed_match(con_match)
    result_v, result_group = un_greed_match(con_match)
    print(result_v, result_group)
````



# 第十二章       文件操作



## 打开文件

### open 函数

你必须先用Python内置的open()函数打开一个文件，创建一个file对象，相关的方法才可以调用它进行读写。语法：

```p
file object = open(file_name [, access_mode][, buffering])
```

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\open函数.png)

示例如下：

```py
path='d/test.txt'
f_name=open(path)
print(f_name.name)
执行结果如下：
d:/test.txt
```



### 文件模式

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\文件模式.png)

下图很好的总结了这几种模式：

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\总结文件模式.png)



## 基本文件方法



### 读与写

open 函数返回的是一个File 对象，有了 File 对象，就可以开始读取内容。如果希望将整个文件的内容读取为一个字符串值，可以使用 File 对象的 read() 方法。Read() 方法从一个打开的文件中读取字符串。需要注意，Python 字符串可以是二进制数据，而不仅仅是文字。语法如下：

```py
fileObject.read([count]);
```

fileObject 为 open 函数返回的 File 对象，count 参数是从已打开的文件中读取的字节计数。该方法从文件的开头开始读入，如果没有传入 count，就会尝试尽可能多地读取内容，很可能一直读取到文件末尾。

```py
path = './test2.txt'

f_name = open(path,'r')
print(f'read result:{f_name.read(12)}')
```



在 Python 中，用write() 方法向一个文件写入数据。write() 方法可将任何字符串写入一个打开的文件。需要注意，Python 字符串可以是二进制数据，而不仅仅是文字。write() 方法不会再字符串结尾添加换行符（'\n'），语法如下：

````py
fileObject.write(string);
````

示例如下：

```py
path = './test.txt'

f_name = open(path, 'w')
print(f"write length:{f_name.write('Hello world!')}")
```



写文件（write）方法的处理方式是：将覆盖原有文件，从头开始，每次写入都覆盖前面所有内容，就像用一个新值覆盖一个变量的值。若需要在当前文件的字符串后追加字符，该怎么办呢？可以将第二个参数 w 更换为 a，即以追加模式打开文件，例如：

````py
path = './test.txt'

f_name = open(path, 'w')
print(f"write length:{f_name.write('Hello world!')}")
f_name = open(path, 'r')
print(f'read result:{f_name.read()}')

f_name = open(path, 'a')
print(f"add length:{f_name.write('welcome!')}")
f_name = open(path, 'r')
print(f'read result:{f_name.read()}')
````



### 读写行

我们目前对文件的读操作是按字节读或整个读取，而写操作是全覆盖写或追加，这样的操作在实际应用中很不实用。Python 为我们提供了 readline()、readlines() 和 writelines() 等方法用于行操作，例如：

```py
path = './test.txt'
f_name = open(path, 'w')
f_name.write('Hello world!\n')
f_name = open(path, 'a')
f_name.write('welcome!')
f_name = open(path, 'r')
print(f'readline result:{f_name.readline()}')
print(f'readline result:{f_name.readlines()}')
```

writelines 方法和 readlines 方法相反，传给它一个字符串列表（任何序列或可迭代对象），它会把所有字符串写入文件。如果没有 writeline 方法，那么可以使用 write 方法代替这个方法的功能。



### 关闭文件

一般情况下，一个文件对象在退出程序后会自动关闭，但是为了安全起见，还是要显式地写一个close 方法关闭文件。一般显式关闭文件读或写的操作如下：

````py
path = './test.txt'
f_name = open(path, 'w')
print(f"write length:{f_name.write('Hello world!')}")
f_name.close()
````

Python 中引入了 with 语句自动帮我们调用 close 方法。可以使用 with 语句将上面的程序更改为：

```py
path = './test.txt'
with open(path, 'w') as f:
    f_name = open(path, 'w')
    print(f"write length:{f_name.write('Hello world!')}")
```



### 文件重命名

Python 的 os 模块为我们提供了 rename 方法，即文件重命名。使用这个方法需要导入 os 模块。rename 方法的语法如下：

```py
os.rename(current_file_name,new_file_name)
```

使用示例如下：

```py
import os

open('d:/test.txt', 'w')
os.rename('d:/test.txt', 'd:/test2.txt')
```



### 删除文件

Python 的 os 模块为我们提供了 remove 方法，即删除文件。使用这个方法需要导入 os 模块。remove 方法的语法如下：

```py
os.remove(file_name)
```

使用示例如下：

```py
import os

try:
    print(f"remove result:{os.remove('test2.txt')}")
except Exception:
    print('file not found')
```



## 对文件内容进行迭代



### 按字节处理

在 while 循环中，read() 方法是最常见的对文件内容进行迭代的方法，例如：

```py
path = './test.txt'
f_name = open(path, 'w')
print(f"write length:{f_name.write('Hello')}")
f_name = open(path)
c_str = f_name.read(1) 
while c_str :
    print(f'read str is:{c_str}')
    c_str = f_name.read(1)
f_name.close()
```

该示例中也使用了赋值表达式，在该示例中，如果变量 c_str 不存在则会被创建，然后将 f_name.read() 的返回值赋值给它。该示例中出现重复代码的使用，可以使用 while true/break 语句结构进一步优化。优化代码如下：

```py
path = './test.txt'
f_name = open(path)
while True:
    c_str = f_name.read(1)
    if not c_str:
        break
    print(f'read str is:{c_str}')
f_name.close()
```



### 按行操作

在实际操作中，处理文件是可能需要对文件的行进行迭代，而不是单个字符。此时可以使用和处理字符一样的方式，只不过要使用readline 方法，例如：

````py
path = './test.txt'
f_name = open(path)
while True:
    line = f_name.readline(1)
    if not line:
        break
    print(f'read line is:{line}')
f_name.close()
````



### 使用 fileinput 实现懒加载式迭代

在 Python 中，for 循环是优先考虑的选择，使用 for 循环意味着可以对任务进行分割操作，而不是一步到位。按行读取文件时，若能使用for 循环，则称之为懒加载式迭代，殷伟在操作过程中只读取实际需要的文件部分。使用 fileinput 需要导入 fileinput 模块，例如：

```py
import fileinput

path = './test.txt'
for line in fileinput.input(path):
    print(f'line is:{line}')
```



### 文件迭代器

在 Python 2.2 版本开始，文件对象时可迭代的，这意味着可以直接在 for 循环中使用文件对象，从而进行迭代，例如：

```py
path = './test.txt'
f_name = open(path)
for line in f_name:
    print(f'line is:{line}')
f_name.close()
```



## StringIO 函数

数据的读取除了通过文件外，还可以在内存中进行。Python 中的 io 模块提供了对 str 操作的 StringIO 函数。要把 str 写入StringIO，我们需要创建一个 StringIO ，然后像文件一样写入。操作示例如下：

````py
from io import StringIO

io_val = StringIO()
io_val.write('hello')
print(f'say:{io_val.getvalue()}')
````

由执行结果看到，getvalue() 方法用于获得写入后的 str。要读取 StringIO，还可以用 str 初始化 StringIO，然后像文件一样读取。操作示例如下：

```py
from io import StringIO

io_val = StringIO('Hello\nWorld!\nWelcome!')
while True:
    line = io_val.readline()
    if line == '':
        break
    print(f'line value:{line.strip()}')
```



## 序列化与反序列化

在运行程序的过程中，所有变量都在内存中，我们把变量从内存中变成可存储或传输的过程称为序列化。我们可以把序列化后的内容写入磁盘，或者通过网络传输带别的机器上。反过来，把变量内容从序列化的对象重新读到内存里程为反序列化。序列化是指将数据结构或对象转换成二进制串的过程。反序列化是指将序列化过程中生成的二进制串转换成数据结构或对象的过程。下面我们介绍 Python 中序列化和反序列化的方式。

### 一般序列化与反序列化

Python 的 pickle 模块实现的序列化操作，能够将程序中运行的对象信息保存到文件中，从而永久存储。通过 pickle 模块的反序列化操作，能够从文件中创建上一次程序保存的对象。pickle 模块的基本接口如下：

```py
pickle.dump(obj,file,[,protocol])
```

例如：

```py
import pickle

d = dict(name='xiao zhi', num=1002)
print(pickle.dumps(d))
```

pickle.dumps() 方法把任意对象序列化成一个 bytes，然后把这个 bytes 写入文件。也可以使用另一种方法 pickle.dump()，直接把对象序列化后写入一个文件对象中，程序如下：

```py
import pickle

try:
    d = dict(name='xiao zhi', num=1002)
    f_name = open('dump.txt', 'wb')
    pickle.dump(d, f_name)
finally:
    f_name.close()
```

打开 dump.txt 文件，可以看到里面有一堆看不懂的内容，这些都是 python 保存的对象的内部信息。既然已经将内容序列化到文件夹中了，使用文件是就需要把对象从磁盘读到内存。可以先把内容读到一个 bytes，然后用 pickle.loads() 方法反序列化对象；也可以直接用 pickle.load() 方法从一个文件对象中直接反序列化对象。从 dump.txt 文件中将反序列化的内容反序列化的代码如下：

```py
import pickle

try:
    f_name = open('dump.txt', 'rb')
    print(f'load result:{pickle.load(f_name)}')
finally:
    f_name.close()
```



### JSON 序列化与反序列化

JSON（Javascript Object Notation）是一种轻量级的数据交换格式，是基于 ECMAScript 的一个子集。Python 3 中可以使用 json 模块对JSON 数据进行编码和解码，包括以下两个函数。

json,dumps()：对数据进行编码。

json.load()：对数据进行解码。

![](C:\Users\FY\Desktop\Python笔记\Python基础笔记\image\JSON.jpg)

下面是序列化与反序列化的示例：

```py 
import json

data = {'num': 1002, 'name': 'xiao zhi'}
json_str = json.dumps(data)
print(f"Python 原始数据：{data}")
print(f"JSON 对象：{json_str}")
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
import json

data = {'num': 1002, 'name': 'xiao zhi'}

json_str = json.dumps(data)
print(f"Python 原始数据：{data}")
print(f"JSON 对象：{json_str}")

data2 = json.loads(json_str)
print(f"data2['name']: {data2['name']}")
print(f"data2['num']: {data2['num']}")
```



## 牛刀小试——批量更改文件名

编写实现对某个目录文件下的所有文件，包括子目录下的文件和以某些指定后缀结尾的文件，都以另一种指定的命名方式将文件重命名。

**思维点拨：**

（1）文件目录下文件遍历；（2）文件后缀获取；（3）子目录文件遍历。

示例代码如下：

````py
import os
import time


#  批量文件重命名
def batch_rename(path):
    global img_num
    if not os.path.isdir(path) and not os.path.isfile(path):
        return False

    if os.path.isfile(path):
        # 分割出目录与文件
        file_path = os.path.split(path)
        # 分割出文件与文件扩展名
        lists = file_path[1].split('.')
        # 取出后缀名(列表切片操作)
        file_ext = lists[-1]
        img_ext = ['bmp', 'jpeg', 'gif', 'psd', 'png', 'jpg']
        if file_ext in img_ext:
            os.rename(path, file_path[0] + '/' + lists[0] + '_cn.' + file_ext)
            img_num += 1
    elif os.path.isdir(path):
        for item in os.listdir(path):
            # 递归调用
            batch_rename(os.path.join(path, item))


if __name__ == "__main__":
    img_dir = 'F:\\download\\vpn'
    img_dir = img_dir.replace('\\', '/')
    start = time.time()
    img_num = 0
    batch_rename(img_dir)
    print(f'总共处理了 {img_num} 张图片，耗时：{time.time() - start}')
````



# 第十三章       多线程



## 线程和进程

多线程类似于同时执行多个不同程序，多线程运行有如下优点：

- 使用线程可以把占据长时间的程序中的任务放到后台去处理。
- 用户界面可以更加吸引人，这样比如用户点击了一个按钮去触发某些事件的处理，可以弹出一个进度条来显示处理的进度
- 程序的运行速度可能加快
- 在一些等待的任务实现上如用户输入、文件读写和网络收发数据等，线程就比较有用了。在这种情况下我们可以释放一些珍贵的资源如内存占用等等。

线程在执行过程中与进程还是有区别的。每个独立的进程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。

每个线程都有他自己的一组CPU寄存器，称为线程的上下文，该上下文反映了线程上次运行该线程的CPU寄存器的状态。

指令指针和堆栈指针寄存器是线程上下文中两个最重要的寄存器，线程总是在进程得到上下文中运行的，这些地址都用于标志拥有线程的进程地址空间中的内存。

- 线程可以被抢占（中断）。
- 在其他线程正在运行时，线程可以暂时搁置（也称为睡眠） -- 这就是线程的退让。



## _thread 模块

Python 调用 _thread 模块中的 start_new_thread() 函数产生新线程。 _thread 的语法如下：

```py
_thread.start_new_thread(function,args[,kwarg])
```

其中，function 为线程函数；args 为传递给线程函数的参数，必须是 tuple 类型；kargs 为可选参数。 _thread 模块除了产生线程外，还提供基本同步数据结构锁对象（lock object，也叫原语锁、简单锁、互斥锁、互斥量、二值信号量）。同步原语与线程管理是密不可分的。示例如下：

````py
import _thread
from time import sleep
from datetime import datetime

date_time_format = '%y-%M-%d %H:%M:%S'


def date_time_str(date_time):
    return datetime.strftime(date_time, date_time_format)


def loop_one():
    print(f'+++线程一开始于:{date_time_str(datetime.now())}')
    print('+++线程一休眠4秒')
    sleep(4)
    print(f'+++线程一休眠结束，结束于:{date_time_str(datetime.now())}')


def loop_two():
    print(f'***线程二开始时间:{date_time_str(datetime.now())}')
    print('***线程二休眠2秒')
    sleep(2)
    print(f'***线程二休眠结束，结束时间:{date_time_str(datetime.now())}')


def main():
    print(f'------所有线程开始时间:{date_time_str(datetime.now())}')
    _thread.start_new_thread(loop_one, ())
    _thread.start_new_thread(loop_two, ())
    sleep(6)
    print(f'------所有线程结束时间:{date_time_str(datetime.now())}')


if __name__ == '__main__':
    main()
    
执行结果如下：
------所有线程开始时间:21-51-25 10:51:04
***线程二开始时间:21-51-25 10:51:04+++线程一开始于:21-51-25 10:51:04
***线程二休眠2秒+++线程一休眠4秒
***线程二休眠结束，结束时间:21-51-25 10:51:06
+++线程一休眠结束，结束于:21-51-25 10:51:08
------所有线程结束时间:21-51-25 10:51:10
````

_thread 模块提供了简单的多线程机制，两个循环并发执行，总的运行时间为最慢的线程的运行时间（主线程 6s），而不是所有线程的运行时间之和。start_new_thread() 要求至少传两个参数，即是想要运行的函数不要参数，也要传一个空元组。sleep(6) 是让主线程停下来。主线程一旦运行结束，就会关闭运行着的其他两个线程。这可能造成主线程这时就要使用线程锁，主线程可以在两个线程都退出后立即退出。示例如下：

```py
import _thread
from time import sleep
from datetime import datetime 

loops = [4, 2]
date_time_format = '%y-%M-%d %H:%M:%S'


def date_time_str(date_time):
    return datetime.strftime(date_time, date_time_format)


def loop(n_loop, n_sec, lock):
    print(f'线程（{n_loop}）开始执行:{date_time_str(datetime.now())}，先休眠（{n_sec}）秒')
    sleep(n_sec)
    print(f'线程（{n_loop}）休眠结束，结束于:{date_time_str(datetime.now())}')
    lock.release()


def main():
    print('---所有线程开始执行...')
    locks = []
    n_loops = range(len(loops))

    for i in n_loops:
        lock = _thread.allocate_lock()
        lock.acquire()
        locks.append(lock)

    for i in n_loops:
        _thread.start_new_thread(loop, (i, loops[i], locks[i]))

    for i in n_loops:
        while locks[i].locked(): pass

    print(f'---所有线程执行结束:{date_time_str(datetime.now())}')


if __name__ == '__main__':
    main()
    
执行结果如下：
---所有线程开始执行...
线程（0）开始执行:21-59-25 10:59:55，先休眠（4）秒线程（1）开始执行:21-59-25 10:59:55，先休眠（2）秒
线程（1）休眠结束，结束于:21-59-25 10:59:57
线程（0）休眠结束，结束于:21-59-25 10:59:59
---所有线程执行结束:21-59-25 10:59:59
```



## threading 模块与 Thread 类



### threading 模块

_thread 模块不支持守护线程，当主线程退出时，所有子线程无论是否工作，都会被强行退出。threading 模块支持守护线程，守护线程一般是一个等待客户请求的服务器，如果没有客户提出请求，就一直等着。如果设定一个线程为守护线程，就表示这个线程不重要，在进程退出时，不用等待这个线程退出。如果主线程退出时不用等待子线程完成，就要设定这些线程的 daemon 属性，即在线程 Thread.start() 开始前，调用 setDaemon() 函数设定线程的 daemon 标志（Thread.setDaemon(True))，表示这个线程”不重要“。如果一定要等待子线程执行完成再退出主线程，就什么都不用做或显式调用 Thread.setDaemon(False) 以保证 daemon 标志为 False，可以调用 Thread.isDaemon() 函数判断 daemon 标志的值。新的子线程会继承父线程的 daemon 标志，主线程在所有非守护线程退出后才会结束，即进程中没有非守护线程存在时才结束。



### Thread 类

Thread 有很多 _thread 模块里没有的函数，Thread 对象的函数很丰富。下面创建一个 Thread 的实例，传给它一个函数。示例如下：

````py
import threading
from time import sleep
from datetime import datetime
  
loops = [4, 2] 
date_time_format = '%y-%M-%d %H:%M:%S'


def date_time_str(date_time):
    return datetime.strftime(date_time, date_time_format)


def loop(n_loop, n_sec):
    print(f'线程（{n_loop}）开始执行:{date_time_str(datetime.now())}，先休眠（{n_sec}）秒')
    sleep(n_sec)
    print(f'线程（{n_loop}）休眠结束，结束于:{date_time_str(datetime.now())}')


def main():
    print(f'---所有线程开始执行:{date_time_str(datetime.now())}')
    threads = []
    n_loops = range(len(loops))

    for i in n_loops:
        t = threading.Thread(target=loop, args=(i, loops[i]))
        threads.append(t)

    for i in n_loops:      # start threads
        threads[i].start()

    for i in n_loops:      # wait for all
        threads[i].join()    # threads to finish

    print(f'---所有线程执行结束于:{date_time_str(datetime.now())}')


if __name__ == '__main__':
    main()

执行结果如下：
---所有线程开始执行:21-46-25 11:46:10
线程（0）开始执行:21-46-25 11:46:10，先休眠（4）秒线程（1）开始执行:21-46-25 11:46:10，先休眠（2）秒
线程（1）休眠结束，结束于:21-46-25 11:46:12
线程（0）休眠结束，结束于:21-46-25 11:46:14
---所有线程执行结束于:21-46-25 11:46:14
````

由执行结果我们看到，实例化一个 Thread（调用 Thread() ）与调用 _thread.start_new_thread() 最大的区别是新的线程不会立即开始。创建线程对象却不想马上开始运行线程时，Thread 是一个很有用的同步特性。所有线程都创建之后，再一起调用 start() 函数启动，而不是每创建一个线程就启动。而且不用管理一堆锁的状态（分配锁、获得锁、释放锁、检查锁的状态等），只要简单地对每个线程调用join() 主线程，等待子线程结束即可。join() 还可以设置 timeout 参数，即主线程的超时时间。join() 另一个比较重要的方面是可以完全不用调用。一旦线程启动，就会一直执行，直到线程的函数结束并退出为止。如果主线程除了等线程结束外，还有其他事情要做，就不用调用join()，可等待线程结束时再调用。示例如下：

```py
import threading
from time import sleep
from datetime import datetime
  
loops = [4, 2]
date_time_format = '%y-%M-%d %H:%M:%S'


class ThreadFunc(object):
    def __init__(self, func, args, name=''):
        self.name = name
        self.func = func
        self.args = args

    def __call__(self):
        self.func(*self.args)


def date_time_str(date_time):
    return datetime.strftime(date_time, date_time_format)


def loop(n_loop, n_sec):
    print(f'线程（{n_loop}）开始执行:{date_time_str(datetime.now())}，先休眠（{n_sec}）秒')
    sleep(n_sec)
    print(f'线程（{n_loop}）休眠结束，结束于:{date_time_str(datetime.now())}')


def main():
    print(f'---所有线程开始执行:{date_time_str(datetime.now())}')
    threads = []
    nloops = range(len(loops))

    for i in nloops:  # create all threads
        t = threading.Thread(
            target=ThreadFunc(loop, (i, loops[i]), loop.__name__))
        threads.append(t)

    for i in nloops:  # start all threads
        threads[i].start()

    for i in nloops:  # wait for completion
        threads[i].join()

    print(f'---所有线程执行结束于:{date_time_str(datetime.now())}')


if __name__ == '__main__':
    main()

执行结果如下：
---所有线程开始执行:21-00-25 12:00:05
线程（0）开始执行:21-00-25 12:00:05，先休眠（4）秒线程（1）开始执行:21-00-25 12:00:05，先休眠（2）秒
线程（1）休眠结束，结束于:21-00-25 12:00:07
线程（0）休眠结束，结束于:21-00-25 12:00:09
---所有线程执行结束于:21-00-25 12:00:09
```

由执行结果看到，与传一个函数很相似的一个方法是，在创建线程时，传一个可调用的类的实例供线程启动时执行，这是多线程编程的一个面向对象的方法。相对于一个或几个函数来说，类对象可以使用类的强大功能。创建新线程时，Thread 对象会调用 ThreadFunc 对象，这时会用到一个特殊函数 _ call _()。由于已经有了要用的参数，因此不用再传到 Thread() 的构造函数中。对于有一个参数的元组，要使用 self.func(*self.args)方法。示例如下：

```py
import threading
from time import sleep
from datetime import datetime
  
loops = [4, 2]
date_time_format = '%y-%M-%d %H:%M:%S'


class MyThread(threading.Thread):
    def __init__(self, func, args, name=''):
        threading.Thread.__init__(self)
        self.name = name
        self.func = func
        self.args = args

    def getResult(self):
        return self.res

    def run(self):
        print(f'starting {self.name} at:{date_time_str(datetime.now())}')
        self.res = self.func(*self.args)
        print(f'{self.name} finished at:{date_time_str(datetime.now())}')


def date_time_str(date_time):
    return datetime.strftime(date_time, date_time_format)


def loop(n_loop, n_sec):
    print(f'线程（{n_loop}）开始执行:{date_time_str(datetime.now())}，先休眠（{n_sec}）秒')
    sleep(n_sec)
    print(f'线程（{n_loop}）休眠结束，结束于:{date_time_str(datetime.now())}')


def main():
    print(f'---所有线程开始执行:{date_time_str(datetime.now())}')
    threads = []
    n_loops = range(len(loops))

    for i in n_loops:
        t = MyThread(loop, (i, loops[i]),
        loop.__name__)
        threads.append(t)

    for i in n_loops:
        threads[i].start()

    for i in n_loops:
        threads[i].join()

    print(f'---所有线程执行结束于:{date_time_str(datetime.now())}')


if __name__ == '__main__':
    main()

执行结果如下：
---所有线程开始执行:21-06-25 12:06:58
starting loop at:21-06-25 12:06:58starting loop at:21-06-25 12:06:58
线程（0）开始执行:21-06-25 12:06:58，先休眠（4）秒线程（1）开始执行:21-06-25 12:06:58，先休眠（2）秒
线程（1）休眠结束，结束于:21-07-25 12:07:00
loop finished at:21-07-25 12:07:00
线程（0）休眠结束，结束于:21-07-25 12:07:02
loop finished at:21-07-25 12:07:02
---所有线程执行结束于:21-07-25 12:07:02
```



## 线程同步

如果多个线程共同对某个数据修改，则可能出现不可预料的结果，为了保证数据的正确性，需要对多个线程进行同步。

使用 Thread 对象的 Lock 和 Rlock 可以实现简单的线程同步，这两个对象都有 acquire 方法和 release 方法，对于那些需要每次只允许一个线程操作的数据，可以将其操作放到acquire和release方法之间。如下：

多线程的优势在于可以同时运行多个任务（至少感觉起来是这样）。但是当线程需要共享数据时，可能存在数据不同步的问题。

考虑这样一种情况：一个列表里所有元素都是0，线程"set"从后向前把所有元素改成1，而线程"print"负责从前往后读取列表并打印。

那么，可能线程"set"开始改的时候，线程"print"便来打印列表了，输出就成了一半0一半1，这就是数据的不同步。为了避免这种情况，引入了锁的概念。

锁有两种状态——锁定和未锁定。每当一个线程比如"set"要访问共享数据时，必须先获得锁定；如果已经有别的线程比如"print"获得锁定了，那么就让线程"set"暂停，也就是同步阻塞；等到线程"print"访问完毕，释放锁以后，再让线程"set"继续。

经过这样的处理，打印列表时要么全部输出0，要么全部输出1，不会再出现一半0一半1的尴尬场面。

**锁的 核心作用 就是为了保证数据的 一致性 ，对锁内的资源（变量）进行锁定，避免其它线程偷偷进行 篡改 。以达到我们的预期效果。即： 异步变同步。由于线程是内核级别的，它的切换是由CPU说了算，两线程间的执行顺序是完全没有约束的，轮到谁了就谁上。所以整个结果是无序的。**

示例如下：

````py
import threading
from time import sleep
from datetime import datetime
  
date_time_format = '%y-%M-%d %H:%M:%S'


class MyThread (threading.Thread):
    def __init__(self, threadID, name, counter):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.counter = counter

    def run(self):
        print(f"开启线程： {self.name}")
        # 获取锁，用于线程同步
        threadLock.acquire()
        print_time(self.name, self.counter, 3)
        # 释放锁，开启下一个线程
        threadLock.release()


def date_time_str(date_time):
    return datetime.strftime(date_time, date_time_format)


def print_time(threadName, delay, counter):
    while counter:
        sleep(delay)
        print(f"{threadName}: {date_time_str(datetime.now())}")
        counter -= 1


def main():
    # 创建新线程
    thread1 = MyThread(1, "Thread-1", 1)
    thread2 = MyThread(2, "Thread-2", 2)

    # 开启新线程
    thread1.start()
    thread2.start()

    # 添加线程到线程列表
    threads.append(thread1)
    threads.append(thread2)

    # 等待所有线程完成
    for t in threads:
        t.join()
    print("退出主线程")


if __name__ == "__main__":
    threadLock = threading.Lock()
    threads = []
    main()

执行结果如下：
开启线程： Thread-1开启线程： Thread-2

Thread-1: 21-10-25 12:10:35
Thread-1: 21-10-25 12:10:36
Thread-1: 21-10-25 12:10:37
Thread-2: 21-10-25 12:10:39
Thread-2: 21-10-25 12:10:41
Thread-2: 21-10-25 12:10:43
退出主线程
````



## 线程优先级队列

## 线程优先级队列（ Queue）

Python 的 Queue 模块中提供了同步的、线程安全的队列类，包括FIFO（先入先出）队列 Queue，LIFO（后入先出）队列 LifoQueue，和优先级队列 PriorityQueue。这些队列都实现了锁原语，能够在多线程中直接使用。可以使用队列来实现线程间的同步。

Queue模块中的常用方法:

- Queue.qsize() 返回队列的大小
- Queue.empty() 如果队列为空，返回True,反之False
- Queue.full() 如果队列满了，返回True,反之False
- Queue.full 与 maxsize 大小对应
- Queue.get([block[, timeout]])获取队列，timeout等待时间
- Queue.get_nowait() 相当Queue.get(False)
- Queue.put(item) 写入队列，timeout等待时间
- Queue.put_nowait(item) 相当Queue.put(item, False)
- Queue.task_done() 在完成一项工作之后，Queue.task_done()函数向任务已经完成的队列发送一个信号
- Queue.join() 实际上意味着等到队列为空，再执行别的操作

示例如下：

```py
import threading
import queue
from time import sleep


class MyThread (threading.Thread):
    def __init__(self, threadID, name, q):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.q = q

    def run(self):
        print(f"开启线程：{self.name}")
        process_data(self.name, self.q)
        print(f"退出线程：{self.name}")


def process_data(threadName, q):
    while not exitFlag:
        queueLock.acquire()
        if not workQueue.empty():
            data = q.get()
            queueLock.release()
            print(f"{threadName} processing {data}")
        else:
            queueLock.release()
        sleep(1)


def main():
    global exitFlag
    exitFlag = 0
    threadList = ["Thread-1", "Thread-2", "Thread-3"]
    nameList = ["One", "Two", "Three", "Four", "Five"]

    threads = []
    threadID = 1

    # 创建新线程
    for tName in threadList:
        thread = MyThread(threadID, tName, workQueue)
        thread.start()
        threads.append(thread)
        threadID += 1

    # 填充队列
    queueLock.acquire()
    for word in nameList:
        workQueue.put(word)
    queueLock.release()

    # 等待队列清空
    while not workQueue.empty():
        pass

    # 通知线程是退出的时候了
    exitFlag = 1

    # 等待所有线程完成
    for t in threads:
        t.join()
    print("退出主线程")


if __name__ == "__main__":
    queueLock = threading.Lock()
    workQueue = queue.Queue(10)
    main()

执行结果如下：
开启线程：Thread-2开启线程：Thread-3开启线程：Thread-1
Thread-3 processing One
Thread-2 processing TwoThread-1 processing Three
Thread-3 processing Four
Thread-2 processing Five
退出线程：Thread-3退出线程：Thread-1
退出线程：Thread-2
退出主线程
```



## 牛刀小试——多线程简单爬虫

结合本章所学写一个多线程函数，实现以不阻塞多线程的方式从一个指定网页抓取网页链接，并打印各个线程执行网页的情况和总耗时。

**思维点拨：**

（1）URL 拼接；（2）多线程构造；（3）不阻塞的实现；（4）总时间打印，实现需要用到之前未讲解过的知识点，即 urllib 库。

实现示例如下：

````py
import threading, queue, time, urllib
from urllib import request

BASE_URL = 'http://www.pythontab.com/html/pythonjichu/'
URL_QUEUE = queue.Queue()
for item in range(2, 10):
    url = BASE_URL + str(item) + '.html'
    URL_QUEUE.put(url)


def fetch_url(url_queue):
    while True:
        try:
            # 不阻塞的读取队列数据
            url_val = url_queue.get_nowait()
            url_queue.qsize()
        except Exception as ex:
            print(f'ex info is:{ex}')
            break
        curr_thread_name = threading.currentThread().name
        print(f'Current Thread Name {curr_thread_name}, Url: {url_val} ')
        try:
            response = urllib.request.urlopen(url_val)
            response_code = response.getcode()
        except Exception as ep:
            print(f'xp info is:{ep}')
            continue
        if response_code == 200:
            # 抓取内容的数据处理放这里
            # 为了突出效果， 设置延时
            time.sleep(1)


if __name__ == '__main__':
    start_time = time.time()
    threads = []
    # 可以调节线程数， 进而控制抓取速度
    thread_num = 4
    for num in range(0, thread_num):
        thread = threading.Thread(target=fetch_url, args=(URL_QUEUE,))
        threads.append(thread)
    for item_t in threads:
        item_t.start()
    for thread_t in threads:
        # 多线程多join，依次执行各线程的join方法, 确保主线程最后退出， 线程间没有阻塞
        thread_t.join()
    print(f'All thread done, spend: {(time.time() - start_time)} s')
````



# 第十四章       发送和接收电子邮件

# 第十五章       网络编程

# 第十六章       GUI 编成

# 第十七章       操作数据库



## 数据库操作



### 数据库连接

```py
import pymysql


def db_connect():
    # 打开数据库连接
    db = pymysql.connect("localhost", "root", "root", "test")

    # 使用cursor()方法创建一个游标对象cursor
    cursor = db.cursor()

    # 使用execute()方法执行SQL查询
    cursor.execute("SELECT VERSION()")

    # 使用 fetchone() 方法获取单条数据
    data = cursor.fetchone()

    print(f"Database version : {data[0]} ")

    # 关闭数据库连接
    db.close()


def main():
    db_connect()


if __name__ == "__main__":
    main()
```



### 创建数据库表

````py
import pymysql


def create_table():
    db = pymysql.connect("localhost", "root", "root", "test")
    # 使用 cursor() 方法创建一个游标对象cursor
    cursor = db.cursor()

    # 使用 execute() 方法执行 SQL，如果表存在就删除
    cursor.execute("DROP TABLE IF EXISTS EMPLOYEE")

    # 使用预处理语句创建表
    sql = """CREATE TABLE EMPLOYEE (
         FIRST_NAME  CHAR(20) NOT NULL,
         LAST_NAME  CHAR(20),
         AGE INT,
         SEX CHAR(1),
         INCOME FLOAT,
         CREATE_TIME DATETIME)"""
    try:
        cursor.execute(sql)
        print("CREATE TABLE SUCCESS.")
    except Exception as ex:
        print(f"CREATE TABLE FAILED,CASE:{ex}")
    finally:
        # 关闭数据库连接
        db.close()


def main():
    create_table()


if __name__ == "__main__":
    main()
````



### 数据库插入

```py
import pymysql
import datetime


def insert_record():
    db = pymysql.connect("localhost", "root", "root", "test")

    # 使用cursor()方法获取操作游标
    cursor = db.cursor()

    # SQL 插入语句
    sql = "INSERT INTO EMPLOYEE(FIRST_NAME,LAST_NAME, AGE, SEX, INCOME," \
          " CREATE_TIME) VALUES('{}', '{}', {}, '{}', {}, '{}')".\
        format('xiao', 'zhi', 22, 'M', 30000, datetime.datetime.now())
    try:
        # 执行sql语句
        cursor.execute(sql)
        # 提交到数据库执行
        db.commit()
        print("INSERT SUCCESS.")
    except Exception as ex:
        print(f'INSERT INTO MySQL table failed.Case:{ex}')
        # 如果发生错误就回滚
        db.rollback()
    finally:
        # 关闭数据库连接
        db.close()


def main():
    insert_record()


if __name__ == "__main__":
    main()
```



### 数据库查询

Python 查询 MySQL 使用 fetchone() 方法获取单条数据，使用 fetchall() 方法获取多条数据。

fetchone()：该方法获取下一个查询结果集。结果集是一个对象。

fetchall()：接收全部返回结果行。

rowcount()：这是一个只读属性，返回执行 execute() 方法后影响的行数。

````py
import pymysql


def query_data():
    # 打开数据库连接
    db = pymysql.connect("localhost", "root", "root", "test")

    # 使用cursor()方法获取操作游标
    cursor = db.cursor()

    # SQL 查询语句
    income = 10000
    sql = f"SELECT * FROM EMPLOYEE WHERE INCOME > {income}"
    try:
        # 执行SQL语句
        cursor.execute(sql)
        # 获取所有记录列表
        results = cursor.fetchall()
        for row in results:
            first_name = row[0]
            last_name = row[1]
            age = row[2]
            sex = row[3]
            income = row[4]
            create_time = row[5]
            # 输出结果
            print(f"{first_name=},{last_name=},{age=},{sex=},{income=},{create_time=}")
    except Exception as ex:
        print(f"Error: unable to fecth data.Error info:{ex}")
    finally:
        # 关闭数据库连接
        db.close()


def main():
    query_data()


if __name__ == "__main__":
    main()
````



### 数据库更新

```py
import pymysql


def update_table():
    # 打开数据库连接
    db = pymysql.connect("localhost", "root", "root", "test")

    # 使用cursor()方法获取操作游标
    cursor = db.cursor()

    # SQL 更新语句
    sex = 'M'
    sql = f"UPDATE EMPLOYEE SET AGE = AGE + 1 WHERE SEX = '{sex}'"
    try:
        # 执行SQL语句
        cursor.execute(sql)
        # 提交到数据库执行
        db.commit()
        print("UPDATE SUCCESS.")
    except Exception as ex:
        print(f'UPDATE MySQL table failed.Case:{ex}')
        # 发生错误时回滚
        db.rollback()
    finally:
        # 关闭数据库连接
        db.close()


def main():
    update_table()


if __name__ == "__main__":
    main()
```



### 数据库删除

```py
import pymysql


def delete_record():
    # 打开数据库连接
    db = pymysql.connect("localhost", "root", "root", "test")

    # 使用cursor()方法获取操作游标
    cursor = db.cursor()

    # SQL 删除语句
    sql = "DELETE FROM EMPLOYEE WHERE AGE > {}".format(22)
    try:
        # 执行SQL语句
        cursor.execute(sql)
        # 提交修改
        db.commit()
        print("DELETE SUCCESS.")
    except Exception as ex:
        print(f"DELETE RECORD FAILED.Case:{ex}")
        # 发生错误时回滚
        db.rollback()
    finally:
        # 关闭连接
        db.close()


def main():
    delete_record()


if __name__ == "__main__":
    main()
```







# 第十八章       网络爬虫项目实战

# 第十九章      自然语言分词与词频统计项目实战

# 第二十章      区块链项目实战

# 第二十一章       图片处理项目实战
