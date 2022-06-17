# 第一章



## Java介绍

### Java 开发场景

**Java 开发场景举例 1 - SSM**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SSM.png)

**Java 开发场景举例 2 - Android 核心代码**

**Java 开发场景举例 3 - 大数据-hadoop**



### Java的应用领域

企业级应用：主要指复杂的大企业的软件系统、各种类型的网站。应用领域包括金融、电信、交通、电子商务等。

Android平台应用：Android 应用程序使用 Java 语言编写。Android开发水平的高低很大程度取决于 Java 语言核心能力是否扎实。

移动领域应用：主要表现在消费者和嵌入式领域，是指在各种小型设备上的应用，包括机顶盒、车载的大屏影音娱乐设备、汽车通信设备、扫码的POS机等。



# 第二章       Java 语言概述



## Java 特点

1、Java 语言是面向对象的（oop）

2、Java 语言是健壮的。Java 的强类型机制、异常处理、垃圾的自动收集等是 Java 程序健壮性的重要保证

3、Java 语言是跨平台性的。[即：一个编译好的。class文件可以在多个系统下运行，这种特性称为跨平台]

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java跨平台性.png) 

4、Java 语言解释性的

解释性语言：JavaScript，PHP，Java；编译性语言：c，c++

区别是：解释性语言，编译后的代码，不能直接被机器执行，需要解释器来执行，编译型语言，编译后的代码，可以直接被机器执行，c / c++



## Java 运行机制及运行过程

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java运行机制即运行过程.png)

### Java 虚拟机概述

Java 核心机制 - Java虚拟机 [JVM  java virtual machine]

基本介绍

1、JVM 是一个虚拟的计算机，具有指令并使用不同的存储区域。负责执行指令，管理数据、内存、寄存器，包括在 JDK 中。

2、对于不同的平台，有不同的虚拟机。

3、Java 虚拟机机制屏蔽了底层运行平台的差别，实现了 “一次编译，到处执行”

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java虚拟机编译.png)

### 什么是JDK，JRE

**JDK 基本介绍**

1、JDK 的全称（Java Development Kit ---  Java 开发工具包）

JDK = JRE + Java 的开发工具 [java,javac,javadoc,javap等]

2、JDK 是提供 Java 开发人员使用的，其中包括了 Java 的开发工具，也包括了 JRE。所以安装了 JDK，就不用在单独安装JRE了。

**JRE 基本介绍**

1、JRE （Java Runtime Environment  ---  Java 运行环境）

JRE = JVM + Java 的核心类库[类]

2、包括 Java 虚拟机（JVM Java Virtual Machine）和 Java 程序所需的核心类库等，如果想要运行一个开发好的 Java 程序，计算机中只需要安装 JRE 即可。

JDK 、 JRE 和 JVM 的包含关系

1、JDK = JRE + Java 的开发工具 [java,javac,javadoc,javap编译工具等]

2、JRE = JVM + Java SE的标准类库[类]

3、JDK = JVM + Java SE的标准类库[类] + Java 的开发工具 [java,javac,javadoc,javap编译工具等]

4、如果只想运行开发好的 .class 文件只需要 JRE

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDK下载安装.png)



## Java 开发注意事项和细节说明

1、Java 源文件以 .java 为扩展名。源文件的基本组成部分是类（class），如本类中的 Hello 类。

2、Java 应用程序的执行入口是 main()  方法。它有固定的书写格式：

public static void main(String[] args){...}

3、Java 语言严格区分大小写。

4、Java 方法有一条条语句构成，每个语句以“；”结束。

5、大括号都是成对出现的，缺一不可。[习惯，先写{}再写代码]

6、一个源文件中最多只能有一个 public 类。其他类的个数不限。

7、如果源文件包括一个 public 类，则文件名必须按该类名命名！

8、一个源文件中最多只能有一个 public 类。其他类的个数不限，也可以将 main 方法写在非 public 类中，然后指定运行非 public 类，这样入口方法就是非 public 的 main 方法。



## Java 中的注释类型

1、单行注释

2、多行注释

**3、文档注释**

注释内容可以被 JDK 提供的工具 javadoc 所解析，生成一套以网页文件形式体现的该程序的说明文档，一般写在类

javadoc -d 文件夹名 -xx -yy Demo3.java

javadoc -d d:\\temp -author -version Comments.java

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\javadoc标签.png)



## DOS 命令

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\DOS命令.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\DOS的基本原理.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\DOS举例.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\DOS.png)



# 第三章       变量

## 变量

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\变量使用注意事项.png)

## 数据类型

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据类型.png)

## Java API 文档

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JavaAPI文档.png)

![Java类的组织形式](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java类的组织形式.png)



## ASCLL 码介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ASCLL码介绍.png)



## Unicode 编码介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Unicode编码介绍.png)



## UTF-8编码介绍

![UTF-8编码介绍](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\UTF-8编码介绍.png)



## 基本数据类型转换

### 自动类型转换注意和细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自动类型转换注意和细节.png)



### 强制类型转换细节和说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\强制类型转换细节和说明.png)



### 基本数据类型和 String 类型的转换

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\基本数据类型和String类型的转换.png)

**代码演示**

```java
public class StringToBasic{
    public static void main（String[] args){
        //基本数据类型 -> String
        int n1 = 100;
        float f1 = 1.1F;
        double d1 = 4.5;
        boolean b1 = true;
        String s1 = n1 + "";
        String s2 = f1 + "";
        String s3 = d1 + "";
        String s4 = b1 + "";
        System.out.println(s1 + " " + s2 + " " + s3 + " " + s4);
        //String -> 基本数据类型
        String s5 = "123";
        //会在 OOP 讲对象和方法的时候讲详细
        int num1 = Integer.parseInt(s5);
        double num2 = Double.parseDouble(s5);
        float num3 = Float.parseFloat(s5);
        long num4 = Long.parseLong(s5);
        short num4 = Short.parseShort(s5);
        byte num4 = Byte.parseByte(s5);
        boolean num4 = Boolean.parseBoolean(s5);
        //怎么把字符串转成字符char -> 含义是指把字符串的第一个字符得到
        //解读 s5.charAt(0) 得到 s5字符串的第一个字符 '1'
        System.out.println(s5.charAt(0));
    }
}
```



# 第四章       运算符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\运算符介绍.png)



## 算术运算符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\算术运算符.png)

### 算术运算符细节（取模本质）

**当对一个数取模时，可以等价于 a % b = a - a / b * b，这样我们可以看到取模的一个本质运算**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\算术运算符细节.png)



## 逻辑运算符

![逻辑运算符](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\逻辑运算符.png)

![逻辑运算符规则](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\逻辑运算符规则.png)

![逻辑运算符&&](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\逻辑运算符&&.png)



![逻辑运算符或](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\逻辑运算符或.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\逻辑运算符！.png)



## 赋值运算符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\赋值运算符.png)

### 复合赋值运算符会进行类型转换

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\复合赋值运算符会进行类型转换.png)



## 运算符优先级

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\运算符优先级.png)



## 标识符的命名规则和规范



### 标识符概念

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\标识符的命名规则和规范.png)



### 标识符的命名规范

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\标识符的命名规范.png)



## 键盘输入语句

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\键盘输入语句.png)

```java
public class Input{
    public static void main(String[] args){
        //步骤
        //Scanner 类表示简单文本扫描器，在java.util 包
        //1、引入/导入 Scanner类所在的包
        //2、创建 Scanner 对象，new 创建一个对象，体会myscanner 就是 Scanner类的对象
        Scanner myscanner = new Scanner(System.in);
        //3、接收用户输入了，使用相关方法
        System.out.println("请输入名字");
        String name = myScanner.next();//接受用户输入字符串
        System.out.println("请输入年龄");
        int age = myScanner.nextInt();//接受用户输入int
        System.out.println("请输入薪水");
        double sal = myScanner.nextDouble();//接受用户输入double
        System.out.println("人的信息如下：");
        System.out.println("名字：" + name + " 年龄：" + age + " 薪水：" + sal);
    }
}
```



## 进制



### 二进制转换成十进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\二进制转换成十进制.png)

### 八进制转换成十进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\八进制转换成十进制.png)

### 十六进制转换成十进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\十六进制转换成十进制.png)

### 十进制转换成二进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\十进制转换成二进制.png)

### 十进制转换成八进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\十进制转换成八进制.png)

### 十进制转换成十六进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\十进制转换成十六进制.png)

### 二进制转换成八进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\二进制转换成八进制.png)

### 二进制转换成十六进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\二进制转换成十六进制.png)

### 八进制转换成二进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\八进制转换成二进制.png)

### 十六进制转换成二进制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\十六进制转换成二进制.png)



### 原码、反码、补码

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\原码反码补码.png)

## 位运算符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\位运算符.png)



# 第五章       控制结构

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\控制结构.png)



## 分支控制

### switch分支结构细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\switch分支结构细节.png)



### switch和if的比较

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\switch和if的比较.png)



## 循环控制

### 多重循环控制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多重循环控制.png)

**用法举例**

```java
public class Star{
    public static void main(String[] args){
        /*
        *
        **
        ***
        ****
        *****
        */
        for(int i = 1; i <=5; i++){// i 表示层数
         	//控制打印每层的*个数
            for(int j = 1; j <= i; j++){
                System.out.print("*");
            }
            //每打印完一层的*后，就换行 println 本身会换行
            System.out.println("");
        }
        /*
            *
           ***
          *****
         *******
        *********
       */
        for(int i = 1; i <=5; i++){// i 表示层数
         	//在输出*之前，还有输出 对应空格 = 总层数 - 当前层
            for(int k = 1; k <= 5-i; k++){
                System.out.print(" ");
            }
            //控制打印每层的*个数
            for(int j = 1; j <=2 * i - 1; j++){
                    System.out.print("*");
            }
             //每打印完一层的*后，就换行 println 本身会换行
            System.out.println("");
        }
        /*
            *
           * *
          *   *
         *     *
        *********
       */
        for(int i = 1; i <= 5; i++){
            //在输出*之前，还有输出 对应空格 = 总层数 - 当前层
            for(int k = 1; k <= 5-i; k++){
                System.out.print(" ");
            }
            //控制打印每层的*个数
            for(int j = 1; j <=2 * i - 1; j++){
                //当前行的第一个位置是*，最后一个位置也是*
                if(j == 1 || j == 2 * i -1 || i == 5){
                    System.out.print("*");
                }
                else{//其他情况输出空格
                    System.out.print(" ");
                }
            }
            //每打印完一层的*后，就换行 println 本身会换行
            System.out.println("");
        }
    }
}
```



# 第六章       数组、排序和查找



## 数组的使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数组的使用-1.png)

![数组的使用-2](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数组的使用-2.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数组的使用-3.png)



## 数组使用注意事项和细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数组使用注意事项和细节.png)



### 数组值拷贝和引用赋值

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数组值拷贝和引用赋值.png)



### 数组值拷贝和引用赋值区别

![数组值拷贝和引用赋值区别](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数组值拷贝和引用赋值区别.png)



### 数组拷贝

通过另一个数组进行拷贝



## 二维数组的使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\二维数组的使用-1.png)

![二维数组的使用-2](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\二维数组的使用-2.png)

![二维数组的使用-3](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\二维数组的使用-3.png)



## 二维数组使用细节和注意事项

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\二维数组使用细节和注意事项.png)



# 第七章       面向对象编程（基本部分）



## 属性

### 属性的注意事项和细节说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\属性的注意事项和细节说明.png)

**属性举例**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\属性举例.png)



### JVM的内存分析代码执行流程

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JVM的内存分析代码执行流程.png)

### 类和对象的内存分配机制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类和对象的内存分配机制.png)



## 成员方法

### JVM的内存方法的调用机制分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JVM的内存方法的调用机制分析.png)



### 成员方法的注意事项和使用细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的注意事项和使用细节.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的注意事项和使用细节-1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的注意事项和使用细节-2.png)



### 成员方法的传参机制（属性）值拷贝

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法传参机制.png)

![成员方法的传参机制](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的传参机制.png)



### 成员方法的传参机制（数组）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的传参机制-数组.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的传参机制（数组）.png)



### 成员方法的传参机制（对象）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的传参机制（对象）.png)

![成员方法的传参机制（对象null）](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的传参机制（对象null）.png)

![成员方法的传参机制（方法内创建新的对象）](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员方法的传参机制（方法内创建新的对象）.png)



### 成员方法的传参机制应用实例

```java
public class MethodExercise{
    public static void main(String[] args){
   		Person p = new Person();
        p.name = "milan";
        p.age = 100;
        //创建tools
        MyTools tools = new MyTools();
        Person p2 = tools.copyPerson(p);
        //到此 p 和 p2 是Person对象，但是是两个独立的对象，属性相同
        System.out.println("p的属性 age=" + p.age + " 名字=" + p.name);
        System.out.println("p2属性 age=" + p2age + " 名字=" + p2name);
        //这里提示：可以同对象比较看看是否为同一个对象
        System.out.println(p==p2);
    }
}
class Person{
    String name;
    int age;
}
class MyTools{
    //编写一个方法 copyPerson，可以复制一个Person对象，返回复制的对象。克隆对象。
    /*注意要求得到新对象和原来的对象是两个独立的对象，只是他们的属性相同
    编写方法的思路
    1、方法的返回类型 Person
    2、方法的名字 copyPerson
    3、方法的形参 （Person p）
    4、方法体，创建一个新对象，并复制属性，返回即可
    */
    public Person copyPerson(Person p){
        Person p2 = new Person();
        p2.name = p.name;//把原来对象的名字赋给p2.name
        p2.age p.age//原来对象的名字赋给p2.age
        return p2;
    }
}
```

![0](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MethodExercise图解.png)



## 方法递归调用

### 方法递归调用举例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\方法递归调用举例.png)



**示例一**

```java
public void test(int n){
    if(n > 2){
        test(n - 1);
    }
    System.out.println("n=" + n)
}
```

![方法递归调用举例图解](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\方法递归调用举例图解.png)



**示例二**

```java
public void test(int n){
    if(n > 2){
        test(n - 1);
    }else{
        System.out.println("n=" + n)
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\方法递归调用举例图解（else）.png)



### 递归重要规则

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\递归重要规则.png)



### 递归调用应用实例-迷宫问题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\递归调用应用实例-迷宫问题.png)

**代码如下：**

```java
public class MiGong{
    public static void main(String[] args){
        //思路
        //1、先创建迷宫，用二维数组表示 int[][] map = new int[8][7]
        //2、先规定 map 数组的元素值：0表示可以走，1表示障碍物
        int[][] map = new int[8][7];
        //3、将最上面的一行和最下面的一行，全部设置为1
        for(int i = 0; i < 7; i++){
            map[0][i] = 1;
            map[7][i] = 1;
        }
        //4、将最右面的一列和最左面的一列，全部设置为1
        for(int i = 0; i < 8; i++){
            map[i][0] = 1;
            map[i][6] = 1;
        }
        map[3][1] = 1;
        map[3][2] = 1;
        map[2][2] = 1;
        //输入当前的地图
        for(int i = 0; i < map.length; i++){
            for(int j = 0; j < map[i].length; j++){
                System.out.print(map[i][j] + " ");//输出一行
            }
            System.out.println();
        }
        //使用findWay给老鼠找路
        T t1 = new T();
        t1.findWay(map,1,1);
        System.out.println("\n====找路情况如下====");
        for(int i = 0; i < map.length; i++){
            for(int j = 0; j < map[i].length; j++){
                System.out.print(map[i][j] + " ");//输出一行
            }
            System.out.println();
        }
    }
}
class T{
    //使用递归回溯的思想来解决老鼠出迷宫
    /*
    1、findWay 方法就是专门来找出迷宫的路径
    2、如果找到，就返回 true，否则返回 false
    3、map 就是二维数组，即表示迷宫
    4、i，j就是老鼠的位置，初始化的位置为（1，1）
    5、因为我们是递归的找路，所以我先规定 map 数组的各个值的定义
       0 表示可以走；1 表示障碍物；2 表示可以走；3 表示走过，但是走不通死路
    6、当 map[6][5] = 2 就说明找到通路，就可以结束，否则就继续找。
    7、先确定老鼠找路策略 下->右->上->左
    */
    public boolean findWay(int[][] map, int i, int j){
        if(map[6][5] == 2){//说明已经找到
            return true;
        }
        else{
            if(map[i][j] == 0){//当前这个位置0，说明表示可以走
            	//我们假定可以走通
                map[i][j] = 2;
                //使用找路策略，来确定该位置是否真的可以走通
                //下->右->上->左
                if(findWay(map, i + 1, j)){//先走下
                    return true;
                }else if(findWay(map, i, j + 1)){//先走右
                    return true;
                }else if(findWay(map, i - 1, j)){//先走上
                    return true;
                }else if(findWay(map, i, j - 1)){//先走左
                    return true;
                }else{
                    map[i][j] = 3;
                    return false;
                }
            }else{//map[i][j] = 1, 2, 3
                return false;
            }
        }
    }
}
```



### 递归调用应用实例-汉诺塔

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\递归调用应用实例-汉诺塔.png)

**代码如下：**

```java
public class HanoiTower{
    public static void main(String[] args){
        Tower tower = new Tower();
            tower.move(5,'A','B','C');
    }
}
class Tower{
    //方法
    //num 表示要移动的个数，a，b，c 分别表示 A塔，B塔，C塔
    public void move(int num.char a,char b,char c){
        //如果只有一个盘 num = 1
        if(num == 1){
            System.out.println(a + "->" + c);
        }
        else{
            //如果有多个盘，可以看成两个，最下面的和上面的所有盘(num - 1)
            //(1)先移动上面所有的盘到 b，借助 c
            move(num - 1, a, c, b);
            //(2)把最下面的这个盘，移动到 c
            System.out.println(a + "->" + c);
            //(3)再把 b 塔的所有盘，移动到 c，借助 a
             move(num - 1, b, a, c);
        }
    }
}
```



### 递归调用应用实例-八皇后问题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\递归调用应用实例-八皇后问题.png)

![递归调用应用实例-八皇后问题分析](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\递归调用应用实例-八皇后问题分析.png)



## 方法重载

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\方法重载.png)

![方法重载练习](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\方法重载练习.png)



## 可变参数

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\可变参数.png)

**可变参数实例**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\可变参数实例.png)



### 可变参数注意事项和使用细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\可变参数注意事项和使用细节.png)

```java
class T{
    public void f1(int... nums){
        System.out.println("长度=" + nums.length);
    }
    //细节：可变参数可以和普通类型的参数一起放在形参列表，但必须保证可变参数在最后
    public void f2(String str,double... nums){    
    }
    //细节：一个形参列表中只能出现一个可变参数
    //下面的写法是错的
    //public void f3(int... nums1, double... nums2){
	//}
}
```



## 作用域

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\作用域.png)



### 作用域注意事项和细节使用

![作用域注意事项和细节使用](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\作用域注意事项和细节使用.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\作用域注意事项和细节使用-1.png)



## 构造器

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\构造器.png)

![构造器-1](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\构造器-1.png)



### 构造器注意事项和使用细节

![构造器注意事项和使用细节](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\构造器注意事项和使用细节.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\构造器注意事项和使用细节-1.png)



## javap的使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\javap的使用.png)



## 对象

### JVM的内存对象存在形式

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JVM的内存对象存在形式.png)



### 对象创建的流程分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\对象创建的流程分析.png)

![对象创建的流程分析-1](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\对象创建的流程分析-1.png)



## this 关键字

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\this关键字.png)



### JVM的内存this的理解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JVM的内存this的理解.png)

```java
public class This01{
    public static void main(String[] args){
        Dog dog1 = new Dog("大壮",3);
        System.out.println("dog1的hascode=" + dog1.hashCode());
        dog1.info();	
        System.out.println("----------------------");
        Dog dog2 = new Dog("大黄",2);
        System.out.println("dog2的hascode=" + dog2.hashCode());
        dog2.info();
    }
}
class Dog{
    String name;
    int age;
    //public Dog(String dName, int dAge){
    // 	name = dName;
    //    age = dAge;
    //}
    /*
    如果我们构造器的形参，能够直接写成属性名，就更好了
    但是出现了一个问题，根据变量的作用域原则
    构造器的name是局部变量，而不是属性
    构造器的age是局部变量，而不是属性
    ==>引出this关键字来解决
    */
    public Dog(String Name, int Age){
        //this.name 就是当前对象的属性name
     	this.name = Name;
        //this.age 就是当前对象的属性age
        this.age = Age;
    }
    public void info(){//成员方法，输出属性x信息
        System.out.println(name + "\t" + age + "\t");
        System.out.println("this的hascode=" + this.hashCode());
    }
}
```



### this的注意事项和使用细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\this的注意事项和使用细节.png)

**this关键字可以用来访问本类的属性**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\this关键字可以用来访问本类的属性.png)



### this案例

```java
public class This02{
    public static void main(String[] args){
		Person p1 = new Person("小明",14);
       	 Person p2 = new Person("小明",14);
        System.out.println(p1.compareTo(p2));
    }
}
/*
定义Person类，里面有name、age属性，并提供compareTo比较方法，
用于判断是否和另一个人相等，提供测试类TestPerson用于测试，
名字和年龄完全一样，就返回true，否则返回false
*/
class Person{
    String name;
    int age;
    //构造器
    public Person(String name, int age){
        this.name = name;
        this.age = age;
    }
    //compareTo比较方法
    public boolean compareTo(Person p){
        //名字和年龄完全一样
        //if(this.name.equals(p.name) && this.age == p.age){
        //    return true;
        //}
        //else{
        //    return false;
        //}
        return this.name.equals(p.name) && this.age == p.age;
        //return this.equals(p);
    }
}
```



**猜拳案例**

```java
import java.util.Random;
import java.util.Scanner;

/*
请编写一个猜拳的游戏
有个人 Tom，设计它的成员变量，成员方法，可以电脑猜拳，电脑每次都会随机生成0，1，2
0表示 石头；1 表示剪刀；2 表示布
并要可以显示 Tom 的输赢次数（清单），假定玩三次
*/

public class MoraGame{
    public static void main(String[] args){
        //创建一个玩家对象
        Tom t = new Tom();
        //用于记录最后输赢的次数
        int isWinCount = 0;
        //创建一个二维数组，用于接收局数，Tom出拳情况及电脑出拳情况
        int[][] arr1 = new int[3][3];
        int j = 0;
        //创建一个一维数组，用来接收输赢情况
        String[] arr2 = new String[3];
        Scanner scanner = new Scanner(System.in);
        for(int i = 0; i <3; i++){
            //获取玩家出的拳
            System.out.println("请输入你要出的拳（0-拳头，1-剪刀，2-布");
            int num = scanner.nextInt();
            t.setTomGuessNum(num);
            int tomGuess = t.getTomGuessNum();
            arr1[i][j + 1] = tomGuess;
            
            //获取电脑出的拳
            int comGuess = t.computerNum();
            arr1[i][j + 2] = comGuess;
            
            //将玩家猜的拳与电脑做比较
            String isWin = t.vsComputer();
            arr2[i] = isWin;
            arr1[i][j] = t.count;
            
            //对每一局的情况进行输出
            System.out.println("-------------------------");
            System.out.println("局数\t玩家的出拳\t电脑的出拳\t\t输赢情况");
            System.out.println(t.count + "\t" + tomGuess + "\t\t" + comGuess + "\t\t" + isWin);
            System.out.println("--------------------------");
            System.out.println("\n\n");
            isWinCount = t.winCount(isWin);
        }
        //对游戏的最终结果进行输出
        System.out.println("局数\t玩家的出拳\t电脑的出拳\t\t输赢情况");
        for(int a = 0; a < arr1.length; a++){
            for(int b = 0; b < arr1[a].length; b++){
                System.out.print(arr1[a][b] + "\t\t\t");
            }
            System.out.println(arr2[a]);
            System.out.println();
        }
        System.out.println("你赢了" + isWinCount + "次");
    }
}
//Tom类
class Tom{//核心代码
    //玩家出拳的类型
    int tomGuessNum;
    //电脑出拳的类型
    int comGuessNum;
    //玩家赢得次数
    int winCountNum;
    //比赛的次数
    int count = 1;
    public void showInfo(){
        //...
    }
    /**
    * 电脑随机生成猜拳的数字的方法
    * @return
    */
    public int computerNum(){
        Random r = new Random();
        comGuessNum = r.nextInt(3);//方法返回0-2的随机数
        return comGuessNum;
    }
    /**
    * 设置玩家猜拳的数字的方法
    * @param tomGuessNum
    */
    public void setTomGuessNum(int tomGuessNum){
        if(tomGuessNum > 2 || tomGuessNum < 0){
            //抛出一个异常，李同学会写，没有处理
            throw new IllegalArgumentException("数字输入错误");
        }
        this.tomGuessNum = tomGuessNum;
    }
    public int getTomGuessNum(){
        return tomGuessNum;
    }
    /**
    * 比较猜拳的结果
    * @return 玩家赢返回true，否则返回false
    */
    public String vsComputer(){
        //比较
        if(tomGuessNum == 0 && comGuessNum == 1){
            return "你赢了";
        }else if(tomGuessNum == 1 && comGuessNum == 2){
            return "你赢了";
        }else if(tomGuessNum == 2 && comGuessNum == 0){
            return "你赢了";
        }else if(tomGuessNum == comGuessNum){
            return "平手";
        }else{
            return "你输了";
        }
    }
    /**
    * 记录玩家赢的次数
    * @return
    */
    public int winCount(String s){
        count++; //控制玩的次数
        if(s.equals("你赢了")){//统计赢的次数
            winCountNum++;
        }
        return winCountNum;
    }
}
```



# 第八章       面向对象编程（中级部分）



## IDEA 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\IDE.png)



### IDE的使用和常用快捷键

1、删除当前行，默认是 Ctrl + Y ；自己配置 Ctrl + D

2、复制当前行，自己配置 Ctrl +Alt + 向下光标

3、补全代码 Alt + /

4、添加注释和取消注释 Ctrl + / 【第一次是添加注释，第二次是取消注释】

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Settings-Keymap.png)

5、导入该行需要的类，先配置 auto import ，然后使用 Alt + Enter 即可

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Settings-AutoImport.png)

6、快速格式化代码 Ctrl + Alt + L

7、快速运行程序 自己定义 Alt + R

8、生成构造器等 Alt + Insert ； 自己配置 Ctrl + I

9、查看一个类的层级关系 Ctrl + H

10、将光标放在一个方法上，输入 Ctrl + B，可以定位方法

11、自动的分配变量名，通过在后面 .var



### 模板/自定义模板

file -> settings -> editor -> Live templates -> 查看有哪些模板快捷键/可以自己增加模板



## 包

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\包.png)



### 包的本质分析（原理）

包的本质实际上就是创建不同的文件夹来保存类文件

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\包的本质.png)

### 包的案例（eight.one）

com.xiaoming 包下的 Dog 类

```java
package eight.one.xiaoming;

public class Dog {}
```

com.xiaoqiang包下的 Dog 类

```java
package eight.one.xiaoqiang;

public class Dog {}
```

com.use 包下的 Test 类

```java
package eight.one.use;
import eight.one.xiaoqiang.Dog;

public class Test{
    public static void main(String[] args){
        Dog dog = new Dog();
        System.out.println(dog);

        eight.one.xiaoming.Dog dog1 = new eight.one.xiaoming.Dog();
        System.out.println(dog1);
    }
}
```



### 包的命名

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\包的命名.png)

**常用的包**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\常用的包.png)

**建议：**引入包时，需要哪些包就导入那些包，不建议使用 * 导入。



### 注意事项和使用细节

1、package 的作用是声明当前类所在的包，需要放在类的最上面，一个类中最多只有一个句 package

2、import 指令位置放在 package 的下面，在类定义前面，可以有多句且没有顺序要求。



## 访问修饰符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\访问修饰符.png)

### 访问修饰符范围

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\访问修饰符范围.png)



## 面向对象编程 - 封装



### 封装介绍

封装（encapsulation）就是把抽象出的数据【属性】和对数据的操作【方法】封装在一起，数据被保护在内部，程序的其他部分只有通过被授权的操作【方法】，才能对数据进行操作。

**封装的好处**

1、隐藏实现的细节

2、可以对数据进行验证，保证安全合理

### 封装的实现步骤

1、将属性进行私有化【不能直接修改属性】

2、提供一个公共的 （public）set 方法，用于对属性判断并赋值

```java
public void setXxx(类型 参数名){
    //加入数据验证的业务逻辑
    属性 = 参数名;
}
```

3、提供一个公共的 （public）get 方法，用于获取属性的值

```java
public void getXxx(){//权限判断
    return xx;
}
```



### 封装案例（eight.two）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\封装案例.png)

将构造器和 setXxx 结合

```java
package eight.two;

import java.sql.SQLOutput;

public class Encapsulation01 {
    public static void main(String[] args) {
        Person person = new Person();
        person.setName("钢铁侠");
        person.setAge(45);
        person.setSalary(300000);
        System.out.println(person.info());
        System.out.println(person.getSalary());

        Person smith = new Person("smith", 30, 40000);
        System.out.println("============smith=============");
        System.out.println(smith.info());
    }
}
class Person{
    public String name;//名字公开
    private int age;//age私有化
    private double salary;//薪水私有化

    public Person() {
    }

    public Person(String name, int age, double salary) {
//        this.name = name;
//        this.age = age;
//        this.salary = salary;
        //我们可以将 set 方法写在构造器中，这样仍然可以验证
        setName(name);
        setAge(age);
        setSalary(salary);
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        //加入对数据的校验，相当于增加了业务逻辑
        if(name.length() >= 2 && name.length() <= 6){
            this.name = name;
        }else{
            System.out.println("名字的长度不对，需要（2-6）个字符，默认名字");
            this.name = "无名人";
        }
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }
    //写一个方法，返回属性信息
    public String info(){
        return "信息为 name=" + name + " age=" + age + " 薪水=" + salary;
    }
}
```



## 面向对象编程 - 继承



### 继承介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\继承介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\继承示意图.png)

**继承给编程带来的便利**

1、代码的复用性提高

2、代码的扩展性和维护行提高了



### 继承的注意事项和使用细节

1、子类继承了所有的属性和方法，非私有的属性和方法可以在子类直接访问，但是私有属性和方法不能在子类直接访问，要通过公共的方法去访问

示例：

eight.three 包下的 Base 类（父类）

```java
package eight.three;

public class Base {
    public int n1 = 1;
    protected int n2 = 2;
    int n3 = 3;
    private int n4 = 4;
    public void test1(){
        System.out.println("test1");
    }
    protected void test2(){
        System.out.println("test2");
    }
    void test3(){
        System.out.println("test3");
    }
    private void test4(){
        System.out.println("test4");
    }
    public void callTest4(){
        test4();
        System.out.println(n4);
    }
}
```

eight.three 包下的 Sub 类（子类）

```java
package eight.three;

public class Sub extends Base{
    public Sub(){
        System.out.println("sub()...");
    }
    public void sayOk() {
        //我们发现父类方法的非private属性和方法都可以访问
    }
}
```

eight.three 包下的 Test类（测试类）

```java
package eight.three;

public class Test {
    public static void main(String[] args) {
        Sub sub = new Sub();
        sub.callTest4();
    }
}
```



2、子类必须调用的构造器，完成父类的初始化

3、当创建子类对象时，不管使用子类的那个构造器，默认情况下总会去调用父类的无参构造器，如果父类没有提供无参构造器，则必须在子类的构造器中用 super 去指定使用父类的那个构造器完成对父类的初始化工作，否则，编译不会通过。

改进上面的示例

eight.three 包下的 Base 类（父类）

```java
package eight.three;

public class Base {
    public int n1 = 1;
    protected int n2 = 2;
    int n3 = 3;
    private int n4 = 4;

    public Base() {
        System.out.println("父类构造器Base被调用....");
    }
    public Base(String name,int age){
        System.out.println("父类构造器Base(String name,int age)被调用了....");
    }
    public void test1(){
        System.out.println("test1");
    }
    protected void test2(){
        System.out.println("test2");
    }
    void test3(){
        System.out.println("test3");
    }
    private void test4(){
        System.out.println("test4");
    }
    public void callTest4(){
        test4();
        System.out.println(n4);
    }
}
```

eight.three 包下的 Sub 类（子类）

```java
package eight.three;

public class Sub extends Base{
    public Sub(){//无参构造器
        //super();//默认调用父类的无参构造器
        System.out.println("sub()...");
    }
    public Sub(String name){
        //如果父类的无参构造器被覆盖，则需指明调用了那个父类构造器进行初始化
        super(name,23);
        System.out.println("子类Sub(String name)构造器被调用了...");
    }
    public void sayOk() {
        //我们发现父类方法的非private属性和方法都可以访问
    }
}
```

eight.three 包下的 Test类（测试类）

```java
package eight.three;

public class Test {
    public static void main(String[] args) {
        Sub sub = new Sub();
        sub.callTest4();
        Sub mike = new Sub("Mike");
        mike.callTest4();
    }
}
```

4、如果希望指定去调用弗雷德某个构造器，则显式的调用一下：super()

5、super 在使用时，必须放在构造器第一行()

6、super() 和 **this()【第七章 this 注意事项和使用细节】** 都只能放在构造器第一行，因此这两个方法不能共存在一个构造器中

7、java 所有类都是 Object 类的子类

8、父类构造器的调用不限于直接父类！将一直往上追溯直到Object 类（顶级父类）

9、子类最多只能继承一个父类（指直接继承），即 java 是单继承机制。

10、不能滥用继承，子类和父类之间必须满足 is - a 的逻辑关系

```
Person is a Music?
Person  Music
Music extends Person 

Animal
Cat extends Animal
```



### 继承的本质分析（重要）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\继承的本质分析.png)

这时要请大家注意，要按照查找关系返回信息

（1）首先看子类是否有该属性

（2）如果子类有这个属性，并且可以访问（访问修饰符是否允许），则返回信息

（3）如果子类没有这个属性，就看父类有没有这个属性（如果父类有该属性，并且可以访问，就返回信息...）

（4）如果父类没有就返回按照（3）的规则，继续找上级父类，直到 Object...



### 继承案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\继承案例.png)

eight.four 包下的 Computer 类（父类）

```java
package eight.four;

//编写 Computer 类，包含 CPU、内存、硬盘等属性，getDetails 方法用于返回Computer的详细信息
public class Computer {
    private String cpu;
    private int memory;
    private int disk;
    public Computer(String cpu,int memory,int disk){
        this.cpu = cpu;
        this.memory = memory;
        this.disk = disk;
    }

    public String getCpu() {
        return cpu;
    }

    public void setCpu(String cpu) {
        this.cpu = cpu;
    }

    public int getMemory() {
        return memory;
    }

    public void setMemory(int memory) {
        this.memory = memory;
    }

    public int getDisk() {
        return disk;
    }

    public void setDisk(int disk) {
        this.disk = disk;
    }
    public String getDetails(){
        return "cpu:" + getCpu() + " memory:" + getMemory() + " disk:" + getDisk();
    }
}
```

eight.four 包下的 PC 类（子类）

```java
package eight.four;

public class PC extends Computer{
    private String brand;
    //这里IDEA 根据继承的规则，自动把构造器的调用写好
    //这里也体现：继承设计的基本思想，父类的构造器完成父类属性初始化
    //子类的构造器完成子类属性初始化
    public PC(String cpu, int memory, int disk, String brand) {
        super(cpu, memory, disk);
        this.brand = brand;
    }

    public String getBrand() {
        return brand;
    }

    public void setBrand(String brand) {
        this.brand = brand;
    }
    public void printInfo(){
        System.out.println("PC的信息：");
        //调用父类的 getDetails 方法，得到相关属性信息
        System.out.println(getDetails() + " brand:" + brand);
    }
}
```

eight.four 包下的 ExtendsExercise01 类（测试类）

```java
package eight.four;

public class ExtendsExercise01 {
    public static void main(String[] args) {
        PC pc = new PC("Inter", 512, 512, "联想");
        pc.printInfo();
    }
}
```



## super 关键字

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\super关键字.png)

以 eight.three 包下的类为例

```java
package eight.three;

public class B extends Base{
    //访问父类的属性，但不能访问父类的 private 属性，super.属性名
    public void hi(){
        System.out.println(super.n1 + " " + super.n2 + " " + super.n3);
    }
    //访问父类的方法，但不能访问父类的 private 方法，super.方法名(参数列表)
    public void ok(){
        super.test1();
        super.test2();
        super.test3();
        //super.test4();不能访问父类 private 方法
    }
    //访问父类的构造器：super(参数列表);，只能放在构造器的第一句，只能出现一句。
    public B() {
        super();
    }
}
```



### super 注意事项和使用细节

1、调用父类的构造器的好处（分工明确，父类属性由父类初始化，子类的属性由子类初始化）

2、当子类中有和父类中的成员（属性和方法）重名时，为了访问父类的成员，必须通过 super。如果没有重名，使用 super、this、直接访问是一样的效果！

<img src="C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\super-this-直接访问.png" style="zoom:200%;" />

3、super 的访问不限于直接父类，如果爷爷类和本类中同名的成员，也可以使用 super 去访问 爷爷类的成员；如果多个基类中都有同名的成员，使用 super 访问遵循就近原则。 A -> B -> C

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\super与this的比较.png)



## 方法重写/覆盖（override）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\方法重写、覆盖.png)

### 方法重写/覆盖注意事项和使用细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\方法重写、覆盖注意事项和使用细节.png)

**方法重写和重载的比较**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\重写和重载的比较.png)



## 面向对象编程 - 多态

请编写一个程序，Master 类中有一个 feed（喂食）方法，可以完成主人给动物喂食物的信息

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多态.png)

**使用传统的方法来解决**

eight.five 包下的代码

传统的方法：代码的复用性不高，而且不利于代码维护

### 多[多种]态[状态]基本介绍

方法或对象具有多种状态，是面向对象的第三大特征。多态是建立在封装和继承基础之上的。

### 多态的具体表现（方法多态、对象多态【重要】）

1、方法的多态：重写和重载就体现多态

**2、对象的多态：**

（1）一个对象的编译类型和运行类型可以不一致

（2）编译类型在定义对象时，就确定了，不能改变

（3）运行类型是可以变化的

（4）编译类型看定义时 = 号的左边，运行类型看 = 号的右边

**示例：**

eight.seven 包下的 Animal 类（父类）

```java
package eight.seven;

public class Animal {
    public void cry(){}
}
```

eight.seven 包下的 Dog 类（子类）

```java
package eight.seven;

public class Dog extends Animal{
    @Override
    public void cry() {
        System.out.println("小狗汪汪叫....");
    }
}
```

eight.seven 包下的 Cat 类（子类）

```java
package eight.seven;

public class Cat extends Animal{
    @Override
    public void cry() {
        System.out.println("小猫喵喵叫....");
    }
}
```

eight.seven 包下的 Test 类（测试类）

```java
    package eight.seven;

public class Test {
    public static void main(String[] args) {
        Animal animal = new Dog();
        animal.cry();
        System.out.println("================");
        Animal animal1 = new Cat();
        animal1.cry();
    }
}
```



### （多态的）向上转型

**本质：**父类的引用指向了子类的对象

**语法：**父类类型 引用名 = new 子类类型();

**特点：**编译类型看左边，运行类型看右边。可以调用父类中的所有成员（需遵守访问权限），不能调用子类中特有成员；最终运行效果看子类具体实现！

eight.eight包下的 Animal 类（父类）

```java
package eight.eight;

public class Animal {
    String name = "动物";
    int age = 10;
    public void sleep(){
        System.out.println("睡");
    }
    public void run(){
        System.out.println("跑");
    }
    public void eat(){
        System.out.println("吃");
    }
    public void show(){
        System.out.println("hello,你好");
    }
}
```

eight.eight包下的 Cat 类（子类）

```java
package eight.eight;

public class Cat extends Animal{
    @Override
    public void eat() {
        System.out.println("猫吃鱼");
    }
    public void catchMouse(){//Cat 特有方法
        System.out.println("猫抓老鼠");
    }
}
```

eight.eight包下的 Test 类（测试类）

```java
package eight.eight;

public class Test {
    public static void main(String[] args) {
        //向上转型：父类的引用指向了子类的对象
        Animal animal = new Cat();
        Object obj = new Cat(); //也可以

        //向上转型调用方法的规则如下：
        //可以调用父类中的所有成员（需遵守访问权限）
        //但是不能调用子类的特有成员
        //animal.catchMouse();错误
        //因为在编译阶段，能调用那些成员，是由编译类型来决定的
        //最终运行效果看子类（运行类型）的具体实现，即调用方法时，按照从子类（运行类型开始查找方法
        animal.eat();
        animal.run();
        animal.show();
        animal.sleep();
        System.out.println("ok~~~");
    }
}
```



### （多态的）向下转型

1、语法：子类类型 引用名 = （子类类型） 父类引用;

2、只能强转父类的引用，不能强转父类的对象

3、要求父类的引用必须指向的是当前目标类型的对象

4、可以调用子类类型中所有的成员

使用 eight.eight 包下的代码

```java
package eight.eight;

public class Test {
    public static void main(String[] args) {
        //向上转型：父类的引用指向了子类的对象
        Animal animal = new Cat();
        Object obj = new Cat(); //也可以

        //向上转型调用方法的规则如下：
        //可以调用父类中的所有成员（需遵守访问权限）
        //但是不能调用子类的特有成员
        //animal.catchMouse();错误
        //因为在编译阶段，能调用那些成员，是由编译类型来决定的
        //最终运行效果看子类（运行类型）的具体实现，即调用方法时，按照从子类（运行类型开始查找方法
        animal.eat();
        animal.run();
        animal.show();
        animal.sleep();
        System.out.println("ok~~~");
        //希望可以调用 Cat 的 CatchMouse 方法
        //多态的向下转型
        //cat 的编译类型是 Cat，运行类型是 Cat
        Cat cat = (Cat)animal;
        cat.catchMouse();
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\向下转型.png)



### 多态注意事项和使用细节

属性没有重写之说！属性的值看编译类型

```java
package eight.nine;

public class Test {
    public static void main(String[] args) {
        //属性没有重写之说！属性的值看编译类型
        Base base = new Sub();//向上转型,编译类型 Base
        System.out.println(base.count);
        Sub sub = new Sub();//编译类型 Sub
        System.out.println(sub.count);
        Sub Sub1 = (Sub)base;//编译类型 Sub
        System.out.println(sub.count);
    }
}
class Base{//父类
    int count = 10;//属性
}
class Sub extends Base{
    int count = 20;
}
```

**多态练习**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多态练习.png)



### instanceOf 比较操作符

instanceOf 比较操作符，用于判断对象的运行类型是否为 XX 类型或 XX 类型的子类型

```java
package eight.nine;

public class InstanceOfExercise {
    public static void main(String[] args) {
        //bb 编译类型 BB，运行类型 BB
        BB bb =new BB();
        System.out.println(bb instanceof BB);
        System.out.println(bb instanceof AA);
        //aa 编译类型 AA，运行类型 BB
        AA aa =new BB();
        System.out.println(aa instanceof AA);
        System.out.println(aa instanceof BB);

        Object obj = new Object();
        System.out.println(obj instanceof AA);
        String str = "hello";
        System.out.println(str instanceof Object);
    }
}
class AA{}//父类
class BB extends AA{}//子类
```



### java 的动态绑定机制（非常重要）



**Java 重要特性：动态绑定机制**

1、当调用对象方法的时候，该方法和该对象的内存地址/运行类型绑定

2、当调用对象属性时，没有动态绑定机制，哪里声明，哪里使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\java动态绑定机制.png)

**示例(eight.ten)**

```java
package eight.ten;

public class DynamicBinding {
    public static void main(String[] args) {
        //a 的编译类型 A，运行类型 B
        A a = new B();//向上转型
        System.out.println(a.sum());//40
        System.out.println(a.sum1());//30
    }
}
class A{
    public int i = 10;
    //动态绑定机制：
    public int sum(){
        return getI() + 10;
    }
    public int sum1(){
        return i + 10;
    }
    public int getI(){
        return i;
    }
}

class B extends A{
    public int i = 20;

    @Override
    public int sum() {
        return i + 20;
    }

    @Override
    public int sum1() {
        return i + 10;
    }
    public int getI(){
        return i;
    }
}
```



### 多态的应用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多态的应用.png)

**多态数组**

**示例（eight.eleven）**

```java
package eight.eleven;

public class Test {
    public static void main(String[] args) {
        //应用实例：现有一个要继承结构如下：要求创建一个Person对象
        //两个Student对象和两个Teacher对象，统一放在数组，并调用每个对象 say 方法
        Person[] persons = new Person[5];
        persons[0] = new Person("jack",20);
        persons[1] = new Student("mike",17,100);
        persons[2] = new Student("smith",23,123);
        persons[3] = new Teacher("scott",38,30000);
        persons[4] = new Teacher("king",26,434667);
        //循环遍历多态数组，调用 say
        for(int i = 0; i < persons.length; i++){
            //persons[i] 编译类型是 Person，运行类型是根据实际情况由 JVM 来判断
            System.out.println(persons[i].say());//动态绑定机制
            //使用 类型判断 + 向下转型
            if(persons[i] instanceof Student){//判断persons[i]的运行类型是不是Student
                Student student = (Student)persons[i];//向下转型
                student.study();
                //((Student)persons[i]).study();
            }else if(persons[i] instanceof Teacher){
                ((Teacher)persons[i]).teach();
            }else{
                System.out.println("你的类型有误，请自己检查...");
            }
        }
    }
}
```



**多态参数**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多态参数.png)

**示例（eight.twelve)**

Employee（父类）

```java
package eight.twelve;

public class Employee {
    private String name;
    private double salary;

    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }
    //得到年薪的方法
    public double getAnnual(){
        return 12 * salary;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary(double salary) {
        this.salary = salary;
    }
}
```

Worker（子类）

```java
package eight.twelve;

public class Worker extends Employee{
    public Worker(String name, double salary) {
        super(name, salary);
    }
    public void work(){
        System.out.println("普通员工 " + getName() + " is working");
    }

    @Override
    public double getAnnual() {
        return super.getAnnual();
    }
}
```

Manager（子类）

```java
package eight.twelve;

public class Manager extends Employee{

    private double bonus;

    public Manager(String name, double salary, double bonus) {
        super(name, salary);
        this.bonus = bonus;
    }

    //重写获取年薪的方法
    @Override
    public double getAnnual() {
        return super.getAnnual() + bonus;
    }

    public double getBonus() {
        return bonus;
    }

    public void setBonus(double bonus) {
        this.bonus = bonus;
    }
    public void manage(){
        System.out.println("经理 " + getName() + " is managing");
    }
}
```

Test（测试类）

```java
package eight.twelve;

public class Test {
    public static void main(String[] args) {
        Worker tom = new Worker("tom", 2500);
        Manager milan = new Manager("milan", 5000, 200000);
        Test test = new Test();
        test.showEmpAnnual(tom);
        test.showEmpAnnual(milan);
        test.testWork(tom);
        test.testWork(milan);
    }

    //showEmpAnnual(Employee e)
    //实现获取任何员工对象的年薪，并在main方法中调用该方法[e.getAnnual()]
    public void showEmpAnnual(Employee e) {
        System.out.println(e.getAnnual());
    }
    //添加一个方法，testWork，如果是普通员工，则调用work方法，如果是经理，则调用manage方法
    public void testWork(Employee e){
        if(e instanceof Worker){
            ((Worker)e).work();//有向下转型操作
        }else if(e instanceof Manager){
            ((Manager)e).manage();
        }else{
            System.out.println("不做处理...");
        }
    }
}
```



## Object 类详解

### Idea 查看 Jdk 源码

1、一般来说 IDEA 配置好 JDK 以后，jdk 的源码也就自动配置好了

2、如果没有的话带年纪菜单 File -> Project Structure -> SDKs -> Sourcepath 然后点击右侧绿色的加号

3、有需要查看某个方法源码时，讲光标放在方法，输入 Ctrl + B 即可或者在方法点击右键 -> go to -> Declaration or ...

### equals方法

== 和 equals 的对比

1、==：既可以判断基本类型，又可以判断引用类型

2、==：如果判断基本类型，判断的是值是否相等。示例：int i =10;double d = 10.0;

3、==：如果判断引用类型，判断的是地址是否相等，即判断是不是同一个对象

4、equals：是Object类中的方法，只能判断引用类型，如何看 Jdk 源码，看示例

5、默认判断的是地址是否相等，子类中往往重写该方法，用于判断内容是否相等。比如 Integer，String

**示例（eight.thirteen）**

```java
package eight.thirteen;

import sun.security.rsa.RSAUtil;

public class Test {
    public static void main(String[] args) {
        A a = new A();
        A b = a;
        A c = b;
        System.out.println(a == c);//true
        System.out.println(b == c);//true
        B bObj = a;
        System.out.println(bObj == c);//true
        int num1 = 10;
        double num2 = 10.0;
        System.out.println(num1 == num2);//true

        Integer integer1 = new Integer(1000);
        Integer integer2 = new Integer(1000);
        System.out.println(integer1 == integer2);//false
        System.out.println(integer1.equals(integer2));//true

        String str1 = new String("hsp");
        String str2 = new String("hsp");
        System.out.println(str1 == str2);//false
        System.out.println(str1.equals(str2));//true

        //equals 方法，源码怎么查看
        //把光标放在 equals 方法，直接输入 Ctrl + B
        "heel".equals("hkek");
        //带大家看看Jdk的源码，Object类的equals方法
        //把Object的equals方法重写了，变成了比较两个字符串值是否相等
//        public boolean equals(Object anObject) {
//            if (this == anObject) {//如果是同一个对象
//                return true;//返回 true
//            }
//            if (anObject instanceof String) {//判断类型
//                String anotherString = (String)anObject;//向下转型
//                int n = value.length;
//                if (n == anotherString.value.length) {//如果长度相同
//                    char v1[] = value;
//                    char v2[] = anotherString.value;
//                    int i = 0;
//                    while (n-- != 0) {//然后一个一个的比较字符
//                        if (v1[i] != v2[i])
//                            return false;
//                        i++;
//                    }
//                    return true;//如果两个字符串的所有字符都相等，则返回 true
//                }
//            }
//            return false;//如果两个字符串的字符比较有不相等的，则返回 false
//        }
    }
}

class B {
}

class A extends B {
}
```

**equals 练习**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\equals练习.png)



### toString 方法

**当直接输出一个对象时，toString() 方法会被默认的调用**

**System.out.println(monster); 就会默认调用 monster.toString()**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\toString方法.png)



### finalize 方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\finalize方法.png)

使用 System.gc(); ------- 主动调用垃圾回收器，就会调用finalize()方法



## 断点

### 断点调试的快捷键

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\断点.png)

### Idea debug进入 Jdk 源码

1、使用 force step into：快捷键 alt + shift + F7

2、这个配置一下就好了：点击 Settings -> Build,Execution,Deployment -> Debugger -> Stepping 把 Do not step into the classes 中的 ajva.*，javax.* 取消勾选，其他的随意

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\断点流程.png)



## 项目 - 零钱通

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\项目零钱通.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\项目零钱通说明.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\项目零钱通改进.png)



### **项目代码**

```java
package eight.fourteen;

import java.text.SimpleDateFormat;
import java.util.Scanner;
import java.util.Date;

public class SmallChangeSys{
    //1、先完成显示菜单，并可以选择菜单，给出对应提示
    public static void main(String[] args) {
        //定义相关的变量
        boolean loop = true;
        Scanner scanner = new Scanner(System.in);
        String key = "";
        //2、完成零钱通明细
        //（1）可以把收益入账和消费，保存到数组；（2）可以使用对象；（3）简单的话可以使用String拼接
        String details = "--------------零钱通明细---------------";
        //3、完成收益入账，完成功能驱动程序员增加新的变化和代码
        //定义新的变量
        double money = 0;
        double balance = 0;
        Date date = null;//date 是 java.util.Date 类型，表示日期
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH：mm");//可以用于日期格式化
        //4、消费
        //定义新的变量，保存消费的原因
        String note = "";
        do {
            System.out.println("==========零钱通菜单==========");
            System.out.println("\t\t\t1 零钱通明细");
            System.out.println("\t\t\t2 收益入账");
            System.out.println("\t\t\t3 消   费");
            System.out.println("\t\t\t4 退   出");

            System.out.println("请选择（1-4）：");
            key = scanner.next();

            //使用 switch 分支
            switch (key) {
                case "1":
                    System.out.println(details);
                    break;
                case "2":
                    System.out.println("收益入账金额：");
                    money = scanner.nextDouble();
                    //money 的值范围应该校验，判断金额是否合理，并给出相应的提示
                    if(money <= 0){
                        System.out.println("收益入账金额需要大于0");
                        break;
                    }

                    balance += money;
                    date = new Date();//获取当前时间
                    details += "\n收益入账\t+" + money + "\t" + sdf.format(date) + "\t" + balance;

                    break;
                case "3":
                    System.out.println("消费金额：");

                    money = scanner.nextDouble();
                    //money 的值范围应该校验，判断金额是否合理，并给出相应的提示
                    if(money <= 0 || money > balance){
                        System.out.println("你的消费金额应该在 0-" + balance);
                        break;
                    }

                    System.out.println("消费说明：");
                    note = scanner.next();
                    balance -= money;
                    //拼接消费信息到 details
                    date = new Date();//获取当前日期
                    details += "\n" + note + "\t-" + money + "\t" + sdf.format(date) + "\t" + balance;
                    break;
                case "4":
                    //用户输入4退出时，给出提示“你确定要退出吗？ y/n”，必须输入正确的y/n
                    //否则循环输入指令，直到输入 y 或者 n
                    //（1）定义一个变量 choice，接收用户的输入
                    //（2）使用 while + break，来处理接收的输入时 y 或者 n
                    //（3）退出 while 后，再判断 choice 是 y 或者 n，就可以决定是否退出
                    //（4）建议一段代码完成一个小功能，尽量不要混在一起
                    String choice = "";
                    while (true) {
                        System.out.println("你确定要退出吗？y/n");
                        choice = scanner.next();
                        if ("y".equals(choice) || "n".equals(choice)) {
                            break;
                        }
                    }
                    //当用户退出 while，进行判断
                    if(choice.equals("y")) {
                        loop = false;
                    }
                    break;
                default:
                    System.out.println("选择有误，请重新选择");
            }
        }
        while (loop);
    }
}
```

### **零钱通OOP改进代码**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\零钱通总结.png)

**（eight.fourteen) -- SmallChangeSysOOP**

```java
package eight.fourteen;

import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Scanner;

/**
 * 完成 OOP 编程
 */
public class SmallChangeSysOOP {
    //定义相关的变量
    boolean loop = true;
    Scanner scanner = new Scanner(System.in);
    String key = "";
    //2、完成零钱通明细
    //（1）可以把收益入账和消费，保存到数组；（2）可以使用对象；（3）简单的话可以使用String拼接
    String details = "--------------零钱通明细---------------";
    //3、完成收益入账，完成功能驱动程序员增加新的变化和代码
    //定义新的变量
    double money = 0;
    double balance = 0;
    Date date = null;//date 是 java.util.Date 类型，表示日期
    SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH：mm");//可以用于日期格式化
    //4、消费
    //定义新的变量，保存消费的原因
    String note = "";

    //先完成显示菜单，并可以选择
    public void mainMenu(){
        do {
            System.out.println("==========零钱通菜单==========");
            System.out.println("\t\t\t1 零钱通明细");
            System.out.println("\t\t\t2 收益入账");
            System.out.println("\t\t\t3 消   费");
            System.out.println("\t\t\t4 退   出");

            System.out.println("请选择（1-4）：");
            key = scanner.next();

            //使用 switch 分支
            switch (key) {
                case "1":
                    detail();
                    break;
                case "2":
                    income();
                    break;
                case "3":
                   pay();
                    break;
                case "4":
                    exit();
                    break;
                default:
                    System.out.println("选择有误，请重新选择");
            }
        }
        while (loop);
    }
    //完成零钱通明细
    public void detail(){
        System.out.println(details);
    }
    //完成收益入账
    public void income(){
        System.out.println("收益入账金额：");
        money = scanner.nextDouble();
        //money 的值范围应该校验，判断金额是否合理，并给出相应的提示
        if(money <= 0){
            System.out.println("收益入账金额需要大于0");
            return;//退出方法，不再执行后面的代码（传统方式：break;）
        }

        balance += money;
        date = new Date();//获取当前时间
        details += "\n收益入账\t+" + money + "\t" + sdf.format(date) + "\t" + balance;
    }
    //消费
    public void pay(){
        System.out.println("消费金额：");

        money = scanner.nextDouble();
        //money 的值范围应该校验，判断金额是否合理，并给出相应的提示
        if(money <= 0 || money > balance){
            System.out.println("你的消费金额应该在 0-" + balance);
            return;//退出方法，不再执行后面的代码（传统方式：break;）
        }

        System.out.println("消费说明：");
        note = scanner.next();
        balance -= money;
        //拼接消费信息到 details
        date = new Date();//获取当前日期
        details += "\n" + note + "\t-" + money + "\t" + sdf.format(date) + "\t" + balance;
    }
    //退出
    public void exit(){
//用户输入4退出时，给出提示“你确定要退出吗？ y/n”，必须输入正确的y/n
        //否则循环输入指令，直到输入 y 或者 n
        //（1）定义一个变量 choice，接收用户的输入
        //（2）使用 while + break，来处理接收的输入时 y 或者 n
        //（3）退出 while 后，再判断 choice 是 y 或者 n，就可以决定是否退出
        //（4）建议一段代码完成一个小功能，尽量不要混在一起
        String choice = "";
        while (true) {
            System.out.println("你确定要退出吗？y/n");
            choice = scanner.next();
            if ("y".equals(choice) || "n".equals(choice)) {
                break;
            }
        }
        //当用户退出 while，进行判断
        if(choice.equals("y")) {
            loop = false;
        }
    }
}
```

**（eight.fourteen) -- SmallChangeSysAPP**

```java
package eight.fourteen;

public class SmallChangeSysAPP {
    public static void main(String[] args) {
        new SmallChangeSysOOP().mainMenu();
    }
}
```



# 第九章       房屋出租系统



## 房屋出租系统项目需求

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租系统项目需求.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租系统界面.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租系统新增房源.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租查找房源.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租删除房源.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租修改房源信息.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租房屋列表.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租系统退出系统.png)



## 房屋出租系统工具类开发

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\房屋出租系统工具类开发.png)

**工具类 Utility（nine包）**

```java
package nine.utils;

import java.util.Scanner;

public class Utility {
    //静态属性...
    private static Scanner scanner = new Scanner(System.in);

    private static String readKeyBoard(int limit, boolean blankReturn){
        //定义字符串
        String line = "";
        //scanner.hasNextLine()判断有没有下一行
        while(scanner.hasNextLine()){
            line = scanner.nextLine();//读取这一行
            //如果 line.length = 0,即用户没有输入任何内容，直接回车
            if(line.length() == 0){
                if(blankReturn) return line;//如果blankReturn = true，可以返回空串
                else continue;//如果blankReturn=false，不接受空串，必须输入内容
            }
            //如果用户输入的内容大于了 limit，就提示重新输入
            //如果用户输入的内容 >0 <=limit，我就接受
            if(line.length() < 1 || line.length() > limit){
                System.out.print("输入长度（不能大于" + limit + "）错误，请重新输入：");
                continue;
            }
            break;
        }
        return line;
    }
    public static char readMenuSelection() {
        char c;
        for (; ; ) {
            String str = readKeyBoard(1, false);
            c = str.charAt(0);//将字符串转换成字符char
            if (c != '1' && c != '2' && c != '3' && c != '4' && c != '5') {
                System.out.println("选择错误，请重新输入");
            } else break;
        }
        return c;
    }

    public static char readChar() {
        String str = readKeyBoard(1, false);
        return str.charAt(0);
    }

    public static char readChar(char defaultValue) {
        String str = readKeyBoard(1, true);
        return (str.length() == 0) ? defaultValue : str.charAt(0);
    }

    public static int readInt() {
        int n;
        for (; ; ) {
            String str = readKeyBoard(2, false);
            try {
                n = Integer.parseInt(str);
                break;
            } catch (NumberFormatException e) {
                System.out.println("数字输入错误，请重新输入：");
            }
        }
        return n;
    }

    public static int readInt(int defaultValue) {
        int n;
        for (; ; ) {
            String str = readKeyBoard(10, true);
            if (str.equals("")) {
                return defaultValue;
            }
            //异常处理
            try {
                n = Integer.parseInt(str);
                break;
            } catch (NumberFormatException e) {
                System.out.println("数字输入错误，请重新输入：");
            }
        }
        return n;
    }

    public static String readString(int limit, String defaultValue){
        String str = readKeyBoard(limit, true);
        return str.equals("") ? defaultValue : str;
    }

    public static String readString(int limit){
        return readKeyBoard(limit, false);
    }

    public static char readConfirmSelection(){
        System.out.println("请输入你的选择（y/n）");
        char c;
        for(; ; ){
            String str = readKeyBoard(1, false).toUpperCase();
            c = str.charAt(0);
            if(c == 'Y' || c == 'N'){
                break;
            }
            else{
                System.out.println("选择错误，请重新输入：");
            }
        }
        return c;
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\项目分析图.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\项目完全分析.png)



### 项目代码（在nine包下）



# 第十章       面向对象编程（高级部分）



## 类变量和类方法（静态变量和静态方法）

### 类变量

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类变量.png)

**传统的写法（ten.one包）**

```java
package ten.one;

public class ChildGame {
    public static void main(String[] args) {

        //定义一个变量 count，统计有多少个小孩加入游戏
        int count = 0;
        Child child = new Child("白骨精");
        child.join();
        count++;

        Child child1 = new Child("狐狸精");
        child.join();
        count++;

        Child child2 = new Child("老鼠精");
        child.join();
        count++;

        System.out.println("共有" + count + "个小孩加入游戏");
    }
}
class Child{//类
    private String name;

    public Child(String name) {
        this.name = name;
    }
    public void join(){
        System.out.println(name + "加入游戏...");
    }
}
```



**使用静态变量的代码（ten.one包）**

```java
package ten.one;

public class ChildGameUD {
    public static void main(String[] args) {

//        //定义一个变量 count，统计有多少个小孩加入游戏
//        int count = 0;
        Childs child = new Childs("白骨精");
        child.join();
        child.count++;

        Childs child1 = new Childs("狐狸精");
        child1.join();
        child1.count++;

        Childs child2 = new Childs("老鼠精");
        child2.join();
        child2.count++;

        //类变量，可以通过类名来访问
        System.out.println("共有" + Childs.count + "个小孩加入游戏");
        System.out.println("child.count=" + child.count);//3
        System.out.println("child1.count=" + child1.count);//3
        System.out.println("child2.count=" + child2.count);//3
    }
}
class Childs{//类
    private String name;
    //定义一个变量 count，是一个类变量（静态变量）static 静态
    //该变量最大的特点就是会被Childs类所有的对象实例共享
    public static int count = 0;

    public Childs(String name) {
        this.name = name;
    }
    public void join(){
        System.out.println(name + "加入游戏...");
    }
}
```



### **类变量内存布局（介绍）**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类变量内存布局.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\静态变量示意图.png)



### 类变量定义

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类变量定义.png)

### 类变量使用注意事项和细节讨论

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类变量使用注意事项和细节讨论.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类变量使用注意事项和细节讨论1.png)



### 类方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类方法介绍.png)

**类方法的使用场景**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类方法的使用场景.png)

**示例代码（ten.two包）**

```java
package ten.two;

public class StaticMethod {
    public static void main(String[] args) {
        //创建两个学生对象，交学费
        Stu tom = new Stu("tom");
        tom.payFee(100);

        Stu mary = new Stu("mary");
        mary.payFee(200);
        //输出当前收到的总学费
        Stu.showFee();//300

        //如果我们希望不创建实例，可以调用某个方法（即当做工具来使用）
        //这时，把方法做成静态方法时非常合适
        System.out.println("9的开平方的结果是=" + Math.sqrt(9));
        System.out.println(MyTools.calSum(10,30));
    }
}

//开发自己的工具类时，可以将方法做成静态的，方便调用
class MyTools{
    //求出两个数的和
    public static double calSum(double n1, double n2){
        return n1 + n2;
    }
}

class Stu{
    private String name;//普通成员
    //定义一个静态变量，来积累学生的学费
    private static double fee = 0;

    public Stu(String name) {
        this.name = name;
    }
    //说明
    //1、当方法使用了 static 修饰后，该方法就是静态方法
    //2、静态方法就可以访问静态属性/变量
    public static void payFee(double fee){
        Stu.fee += fee;//累积学费
    }

    public static void showFee(){
        System.out.println("总学费有：" + Stu.fee);
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类方法使用注意事项和细节讨论.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类方法使用注意事项和细节讨论1.png)



## main方法介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\main方法介绍.png)

### main方法参数使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\main方法参数使用.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\main方法介绍代码.png)

```java
public class Hello{
    public static void main(String[] args){
        //args 是如何传入
        //遍历显示
        for(int i = 0; i < args.length; i++){
            System.out.println("第" + (i + 1) + "个参数=" + args[i]));
        }
    }
}
```



### main注意事项和使用细节（ten.three）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\main注意事项和使用细节.png)

```java
package ten.three;

public class Main01 {

    //静态的变量/属性
    private static String name = "Mike";
    public int n1 = 0;

    public void cry(){
        System.out.println("在哭！！！");
    }

    public static void main(String[] args) {
        //可以直接使用 name
        //1、静态方法 main 可以访问本类的静态成员
        System.out.println("name=" + name);
        //2、静态方法 main 不可以访问本类的非静态成员
//        System.out.println("n1=" + n1);
//        cry();
        //3、静态方法 main 要访问本类的非静态成员，需要先创建对象，再调用即可
        Main01 main01 = new Main01();
        System.out.println(main01.n1);
        main01.cry();
    }
}
```



### idea 传递参数 main

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\idea传递参数main.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\idea传递参数main使用.png)



## 代码块

### 代码块介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\代码块介绍.png)

### 代码块的好处

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\代码块的好处.png)

**示例代码（ten.four）**

```java
package ten.four;

public class CodeBlock01 {
}
class Movie{
    private String name;
    private double price;
    private String director;

    //构造器
    //三个构造器 -> 重载
    /*
    （1）下面的三个构造器都有相同的语句
    （2）这样代码看起来比较冗余
    （3）这时我们可以把相同的语句，放入到一个代码块中，即可
    （4）这样当我们不管调用哪一个构造器，创建对象，都会先调用代码块的内容
    （5）代码块调用的顺序优先于构造器..
     */
    {
        System.out.println("电影屏幕打开...");
        System.out.println("广告开始...");
        System.out.println("电影正在开始...");
    }

    public Movie(String name) {
        this.name = name;
        System.out.println("Moice(String name)被调用...");
    }

    public Movie(String name, double price) {
        this.name = name;
        this.price = price;
        System.out.println("Moice(String name, double price)被调用...");
    }

    public Movie(String name, double price, String director) {
        this.name = name;
        this.price = price;
        this.director = director;
        System.out.println("Moice(String name, double price, String director)被调用...");
    }
}
```



### 代码块使用注意事项和细节讨论

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\代码块使用注意事项和细节讨论.png)

**示例代码（ten.four）**

```java
package ten.four;


public class CodeBlockDetail01 {
    public static void main(String[] args) {
        //类被加载的情况举例（静态代码块只能被执行一次）
        //1、创建对象实例时（new）
        AA aa = new AA();
        //2、创建子类对象实例，父类也会被加载，而且，父类先被加载，子类后被加载
        BB bb = new BB();
    }
}
class AA extends BB{
    static{
        System.out.println("AA 静态代码块被执行...");
    }
    {
        System.out.println("AA 普通代码块被执行...");
    }

    public AA() {
    }
}
class BB{
    static{
        System.out.println("BB 静态代码块被执行...");
    }

    public BB() {
    }
}
```



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\代码块使用注意事项和细节讨论1.png)

**示例代码（ten.four）**

```java
package ten.four;

public class CodeBlockDetail02 {
    public static void main(String[] args) {
        DD bb = new DD();
    }
}

class DD{
    //静态属性的初始化
    private static int n1 = getN1();
    private int n2 = getN2();
    static{
        System.out.println("DD 静态代码块被执行...");
    }
    {
        System.out.println("DD 普通代码块被执行...");
    }

    public DD() {
    }
    public static int getN1(){
        System.out.println("getN1被调用...");
        return 100;
    }
    public int getN2(){
        System.out.println("getN2被调用...");
        return 99;
    }
}
```



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\代码块使用注意事项和细节讨论2.png)

**示例代码（ten.four）**

```java
package ten.four;

public class CodeBlockDetail03 {
    public static void main(String[] args) {
        new BBB();
    }
}
class AAA{//父类Object
    {
        System.out.println("AAA的普通代码块被调用...");
    }
    public AAA(){
        //(1)super()
        //(2)调用本类的普通的代码块
        System.out.println("AAA() 构造器被调用...");
    }
}
class BBB extends AAA{
    {
        System.out.println("BBB的普通代码块被调用...");
    }
    public BBB(){
        //(1)super()
        //(2)调用本类的普通的代码块
        System.out.println("BBB() 构造器被调用...");
    }
}
```



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\代码块使用注意事项和细节讨论3.png)

**示例代码（ten.four）**

```java
package ten.four;

public class CodeBlockDetail04 {
    public static void main(String[] args) {
        new BBBB();
    }
}
class AAAA{//父类Object
    //静态属性的初始化
    private static int n1 = getN1();//1
    public int n2 = getN2();//5
    static{//2
        System.out.println("AAAA的静态代码块被调用...");
    }
    {//6
        System.out.println("AAAA的普通代码块被调用...");
    }
    public AAAA(){//7
        //(1)super()
        //(2)调用本类的普通的代码块和普通属性的初始化
        System.out.println("AAAA() 构造器被调用...");
    }
    public static int getN1(){//3
        System.out.println("AAAA类的getN1被调用...");
        return 100;
    }
    public int getN2(){//5
        System.out.println("AAAA类的getN2被调用...");
        return 99;
    }
}
class BBBB extends AAAA{
    //静态属性的初始化
    private static int n1 = getN3();//3
    public int n2 = getN4();//8
    static{//4
        System.out.println("BBBB的静态代码块被调用...");
    }
    {//9
        System.out.println("BBBB的普通代码块被调用...");
    }
    public BBBB(){//10
        //(1)super()
        //(2)调用本类的普通的代码块和普通属性的初始化
        System.out.println("BBBB() 构造器被调用...");
    }
    public static int getN3(){//1
        System.out.println("BBBB类的getN3被调用...");
        return 100;
    }
    public int getN4(){
        System.out.println("BBBB类的getN4被调用...");
        return 99;
    }
}
```



## 单例设计模式

### 单例设计模式介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\单例设计模式介绍.png)

### 单例设计模式应用场景

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\单例设计模式应用场景.png)

### 饿汉式

**饿汉式示例代码（ten.five）**

```java
package ten.five;

public class SingeTon01 {
    public static void main(String[] args) {
        GrilFriend instance = GrilFriend.getInstance();
        System.out.println(instance);
        GrilFriend instance1 = GrilFriend.getInstance();
        System.out.println(instance1);
        System.out.println(instance == instance1);
    }
}
//有一个类，GrilFriend
//只能有一个女朋友
class GrilFriend{

    private String name;
    //为了能够在静态方法中，返回 gf 对象，需要将其修饰为 static
    //对象，通常是重量级的对象，饿汉式可能造成创建了对象，但是没有使用
    private static GrilFriend gf = new GrilFriend("小红");

    //如何保障我们只要能创建一个 GrilFriend 对象
    //步骤[单利模式-饿汉式]
    /*
    1、将构造器私有化
    2、在类的内部直接创建
    3、提供一个公共的 static 方法，返回 gf 对象
     */
    private GrilFriend(String name){
        this.name = name;
    }
    public static GrilFriend getInstance(){
        return gf;
    }
}

```



### 懒汉式

**懒汉式示例代码（ten.five）**

```java
package ten.five;

public class SingleTon02 {
    public static void main(String[] args) {

        Cat instance = Cat.getInstance();
        System.out.println(instance);
        //再次调用getInstance
        Cat instance1 = Cat.getInstance();
        System.out.println(instance1);
    }
}
//希望在程序运行过程中，只能创建一个 Cat 对象
//使用单例模式
class Cat{
    private String name;
    private static Cat cat;
    //步骤[单利模式-懒汉式]
    /*
    1、将构造器私有化
    2、定义一个static静态属性对象
    3、提供一个公共的 static 方法，返回 一个 Cat 对象
     */
    private Cat(String name){
        this.name = name;
    }
    public static Cat getInstance(){
        if(cat == null){
            cat = new Cat("小可爱");
        }
        return cat;
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\单例模式懒汉式.png)



### 单例模式两种形式的比较

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\单例模式两种形式的比较.png)

**单例模式小结**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\单例模式小结.png)



## final关键字

### final关键字介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\final关键字介绍.png)

**示例代码（ten.six）**

```java
package ten.six;

public class Final01 {
    public static void main(String[] args) {
        E e = new E();
//        e.TAX_RATE = 0.09;//错误
    }
}
//如果我们要求 A 类不能被其它类继承
//可以使用 final 修饰 A 类
final class A{}
//class B extends A{}//错误

class C{
    //如果我们要求 hi 不能被子类重写
    //可以使用final修饰 hi方法
    public final void hi(){}
}
class D extends C{
//    public void hi(){
//        System.out.println("重写了C类的hi方法");
//    }
}
//当不希望类的某个属性的值被修改，可以用 final 修饰
class E{
    public final double TAX_RATE = 00.8;
}
//当不希望某个局部变量的值被修改，可以用 final 修饰
class F{
    public void cry(){
        //这时，NUM 也称为局部常量
        final double NUM = 0.01;
//        NUM = 0.9;//错误
        System.out.println("NUM=" + NUM);
    }
}
```



### final使用注意事项和细节讨论

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\final使用注意事项和细节讨论.png)

**示例代码（ten.six）**

```java
package ten.six;

public class FinalDetail01 {
    public static void main(String[] args) {
        CC cc = new CC();
        new EE().cal();
    }
}
class AA{
    /*
    如果 final 修饰的属性是静态的，则初始化的位置只能是
    1、定义时：如 public final double TAX_RATE= 0.08
    2、在构造器中
    3、在代码块中
     */
    public final double TAX_RATE = 0.08;
    public final double TAX_RATE2;
    public final double TAX_RATE3;
    public AA(){
        TAX_RATE2 = 1.1;
    }
    {
        TAX_RATE3 = 0.99;
    }
}
//final 类不能继承，但是可以实现实例化对象
final class CC{}
//如果类不是 final 类，但是含有 final 方法，则该方法虽然不能重写，但是可以被继承
//即，仍然遵守继承的机制
class DD{
    public final void cal(){
        System.out.println("cal()方法");
    }
}
class EE extends DD{}
```



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\final使用注意事项和细节讨论1.png)

**示例代码（ten.six）**

```java
package ten.six;

public class FinalDetail02 {
    public static void main(String[] args) {
        System.out.println(BBB.num);
        //包装类，String 是final类，不能被继承
    }
}
//final 和 static 往往搭配使用，效率更高，不会导致类加载，底层编译器做了优化处理
class BBB{
    public static int num = 10000;
    static{
        System.out.println("BBB 静态代码块被执行...");
    }
}
final class AAA{
    //一般来说，如果一个类已经是 final 类了，就没有必要再将方法修饰成 final 方法
//    public final void cry(){}
}
```



## 抽象类

### 抽象类介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类入门.png)

**父类方法不确定性问题**

===>考虑将该方法设计为抽象（abstract）方法

===>所谓抽象方法就是没有实现的方法

===>所谓没有实现是指，没有方法体

===>当一个类中存在抽象方法时，需要将声明为 abstract 类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类的介绍.png)





### 抽象类使用注意事项和细节讨论

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类使用注意事项和细节讨论.png)

**示例代码（ten.seven）**

```java
package ten.seven;

public class AbstractDetail01 {
    public static void main(String[] args) {
        //抽象类，不能被实例化
        //new A();
    }
}
//抽象类不一定要包含 abstract 方法。也就是说，抽象类可以没有 abstract 方法
//还可以有实现的方法
abstract class A{
    public void hi(){
        System.out.println("hi");
    }
}
```



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类使用注意事项和细节讨论1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类使用注意事项和细节讨论2.png)

**示例代码（ten.seven）**

```java
package ten.seven;

public class AbstractDetail02 {
    public static void main(String[] args) {
        System.out.println("hello");
    }
}
//如果一个类继承了抽象类，则它必须实现抽象类的所有抽象方法，除非它自己也声明为 abstract 类
abstract class E{
    public abstract void hi();
}
abstract class F extends E{}
class G extends E{
    //这里相等于G子实现了父类E的抽象方法，所谓实现方法，就是有方法体
    @Override
    public void hi() {
        System.out.println("必须重写抽象类的抽象方法");
    }
}
//抽象方法不能使用 private、final 和 static 类修饰，因为这些关键字都是和重写相违背的
abstract class H {
    public abstract void hi();//抽象方法
}
```



## 抽象类最佳实践 - 模板设计模式

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类-模板设计模式.png)



**抽象类模板设计图解**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类模板设计图解.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\抽象类模板设计.png)

**示例代码（ten.seven.Test 测试类）：略**



## 接口

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口入门.png)

**示例代码（ten.eight)**

UsbInterface 接口

```java
package ten.eight;

public interface UsbInterface {//接口
    //规定接口的相关方法
    public void start();
    public void stop();
}
```

Camera 类

```java
package ten.eight;

public class Camera implements UsbInterface{
    @Override
    public void start() {
        System.out.println("相机开始工作...");
    }

    @Override
    public void stop() {
        System.out.println("相机停止工作...");
    }
}
```

Phone 类

```java
package ten.eight;

public class Phone implements UsbInterface{
    @Override
    public void start() {
        System.out.println("手机开始工作...");
    }

    @Override
    public void stop() {
        System.out.println("手机停止工作...");
    }
}
```

Computer 类

```java
package ten.eight;

public class Computer {
    //编写一个方法，计算机工作
    public void work(UsbInterface usbInterface){
        usbInterface.start();
        usbInterface.stop();
    }
}
```

Interface01 类（测试类）

```java
package ten.eight;

public class Intetrface01 {
    public static void main(String[] args) {
        //创建手机，相机对象
        Camera camera = new Camera();
        Phone phone = new Phone();
        //创建计算机
        Computer computer = new Computer();
        computer.work(phone);//把手机接入到计算机
        System.out.println("==========");
        computer.work(camera);
    }
}
```



### 接口介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口介绍.png)

AInterface 接口

```java
package ten.eight;

public interface AInterface {
    //写属性
    public int n1 = 10;
    //写方法
    //在接口中，抽象方法，可以省略abstract关键字
    public void hi();
    //在jdk8及之后，可以有默认实现方法,需要使用default关键字
    default public void ok(){
        System.out.println("ok。。。。");
    }
    //在jdk8及之后，可以有静态方法
    public static void cry(){
        System.out.println("cry....");
    }
}
```

Interface02 类

```java
package ten.eight;

public class Interface02 {
    public static void main(String[] args) {

    }
}
class AAA implements AInterface{
    //1、如果一个类 implenments 实现 接口
    //2、需要将该接口的所有抽象方法都要实现
    @Override
    public void hi() {
        System.out.println("重写接口的抽象方法");
    }
}
```



### 接口深入讨论

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口深入讨论.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口深入讨论1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口应用举例说明.png)



### 接口注意实现和细节使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口注意实现和细节使用.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口注意实现和细节使用1.png)



### 接口 vs 继承

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口vs继承.png)

**示例代码（ten.nine)**

```java
package ten.nine;

public class ExtendsVsInterface {
    public static void main(String[] args) {
        LittleMonkey wukong = new LittleMonkey("悟空");
        wukong.climbing();
        wukong.swimming();
        wukong.flying();
    }
}
class Monkey{
    private String name;

    public Monkey(String name) {
        this.name = name;
    }

    public void climbing(){
        System.out.println(name + " 会爬树...");
    }

    public String getName() {
        return name;
    }
}
//接口
interface Fishable{
    void swimming();
}
interface Birdable{
    void flying();
}

//小结：当子类继承父类，就自动的拥有父类的功能
//如果子类需要扩展功能，可能通过实现接口的方式扩张
//可以理解实现接口是对Java单继承机制的一种补充
//继承
class LittleMonkey extends Monkey implements Fishable,Birdable{
    public LittleMonkey(String name){
        super(name);
    }
    public void swimming(){
        System.out.println(getName() + " 通过学习，会游泳...");
    }
    public void flying(){
        System.out.println(getName() + " 通过学习，会飞行...");
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口vs继承小结.png)

接口在一定程度上实现代码解耦【即 接口规范化 + 动态绑定】



### 接口的多态特性

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\接口的多态特性.png)

**（多态参数）示例代码（ten.ten)**

```java
package ten.ten;

public class InterfacePloyParameter {
    public static void main(String[] args) {
        //接口类型的变量 if01 可以指向实现了IF 接口类的对象实例
        IF if01 = new Monster();
        if01 = new Car();
        //继承体现的多态
        //父类类型的变量 a 可以指向继承 AAA 的子类的对象实例
        AAA a = new BBB();
        a = new CCC();
    }
}
interface IF{}
class Monster implements IF{}
class Car implements IF{}
class AAA{}
class BBB extends AAA{}
class CCC extends AAA{}
```



**（多态数组）示例代码（ten.ten)**

```java
package ten.ten;

public class InterfacePloyArr {
    public static void main(String[] args) {
        //多态数组 -> 接口类型数组
        Usb[] usbs = new Usb[2];
        usbs[0] = new Phone();
        usbs[1] = new Camera();
        /*
        给 Usb 数组中，存放 Phone 和 Camera 对象，Phone 类还有一个特有的方法 call()，
        请遍历 Usb 数组，如果是 Phone 对象，除了调用 Usb 接口定义的方法外，
        还需要调用 Phone 特有方法 call
         */
        for(int i = 0; i < usbs.length; i++){
            usbs[i].work();//动态绑定
            //和前面一样，我们仍然需要进行类型的向下转型
            if (usbs[i] instanceof Phone) {
                ((Phone)usbs[i]).call();
            }
        }
    }
}
interface Usb{
    void work();
}
class Phone implements Usb{
    public void call(){
        System.out.println("手机开始打电话...");
    }

    @Override
    public void work() {
        System.out.println("手机工作中...");
    }
}
class Camera implements  Usb{
    @Override
    public void work() {
        System.out.println("相机工作中...");
    }
}
```



**（多态传递）示例代码（ten.ten)**

```java
package ten.ten;

public class InterfacePloyPass {
    public static void main(String[] args) {
        //接口类型的变量可以指向，实现了该接口的类的对象实例
        IG ig = new Teacher();
        //如果 IG 继承了 IH 接口，而Teacher类实现了 IG 接口
        //那么，实际上相当于 Teacher 类 也实现了 IH 接口
        //这就是所谓的，接口多态传递现象
        IH ih = new Teacher();
    }
}
interface IH{}
interface IG extends IH{}
class Teacher implements IG{

}
```



## 内部类

### 内部类介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\内部类介绍.png)

### 内部类分类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\内部类分类.png)

### 局部内部类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\局部内部类的使用.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\局部内部类的使用1.png)



### 匿名内部类（重要）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\匿名内部类的使用.png)

**示例代码（ten.eleven)**

```java
package ten.eleven;

import com.sun.xml.internal.ws.api.model.wsdl.WSDLOutput;

public class AnonymouslnnerClass {
    public static void main(String[] args) {

    }
}
class Outer01{
    private int n1 = 10;//属性
    public void method(){//方法
        //传统方法
//        IA tiger = new Tiger();
//        tiger.cry();
        //基于接口的基于内部类
        //1、需求：想使用IA接口，并创建对象
        //2、传统方式，是写一个类，实现该接口，并创建对象
        //3、需求是 Tiger/Dog 类只能使用一次，后面再不使用
        //4、可以使用匿名内部类来简化开发
        //5、tiger 的编译类型 ？ IA
        //6、tiger 的运行类型 ？ 就是匿名内部类

        /*
        它的底层相当于,XXXX 会分配 类名 Outer04$1 的编号
        class XXXX implements IA{
            @Override
            public void cry() {
                System.out.println("老虎吼吼叫...");
            }
        }
         */
        //7、jdk 底层在创建匿名内部类 Outer04$1，立即马上就创建了 Outer04$1 实例，并且把地址返回给 tiger
        //8、匿名内部类使用一次，就不能再使用
        IA tiger = new IA(){
            @Override
            public void cry() {
                System.out.println("老虎吼吼叫...");
            }
        };
        tiger.cry();

        //演示基于类的匿名内部类
        //分析
        //1、father 的编译类型 Father
        //2、father 运行类型 Outer04$2
        //3、底层会创建匿名内部类
        //4、同时也直接返回了 匿名内部类 Outer04$2 的对象
        //5、注意("jack") 参数列表会传递给构造器
        /*
        class Outer04$2 extends Father{}
         */
        Father father = new Father("jack"){
            @Override
            public void test() {
                System.out.println("匿名内部类重写了test方法");
            }
        };
        System.out.println("father对象的运行类型为" + father.getClass());
        father.test();

        //基于抽象类的匿名内部类
        Animal animal = new Animal(){
            @Override
            void eat() {
                System.out.println("小狗吃骨头...");
            }
        };
    }
}
interface IA{//接口
    public void cry();
}
//匿名内部类实现，写法可以简化，不用创建相关的类了
//class Tiger implements IA{
//    @Override
//    public void cry() {
//        System.out.println("老虎吼吼叫...");
//    }
//}
//class Dog implements IA{
//    @Override
//    public void cry() {
//        System.out.println("小狗汪汪叫...");
//    }
//}
class Father{//类
    public Father(String name){//构造器
        System.out.println("接收到name" + name);
    }
    public void test(){}//方法
}
abstract class Animal{
    abstract void eat();
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\匿名内部类的使用1.png)

**示例代码（ten.eleven)**

```java
package ten.eleven;

public class AnonymouslnnerClassDetail {
    public static void main(String[] args) {

    }
}
class Outer2{
    private int n1 = 99;
    public void f1(){
        //创建一个基于类的匿名内部类
        Person p = new Person(){
            @Override
            public void hi() {
                System.out.println("匿名内部类重写了 hi 方法");
            }
        };
        p.hi();//第一种该方法：动态绑定，运行类型是 Outer05$1
        
        //第二种方法：也可以直接调用
        new Person(){
            @Override
            public void hi() {
                System.out.println("匿名内部类 hi 方法被重写了");
            }

            @Override
            public void ok(String str) {
                super.ok(str);
            }
        }.ok("jack");
    }
}
class Person{
    public void hi(){
        System.out.println("Person hi()");
    }
    public void ok(String str){
        System.out.println("Person ok() " + str);
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\匿名内部类的使用2.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\匿名内部类的使用3.png)



### 匿名内部类的最佳实践

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\匿名内部类的最佳实践.png)

**示例代码（ten.twelve)**

```java
package ten.twelve;

public class InnerClassExercise01 {
    public static void main(String[] args) {
        //当做实参直接传递，简洁高效
        f1(new IL(){
            @Override
            public void show() {
                System.out.println("这是一幅名画...");
            }
        });
        //传统方式
        f1(new Picture());
    }
    //静态方法，形参是接口类型
    public static void f1(IL il){
        il.show();
    }
}
//接口
interface IL{
    void show();
}
//类 -> 实现IL => 编程领域（硬编程）
class Picture implements IL{
    @Override
    public void show() {
        System.out.println("这是一幅名画...");
    }
}
```



## 成员内部类

### 成员内部类的使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员内部类的使用.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员内部类的使用1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\成员内部类的使用1.png)



## 静态内部类

### 静态内部类的使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\静态内部类的使用.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\静态内部类的使用1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\静态内部类的使用2.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\静态内部类的使用3.png)





# 第十一章       枚举和注解



## 枚举介绍

### **先看一个需求**

要求创建季节（Season）对象，请设计并完成，Enumeration01.java（eleven.one）

```java
package eleven.one;

public class Enumeration01 {
    public static void main(String[] args) {
        Season spring = new Season("春天", "温暖");
        Season summer = new Season("夏天", "炎热");
        Season autumn = new Season("秋天", "凉爽");
        Season winter = new Season("冬天", "寒冷");
//        autumn.setName("NNN");
//        autumn.setDesc("非常热。。。");
        //因为对于季节而已，它的对象（具体值），是固定的四个，不会有更多
        //按这个设计类的思路，不能体现季节是指定的四个对象
        //因此，这样的设计不好
        Season other = new Season("红天","~~~");

    }
}
class Season{
    private String name;
    private String desc;//描述

    public Season(String name, String desc) {
        this.name = name;
        this.desc = desc;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getDesc() {
        return desc;
    }

    public void setDesc(String desc) {
        this.desc = desc;
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\基本默认注解创建.png)



### 分析问题

创建 Season 对象有如下特点：

1、季节的值是有限的几个值（spring，summer，autumn，winter）。

2、只读，不需要修改。



### 解决方案 - 枚举

1、枚举对应英文（enumeration，简写enum）

2、枚举是一组常量的集合

3、可以这样理解：枚举属于一种特殊的类，里面只包含一组有限的特定的对象



### 枚举的两种实现方式

1、自定义类实现枚举

2、使用 enum 关键字实现枚举



## 自定义枚举



### 自定义类实现枚举 - 应用案例

1、不需要提供 setXXX 方法，因为枚举对象值通常为只读。

2、对枚举对象/属性使用 final + static 共同修饰，实现底层优化。

3、枚举对象名通常使用全部大写，常量的命名规范。

4、枚举对象根据需要，也可以有多个属性 // Enumeration02.java（eleven.one）

```java
package eleven.one;

public class Enumeration02 {
    public static void main(String[] args) {
        System.out.println(Season2.AUTUMN);
        System.out.println(Season2.SPRING);
    }
}
//展示定义枚举实现
class Season2{
    private String name;
    private String decs;
    //定义了四个对象
    public final static Season2 SPRING = new Season2("春天", "温暖");
    public final static Season2 SUMMER = new Season2("夏天", "炎热");
    public final static Season2 AUTUMN = new Season2("秋天", "凉爽");
    public final static Season2 WINTER = new Season2("冬天", "寒冷");

    //1、将构造器私有化，目的防止直接 new
    //2、去掉 setXXX 方法，防止属性被修改
    //3、在 Season 内部，直接创建固定的对象，加上 static，可以直接通过类名访问
    //4、优化，可以加入 final 修饰符，可以防止类的加载
    private Season2(String name, String decs) {
        this.name = name;
        this.decs = decs;
    }

    public String getName() {
        return name;
    }

    public String getDecs() {
        return decs;
    }

    @Override
    public String toString() {
        return "Season2{" +
                "name='" + name + '\'' +
                ", decs='" + decs + '\'' +
                '}';
    }
}
```

### 自定义类实现枚举 - 小结

小结：进行自定义类实现枚举，有如下特点：

1、构造器私有化

2、本类内部创建一组对象[]

3、对外暴露对象（通过为对象添加 public final static 修饰符）

4、可以提供 get 方法，但是不要提供 set



## enum 关键字实现枚举



### enum 关键字实现枚举 - 应用案例

使用 enum 来实现前面的枚举案例，主要体会和自定义类实现的不同的地方。Enumeration02.java（eleven.one）

```java
package eleven.one;

public class Enumeration03 {
    public static void main(String[] args) {
        System.out.println(Season3.SUMMER);
        System.out.println(Season3.WINTER);
    }
}
//展示使用 enum 关键字来实现枚举类
enum Season3{
    //如果使用关键字 enum 来实现枚举类
    //1、使用关键字 enum 替代 class
    //2、public static final Season3 SPRING = new Season3("春天","温暖") 直接使用
    //SPRING("春天","温暖") 解读 常量名(实参列表)
    //3、如果有多个常量（对象），使用逗号分割即可
    //4、如果使用 enum 来实现枚举，要求将定义常量对象，写在前面
    //5、如果我们使用的是无参构造器，创建常量对象，则可以省略（）
    SPRING("春天","温暖"),
    SUMMER("夏天","炎热"),
    AUTUMN("秋天","凉爽"),
    WINTER("冬天","寒冷"),
    WHAT;//这里调用无参构造器
    private String name;
    private String decs;

    Season3() {}

    Season3(String name, String decs) {
        this.name = name;
        this.decs = decs;
    }

    public String getName() {
        return name;
    }

    public String getDecs() {
        return decs;
    }

    @Override
    public String toString() {
        return "Season3{" +
                "name='" + name + '\'' +
                ", decs='" + decs + '\'' +
                '}';
    }
}
```



### enum 关键字实现枚举 - 注意事项

1、当我们使用 enum 关键字开发一个枚举类时，默认会继承 Enum 类[如何证明]，使用 javap 工具来演示。

2、传统的 public static final Season2 SPRING = new Season2("春天","温暖");简化成 SPRING("春天","温暖")，这里必须知道，它调用的是那个构造器。

3、如果使用无参构造器创建枚举对象，则实参列表和小括号都可以省略。

4、当有多个枚举对象时，使用 “，” 间隔，最后有一个分号结尾。

5、枚举对象必须放在枚举类的行首。

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\枚举javap演示.png)

### 

### enum 关键字实现枚举 - 课堂练习

下面代码是否正确，并且说明表示的含义？

```java
enum Gender{
    BOY,GIRL;//这里其实就是调用Gender类的无参构造器
}
```

1、上面语法是 OK。

2、有一个枚举类 Gender，没有属性。

3、有两个枚举对象 BOY，GIRL，使用的是无参构造器创建。



### enum 常用方法说明

说明：使用关键字 enum 时，会隐式继承 Enum类，这样我们就可以使用 Enum 类的相关的方法。[看下源代码定义]

```java
public abstract class Enum<E extends Enum<e>> implements Comparable<E>,Serializable{
}
```

### enum 常用方法应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\enum常用方法应用实例.png)

我们一起来是举例说明 enum 常用方法的使用，对 Season3 测试。EnumMethod.java（eleven.one）

```java
package eleven.one;

public class EnumMethod {
    public static void main(String[] args) {
        //使用 Season3 枚举类，来演示各种方法
        Season3 autumn = Season3.AUTUMN;

        //输出枚举对象的名字
        System.out.println(autumn.name());

        //ordinal()输出的是该枚举对象的次序/编号，从0开始编号
        //AUTUMN 枚举对象是第三个，因此输出2
        System.out.println(autumn.ordinal());

        //从反编译可以看出 values方法，返回 Season3[]
        //含有定义的所有枚举对象
        Season3[] values = Season3.values();
        System.out.println("===遍历取出枚举对象（增强for）===");
        for(Season3 season: values){//增强for循环
            System.out.println(season);
        }

        //valueOf:将字符串转换成枚举对象，要求字符串必须VT为已有的常量名，否则报异常
        //执行流程
        //1、根据你输入的 "AUTUMN" 到 Season3 的枚举对象去查找
        //2、如果找到了，就返回，如果没找到，就报错
        Season3 spring1 = Season3.SPRING;
        Season3 spring = Season3.valueOf("SPRING");
        System.out.println("spring="+spring);
        System.out.println(spring == spring1);

        //compareTO:比较两个枚举常量，比较的就是编号
        //1、就是把 Season3.AUTUMN 枚举对象的编号和 Season3.SUMMER 枚举对象的编号比较
        //2、看看结果
        System.out.println(Season3.AUTUMN.compareTo(Season3.SUMMER));
        /*
        public final int compareTo(E o) {
            return self.ordinal - other.ordinal;
        }
        Season3.AUTUMN的编号[2] - Season3.SUMMER的编号[1] = 1
         */
    }
}
```



### enum 常用方法一览表

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\enum常用方法一览表.png)

### enum 课堂练习

EnumExercise02.java（eleven.one）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\enum课堂练习.png)

```java
package eleven.one;

public class EnumExercise02 {
    public static void main(String[] args) {
        //获取到所有枚举对象，即数组
        Week[] weeks = Week.values();
        //遍历，使用增强 for 循环
        for(Week week:weeks){
            System.out.println(week);
        }
    }
}
enum Week{
    //定义Week的枚举对象
    MONDAY("星期一"),TUESDAY("星期二"),WEDNESDAY("星期三"),THURSDAY("星期四"),FRIDAY("星期五"),SATURDAY("星期六"),SUNDAY("星期日");

    private String name;

    public String getName() {
        return name;
    }

    Week(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Week{" +  "name='" + name + '\'' + '}';
    }
}
```

### enum 实现接口

EnumDetail.java（eleven.one）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\enum实现接口.png)

```java
package eleven.one;

public class EnumDetail {
    public static void main(String[] args) {
        Music.CLASSICMUSIC.playing();
    }
}
//1、使用 enum 关键字后，就不能在继承其它类了，因为 enum 会隐式继承 Enum，而 Java 是单继承机制
//enum Season3 extends A{
//
//}
//2、enum 实现的枚举类，仍然是一个类，所以还是可以实现接口的
interface IPlaying{
    public void playing();
}
enum Music implements IPlaying{
    CLASSICMUSIC;
    @Override
    public void playing() {
        System.out.println("播放好听的音乐...");
    }
}

```



## JDK 内置的基本注解类型



### 注解的理解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\注解的理解.png)

### 基本的 Annotation 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\基本的Annotation介绍.png)

### @Override 注解

Override 使用说明

1、@Override 注解放在 fly 方法上，表示子类的 fly 方法时重写了父类的 fly。
2、这里如果没有写 @Override 还是会重写父类 fly。
3、如果你写了 @Override 注解，编译器就会去检查该方法是否真的重写了父类的方法，如果的确重写了，则编译通过，如果没有构成重写，则编译错误。
4、查看 @Override 注解源码为 @Target(ElementType.METHOD)，说明只能修饰方法。
5、@Target 是修饰注解的注解，称为元注解。

@Override 注解的案例 OverrideTest.java（eleven.two）

```java
package eleven.two;

public class OverrideTest {
    public static void main(String[] args) {
        Son son = new Son();
        son.fly();
    }
}
class Father{
    public void fly(){
        System.out.println("Father fly...");
    }
}
class Son extends Father{
    //1、@Override 注解放在 fly 方法上，表示子类的 fly 方法时重写了父类的 fly
    //2、这里如果没有写 @Override 还是会重写父类 fly
    //3、如果你写了 @Override 注解，编译器就会去检查该方法是否真的重写了父类的方法
    //   如果的确重写了，则编译通过，如果没有构成重写，则编译错误
    //4、看看 @Override 的定义
    /*
    解读：如果发现 @interface 表示一个注解类
    @Target(ElementType.METHOD)
        @Retention(RetentionPolicy.SOURCE)
        public @interface Override {
        }
     */
    @Override
    public void fly() {
        System.out.println("Son fly...");
    }
}
```

### @interface 注解

@interface 的说明：

@interface 不是 interface，是注解类，是 jdk1.5之后加入的

### @Deprecated 注解

@Deprecated 注解用于表示某个程序元素（类，方法等）已过时

//1、 @Deprecated 修饰某个元素，表示该元素已经过时
//2、即不在推荐使用，但是仍然可以使用
//3、@Target(value={CONSTRUCTOR, FIELD, LOCAL_VARIABLE, METHOD, PACKAGE,PARAMETER, TYPE})。可以修饰方法，类，字段，包，参数等等。
//4、@Deprecated 的作用可以做到新旧版本的兼容和过渡

@Deprecated 注解的案例 DeprecatedTest.java（eleven.two）

```java
package eleven.two;

public class DeprecatedTest {
    public static void main(String[] args) {
        A a = new A();
        a.hi();
    }
}
//1、 @Deprecated 修饰某个元素，表示该元素已经过时
//2、即不在推荐使用，但是仍然可以使用
//3、@Target(value={CONSTRUCTOR, FIELD, LOCAL_VARIABLE, METHOD, PACKAGE, PARAMETER, TYPE})
//4、@Deprecated 的作用可以做到新旧版本的兼容和过渡
@Deprecated
class A{
    @Deprecated
    public int n1 = 10;
    @Deprecated
    public void hi(){}
}

```

### @SuppressWarnings 注解

@SuppressWarnings 注解用于抑制编译器警告

​    boxing,抑制与封装/拆装作业相关的警告
​    cast，抑制与强制转型作业相关的警告
​    dep-ann，抑制与淘汰注释相关的警告
​    deprecation，抑制与淘汰的相关的警告
​    fallthrough，抑制与 switch 陈述式中遗漏 break 相关的警告
​    finally，抑制与未传回 finally 区块相关的警告
​    hiding，抑制与隐藏变数的区域变数相关的警告
​    incomplete-switch，抑制与 switch 陈述式（enum case）中遗漏项目相关的警告
​    javadoc，抑制与 javadoc 相关的警告
​    nls，抑制与 nls 字串文字相关的警告
​    null，抑制与空值分析相关的警告
​    rawtypes，抑制与使用 raw 类型相关的警告
​    resource，抑制与使用 Closeable 类型的资源相关的警告
​    restriction，抑制与使用不建议或禁止参照相关的警告
​    serial，抑制与可序列化的类别遗漏 serialVersionUID 栏位相关的警告
​    static-access，抑制与静态存取不正确相关的警告
​    static-method，抑制与可能宣告为 static 的方法相关的警告
​    super，抑制与置换方法相关但不含 super 呼叫的警告
​    synthetic-access，抑制与内部类别的存取未最佳化相关的警告
​    sync-override，抑制因为置换同步方法面遗漏同步化的警告
​    unchecked，抑制与未检查的作业相关的警告
​    unqualified-field-access,抑制与栏位存取不合格相关的警告
​    unused，抑制与未用的程式码及停用的程式码相关的警告

@SuppressWarnings 注解的案例 SuppressWarningsTest.java

```java
package eleven.two;

import java.util.ArrayList;
import java.util.List;

public class SuppressWarningsTest {
    //1、当我们不希望看到这些警告的时候，可以使用 SuppressWarnings 注解抑制警告信息
    //2、在 {""} 中，可以写入你希望抑制（不显示）警告信息
//    @SuppressWarnings({"all"})
    @SuppressWarnings({"rawtypes","unchecked"})
    public static void main(String[] args) {
        List list = new ArrayList();
        list.add("jack");
        list.add("tom");
        list.add("mary");
        int i;
        System.out.println(list.get(1));
    }
}
```



## 元注解：对注解进行注解



### 元注解的基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDK的元注解.png)



### @Retention 注解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\@Retention注解.png)

**@Retention 注解示意图**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\@Retention注解示意图.png)

**@Retention 注解的案例**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\@Retention注解案例.png)



### @Target 注解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\@Target注解.png)

**@Target 注解源码说明**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\@Target注解源码说明.png)



### @Documented 注解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\@Documented注解.png)

**@Documented 注解源码**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\@Documented注解源码.png)



### @Inherited 注解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\@Inherited注解.png)





# 第十二章       异常（Exception）



## 异常的概念

### 看个实际的问题和一段代码

运行下面的代码，看看有什么问题 - > 引出异常和异常处理机制。Exception01.java（twelve.one）

```java
public static void main(String[] args){
    int num1 = 10;
    int num2 = 0;
    int res = num1 / num2;
    System.out.println("程序继续运行...");
}
```

### 解决方案 - 异常捕获

对异常进行捕获，保证程序可以继续运行。使用 try - catch。

```java
package twelve.one;

public class Exception01 {
    public static void main(String[] args){
        int num1 = 10;
        int num2 = 0;
        //1、num1 / num2 = > 10 / 0
        //2、当执行到 num1 / num2 因为 num2 = 0 ，程序就会出现（抛出）异常 ArithmeticException
        //3、当抛出异常后，程序就退出，崩溃了，下面的代码就不再执行
        //4、大家想想这样的程序好吗？不好，不应该出现了一个不致命的问题，就导致整个系统崩溃
        //5、java 设计者，提供了一个叫异常处理机制来解决该问题
        //int res = num1 / num2;
        /*
        如果程序员，认为一段代码可能出现异常/问题，可以使用 try - catch 异常处理机制解决
        从而保证程序的健壮性
        将该代码块 -> 选中 -> 快捷键 ctrl + alt + t -> 选中 try - catch
        6、如果进行异常处理，那么即使出现了异常，程序可以继续执行
         */
        try {
            int res = num1 / num2;
        } catch (Exception e) {
//            e.printStackTrace();
            System.out.println("出现异常的原因：" + e.getMessage());//输出异常信息
        }
        System.out.println("程序继续运行...");
    }
}
```



## 异常介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\异常介绍.png)



## 异常体系图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\异常体系图.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\异常体系图-1.png)



### 异常体系图小结

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\异常体系图小结.png)



## 常见的异常

### 常见的运行时异常

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\常见的运行时异常.png)

### 常见的运行时异常举例 （NullPointerException）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\常见的运行时异常举例-1.png)

### 常见的运行时异常举例（ArithmeticException）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\常见的运行时异常举例-2.png)

### 常见的运行时异常举例（ArrayIndexOutBoundsException）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\常见的运行时异常举例-3.png)

### 常见的运行时异常举例（ClassCastException）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\常见的运行时异常举例-4.png)

### 常见的运行时异常举例（NumberFormatException）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\常见的运行时异常举例-5.png)



## 编译异常

### 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\编译异常介绍.png)

### 案例说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\编译异常案例说明.png)



## 异常处理概念

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\异常处理基本介绍.png)

```java
try{
    //代码/可能有异常
}catch(Exception e){
    //捕获到异常
    /*
    1、当异常发生时
    2、系统将异常封装成Exception对象e，传递给catch
    3、得到异常对象后，程序员自己处理
    4、注意，如果没有异常，catch代码块不执行
    */
}finally{
    /*
    1、不管 try 代码块是否有异常发生，始终要执行 finally
    2、所以，通常将释放资源的代码，放在 finally
    */
}
```

### throws 处理机制图

1、try - catch - finally 和 throws 二选一

2、如果程序员，没有显示处理异常，默认为 throws。

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\异常处理示意图.png)

### try-catch 异常处理

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\try-catch异常处理.png)

### try-catch 异常处理 - 快速入门

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\try-catch异常处理快速入门.png)

### try-catch 异常处理 - 注意事项

1、如果异常发生了，则异常发生后面的代码不会执行，直接进入到 catch 块。

2、如果异常没有发生，则顺序执行 try 的代码块，不会进入到 catch。

3、如果希望不管是否发生异常，都执行某段代码（比如关闭连接，释放资源等），则使用如下代码 - finally{}

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\try-catch异常处理注意事项.png)

TryCatchDetail.java（twelve.one)

```java
package twelve.one;

public class TryCatchDetail {
    public static void main(String[] args) {
        //1、如果异常发生了，则异常发生后面的代码不会执行，直接进入到 catch 块。
        //2、如果异常没有发生，则顺序执行 try 的代码块，不会进入到 catch。
        //3、如果希望不管是否发生异常，都执行某段代码（比如关闭连接，释放资源等），则使用如下代码 - finally{}
        try {
            String str = "钢铁侠";
            int a = Integer.parseInt(str);
            System.out.println("数字:" + a);
        } catch (NumberFormatException e) {
            System.out.println("异常信息：" + e.getMessage());
        }finally{
            System.out.println("finally代码块被执行...");
        }
        System.out.println("程序继续执行...");
    }
}
```

4、可以有多个 catch 语句，捕获不同的异常（进行不同的业务处理），要求父类异常在后，子类异常在前。

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\try-catch方式处理异常注意事项.png)

TryCatchDetail_java（twelve.one）

```java
package twelve.one;

public class TryCatchDetail_ {
    public static void main(String[] args) {
        /*
        1、如果 try 代码块有可能有多个异常
        2、可以使用多个 catch 分别捕获不同的异常，相应处理
        3、要求子类异常写在前面，父类异常写在后面
         */
        try {
            Person person = new Person();
            person = null;
            System.out.println(person.getName());//NullPointerException
            int n1 = 10;
            int n2 = 0;
            int res = n1 / n2;//ArithmeticException
        } catch (NullPointerException e) {
            System.out.println("空指针异常：" + e.getMessage());
        } catch (ArithmeticException e) {
            System.out.println("算数异常：" + e.getMessage());
        } catch (Exception e) {
            System.out.println(e.getMessage());
        } finally {
        }
    }
}
class Person{
    private String name = "jack";

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

5、可以进行 try - catch 配合只用，这种使用相当于没有捕获异常，因此程序会直接崩溃。

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\try-catch方式处理异常注意事项-5.png)

### try-catch方式处理异常小结

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\try-catch方式处理异常小结.png)



## throws 异常处理

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\throws异常处理基本介绍.png)

### throws 异常处理示意图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\throws异常处理示意图.png)

### 快速入门

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\throws异常处理快速入门.png)

Throws01.java（twelve.two）

```java
package twelve.two;

import java.io.FileInputStream;
import java.io.FileNotFoundException;

public class Throws01 {
    public static void main(String[] args) {

    }
    public void f2() throws FileNotFoundException,NullPointerException{
        /*
        创建了一个文件流对象
        1、这里的异常是一个 FileNotFoundException 编译异常
        2、使用前面讲过的 try - catch - finally
        3、使用 throws，抛出异常，让调用 f2 方法的调用者（方法）处理
        4、throws 后面的异常类型可以是方法中产生的异常类型，也可以是它的父类
        5、throws 关键字后也可以是异常列表，既可以抛出多个异常
         */
        FileInputStream files = new FileInputStream("C://a.txt");
    }
}
```

### 注意事项和使用细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\throws异常处理注意事项.png)

ThrowsDetail.java（twelve.two）

```java
package twelve.two;

import java.io.FileInputStream;
import java.io.FileNotFoundException;

public class ThrowsDetail {
    public static void main(String[] args) {
        f2();
    }
    public static void f2()/* throws ArithmeticException */{
        /*
        1、对于编译异常，程序中必须处理，比如 try - catch 或者 throws
        2、对于运行时异常，程序中如果没有处理，默认就是 throws 的方式处理
         */
        int n1 = 10;
        int n2 = 0;
        double res = n1 / n2;
    }
    public static void f1() /* throws FileNotFoundException */{
        /*
        1、因为f3()方法抛出的是一个编译异常
        2、即这时，就要去f1()必须处理这个编译异常
        3、在 f1() 中，要么 try - catch - finally，或者继续 throws 这个编译异常
         */
        try {
            f3();//抛出异常
        } catch (FileNotFoundException e) {
            System.out.println(e.getMessage());
        }
    }
    public static void f3() throws FileNotFoundException{
        FileInputStream fileInputStream = new FileInputStream("d://aa.txt");
    }
    public static void f4(){
        /*
        1、在f4()中调用方法f5()是OK的
        2、原因是f5()抛出的是运行异常
        3、面java中，并不要求程序员显示处理，因为有默认处理机制
         */
        f5();
    }
    public static void f5() throws ArithmeticException{}
}
class Father{
    public void method() throws RuntimeException{}
}
class Son extends Father{
    //3、子类重写父类的方法时，对抛出异常的规定：子类重写的方法
    //   所有出的异常类型要么和父类抛出的异常一致，要么为父类抛出的异常的类型的子类型
    //4、在 throws 过程中，如果有方法 try - catch，就相当于处理异常，就可以不必throws
    @Override
    public void method() throws NullPointerException {
        super.method();
    }
}
```





异常处理分类

## 自定义异常

### 基本概念

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自定义异常基本概念.png)

### 自定义异常的步骤

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自定义异常的步骤.png)

### 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自定义异常的应用实例.png)

CustomException.java（twelve.two）

```java
package twelve.two;

public class CustomException {
    public static void main(String[] args) {
        int age = 180;
        //要求范围在 18-120 之间，否则抛出一个自定义异常
        if(!(age >= 18 && age <= 120)){
            //这里我们可以通过构造器设置信息
            throw new AgeException("年龄需要在18-120之间");
        }
        System.out.println("你的年龄范围正确");
    }
}
//自定义一个异常
/*
1、一般情况下，我们自定义异常是继承 RuntimeException
2、即把自定义异常做成运行时异常，好处是我们可以使用默认的处理机制
 */
class AgeException extends RuntimeException{
    public AgeException(String message) {//构造器
        super(message);
    }
}
```



## throw 和 throws 的对比

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\throw和throws的区别.png)

### throw和throws的对比 - 测试题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\throw和throws的对比.png)

ThrowException.java（twelve.three）

```java
package twelve.three;

public class ThrowException {
    public static void main(String[] args) {
        try {
            ReturnExceptionDemo.methodA();
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
        ReturnExceptionDemo.methodB();
    }
}
class ReturnExceptionDemo{
    static void methodA(){
        try {
            System.out.println("进入方法A");
            throw new RuntimeException("制造异常");
        } finally{
            System.out.println("用方法A的finally");
        }
    }
    static void methodB(){
        try {
            System.out.println("进入方法B");
            return;
        } finally{
            System.out.println("用方法B的finally");
        }
    }
}
```



# 第十三章       常用类



## 包装类

### 包装类的分类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\包装类的分类.png)

### 包装类的分类示意图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\包装类的分类示意图.png)

### 包装类的基本数据类型的转换

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\包装类的基本数据类型的转换.png)

Integer01.java（thirty.one）

```java
package thirty.one;

public class Integer01 {
    public static void main(String[] args) {
        //演示int <--> Integer 的装箱和拆箱
        /*
        jdk5前是手动装箱和拆箱
        手动装箱 int -> Integer
         */
        int n1 = 100;
        //两种手动装箱方式
        Integer integer = new Integer(n1);//第一种
        Integer integer1 = Integer.valueOf(n1);//第二种
        //手动拆箱
        //Integer -> int
        int i = integer.intValue();


        //jdk5后，就可以自动装箱和自动拆箱
        int n2 = 200;
        //自动装箱 int -> Integer
        Integer integer2 = n2;//底层使用的是 Integer.valueOf(n2) 方法
        //自动拆箱 Integer -> int
        int n3 = integer2;//底层使用的是 integer.intValue() 方法
    }
}
```



### 包装类课堂练习

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\包装类课堂练习.png)

```java
Object obj1 = true ? new Integer(1) : new Double(2.0);
System.out.println(obj1);//1.0
//原因：是三元运算符是一个整体，所以 true ? new Integer(1) : new Double(2.0) 在精度上会提升到 Double 精度。
```



### 包装类型和 String 类型的相互转换

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\包装类型和String类型的相互转换.png)

WrapperVSString.java（thirty.one）

```java
package thirty.one;

public class WrapperVSString {
    public static void main(String[] args) {
        //包装类（Integer） -> String
        Integer i = 100;
        //方式1
        String str1 = i + "";
        //方式2
        String str2 = i.toString();
        //方式3
        String str3 = String.valueOf(i);

        //String -> 包装类（Integer）
        String str4 = "123456";
        Integer i2 = Integer.parseInt(str4);//使用到自动装箱
        Integer i3 = new Integer(str4);//构造器
    }
}
```

### Integer 类和 Character 类的常用方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Integer类和Character类的常用方法.png)

### Integer 类练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Integer类面试题.png)

WrapperExercise02.java（thirty.one）

```java
package thirty.one;

public class WrapperExercise02 {
    public static void main(String[] args) {
        Integer i = new Integer(1);
        Integer j = new Integer(1);
        System.out.println(i == j);//False
        //所以，这里主要是看范围 -128 ~ 127 就是直接返回
        /*
        1、如果 i 在 IntegerCache.low(-128) ~ IntegerCache.high(127) 就直接从数组返回
        2、如果不在 -128 ~ 127，就直接 new Integer(i)
        public static Integer valueOf(int i) {
            if (i >= IntegerCache.low && i <= IntegerCache.high)
                return IntegerCache.cache[i + (-IntegerCache.low)];
            return new Integer(i);
        }
         */
        Integer m = 1;//底层Integer.valueOf(1);->阅读源码
        Integer n = 1;//底层Integer.valueOf(1)
        System.out.println(m == n);//True
        //所以，这里主要是看范围 -128 ~ 127 就是直接返回
        //否则，就 new Integer(xx);
        Integer x = 128;//底层Integer.valueOf(128)
        Integer y = 128;//底层Integer.valueOf(128)
        System.out.println(x == y);//False
    }
}
```

### Integer 类练习题总结

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Integer类面试题总结.png)



## String 类

### String 类的理解和创建对象

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的理解.png)

### String 类架构示意图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类示意图.png)

String01.java（thirty.two）

```java
package thirty.two;

public class String01 {
    public static void main(String[] args) {
        /*
        1、String 对象用于保存字符串，也就是一组字符序列
        2、"jack" 字符串常量，双引号括起来的字符序列
        3、字符串的字符使用 Uncode 字符编码，一个字符（不区分字母还是汉字）占两个字符
        4、String 类有很多构造器，构造器的重载
        常用的有 String s1 = new String();
        String s2 = new String(String original);
        String s3 = new String(char[] a);
        String s4 = new String(char[] a, int startIndex, int count);
        String s5 = new String(byte[] b);
        5、String 类实现了接口 Serializable 【String 可以串行化：可以在网络传输】
                         接口 Comparable [String 对象可以比较大小】
        6、String 是 final 类，不能被其他类继承
        7、String 有属性 private final char value[]; 用于存放字符串内容
        8、一定要注意：value 是一个 final 类型，不能修改。
         */
        String name =  "jack";
        name = "tom";
        
        final char[] value = {'a','b','c'};
        char[] v2 = {'t','o','m'};
        value[0] = 'H';
        //value = v2;不可以修改 value 地址
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String值的改变.png)

### String 对象创建的两种方式

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String对象创建的方式.png)

### String 对象两种创建方式的区别

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String对象两种创建方式的区别.png)

**String 在 JVM 的内存布局**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String在JVM的内存布局.png)

### String 类的练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的练习题-1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的练习题-2.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类练习题-3.png)

StringExercise03.java（thirty.two）

```java
package thirty.two;

public class StringExercise03 {
    public static void main(String[] args) {
        String a = "hsp";//a 指向 常量池的 ”hsp“
        String b = new String("hsp");//b 指向堆中对象
        System.out.println(a.equals(b));//T
        System.out.println(a == b);//F
        //b.intern() 方法返回常量池地址
        System.out.println(a == b.intern());//T；intern 方法自己先查看 API
        System.out.println(b == b.intern());//F
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的练习题-4.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的练习题-5.png)



### 字符串的特性

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\字符串的特性-1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\字符串的特性-2.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\字符串的特性-3.png)

StringExercise08.java（thirty.two）

```java
package thirty.two;

public class StringExercise08 {
    public static void main(String[] args) {
        String a = "hello";
        String b = "abc";
        /*
        1、先创建一个 StringBuilder sb = StringBuilber()
        2、执行 sb.append("hello");
        3、sb.append("abc");
        4、String c = toString();
        最后其实是 c 指向堆中的对象(String) value[] -> 常量池中 "helloabc"
         */
        String c = a + b;
        String d = "helloabc";
        System.out.println(c == d);//False
        String e = "hello" + "abc";
        System.out.println(d == e);//True
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\字符串的特性-4.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\字符串的特性-5.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\字符串的特性-6.png)



### String 类的常见方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的常见方法.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的常见方法一览.png)



### String 类的常见方法应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的常见方法应用实例-1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的常见方法应用实例-2.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的常见方法应用实例-3.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的常用方法应用实例-4.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类的常用方法应用实例-5.png)



## StringBuffer 类

### 基本介绍

​        1、StringBuffer 的直接父类是 AbstractStringBuilder
​        2、StringBuffer 实现了 Serializable，即 StringBuffer 的对象可以串行化
​        3、在父类中，AbstractStringBuilder 有属性 char[] value,不是 final
​           该 value 数组存放字符串内容，引出存放在堆中的
​        4、StringBuffer 是一个 final 类，不能被继承
​        5、因为 StringBuffer 字符内容是存在 char[] value，所有在变化（增加/删除）不用每次都更换地址（即不是每次创建新对象），所以效率高于 String

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\StringBuffer类基本介绍.png)

StringBuffer01.java（thirty.three）

```java
package thirty.three;

public class StringBuffer01 {
    public static void main(String[] args) {
        /*
        1、StringBuffer 的直接父类是 AbstractStringBuilder
        2、StringBuffer 实现了 Serializable，即 StringBuffer 的对象可以串行化
        3、在父类中，AbstractStringBuilder 有属性 char[] value,不是 final
           该 value 数组存放字符串内容，引出存放在堆中的
        4、StringBuffer 是一个 final 类，不能被继承
        5、因为 StringBuffer 字符内容是存在 char[] value，所有在变化（增加/删除）
           不用每次都更换地址（即不是每次创建新对象），所以效率高于 String
         */
        StringBuffer stringbuffer = new StringBuffer("hello");
    }
}
```

### String 和 StringBuffer 的对比

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String和StringBuffer的对比.png)

### StringBuffer的构造器

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\StringBuffer的构造器.png)

### String 和StringBuffer 相互转换

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String和StringBuffer相互转换.png)

### StringBuffer 类常见方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\StringBuffer类常见方法-1.png)

### StringBuffer 类的练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\StringBuffer类的练习题-1.png)

```java
String str = null;
StringBuffer sb = new StringBuffer();
sb.append(str);//看源码可知，底层调用的是 AbstractStringBuilder 的 appendNull 方法
System.out.println(sb.length());
System.out.println(sb);
StringBuffer sb1 = new StringBUffer(str);//看源码可知，底层调用 super(str.length() + 16)，即 null.length()，会抛出 NullPointerException 异常
Sytem.out.println(sb1);
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\StringBuffer类的练习题-2.png)

StringBufferExercise02.java（thirty.three）

```java
package thirty.three;

import java.util.Scanner;

public class StringBufferExercise02 {
    public static void main(String[] args) {
        /*
        输入商品名称和商品价格，要求打印效果示例，使用前面学习的方法完成：
        商品名     商品价格
        手机       123，564.59//比如3,456,789.88
        要求：价格的小数点前面每三位用逗号隔开，在输出。
        思路分析
        1、定义一个 Scanner 对象，接收用户输入的价格（String）
        2、希望使用到 StringBuffer 的 insert，需要将 String 转成 StringBuffer
        3、然后使用相关方法进行字符串的处理
        代码实现：
         */
//        Scanner scanner = new Scanner(System.in);
        String price = "123456.59";
        StringBuffer sb = new StringBuffer(price);
        /*
        先完成一个最简单的实现123,456.59
        找到小数点的索引，然后在该位置的前三位，插入，即可
        上面的两步需要做一个循环处理，才是正确的
         */
        for (int i = sb.lastIndexOf(".") - 3; i > 0; i -= 3) {
            sb = sb.insert(i , ",");
        }
        System.out.println(sb);
    }
}
```



## StringBuilder 类

### StringBuilder 类基本介绍

​        1、StringBuilder 继承 AbstractStringBuilder 类
​        2、实现了 Serializable，说明 StringBuilder 对象是可以串行化（对象可以网络传输，可以保存到件）
​        3、StringBuilder 是 final 类，不能被继承
​        4、StringBuilder 对象字符序列仍然是存放在其父类 AbstractStringBuilder 的 char[] value;
​           因此，字符序列是堆中
​        5、StringBuilder 的方法，没有做互斥的处理，即没有 synchronized 关键字，因此在单线程的情使用，StringBuilder不是线程安全的

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\StringBuilder类基本介绍.png)

StringBuilder01.java（thirty.four）

```java
package thirty.four;

public class StringBuilder01 {
    public static void main(String[] args) {
        /*
        1、StringBuilder 继承 AbstractStringBuilder 类
        2、实现了 Serializable，说明 StringBuilder 对象是可以串行化（对象可以网络传输，可以保存到文件）
        3、StringBuilder 是 final 类，不能被继承
        4、StringBuilder 对象字符序列仍然是存放在其父类 AbstractStringBuilder 的 char[] value;
           因此，字符序列是堆中
        5、StringBuilder 的方法，没有做互斥的处理，即没有 synchronized 关键字，因此在单线程的情况下使用
           StringBuilder不是线程安全的
         */
        StringBuilder stringBuilder = new StringBuilder();
    }
}
```



### StringBuilder 类常用方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\StringBuilder类常用方法.png)



### String、StringBuffer 和 StringBuilder 的比较

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String、StringBuffer和StringBuilder的比较.png)



### String、StringBuffer 和 StringBuilder 的效率测试

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String、StringBuffer和StringBuilder的效率测试.png)

StringVsStringBufferVsStringBuilder.java（thirty.four）

```java
package thirty.four;

public class StringVsStringBufferVsStringBuilder {
    public static void main(String[] args) {
        String text = "";
        long startTime = 0L;
        long endTime = 0L;
        StringBuffer buffer = new StringBuffer("");
        StringBuilder builder = new StringBuilder("");

        //StringBuffer
        startTime = System.currentTimeMillis();
        for (int i = 0; i < 20000; i++) {
            buffer.append(String.valueOf(i));
        }
        endTime = System.currentTimeMillis();
        System.out.println("StringBuffer的执行时间：" + (endTime - startTime));

        //StringBuilder
        startTime = System.currentTimeMillis();
        for (int i = 0; i < 20000; i++) {
            builder.append(String.valueOf(i));
        }
        endTime = System.currentTimeMillis();
        System.out.println("StringBuilder的执行时间：" + (endTime - startTime));

        //String
        startTime = System.currentTimeMillis();
        for (int i = 0; i < 20000; i++) {
            text = text + i;
        }
        endTime = System.currentTimeMillis();
        System.out.println("String的执行时间：" + (endTime - startTime));
    }
}
```



### String、StringBuffer 和 StringBuilde r的选择

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String、StringBuffer和StringBuilder的选择.png)



## Math 类

### Math 类基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Math类基本介绍.png)



### Math 类常用方法应用实例

**random 返回的是 0 <= x < 1 之间的一个随机小数**
        思考：请写出获取 a-b 之间的一个随机整数，a，b均为整数，比如 a = 2，b = 7
        即返回一个数 x ： 2<= x < 7
        Math.random * (b - a) 返回的就是 0 <= x < b - a
    **(1) (int)(a) <= x <= (int)(a + Math.random() * (b - a + 1))****
    **(2) 使用具体的数演示 a = 2 ， b = 7****
        (int)(a + Math.random() * (b - a + 1)) = (int)(2 + Math.random() + 6)
        Math.random() * 6 返回的是 0 <= x < 6 小数
        2 + Math.random() * 6 返回的就是 2 <= x < 8 小数
        (int)(2 + Math.random() * 6) 取整之后 ——> 2 <= x <= 7
    **(3)公式就是 (int)(a + Math.random() * (b - a + 1))**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Math类常用方法应用实例.png)

MathMethd.java（thirty.five）

```java
package thirty.five;

public class MathMethd {
    public static void main(String[] args) {
        //看看 Math 常用的方法（静态方法）
        //1、abs 绝对值
        int abs = Math.abs(-9);
        System.out.println(abs);
        //2、pow 求幂
        double pow = Math.pow(-3.5,4);
        System.out.println(pow);
        //3、ceil 向上取整，返回 ——>该参数的最小整数
        double ceil = Math.ceil(-3.001);
        System.out.println(ceil);
        //4、floor 向下取整，返回 ——>该参数的最大整数
        double floor = Math.floor(-4.9991);
        System.out.println(floor);
        //5、round 四舍五入 Math.floor(该参数+0.5)
        long round = Math.round(-5.001);
        System.out.println(round);
        //6、sqrt 求开方
        double sqrt = Math.sqrt(9.0);
        System.out.println(sqrt);
        //7、random 求随机数
        /*
        random 返回的是 0 <= x < 1 之间的一个随机小数
        思考：请写出获取 a-b 之间的一个随机整数，a，b均为整数，比如 a = 2，b = 7
        即返回一个数 x ： 2<= x < 7
        Math.random * (b - a) 返回的就是 0 <= x < b - a
        (1) (int)(a) <= x <= (int)(a + Math.random() * (b - a + 1))
        (2) 使用具体的数演示 a = 2 ， b = 7
        (int)(a + Math.random() * (b - a + 1)) = (int)(2 + Math.random() + 6)
        Math.random() * 6 返回的是 0 <= x < 6 小数
        2 + Math.random() * 6 返回的就是 2 <= x < 8 小数
        (int)(2 + Math.random() * 6) 取整之后 ——> 2 <= x <= 7
        (3)公式就是 (int)(a + Math.random() * (b - a + 1))
         */
        for (int i = 0; i < 10; i++) {
            System.out.println((int)(2 + Math.random() * (7 - 2 + 1)));
        }
        //max ， min 返回最大最小值
        int min = Math.min(1,9);
        int max = Math.max(45,214);
        System.out.println("min:" + min);
        System.out.println("max:" + max);
    }
}
```



## Arrays 类

### Arrays 类常见方法应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Arrays类常见方法应用实例-1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Arrays类常见方法应用实例-2.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Arrays类sort方法升降序控制.png)

ArrayMethos01.java（thirty.six）

```java
package thirty.six;

import java.util.Arrays;
import java.util.Comparator;

public class ArrayMethos01 {
    public static void main(String[] args) {
        Integer[] integers = {1,29,200};
        //遍历数组
//        for (int i = 0; i < integers.length; i++) {
//            System.out.println(integers[i]);
//        }
        //直接使用Arrays.toString 方法，显示数组
        System.out.println(Arrays.toString(integers));
        //演示 sort 方法的使用
        Integer arr[] = {1,-1,7,0,89};
        /*
        1、可以直接使用冒泡排序，也可以直接使用 Arrays 提供的 sort 方法排序
        2、因为数组是引用类型，所以通过 sort 排序后，会直接影响到实参 arr
        3、sort 重载的，也可以通过传入一个接口 Comparator 实现定制排序
        4、调用定制排序时，传入两个参数
           （1）排序的数组 arr
           （2）实现了 Comparator 接口的匿名内部类，要求实现 compare 方法
           （3）执行到 binarySort 方法 的代码，会根据动态绑定机制 c.compare() 执行我们传入的匿名内部类 compare()
                   while (left < right) {
                        int mid = (left + right) >>> 1;
                        if (c.compare(pivot, a[mid]) < 0)
                            right = mid;
                        else
                            left = mid + 1;
                    }
           （4）new Comparator(){
                    @Override
                    public int compare(Object o1, Object o2) {
                        Integer i1 = (Integer) o1;
                        Integer i2 = (Integer) o2;
                        return i2 - i1;
                    }
                }
           （5）public int compare(Object o1, Object o2)返回的值 >0 还是 <0
                会影响整个排序结果，这就体现了接口编程 + 动态绑定机制 + 匿名内部类的综合使用
                将来的底层框架和源码的使用方式，会非常常见。
        5、先演示效果，再解释
        6、这里体现了接口编程的方式，看看源码，就明白
        源码分析
         */
//        Arrays.sort(arr);//默认排序
//        System.out.println("====排序后====");
//        System.out.println(Arrays.toString(arr));
        //定制排序
        Arrays.sort(arr,new Comparator(){
            @Override
            public int compare(Object o1, Object o2) {
                Integer i1 = (Integer) o1;
                Integer i2 = (Integer) o2;
                return i2 - i1;
            }
        });
        System.out.println("====排序后====");
        System.out.println(Arrays.toString(arr));
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Arrays类常见方法应用实例-3.png)

ArraysSortCustom.java（thirty.six）

```java
package thirty.six;

import java.util.Arrays;

public class ArraysSortCustom {
    public static void main(String[] args) {
        Integer[] arr = {1,2,3,66,242};
        /*
        binarySearch 通过二分搜索法进行查找，要求必须排好序
        1、使用binarySearch 二叉查找
        2、要求数组是有序的，如果该数组是无序的，不能使用 binarySearch
        3、如果数组中不存在该元素，就返回 return -(low + 1);//key not found
         */
        int index = Arrays.binarySearch(arr,23);
        System.out.println("index:" + index);
    }
}
```



### Arrays类练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Arrays类练习题-1.png)

ArrayExercise.java（thirty.six）

```java
package thirty.six;

import java.util.Arrays;
import java.util.Comparator;

public class ArrayExercise {
    public static void main(String[] args) {
        Book[] books = new Book[4];
        books[0] = new Book("红楼梦",100);
        books[1] = new Book("西游",10);
        books[2] = new Book("三国演义",3000);
        books[3] = new Book("水浒传",7);
        //按price排序
        Arrays.sort(books, new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                Book book1 = (Book) o1;
                Book book2 = (Book) o2;
                return book1.getPrice() - book2.getPrice();
            }
        });
        //按书名name长度排序
        Arrays.sort(books, new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                Book book1 = (Book) o1;
                Book book2 = (Book) o2;
                return book1.getName().length() - book2.getName().length();
            }
        });
    }
}
class Book{
    private String name;
    private int price;

    public Book(String name, int price) {
        this.name = name;
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getPrice() {
        return price;
    }

    public void setPrice(int price) {
        this.price = price;
    }

    @Override
    public String toString() {
        return "Book{" +
                "name='" + name + '\'' +
                ", price=" + price +
                '}';
    }
}
```



## System 类

### System 类常见方法和案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\System类常见方法和案例.png)



## BigInteger 和 BigDecimal 类

### BigInteger 和 BigDecimal 类介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\BigInteger和BigDecimal类介绍.png)

### BigInteger 和 BigDecimal 类常见方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\BigInteger和BigDecimal类常见方法.png)

BigInteger_.java（thirty.seven）

```java
package thirty.seven;

import java.math.BigDecimal;
import java.math.BigInteger;

public class BigInteger_ {
    public static void main(String[] args) {
        /*
        当我们编程中，需要处理很大的整数，long不够用
        可以使用 BigInteger 的类来搞定
        long l = 23788888888888888999999999999l;
        System.out.println("l=" + l);
         */
        BigInteger bigInteger = new BigInteger("23788888888888888999999999999");
        BigInteger bigInteger2 = new BigInteger("100");
        System.out.println(bigInteger);
        BigInteger add = bigInteger.add(bigInteger2);
        System.out.println(add);

        /*
        当我们编程中，需要处理很大的整数，double不够用
        可以使用 BigDecimal 的类来搞定
        double d = 1999.23788888888888888999999999999d;
        System.out.println("d=" + d);
         */
        BigDecimal bigDecimal = new BigDecimal("1999.23788888888888888999999999999");
        BigDecimal bigDecimal1 = new BigDecimal("10.1");
        System.out.println(bigDecimal);

        /*
        1、在对 BigInteger 进行加减乘除的时候，需要使用对应的方法，不能直接进行
        2、创建一个需要操作的 BigDecimal 然后调用相应的方法即可
         */
        System.out.println(bigDecimal.add(bigDecimal1));
        System.out.println(bigDecimal.subtract(bigDecimal1));
        System.out.println(bigDecimal.multiply(bigDecimal));
        System.out.println(bigDecimal.divide(bigDecimal1));
    }
}
```



## 日期类

### 第一代日期类（Date）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第一代日期类.png)

### 第一代日期类应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第一代日期类应用实例.png)

Date01.java（thirty.eight）

```java
package thirty.eight;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Date01 {
    public static void main(String[] args) throws ParseException {
        /*
        1、获取当前系统时间
        2、这里的 Date 类是在 java.util 包
        3、默认输出的日期格式是国外的方式，因此通常需要对格式进行转换
         */
        Date date = new Date();//获取当前系统时间
        System.out.println(date);
        Date date1 = new Date(9516268);//通过指定毫秒数得到时间
        System.out.println(date.getTime());

        /*
        1、创建 SimpleDateFormat 对象，可以指定相应的格式
        2、这里的格式是用的字母是规定好，不能乱写
         */
        SimpleDateFormat sdf = new SimpleDateFormat("yyyy年MM月dd日 hh:mm:ss E");
        String format = sdf.format(date);//format：将日期转换成指定格式的字符串
        System.out.println("当前日期:" + format);

        /*
        1、可以把一个格式化的 String 转成对应的 Date
        2、得到 Date 仍然在输出时，还是按照国外的形式，如果希望指定格式输出，需要转换
        3、在把 String -> Date，使用的 sdf 格式需要和你给的 String 的格式一样，否则会抛出转换异常
         */
        String s = "1996年01月01日 10:30:16 星期一";
        Date parse = sdf.parse(s);
        System.out.println("parse:" + sdf.format(parse));
    }
}
```



### 第二代日期类（Calendar）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第二代日期类.png)

Calendar01.java（thirty.eight）

```java
package thirty.eight;

import java.util.Calendar;

public class Calendar01 {
    public static void main(String[] args) {
        /*
        1、Calendar 是一个抽象类，并且构造器是 private
        2、可以通过 getInstance() 来获取实例
        3、提供大量的方法和字段提供给程序员
        4、Calendar 没有提供对应的格式化的类，因此需要程序员自己组合来输出（灵活）
        5、如果我们需要按照 24 小时进制来获取时间，Calendar.HOUR ==> 改成 Calendar.HOUR_OF_DAY
         */
        Calendar c = Calendar.getInstance();//创建日历类对象，比较简单，自由
        System.out.println("c:" + c);
        //获取日历对象的某个日历字段
        System.out.println("年：" + c.get(Calendar.YEAR));
        System.out.println("月：" + (c.get(Calendar.MONTH) + 1));
        System.out.println("日：" + c.get(Calendar.DAY_OF_MONTH));
        System.out.println("小时：" + c.get(Calendar.HOUR));
        System.out.println("分钟：" + c.get(Calendar.MINUTE));
        System.out.println("秒：" + c.get(Calendar.SECOND));
        //Calendar 没有专门的格式化方法，所以需要程序员自己来组合显示
        System.out.println(c.get(Calendar.YEAR) + "年" + (c.get(Calendar.MONTH) + 1) + "月" + c.get(Calendar.DAY_OF_MONTH) + "日");
    }
}
```



### 第三代日期类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第三代日期类.png)

### 第三代日期类常见方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第三代日期类常见方法.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\DateTimeFormatter格式日期类.png)

LocalDate01.java（thirty.eight）

```java
package thirty.eight;

import java.time.LocalDate;
import java.time.LocalDateTime;
import java.time.LocalTime;
import java.time.format.DateTimeFormatter;

public class LocalDate01 {
    public static void main(String[] args) {
        /*
        1、使用 now() 返回表示当前时间的对象
         */
        LocalDateTime ldt = LocalDateTime.now();
        System.out.println(ldt);
        /*
        2、使用 now() 返回表示当前日期时间的对象
        创建 DateTimeFormatter 对象
         */
        DateTimeFormatter dateTimeFormatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss");
        String format = dateTimeFormatter.format(ldt);
        System.out.println("格式化的日期：" + format);

        System.out.println("年：" + ldt.getYear());
        System.out.println("月：" + ldt.getMonth());
        System.out.println("月：" + ldt.getMonthValue());
        System.out.println("日：" + ldt.getDayOfMonth());
        System.out.println("时：" + ldt.getHour());
        System.out.println("分：" + ldt.getMinute());
        System.out.println("秒：" + ldt.getSecond());
        LocalDate now = LocalDate.now();//获取年月日
        LocalTime now2 = LocalTime.now();//获取到时分秒

        //提供 plus 和 minus 方法可以对当前时间进行加或减
        //看看 890 天后，是什么时候把年月日-时分秒
        LocalDateTime localDateTime = ldt.plusDays(890);
        System.out.println("890天后：" + dateTimeFormatter.format(localDateTime));
        //看看 3456分钟前是什么时候，把 年月日-时分秒
        LocalDateTime localDateTime1 = ldt.minusMinutes(3456);
        System.out.println("3456分钟后：" + dateTimeFormatter.format(localDateTime1));
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Instant时间戳.png)

Instant01.java（thirty.eight）

```java
package thirty.eight;

import java.util.Date;
import java.time.Instant;

public class Instant01 {
    public static void main(String[] args) {
        //1、通过 静态方法 now() 获取表示当前时间戳的对象
        Instant now = Instant.now();
        System.out.println(now);
        //2、通过 from 可以把 Instant 转成 Date
        Date date = Date.from(now);
        //3、通过 date 的 toInstant() 可以把 date 转成 Instant 对象
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第三代日期类更多方法.png)

在LocalDate01.java（thirty.eight）里，代码如下：

```java
        //提供 plus 和 minus 方法可以对当前时间进行加或减
        //看看 890 天后，是什么时候把年月日-时分秒
        LocalDateTime localDateTime = ldt.plusDays(890);
        System.out.println("890天后：" + dateTimeFormatter.format(localDateTime));
        //看看 3456分钟前是什么时候，把 年月日-时分秒
        LocalDateTime localDateTime1 = ldt.minusMinutes(3456);
        System.out.println("3456分钟后：" + dateTimeFormatter.format(localDateTime1));
```



## 本章作业

### 本章作业 - 1

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第十三章作业-1.png)

### 本章作业 - 2

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第十三章作业-2.png)

### 本章作业 - 3

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第十三章作业-3.png)

### 本章作业 - 4

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第十三章作业-4.png)

### 本章作业 - 5

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第十三章作业-5.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\第十三章作业-5解析.png)





# 第十四章       集合



## 集合的理解和好处

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\集合的理解和好处.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\集合的理解和好处-1.png)



## 集合的框架体系

### 集合的框架体系两大类（Collection 和 Map）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\集合的框架体系两大类.png)

Collection01.java（fourteen.one）

```java
package fourteen.one;

import java.util.ArrayList;
import java.util.HashMap;

public class Collection01 {
    public static void main(String[] args) {
        /*
        1、集合主要是两组（单列集合，双列集合）
        2、Collection 接口有两个重要的子接口 List 和 Set，他们的实现子类都是单列集合
        3、Map 接口的实现子类是双列集合，存放的 K-V
         */
        //Collection
        ArrayList arrayList = new ArrayList();
        arrayList.add("Jack");
        arrayList.add("Tom");

        //Map
        HashMap hashMap = new HashMap();
        hashMap.put("NO1","北京");
        hashMap.put("NO2","上海");
    }
}
```



### 集合的框架体系图 Collention

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\集合的框架体系图Collention.png)

### 集合的框架体系图 Map

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\集合的框架体系图Map.png)



## Collection 接口

### Collection 接口实现类的特点

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Collection接口和常用方法.png)

### Collection 接口和常用方法

​        add 添加单个元素
​        remove 删除指定元素
​        contains 查找元素是否存在
​        size 获取元素个数
​        isEmpty 判断是否为空
​        clear 清空
​        addAll 添加多个元素
​        containsAll 查找多个元素是否都存在
​        removeAll 删除多个元素

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Collection接口和常用方法-1.png)

CollectionMethod.java（fourteen.one）

```java
package fourteen.one;

import java.util.ArrayList;
import java.util.List;

public class CollectionMethod {
    public static void main(String[] args) {
        List list = new ArrayList();
        //add 添加单个元素
        list.add("jack");
        list.add(10);
        list.add(true);
        System.out.println("list:" + list);
        //remove 删除指定元素
        list.remove(0);//删除第一个元素
        list.remove(true);//删除指定元素
        System.out.println("list:" + list);
        // contains 查找元素是否存在
        System.out.println(list.contains("jack"));
        // size 获取元素个数
        System.out.println(list.size());
        //isEmpty 判断是否为空
        System.out.println(list.isEmpty());
        //clear 清空
        list.clear();
        System.out.println("list:" + list);
        //addAll 添加多个元素
        List list1 = new ArrayList();
        list1.add("红楼梦");
        list1.add("三国演义");
        System.out.println("list1:" + list1);
        //containsAll 查找多个元素是否都存在
        System.out.println(list.containsAll(list1));
        //removeAll 删除多个元素
        list.add("聊斋");
        list.removeAll(list1);
        System.out.println("list:" + list);
        //说明：以 ArrayList 实现类来演示
    }
}
```



### Collection 接口遍历元素方式 - 使用 Iterator（迭代器）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Collection接口和常用方法-2.png)



### Collection 接口遍历元素方式 - for循环增强

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Collection 接口遍历元素方式 - for循环增强.png)

CollectionFor.java（fourteen.one）

```java
package fourteen.one;

import java.util.ArrayList;
import java.util.Collection;

public class CollectionFor {
    public static void main(String[] args) {
        Collection col = new ArrayList();
        col.add(new Book("三国演义","罗贯中",10.1));
        col.add(new Book("小李飞刀","古龙",8.1));
        col.add(new Book("红楼梦","曹雪芹",70.1));
        //1、使用增强for循环，在 Collection 集合
        //2、增强for，底层仍然是迭代器
        //3、增强for可以理解成就是简化版本的迭代器遍历
        for(Object book : col){
            System.out.println("book:" + book);
        }
        //增强for，也可以直接在数组使用
        int[] nums = {1,5,86,785};
        for(int i :nums){
            System.out.println("i=" + i);
        }
    }
}
```



##  Iterator（迭代器）

### 迭代器的执行原理

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\迭代器的执行原理.png)

### Iterator 接口的方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Iterator接口的方法.png)

###  Iterator 使用案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Iterator使用案例.png)

CollectionIterator.java（fourteen.one）

```java
package fourteen.one;

import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;

public class CollectionIterator {
    public static void main(String[] args) {
        Collection col = new ArrayList();
        col.add(new Book("三国演义","罗贯中",10.1));
        col.add(new Book("小李飞刀","古龙",8.1));
        col.add(new Book("红楼梦","曹雪芹",70.1));
        System.out.println("col:" + col);
        //1、先得到 col 对应的迭代器
        Iterator iterator = col.iterator();
        //2、使用 while 循环遍历
        while(iterator.hasNext()){//判断是否有数据
            //返回下一个元素，类型是 Object
            Object obj = iterator.next();
            System.out.println("obj:" + obj);
        }
        //快速生成 while => itit
        //显示所有的快捷键的快捷键 ctrl + j
        //3、当退出 while 循环后，这时 iterator 迭代器，指向最后的元素
        //   iterator.next();//NoSuchElementException
        //4、如果希望再次遍历，需要重置我们的迭代器
        iterator = col.iterator();
        System.out.println("====第二次遍历====");
        while (iterator.hasNext()) {
            Object obj =  iterator.next();
            System.out.println("obj" + obj);
        }
    }
}
class Book{
    private String name;
    private String author;
    private double price;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getAuthor() {
        return author;
    }

    public void setAuthor(String author) {
        this.author = author;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }

    public Book(String name, String author, double price) {
        this.name = name;
        this.author = author;
        this.price = price;
    }

    @Override
    public String toString() {
        return "Book{" +
                "name='" + name + '\'' +
                ", author='" + author + '\'' +
                ", price=" + price +
                '}';
    }
}
```



## List 接口

### List 接口基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\List接口基本介绍.png)

List01.java（fourteen.two）

```java
package fourteen.two;

import java.util.ArrayList;
import java.util.List;

public class List01 {
    public static void main(String[] args) {
        //1、List集合类中元素有序（即添加顺序和取出顺序一致），且可重复
        List list = new ArrayList();
        list.add("jack");
        list.add("tom");
        list.add("mary");
        list.add("tom");
        list.add("mike");
        System.out.println("list:" + list);
        //2、List集合中的每个元素都有其对应的顺序索引，即支持索引
        
    }
}
```



### List 接口的常用方法

​        **void add(int index, Object ele)**:在index位置插入ele元素
​        **boolean addAll(int index,Collection eles)**:从index位置开始将eles中的所有元素添加进去
​        **Object get(int index)**:获取指定index位置的元素
​        **int indexOf(Object obj)**:返回obj在当前集合中首次出现的位置
​        **int lastIndexOf(Object obj)**:返回obj在当前集合中末次出现的位置
​        **Object remove(int index)**:移除指定index位置的元素，并返回该元素
​        **Object set(int index, Object ele)**:设置指定index位置的元素为ele，相当于是替换。
​        **List subList(int fromIndex, int toIndex)**:返回从fromIndex到toIndex位置的子集合

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\List接口的常用方法.png)

ListMethod.java（fourteen.two）

```java
package fourteen.two;

import java.util.ArrayList;
import java.util.List;

public class ListMethod {
    public static void main(String[] args) {
        List list = new ArrayList();
        list.add("张三风");
        list.add("贾宝玉");
        //void add(int index, Object ele):在index位置插入ele元素
        list.add(1,"孙悟空");
        System.out.println("list:" + list);
        //boolean addAll(int index,Collection eles):从index位置开始将eles中的所有元素添加进去
        List list1 = new ArrayList();
        list1.add("jack");
        list1.add("tom");
        list.addAll(1,list1);
        System.out.println("list:" + list);
        //Object get(int index):获取指定index位置的元素
        //int indexOf(Object obj):返回obj在当前集合中首次出现的位置
        System.out.println(list.indexOf("tom"));
        //int lastIndexOf(Object obj):返回obj在当前集合中末次出现的位置
        list.add("猪八戒");
        System.out.println("list:" + list);
        System.out.println(list.lastIndexOf("tom"));
        //Object remove(int index):移除指定index位置的元素，并返回该元素
        list.remove(0);
        System.out.println("list:" + list);
        //Object set(int index, Object ele):设置指定index位置的元素为ele，相当于是替换。
        list.set(1,"mike");
        System.out.println("list:" + list);
        //List subList(int fromIndex, int toIndex):返回从fromIndex到toIndex位置的子集合
        List returnList = list.subList(0,2);
        System.out.println("returnList:" + returnList);
    }
}
```



### List 的三种遍历方式 [ArrayList，LinkedList，Vector]

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\List的三种遍历方式[ArrayList-LinkedList-Vector].png)



### List 练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\List练习题.png)

```java
//静态方法
//价格要求是从小到大
public static void sort(List list){
    int listSize = list.size();
    for(int i = 0; i < listSize - 1; i++){
        for(int j = 0; j < listSize - 1 - i; j++){
            //取出对象Book
            Book book1 = (Book) list.get(j);
            Book book2 = (Book) list.get(j + 1);
            if(book1.getPrice() > book2.getPrice()){
                list.set(j, book2);
                list.set(j + 1, book1);
            }
        }
    }
}
```



## ArrayList

### ArrayList 的注意事项

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的注意事项.png)

### ArrayList 的底层操作机制源码分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析重点.png)

### ArrayList 的底层操作机制源码分析案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析案例.png)

### 分析使用无参构造器，创建和使用 ArrayList 的源码

**1、创建了一个空的 elementData 数组 = 0**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析-1.png" style="zoom:200%;" />

2、执行 list.add

（1）先确定是否要扩容

（2）然后再执行赋值

<img src="C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析-2.png" style="zoom:200%;" />

3、该方法确定 minCapacity

（1）第一次扩容为10

<img src="C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析-3.png" style="zoom:200%;" />

4、ensureExplicitCapacity() 方法判断是否需要扩容

（1）modCount++ 记录集合被修改的次数

（2）如果 elementData 的大小不够，就调用 grow() 去扩容

<img src="C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析-4.png" style="zoom:200%;" />

5、grow() 扩容方法

（1）真的扩容

（2）使用扩容机制来确定要扩容到多大

（3）第一次 newCapacity = 10

（4）第二次及其以后，按照1.5倍扩容

（5）扩容使用的是 Array.copyOf()

<img src="C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析-5.png" style="zoom:200%;" />



### 分析使用有参构造器，创建和使用 ArrayList 的源码

**第一步不同**

1、创建了一个指定大小 elementData 数组 = new Object[capacity]

（1）第一次扩容，就按照 elementData 的1.5倍扩容

（2）整个执行的流程还是和前面讲的一样

<img src="C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ArrayList的底层操作机制源码分析-6.png" style="zoom:200%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\提示设置.png)



## Vector

### Vector 的基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Vector的基本介绍.png)

### Vector 和 ArrayList 的比较

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Vector和ArrayList的比较.png)



## LinkedList

### LinkedList 的全面说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\LinkedList的全面说明.png)

### LinkedList的底层操作机制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\LinkedList的底层操作机制.png)

**模拟一个简单的双向链表**

LinkedList01.java（fourteen.three）

```java
package fourteen;

public class LinkedList01 {
    public static void main(String[] args) {
        //模拟一个简单的双向链表
        Node jack = new Node("jack");
        Node tom = new Node("tom");
        Node mary = new Node("mary");
        Node first = jack;
        Node last = mary;

        //连接三个节点，形成双向链表
        //jack -> tom ->mary
        jack.next = tom;
        tom.next = mary;
        //mary -> tom ->jack
        mary.pre = tom;
        tom.pre = jack;

        //演示，从头到尾进行遍历
        System.out.println("==从头到尾进行遍历==");
        while(true){
            if(first == null){
                break;
            }
            //输出 first 信息
            System.out.println(first);
            first = first.next;
        }
        //演示，从尾到头的遍历
        System.out.println("==从尾到头的遍历==");
        while(true){
            if(last == null){
                break;
            }
            //输出 last 信息
            System.out.println(last);
            last = last.pre;
        }
        
        //下面就把 smith 加入到撒双向链表
        Node smith = new Node("smith");
        smith.next = mary;
        smith.pre = tom;
        tom.next = smith;
        mary.pre = smith;
        //让 first 再次指向jack
        first = jack;//让 first 引用指向 jack，就是双向链表的头节点,可以在进行从头到尾的遍历
    }
}
//定义一个 Node 类，Node 对象表示双向链表的一个节点
class Node{
    public Object item;//真正存放数据
    public Node next;//指向后一个节点
    public Node pre;//指向前一个结点

    public Node(Object item) {
        this.item = item;
    }

    @Override
    public String toString() {
        return "Node name = " + item;
    }
}
```



### LinkedList 的底层操作机制源码分析案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\LinkedList的底层操作机制源码分析案例.png)

LinkedListCRUD.java（fourteen.three）

```java
package fourteen.three;

import java.util.Iterator;
import java.util.LinkedList;

public class LinkedListCRUD {
    public static void main(String[] args) {
        LinkedList linkedList = new LinkedList();
        linkedList.add("jack");
        linkedList.add("smith");
        linkedList.remove();
        linkedList.set(0,"mike");
        System.out.println("linkedList:" + linkedList);
        /*
        1、LinkedList linkedList = new LinkedList();
        public LinkedList() {} 初始化
        2、这时 linkedList 的属性 first = null ， last = null
        解读添加节点
        3、执行 add()
            public boolean add(E e) {
                linkLast(e);
                return true;
            }
        4、添加节点，将新节点加入双向链表的最后：
            void linkLast(E e) {
                final Node<E> l = last;
                final Node<E> newNode = new Node<>(l, e, null);
                last = newNode;
                if (l == null)
                    first = newNode;
                else
                    l.next = newNode;
                size++;
                modCount++;
            }
         解读删除节点
         linkedList.remove();//这里默认删除的是第一个节点
         5、执行 remove()
             public E remove() {
                return removeFirst();
             }
         6、执行 removeFirst()
             public E removeFirst() {
                final Node<E> f = first;
                if (f == null)
                    throw new NoSuchElementException();
                return unlinkFirst(f);
             }
         7、真正删除节点的地方 unlinkFirst()
             private E unlinkFirst(Node<E> f) {
                // assert f == first && f != null;
                final E element = f.item;
                final Node<E> next = f.next;
                f.item = null;
                f.next = null; // help GC
                first = next;
                if (next == null)
                    last = null;
                else
                    next.prev = null;
                size--;
                modCount++;
                return element;
             }
         8、修改节点信息 set()
             public E set(int index, E element) {
                checkElementIndex(index);
                Node<E> x = node(index);
                E oldVal = x.item;
                x.item = element;
                return oldVal;
             }
         */
        System.out.println("==使用迭代器Iterator遍历==");
        Iterator iterator = linkedList.iterator();
        while (iterator.hasNext()) {
            Object next = iterator.next();
            System.out.println("next:" + next);
        }
        System.out.println("==使用增强for循环遍历==");
        for (Object o1: linkedList) {
            System.out.println("o1:" + o1);
        }
        System.out.println("==使用普通for循环遍历==");
        for (int i = 0; i < linkedList.size(); i++) {
            System.out.println(linkedList.get(i));
        }
    }
}
```



## Set 接口

### Set 接口基本介绍

​    1、以 Set 接口的实现类 HashSet 来讲解 Set 接口的方法
​    2、set 接口的实现类的对象（Set 接口对象），不能存放重复的元素，可以添加一个 null
​    3、set 接口对象存放数据是无序（即添加的顺序和取出的顺序不一致）
​    4、注意：取出的顺序的顺序虽然不是添加的顺序，但是他是固定的。

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Set接口介绍.png)

### Set 接口的常用方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Set接口的常用方法.png)

### Set 接口的常用方法举例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Set接口的常用方法举例.png)

SetMethod.java（fourteen.four）

```java
package fourteen.four;

import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;

public class SetMethod {
    public static void main(String[] args) {
        /*
        1、以 Set 接口的实现类 HashSet 来讲解 Set 接口的方法
        2、set 接口的实现类的对象（Set 接口对象），不能存放重复的元素，可以添加一个 null
        3、set 接口对象存放数据是无序（即添加的顺序和取出的顺序不一致）
        4、注意：取出的顺序的顺序虽然不是添加的顺序，但是他是固定的。
         */
        Set set = new HashSet();
        set.add("john");
        set.add("lucy");
        set.add("john");
        set.add("mary");
        set.add(null);
        set.add("smith");
        set.add(null);
        //方式一：使用迭代器
        System.out.println("==使用迭代器==");
        Iterator iterator = set.iterator();
        while (iterator.hasNext()) {
            Object obj = iterator.next();
            System.out.println("obj:" + obj);
        }
        //方式二：使用增强for循环
        for (Object obj : set) {
            System.out.println("obj:" + obj);
        }
    }
}
```



## HashSet 

### HashSet 的全面说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashSet的全面说明.png)

### HashSet 的案例说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashSet的案例说明.png)

HashSet01.java（fourteen.four）

```java
package fourteen.four;
import java.util.HashSet;

public class HashSet01 {
    public static void main(String[] args) {
        HashSet set = new HashSet();
        System.out.println(set.add("john"));//T
        System.out.println(set.add("lucy"));//T
        System.out.println(set.add("john"));//F
        System.out.println(set.add("jack"));//T
        System.out.println(set.add("Rose"));//T
        set.remove("john");
        System.out.println("set:" + set);

        HashSet set1 = new HashSet();
        set1.add("lucy");//添加成功
        set1.add("lucy");//加不进去
        set1.add(new Dog("tom"));//OK
        set1.add(new Dog("tom"));//OK
        System.out.println("set1：" + set1);
        //在加深一下，非常经典的面试题
        //看源码做分析，就明白了
        set1.add(new String("mary"));//OK
        set1.add(new String("mary"));//加不进去
    }
}
class Dog{
    private String name;

    public Dog(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Dog{" +
                "name='" + name + '\'' +
                '}';
    }
}
```



### HashSet 底层机制说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashSet底层机制说明.png)

HashSetStruture.java（fourteen.four）

```java
package fourteen.four;

import java.util.HashSet;

public class HashSetStruture {
    public static void main(String[] args) {
        HashSet hashSet = new HashSet();
        hashSet.add("java");
        hashSet.add("php");
        hashSet.add("java");
        System.out.println("hashSet:" + hashSet);
        /*
        HashSet 源码解析
        1、执行 HashSet()
            public HashSet() {
                map = new HashMap<>();
            }
         2、执行 add()
             public boolean add(E e) {//e="java"
                return map.put(e, PRESENT)==null;//(static) PRESENT = new Object();
             }
         3、执行 put(),该方法执行 hash(key) 得到 key 对应的 hash 值 算法 (h = hashCode()) ^ (h >>> 16)
             public V put(K key, V value) {
                return putVal(hash(key), key, value, false, true);
             }
         4、执行 putVal()
             final V putVal(int hash, K key, V value, boolean onlyIfAbsent,
                       boolean evict) {
                Node<K,V>[] tab; Node<K,V> p; int n, i;//定义了辅助变量
                // table 就是 HashMap 的一个数组，类型是 Node[]
                // if 语句表示如果当前 table 是 null，或者大小等于0
                // 就是第一次扩容，到16个空间
                if ((tab = table) == null || (n = tab.length) == 0)
                    n = (tab = resize()).length;
                //(1)根据key，得到 hash 去计算该 key 应该存放到 table 表的那个索引位置
                //并把这个位置的对象，赋给 p
                //(2)判断 p 是否为 null
                //(2.1) 如果 p 为 null，表示还没有存放元素，就创建一个 Node(key="java",value=PRESENT)
                //(2.2) 就放该位置 tab[i] = newNode(hash, key, value, null)
                if ((p = tab[i = (n - 1) & hash]) == null)
                    tab[i] = newNode(hash, key, value, null);
                else {
                //一个开发技巧提示：在需要局部变量（辅助变量）时候，再创建
                    Node<K,V> e; K k;
                //如果当前索引位置对应的链表的第一个元素和准备添加的key的hash值一样
                //并且满足下面两个条件之一：
                //(1)准备加入的 key 和 p 指向的 Node 结点的 key 是同一个对象
                //(2)p 指向的 Node 结点的 key 的 equals() 和准备加入的 key 比较后相同
                //就不能加入
                    if (p.hash == hash &&
                        ((k = p.key) == key || (key != null && key.equals(k))))
                        e = p;
                //再判断 p 是不是一个红黑树
                //如果是一颗红黑树，就调用 putTreeVal，来进行添加
                    else if (p instanceof TreeNode)
                        e = ((TreeNode<K,V>)p).putTreeVal(this, tab, hash, key, value);
                    else {//如果 table 对应索引位置，已经是一个链表，就使用 for 循环比较
                          //(1)依次和链表的每一个元素比较后，都不相同，则加入到该链表的最后
                          //   注意在把元素添加到链表后，立即判断，该链表是否已经达到8个结点
                          //   ，就调用 treeifyBin() 对当前这个链表进行树化（转成红黑树）
                          //   注意，在转成红黑树时，要进行判断，判断条件
                          //   if(tab == null || (n = tab.length) < MIN_TREEIFY_CAPACITY(64))
                          //          resize();
                          //   如果上面条件成立，先 table 扩容
                          //   只有上面条件不成立时，才进行转成红黑树
                          //(2)依次和该链表的每一个元素比较过程中，如果有相同的情况，就直接 break
                        for (int binCount = 0; ; ++binCount) {
                            if ((e = p.next) == null) {
                                p.next = newNode(hash, key, value, null);
                                if (binCount >= TREEIFY_THRESHOLD - 1) // -1 for 1st
                                    treeifyBin(tab, hash);
                                break;
                            }
                            if (e.hash == hash &&
                                ((k = e.key) == key || (key != null && key.equals(k))))
                                break;
                            p = e;
                        }
                    }
                    if (e != null) { // existing mapping for key
                        V oldValue = e.value;
                        if (!onlyIfAbsent || oldValue == null)
                            e.value = value;
                        afterNodeAccess(e);
                        return oldValue;
                    }
                }
                ++modCount;
                if (++size > threshold)
                    resize();
                afterNodeInsertion(evict);
                return null;
            }
         */
    }
}
```



### HashSet 的扩容和转成红黑树机制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashSet的扩容和转成红黑树机制.png)



### HashSet 练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashSet练习题-1.png)

HashSetExercise.java（fourteen.four）

```java
package fourteen.four;

import java.util.HashSet;
import java.util.Objects;

public class HashSetExercise {
    public static void main(String[] args) {
        HashSet hashSet = new HashSet();
        hashSet.add(new Employee("milan",18));
        hashSet.add(new Employee("smith",58));
        hashSet.add(new Employee("milan",18));
        //回答：加入了几个？3个
        System.out.println("hashSet:" + hashSet);
    }
}
class Employee{
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public Employee(String name, int age) {
        this.name = name;
        this.age = age;
    }
    //如果 name 和 age 值相同，则返回相同的 hash 值
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Employee employee = (Employee) o;
        return age == employee.age && Objects.equals(name, employee.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }

    @Override
    public String toString() {
        return "Employee{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```



## LinkedHashSet

### LinkedHashSet 的全面说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\LinkedHashSet的全面说明.png)

### LinkedHashSet 底层机制示意图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\LinkedHashSet底层机制示意图.png)

LinkedHashSetSource.java（fourteen.five）

```java
package fourteen.five;
import java.util.LinkedHashSet;
import java.util.Set;

public class LinkedHashSetSource {
    public static void main(String[] args) {
        //分析一下 LinkedHashSet 的底层机制
        LinkedHashSet set = new LinkedHashSet();
        set.add(new String("SS"));
        set.add(459);
        set.add(459);
        set.add("smith");
        System.out.println("set:" + set);
        /*
        1、LinkedHashSet 加入顺序和取出元素/数据的顺序一致
        2、LinkedHashSet 底层维护的是一个 LinkedHashMap（是 HashMap 的子类）
        3、LinkedHashSet 底层结构（数组 table + 双向链表）
        4、添加第一次时，直接将数组 table 扩容到 16，存放的节点类型是 LinkedHashMap$Entry
        5、数组是 HashMap$Node[] 存放的元素/数据是 LinkedHashMap$Entry 类型
        //继承关系是在内部类完成
            static class Entry<K,V> extends HashMap.Node<K,V> {
                Entry<K,V> before, after;
                Entry(int hash, K key, V value, Node<K,V> next) {
                    super(hash, key, value, next);
                }
            }
         */
    }
}
```



### LinkedHashSet 练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\LinkedHashSet练习题.png)

LinkedHashSetExercise.java（fourteen.five）

```java
package fourteen.five;

import java.util.LinkedHashSet;
import java.util.Objects;

public class LinkedHashSetExercise {
    public static void main(String[] args) {
        LinkedHashSet linkedHashSet = new LinkedHashSet();
        linkedHashSet.add(new Car("奥迪",4531.003));
        linkedHashSet.add(new Car("法拉利",300000.0));
        linkedHashSet.add(new Car("本田",453.003));
        linkedHashSet.add(new Car("丰田",45.003));
        linkedHashSet.add(new Car("保时捷",431.003));
        linkedHashSet.add(new Car("奥迪",4531.003));
        System.out.println("linkedHashSet:" + linkedHashSet);
    }
}
class Car{
    private String name;
    private Double price;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Double getPrice() {
        return price;
    }

    public void setPrice(Double price) {
        this.price = price;
    }

    public Car(String name, Double price) {
        this.name = name;
        this.price = price;
    }
    //重写 equals 方法 和 hashCode
    //当 name 和 price 相同时，就返回相同的 hashCode 值，equals 返回 true
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Car car = (Car) o;
        return Objects.equals(name, car.name) && Objects.equals(price, car.price);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, price);
    }

    @Override
    public String toString() {
        return "Car{" +
                "name='" + name + '\'' +
                ", price=" + price +
                '}';
    }
}
```



## Map 接口

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Map接口实现类图.png)

### Map接口实现类的特点

​        1、Map 与 Collection 并列存在。用于保存具有映射关系的数据：Key-Value（双列元素）
​        2、Map 中的 key 和 value 可以是任何引用类型的数据，会封装到 HashMap$Node 对象中
​        3、Map 中的 key 不允许重复，原因和 HashSet 一样，前面分析过源码
​        4、Map 中的 value 可以重复
​        5、Map 的 key 可以为 null，value 也可以为 null，注意 key 为 null，只能有一个；value 为 null，可以有多个

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Map接口实现类的特点.png)

Map01.java（fourteen.six）

```java
package fourteen.six;

import java.util.HashMap;
import java.util.Map;

public class Map01 {
    public static void main(String[] args) {
        /*
        解读 Map 接口的实现类特点，使用实现类 HashMap
        1、Map 与 Collection 并列存在。用于保存具有映射关系的数据：Key-Value（双列元素）
        2、Map 中的 key 和 value 可以是任何引用类型的数据，会封装到 HashMap$Node 对象中
        3、Map 中的 key 不允许重复，原因和 HashSet 一样，前面分析过源码
        4、Map 中的 value 可以重复
        5、Map 的 key 可以为 null，value 也可以为 null，注意
           key 为 null，只能有一个；value 为 null，可以有多个
         */
        Map map = new HashMap();
        map.put("No1","孙悟空");//K-V
        map.put("No2","猪八戒");//K-V
        map.put("No3","沙和尚");//K-V
        map.put("No1","唐僧");//当有相同的 key，就等价于替换
        map.put(null,null);//K-V
        map.put(null,"白骨精");//等价替换
        map.put("No4","牛魔王");//K-V
        map.put("No5","紫霞仙子");//K-V
        System.out.println("map:" + map);
        //通过 get 方法，传入 key，会返回对应的 value
        System.out.println(map.get("No2"));
    }
}
```



### Map 接口的特点

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Map接口的特点.png)

MapSource.java（fourteen.six）

```java
package fourteen.six;

import java.util.HashMap;
import java.util.Map;
import java.util.Set;

public class MapSource {
    public static void main(String[] args) {
        Map map = new HashMap();
        map.put("No1","孙悟空");//K-V
        map.put("No2","猪八戒");//K-V
        map.put("No3","沙和尚");//K-V
        map.put("No4","唐僧");//K-V
        /*
        1、k-v 最后是 HashMap$Node node = newNode(hash, key, value, null)
        2、k-v 为了方便程序员的遍历，还会创建 EntrySet 集合，该集合存放的元素的类型 Entry，而一个 Entry
           对象就有 k，v EntrySet<Entry<K,V>>。即：transient Set<Map.Entry<K,V>> entrySet;
        3、entrySet 中定义的类型是 Map.Entry，但是实际上存放的还是 HashMap$Node
           这时因为 static class Node<K,V> implements Map.Entry<K,V>
        4、当把 HashMap$Node 对象存放到 entrySet 就方便我们的遍历，因为 Map.Entry 提供了重要的方法
           K：getKey(); V：getValue();
         */
        Set set = map.entrySet();
        System.out.println(set.getClass());//HashMap$EntrySet
        for (Object obj : set){
            System.out.println(obj.getClass());
            /*
            为了从 HashMap$Node 取出 K-V
            1、先做一个向下转型
             */
            Map.Entry entry = (Map.Entry) obj;
            System.out.println(entry.getKey() + "-" + entry.getValue());
        }
    }
}
```

### Map 体系的继承图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Map体系的继承图.png)

### Map 接口的常用方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Map接口的常用方法.png)

### Map 接口遍历方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Map接口遍历方法.png)

### Map 接口遍历方法案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Map接口遍历方法案例.png)

MapFor.java（fourteen.six）

```java
package fourteen.six;

import java.util.*;

public class MapFor {
    @SuppressWarnings({"all"})
    public static void main(String[] args) {
        Map map = new HashMap();
        map.put("No1","孙悟空");//K-V
        map.put("No2","猪八戒");//K-V
        map.put("No3","沙和尚");//K-V
        map.put("No1","唐僧");//当有相同的 key，就等价于替换
        map.put(null,null);//K-V
        map.put(null,"白骨精");//等价替换
        map.put("No4","牛魔王");//K-V
        map.put("No5","紫霞仙子");//K-V
        //第一组：先取出所有的 Key，通过 Key 取出对应的 Value
        Set keyset = map.keySet();
        //(1) 增强 for
        System.out.println("第一种方式----");
        for(Object key : keyset){
            System.out.println(key + "-" + map.get(key));
        }
        //(2)迭代器
        System.out.println("第二种方式----");
        Iterator iterator = keyset.iterator();
        while (iterator.hasNext()) {
            Object key = iterator.next();
            System.out.println(key + "-" + map.get(key));
        }
        //第二组：把所有的values取出
        Collection values = map.values();
        //这里可以使用所有的 Collectio 使用的遍历方法
        //(1) 增强 for
        System.out.println("---取出所有的values-增强for---");
        for(Object value : values){
            System.out.println(value);
        }
        //(2) 迭代器
        System.out.println("---取出所有的values-迭代器---");
        Iterator iterator1 = values.iterator();
        while (iterator1.hasNext()) {
            Object value =  iterator1.next();
            System.out.println(value);
        }
        //第三组：通过 EntrySet 来获取 k-v
        Set entrySet = map.entrySet();//EntrySet<Map.Entry<K,V>>
        //(1) 增强 for
        System.out.println("使用 EntrySet 的增强for方法");
        for (Object entry : entrySet){
            //将entry 转成 Map.Entry
            Map.Entry m = (Map.Entry) entry;
            System.out.println(m.getKey() + "-" + m.getValue());
        }
        //(2) 迭代器
        System.out.println("使用 EntrySet 的迭代器方法");
        Iterator iterator2 = entrySet.iterator();
        while (iterator2.hasNext()) {
            Object next = iterator2.next();
            //HashMap$Node -> 实现 -> Map.Entry(getKey,getValue)
            //向下转型 Map.Entry
            System.out.println(next.getClass());
        }
    }
}
```

### Map 接口练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Map接口练习题-1.png)

MapExercise.java（fourteen.six）

```java
package fourteen.six;

import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Set;

public class MapExercise {
    public static void main(String[] args) {
        HashMap hashMap = new HashMap();
        //添加对象
        hashMap.put(1,new Employee("jack",300000,1));
        hashMap.put(2,new Employee("tom",34000,2));
        hashMap.put(3,new Employee("milan",7000,3));
        //遍历的两种方式
        //1、使用 keySet -> 增强 for
        Set set = hashMap.keySet();
        for (Object key : set){
            Employee value = (Employee) hashMap.get(key);
            if(value.getSal() > 18000){
                System.out.println(value);
            }
        }
        //2、使用EntrySet -> 迭代器
        Set entrySet = hashMap.entrySet();
        Iterator iterator = entrySet.iterator();
        while (iterator.hasNext()) {
            Map.Entry  entry = (Map.Entry) iterator.next();
            //通过 entry 取得 key 和 value
            Employee employee = (Employee) entry.getValue();
            if(employee.getSal() > 18000){
                System.out.println(employee);
            }
        }
    }
}
class Employee{
    private String name;
    private double sal;
    private int id;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getSal() {
        return sal;
    }

    public void setSal(double sal) {
        this.sal = sal;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public Employee(String name, double sal, int id) {
        this.name = name;
        this.sal = sal;
        this.id = id;
    }

    @Override
    public String toString() {
        return "Employee{" +
                "name='" + name + '\'' +
                ", sal=" + sal +
                ", id=" + id +
                '}';
    }
}
```

### Map 小结

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashMap小结.png)



## HashMap

### HashMap底层机制及源码剖析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashMap底层机制及源码剖析.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashMap底层机制及源码剖析扩容机制.png)

HashMapSource.java（fourteen.six）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashMap底层机制及源码剖析模拟扩容.png)

```java
package fourteen.six;

import java.util.HashMap;
import java.util.Map;

public class HashMapSource {
    public static void main(String[] args) {
        Map map = new HashMap();
        map.put("No1","孙悟空");//K-V
        map.put("No2","猪八戒");//K-V
        map.put("No3","沙和尚");//K-V
        map.put("4","唐僧");//当有相同的 key，就等价于替换
        System.out.println("map:" + map);
        /*
        1、执行构造器 new HashMap()
           初始化加载因子 loadfactor = 0.75
           HashMap$Node[] table = null
        2、执行 put 调用 hash 方法，计算 key 的 hash 值 (h = key.hashCode()) ^ (h >>> 16)
            public V put(K key, V value) {
                return putVal(hash(key), key, value, false, true);
            }
        3、执行 putVal()
            final V putVal(int hash, K key, V value, boolean onlyIfAbsent,
                       boolean evict) {
                Node<K,V>[] tab; Node<K,V> p; int n, i;//辅助变量
                //如果底层的 table 数组为 null，或者 length = 0，就扩容到16
                if ((tab = table) == null || (n = tab.length) == 0)
                    n = (tab = resize()).length;
                if ((p = tab[i = (n - 1) & hash]) == null)
                    tab[i] = newNode(hash, key, value, null);
                else {
                    Node<K,V> e; K k;
                //如果 table 的索引位置的 key 的 hash 值相同黑犀牛的 key 的 hash 值相同
                //并满足（table 现有的节点的 key 和准备添加的 key 是同一对象 || equals 返回真）
                //就认为不能加入新的 k-v
                    if (p.hash == hash &&
                        ((k = p.key) == key || (key != null && key.equals(k))))
                        e = p;
                    else if (p instanceof TreeNode)
                        e = ((TreeNode<K,V>)p).putTreeVal(this, tab, hash, key, value);
                    else {
                    //如果找到的节点，后面是链表，就循环比较
                        for (int binCount = 0; ; ++binCount) {//死循环
                            if ((e = p.next) == null) {//如果整个链表，没有和他相同，就加到链表的最后
                                p.next = newNode(hash, key, value, null);
                                //加入后，判断当前链表的个数，是否已经到8个，到8个后
                                //就调用 treeifyBin 方法进行红黑树的转换
                                if (binCount >= TREEIFY_THRESHOLD - 1) // -1 for 1st
                                    treeifyBin(tab, hash);
                                break;
                            }
                            if (e.hash == hash &&//如果在循环比较过程中，发现有相同，就break，就只是替换 value
                                ((k = e.key) == key || (key != null && key.equals(k))))
                                break;
                            p = e;
                        }
                    }
                    if (e != null) { // existing mapping for key
                        V oldValue = e.value;
                        if (!onlyIfAbsent || oldValue == null)
                            e.value = value;
                        afterNodeAccess(e);
                        return oldValue;
                    }
                }
                ++modCount;//每增加一个 Node，就size++
                if (++size > threshold)//如 size > 临界值，就扩容
                    resize();
                afterNodeInsertion(evict);
                return null;
            }
         4、关于树化（转成红黑树）
         //如果 table 为 null，或者大小还没有到64，暂时不树化，而是进行扩容
         //否则才会真正的树化 -> 剪枝
             final void treeifyBin(Node<K,V>[] tab, int hash) {
            int n, index; Node<K,V> e;
                if (tab == null || (n = tab.length) < MIN_TREEIFY_CAPACITY)
                    resize();
                else if ((e = tab[index = (n - 1) & hash]) != null) {
                    TreeNode<K,V> hd = null, tl = null;
                    do {
                        TreeNode<K,V> p = replacementTreeNode(e, null);
                        if (tl == null)
                            hd = p;
                        else {
                            p.prev = tl;
                            tl.next = p;
                        }
                        tl = p;
                    } while ((e = e.next) != null);
                    if ((tab[index] = hd) != null)
                        hd.treeify(tab);
                }
            }
         */
    }
}
```



### HashTable 的基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\HashTable的基本介绍.png)

HashTableExercise.java（fourteen.seven）

```java
package fourteen.seven;

import java.util.Hashtable;

public class HashTableExercise {
    public static void main(String[] args) {
        Hashtable table = new Hashtable();
        table.put("john",100);
//        table.put(null,100);//异常NullPointerException
//        table.put("john",null);//异常NullPointerException
        table.put("lucy",100);
        table.put("lic",100);
        table.put("lic",88);//替换
        System.out.println(table);
        /*
        1、底层有数组 Hashtable$Entry[] 初始化大小为 11
        2、临界值 threshold 8 = 11 * 0.75
        3、扩容：按照自己的扩容机制来进行即可
         */
    }
}
```



### Hashtable 和 HashMap 对比

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Hashtable和HashMap对比.png)



## Properties

### Properties 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Properties基本介绍.png)

### Properties 案例使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Properties案例使用.png)

### Properties 基本使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Properties基本使用.png)

Properties01.java（fourteen.seven)

```java
package fourteen.seven;

import java.util.Properties;

public class Properties01 {
    public static void main(String[] args) {
        /*
        1、Properties 继承 Hashtable
        2、可以通过 k-v 存放数据，当然 key 和 value 不能为 null
        增加
         */
        Properties properties = new Properties();
        //properties.put(null,"abc");
        //properties.put("abc",null);
        properties.put("lucy",100);
        properties.put("lic",100);
        properties.put("lic",88);
        System.out.println("properties:" + properties);
        //获取
        System.out.println(properties.get("lic"));
        //删除
        properties.remove("lic");
        System.out.println("properties:" + properties);
    }
}
```



## TreeSet

### TreeSet 介绍

​        1、当我们使用无参构造器，创建 TreeSet 时，仍然是无序的
​        2、添加元素，按照字符串大小类排序
​        3、使用 TreeSet 提供的一个构造器，可以传入比较器（匿名内部类），并指定排序规则

```java
package fourteen.seven;

import java.util.Comparator;
import java.util.TreeSet;

public class TreeSet01 {
    public static void main(String[] args) {
        /*
        1、当我们使用无参构造器，创建 TreeSet 时，仍然是无序的
        2、添加元素，按照字符串大小类排序
        3、使用 TreeSet 提供的一个构造器，可以传入比较器（匿名内部类）
           并指定排序规则
        4、简单看看源码
         */
//        TreeSet treeSet = new TreeSet();
        TreeSet treeSet = new TreeSet(new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                //下面调用 String 的 compareTo 方法进行字符串大小比较
                return ((String) o1).compareTo((String) o2);
            }
        });
        treeSet.add("jack");
        treeSet.add("tom");
        treeSet.add("smith");
        treeSet.add("mike");
        System.out.println("treeSet:" + treeSet);
        /*
        1、构造器把传入的比较器对象，赋给了 TreeSet 的底层的 TreeMap 的属性 this.comparator
            public TreeSet(Comparator<? super E> comparator) {
                this(new TreeMap<>(comparator));
            }
        2、在调用 treeSet.add("tom"),在底层会执行到
            if (cpr != null) {
                do {
                    parent = t;
                    cmp = cpr.compare(key, t.key);
                    if (cmp < 0)
                        t = t.left;
                    else if (cmp > 0)
                        t = t.right;
                    else
                        return t.setValue(value);
                } while (t != null);
            }
         */
    }
}
```



## TreeMap

### TreeMap 基本介绍

```java
package fourteen.seven;

import java.util.Comparator;
import java.util.TreeMap;

public class TreeMap01 {
    public static void main(String[] args) {
        /*
        使用默认的构造器，创建 TreeMap，是无序的（也没有排序）
        按照传入的 k（String）的大小进行排序
         */
        //TreeMap treeMap = new TreeMap();
        TreeMap treeMap = new TreeMap(new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                return ((String) o1).compareTo((String) o2);
            }
        });
        treeMap.put("No1","孙悟空");
        treeMap.put("No2","猪八戒");
        treeMap.put("No3","沙和尚");
        treeMap.put("No4","唐僧");
        /*
        1、new TreeMap();
            public TreeMap(Comparator<? super K> comparator) {
                this.comparator = comparator;
            }
        2、调用 put 方法
        2.1 第一次添加，把 k-v 封装到 Entry 对象，放入 root
            Entry<K,V> t = root;
            if (t == null) {
                compare(key, key); // type (and possibly null) check

                root = new Entry<>(key, value, null);
                size = 1;
                modCount++;
                return null;
            }
         2.2以后添加
             Comparator<? super K> cpr = comparator;
            if (cpr != null) {
                do {//遍历所有的 key，给当前 key 找到适当位置
                    parent = t;
                    cmp = cpr.compare(key, t.key);//动态绑定机制到我们的匿名内部类的compare
                    if (cmp < 0)
                        t = t.left;
                    else if (cmp > 0)
                        t = t.right;
                    else//如果遍历过程中，发现准备添加 key 和当前已有的 key 相等，就不添加
                        return t.setValue(value);
                } while (t != null);
            }
         */
    }
}
```





## 总结-开发中如何选择集合实现类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\总结-开发中如何选择集合实现类.png)



## Collections 工具类

### Collections 工具类介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Collections工具类介绍.png)

### Collections 工具类应用案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Collections工具类应用案例.png)

Collections01.java（fourteen.seven）

```java
package fourteen.seven;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class Collections01 {
    public static void main(String[] args) {
        //创建 ArrayList 集合，用于测试
        List list = new ArrayList();
        list.add("tom");
        list.add("smith");
        list.add("king");
        list.add("milan");
        //reverse(list)：反转 List 中的元素的顺序
        Collections.reverse(list);
        //shuffle(List)：对 List 集合元素进行随机排序
        for (int i = 0; i < 5; i++) {
            Collections.shuffle(list);
            System.out.println("list:" + list);
        }
        //sort(List)：根据元素的自然顺序都指定 List 集合元素按升序排序
        System.out.println("自然排序");
        Collections.sort(list);
        //sort(List, Comparator)：根据指定的 Comparator 产生的顺序对 List 集合元素进行排序
        Collections.sort(list, new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                //可以加入校验代码
                return ((String) o1).length() - ((String) o2).length();
            }
        });
        System.out.println("字符串长度大小排序：" + list);
        //swap(List, int, int)：将指定 List 集合中的 i 处 元素和 j 处元素进行交换
        Collections.swap(list, 0 ,1);
        System.out.println("交换后的情况");
        System.out.println("list:" + list);
    }
}
```



### Collections 工具类（查找、替换）方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Collections工具类方法.png)

Collections02.java（fourteen.seven）

```java
package fourteen.seven;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;

public class Collections02 {
    public static void main(String[] args) {
        //创建 ArrayList 集合，用于测试
        List list = new ArrayList();
        list.add("tom");
        list.add("smith");
        list.add("king");
        list.add("milan");
        //Object max(Collection)：根据元素的自然顺序，返回给定集合中的最大元素
        System.out.println("自然顺序最大元素：" + Collections.max(list));
        //Object max(Coolection, Comparator)：根据 Comparator 指定的顺序，返回给定集合中的最大元素
        //比如，我们要返回长度最大的元素
        Object maxObject = Collections.max(list, new Comparator() {
            @Override
            public int compare(Object o1, Object o2) {
                return ((String) o1).length() - ((String)o2).length();
            }
        });
        System.out.println("长度最大的元素：" + maxObject);
        //Object min(Collection)
        //Object min(Collection, Comparator)
        //上面的两个方法，参考max即可
        //int frequency(Collection, Object)：返回指定集合中指定元素的出现次数
        System.out.println("tom出现的次数："  + Collections.frequency(list, "tom"));
        //void copy(List deat, List src)：将 src 中的内容复制到 dest 中
        ArrayList dest = new ArrayList();
        //为了完成一个完整拷贝，我们需要先给 dest 赋值，大小和 list.size() 一样
        for (int i = 0; i < list.size(); i++) {
            dest.add("");
        }
        Collections.copy(dest, list);
        System.out.println("dest:" + dest);
        //boolean replaceAll(List list, Object oldVal, Object newVal)：使用新值替换 List 对象的所有旧值
        Collections.replaceAll(list, "tom", "汤姆");
        System.out.println("list替换后：" +list);
    }
}
```



# 第十五章       泛型



## 泛型的理解和好处

### 看一个需求

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\泛型的理解和好处.png)

### 使用传统方法的问题分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\使用传统方法的问题分析.png)

Generic01.java（fifteen.one）

```java
package fifteen.one;

import java.util.ArrayList;

public class Generic01 {
    public static void main(String[] args) {
        //使用传统的方法来解决
        ArrayList arrayList = new ArrayList();
        arrayList.add(new Dog("旺财",10));
        arrayList.add(new Dog("发财",1));
        arrayList.add(new Dog("小黄",7));
        //假设我们的程序员，不小心，添加了一个其他对象的元素，则遍历就会抛出异常
        arrayList.add(new String("小黑"));
        //遍历
        for (Object o : arrayList){
            //向下转型 Object -> Dog
            Dog dog = (Dog) o;
            System.out.println(dog.getName() + "-" + dog.getAge());
        }
    }
}

//请编写程序，在 ArrayList 中，添加3个Dog对象
//Dog对象含有 name 和 age，并输出 name 和 age（要求使用 getXXX()）
class Dog{
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Dog{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```



### 使用泛型方法的好处

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\泛型的好处.png)

Generic02.java（fifteen.one）

```java
package fifteen.one;

import com.sun.org.apache.xpath.internal.operations.String;

import java.util.ArrayList;

public class Generic02 {
    public static void main(String[] args) {
        /*
        使用泛型
        1、当我们 ArrayList<Dog> 表示存放到 ArrayList  集合中的元素是 Dog 类型（细节后面说...）
        2、如果编译器发现添加的类型，不满足要求，就会报错
        3、在遍历的时候，可以直接取出 Dog 类型而不是 Object
        4、public class ArrayList<E>{} （E称为泛型，那么 Dog -> E）
         */
        ArrayList<Dog> arrayList = new ArrayList<>();
        arrayList.add(new Dog("旺财",10));
        arrayList.add(new Dog("发财",1));
        arrayList.add(new Dog("小黄",7));
        //假如我们的程序员，不小心添加了字符串类型，会提示错误
        //arrayList.add(new String("小黑"));
        System.out.println("--使用泛型--");
        for (Dog dog : arrayList){
            System.out.println(dog.getName() + "-" + dog.getAge());
        }
    }
}
```



### 泛型的基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\泛型的基本介绍.png)

Generic03.java（fifteen.one）

```java
package fifteen.one;

public class Generic03 {
    public static void main(String[] args) {
        //注意，特别强调：E具体的数据类型在定义Person对象的时候指定，即在编译期间，就确定E是什么类型
        Person<String> person = new Person<>("孙悟空");
        /*
        你可以这样理解，上面的Person类
            class Person{
                String s;//E表示s的数据类型，该数据类型在定义Person对象的时候指定，即在编译期间，就确E是什么类型

                public Person(String s) {//E也可以是参数类型
                    this.s = s;
                }
                public String f(){//E也可以是返回类型
                    return s;
                }
            }
         */
    }
}
//泛型的作用是：可以在类的声明时通过一个标识表示类中某个属性的类型
//或者是某个方法的返回值的类型，或者是参数类型
class Person<E>{
    E s;//E表示s的数据类型，该数据类型在定义Person对象的时候指定，即在编译期间，就确E是什么类型

    public Person(E s) {
        this.s = s;
    }
    public E f(){
        return s;
    }
}
```



## 泛型的语法

### 泛型的声明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\泛型的语法声明.png)

### 泛型使用举例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\泛型使用举例.png)

GenericExercise.java（fifteen.one）

```java
package fifteen.one;
import java.util.*;

public class GenericExercise {
    public static void main(String[] args) {
        HashSet<Student> students = new HashSet<>();
        students.add(new Student("jack",18));
        students.add(new Student("tom",25));
        students.add(new Student("mary",19));
        //遍历
        for (Student student : students){
            System.out.println(student);
        }
        //使用泛型方式给 HashMap 放入3个学生对象
        HashMap<String, Student> hm = new HashMap<>();
        /*
             public class HashMap<K, V>{}
         */
        hm.put("milan", new Student("milan",16));
        hm.put("smith", new Student("smith",17));
        hm.put("mike", new Student("mike",26));
        //迭代器 EntrySet
        /*
        public Set<Map.Entry<K, V>> entrySet(){
            Set<Map.Entry<K, V> es;
            return (es = entrySet) == null ? (entrySet = new EntrySet()) : es;
        }
         */
        Set<Map.Entry<String, Student>> entries = hm.entrySet();
        /*
        public final Iterator<Map.Entry<K, V>> iterator(){
            return new EntryIterator();
        }
         */
        Iterator<Map.Entry<String, Student>> iterator = entries.iterator();
        System.out.println("----------");
        while(iterator.hasNext()) {
        Map.Entry<String, Student> next = iterator.next();
            System.out.println(next.getKey() + "-" + next.getValue());
        }
    }
}
class Student{
    private String name;
    private int age;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```



### 泛型使用的注意事项和细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\泛型使用的注意事项和细节.png)

GenericDetail.java（fifteen.one）

````java
package fifteen.one;

import java.util.ArrayList;
import java.util.List;

public class GenericDetail {
    public static void main(String[] args) {
        //1、给泛型指向数据类型是，要求是引用类型，不能是基本数据类型
        ArrayList<Integer> list1 = new ArrayList<>();//OK
        //ArrayList<int> list2 = new ArrayList<int>();//错误
        //2、说明
        //因为 E 指定了 A 类型，构造器传入了 new A()
        //在给泛型指定具体类型后，可以传入该类型或者其子类类型
        Pig<A> aPig = new Pig<A>(new A());
        aPig.f();
        Pig<A> aPig1 = new Pig<A>(new B());
        aPig1.f();
        //3、泛型的使用方式
        ArrayList<Integer> list3 = new ArrayList<Integer>();
        List<Integer> list4 = new ArrayList<Integer>();
        //在实际开发中，我们往往简写
        ArrayList<Integer> list5 = new ArrayList<>();
        ArrayList<Pig> pig = new ArrayList<>();
        //4、如果是这样写，泛型默认是 Object
        ArrayList arrayList = new ArrayList();
        //等价于ArrayList<Obejct> arrayList = new ArrayList<Object>();
    }
}
class A{}
class B extends A{}
class Pig<E>{
    E e;

    public Pig(E e) {
        this.e = e;
    }
    public void f(){
        System.out.println(e.getClass());//运行类型
    }
}
````



### 泛型练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\泛型练习题-2.png)

**（fifteen.two 包里）**

MyDate.java

```java
package fifteen.two;

public class MyDate implements Comparable<MyDate>{
    private int year;
    private int month;
    private int day;

    public int getYear() {
        return year;
    }

    public void setYear(int year) {
        this.year = year;
    }

    public int getMonth() {
        return month;
    }

    public void setMonth(int month) {
        this.month = month;
    }

    public int getDay() {
        return day;
    }

    public void setDay(int day) {
        this.day = day;
    }

    public MyDate(int year, int month, int day) {
        this.year = year;
        this.month = month;
        this.day = day;
    }

    @Override
    public String toString() {
        return "MyDate{" +
                "year=" + year +
                ", month=" + month +
                ", day=" + day +
                '}';
    }

    @Override
    public int compareTo(MyDate o) {
        int yearMinus = year - o.getYear();
        if(yearMinus != 0){
            return yearMinus;
        }
        //如果 year 相同，就比较 month
        int monthMinus = month - o.getMonth();
        if(monthMinus != 0){
            return monthMinus;
        }
        return day - o.getDay();
    }
}
```

Employee.java

```java
package fifteen.two;

public class Employee {
    private String name;
    private double sal;
    private MyDate birthday;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public double getSal() {
        return sal;
    }

    public void setSal(double sal) {
        this.sal = sal;
    }

    public MyDate getBirthday() {
        return birthday;
    }

    public void setBirthday(MyDate birthday) {
        this.birthday = birthday;
    }

    public Employee(String name, double sal, MyDate birthday) {
        this.name = name;
        this.sal = sal;
        this.birthday = birthday;
    }

    @Override
    public String toString() {
        return "Employee{" +
                "name='" + name + '\'' +
                ", sal=" + sal +
                ", birthday=" + birthday +
                '}';
    }
}
```

GenericExercise02.java

```java
package fifteen.two;

import java.util.ArrayList;
import java.util.Comparator;

@SuppressWarnings({"all"})
public class GenericExercise02 {
    public static void main(String[] args) {
        ArrayList<Employee> employees = new ArrayList<>();
        employees.add(new Employee("tom", 20000, new MyDate(2000, 11, 1)));
        employees.add(new Employee("jack", 12000, new MyDate(1999, 10, 21)));
        employees.add(new Employee("mike", 50000, new MyDate(1980, 1, 13)));
        System.out.println("employees：" + employees);
        System.out.println("---对雇员进行排序---");
        employees.sort(new Comparator<Employee>() {
            @Override
            public int compare(Employee emp1, Employee emp2) {
                //先按照 name 排序，如果 name 相同，则按照生日日期的先后排序，【即：定制排序】
                //先对传入的参数进行验证
                if(!(emp1 instanceof  Employee && emp2 instanceof Employee)){
                    System.out.println("类型不正确...");
                    return 0;
                }
                //比较 name
                int i = emp1.getName().compareTo(emp2.getName());
                if(i != 0){
                    return i;
                }
                //下面是对 Birthday 的比较，因此，我们最好把这个比较，放在 MyDate 类完成
                return emp1.getBirthday().compareTo(emp2.getBirthday());
                //如果 name 相同，就比较 birthday - year
//                int yearMinus = emp1.getBirthday().getYear() -emp2.getBirthday().getYear();
//                if(yearMinus != 0){
//                    return yearMinus;
//                }
//                //如果 year 相同，就比较 month
//                int monthMinus = emp1.getBirthday().getMonth() -emp2.getBirthday().getMonth();
//                if(monthMinus != 0){
//                    return monthMinus;
//                }
//                return emp1.getBirthday().getDay() - emp2.getBirthday().getDay();
            }
        });
        System.out.println("---对雇员进行排序---");
        System.out.println(employees);
    }
}
```





## 自定义泛型

### 自定义泛型类基本语法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自定义泛型类基本语法.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自定义泛型类的使用.png)

CustomGeneric.java（fifteen.three）

```java
package fifteen;

public class CustomGeneric {
    public static void main(String[] args) {
        //T=Double,R=String,M=Integer
        Tiger<Double, String, Integer> g = new Tiger<Double, String, Integer>("john");
        g.setT(10.9);//OK
        //g.setT("tt");//错误，类型不对
        System.out.println(g);
        Tiger g2 = new Tiger("john~~");//OK T=Object,R=Object,M=Object
        g2.setT("yy");//OK T=Object "yy"=String 是 Object 的子类
        System.out.println("g2:" + g2);
    }
}
/*
1、Tiger 后面泛型，所以我们把 Tiger 就称为 自定义泛型类
2、T, R, M 泛型的标识符，一般是单个大写字母
3、泛型标识符可以有多个
4、普通成员可以使用泛型（属性、方法）
5、使用泛型的数组，不能舒初始化
 */
@SuppressWarnings({"all"})
class Tiger<T, R, M>{
    String name;
    R r;
    M m;
    T t;
    //因为数组在 new 不能确定 T 的类型，就无法在内存开空间
    //T[] ts = new T[8];//错误

    public Tiger(String name) {
        this.name = name;
    }

    public Tiger(String name, R r, M m, T t) {//构造器使用泛型
        this.name = name;
        this.r = r;//属性使用到泛型
        this.m = m;
        this.t = t;
    }
    //因为静态是和类相关的，在类加载时，对象还没有创建
    //static R r2;//错误
    //public static void m1(M m){}//错误

    //方法使用泛型

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public R getR() {//方法使用泛型
        return r;
    }

    public void setR(R r) {
        this.r = r;
    }

    public M getM() {
        return m;
    }

    public void setM(M m) {
        this.m = m;
    }

    public T getT() {
        return t;
    }

    public void setT(T t) {
        this.t = t;
    }
}
```



### 自定义泛型接口基本语法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自定义泛型接口.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自定义泛型接口的使用.png)

CustomInterfaceGeneric.java（fifteen.three）

```java
package fifteen.three;

public class CustomInterfaceGeneric {
    public static void main(String[] args) {

    }
}
interface IUsb<U, R>{
    //普通方法中，可以使用接口泛型
    R get(U u);
    void hi(R r);
    void run(R r1, R r2, U u1, U u2);
    //在 JDK8 中，可以在接口中，使用默认方法，也是可以使用泛型
    default R method(U u){
        return null;
    }
}
//在继承接口时，指定泛型接口的类型
interface IA extends IUsb<String, Double>{}
//当我们去实现IA接口时，因为IA继承IUsb接口时，制定了U为String，R为Double
//在实现IUsb接口方法时，使用String替换U，Double替换R
class AA implements IA{
    @Override
    public Double get(String s) {
        return null;
    }
    @Override
    public void hi(Double aDouble) {}
    @Override
    public void run(Double r1, Double r2, String u1, String u2) {}
}
//实现接口时，直接指定泛型接口的类型
//指定了U为Integer，R为Float
//在实现IUsb接口方法时，使用U替换Integer，R替换Float
class BB implements IUsb<Integer, Float>{
    @Override
    public Float get(Integer integer) {
        return null;
    }
    @Override
    public void hi(Float aFloat) {}
    @Override
    public void run(Float r1, Float r2, Integer u1, Integer u2) {}
}
//没指定类型，默认为 Object
class CC implements IUsb{//等价于class CC implements IUsb<Object, Object>
    @Override
    public Object get(Object o) {
        return null;
    }
    @Override
    public void hi(Object o) {}
    @Override
    public void run(Object r1, Object r2, Object u1, Object u2) {}
}
```



### 自定义泛型方法基本语法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自定义泛型方法基本语法.png)

CustomMethodGeneric.java（fifteen.three）

```java
package fifteen.three;

import java.util.ArrayList;

public class CustomMethodGeneric {
    public static void main(String[] args) {
        Car car = new Car();
        car.fly("宝马",100);//当调用方法时，传入参数，编译器，就会确定类型
        System.out.println("------------");
        car.fly(30.2,54);//当调用方法时，传入参数，编译器，就会确定类型
        //T->String，R->ArrayList
        Fish<String, ArrayList> fish = new Fish<>();
        fish.hello(new ArrayList(),11.3f);
    }
}
//泛型方法，可以定义在普通类中，也可以定义在泛型类中
class Car{//普通类
    public void run(){}//普通方法
    /*
    说明泛型方法
    1、<T,R>就是泛型
    2、是提供给 fly 使用的
     */
    public<T, R> void fly(T t, R r){//泛型方法
        System.out.println(t.getClass());
        System.out.println(r.getClass());
    }
}
class Fish<T, R>{//泛型类
    public void run(){}//普通方法
    public<U,M> void eat(U u, M m){}//泛型方法
    /*
    说明：
    1、下面hi方法不是泛型方法
    2、是hi方法使用了声明的泛型
     */
    public void hi(T t){}
    //泛型方法，可以使用类声明的泛型，也可以使用自己声明的泛型
    public<K> void hello(R r, K k){
        System.out.println(r.getClass());
        System.out.println(k.getClass());
    }
}
```



## 泛型的继承和通配符

### 泛型的继承和通配符说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\泛型的继承和通配符说明.png)

GenericExtends.java（fifteen.three）

```java
package fifteen.three;

import java.util.ArrayList;
import java.util.List;

public class GenericExtends {
    public static void main(String[] args) {
        Object o = new String("xx");
        //泛型没有继承性
        //List<Object> list = new ArrayList<String>();
        //举例说明下面三个方法的使用
        ArrayList<Object> list1 = new ArrayList<>();
        ArrayList<String> list2 = new ArrayList<>();
        ArrayList<AAA> list3 = new ArrayList<>();
        ArrayList<BBB> list4 = new ArrayList<>();
        ArrayList<CCC> list5 = new ArrayList<>();
        //如果是 List<?> c，可以接受任意的泛型类型
        printCollection1(list1);
        printCollection1(list2);
        printCollection1(list3);
        printCollection1(list4);
        printCollection1(list5);
        //如果是 List<? extends AAA> c，可以接受 AAA 或者 AAA 的子类
//        printCollection2(list1);//x
//        printCollection2(list2);//x
        printCollection2(list3);//√
        printCollection2(list4);//√
        printCollection2(list5);//√
        //如果是 List<? super AAA> c，支持AAA类以及AAA类的父类，不限于直接父类，规定了泛型的下限
        printCollection3(list1);//√
//        printCollection3(list2);//x
        printCollection3(list3);//√
//        printCollection3(list4);//x
//        printCollection3(list5);//x
    }
    //编写几个方法
    public static void printCollection1(List<?> c){
        for(Object object : c){//通配符，取出时，就是Object
            System.out.println(object);
        }
    }
    // ? extends AAA 表示上限，可以接受 AAA 或者 AAA 的子类
    public static void printCollection2(List<? extends AAA> c){
        for(Object object : c){//通配符，取出时，就是Object
            System.out.println(object);
        }
    }
    // ? super 子类类名AAA:支持AAA类以及AAA类的父类，不限于直接父类，规定了泛型的下限
    public static void printCollection3(List<? super AAA> c){
        for(Object object : c){//通配符，取出时，就是Object
            System.out.println(object);
        }
    }
}
class AAA{}
class BBB extends AAA{}
class CCC extends BBB{}
```





# 十六章       坦克大战 - 1



## 坦克大战游戏演示

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克大战游戏演示.png)

### 坦克游戏说明文档

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克游戏说明文档.png)

**1、程序概述**

本程序是一个简单的坦克游戏程序，用 Java 语言编写，在 JDK环境下运行。游戏开始时，用户通过键盘操纵坦克移动，转弯和射击，与敌人坦克进行交战，知道消灭所有敌人就可以过关。本程序包括23个类，2800 多行代码，和三个 gif 图片。

### 写项目前的提醒

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\写项目前的提醒.png)



## Java 绘图坐标体系

### 坐标体系-介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坐标体系-介绍.png)

### 坐标体系-像素

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坐标体系-像素.png)

## Java 绘图技术

### Java 绘图技术快速入门

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java绘图技术快速入门.png)

### Java绘图技术绘图原理

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java绘图技术绘图原理.png)

DrawCircle.java（sixteen.one）

```java
package sixteen.one;

import javax.swing.*;
import java.awt.*;

public class DrawCircle extends JFrame{//JFrame 对应窗口，可以理解成是一个画板
    //定义一个画板
    private MyPanel mp = null;

    public static void main(String[] args) {
        new DrawCircle();
    }

    public DrawCircle() {
        //初始化画板
        mp = new MyPanel();
        //把画板放入到窗口（画框）
        this.add(mp);
        //设置窗口的大小
        this.setSize(400,300);
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);//可以显示
    }

    //1、先定义一个 MyPanel，继承 JPanel 类，画图形，就在面板上画
    class MyPanel extends JPanel{
        /*
        1、MyPanel 对象就是一个面板
        2、Graphics g 把 g 理解成一支画笔
        3、Graphics 提供了很多绘图的方法
        Graphics g
         */

        @Override
        public void paint(Graphics g) {//绘图方法
            super.paint(g);//调用父类的方法完成初始化
            System.out.println("paint 方法被调用了");
            //画出一个圆形。
            g.drawOval(10,10,100,100);
        }
    }
}
```



### Java 绘图技术 Graphics 类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java绘图技术Graphics类.png)



### Java 绘图技术绘出坦克（sixteen.tankgame01 包的代码）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java绘图技术绘出坦克.png)





## Java 事件处理机制

### 事件处理机制-看个问题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\事件处理机制-看个问题.png)

BallMore.java（sixteen.three）

```java
package sixteen.three;

import javax.swing.*;
import java.awt.*;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;

public class BallMore extends JFrame {//窗口
    MyPanel mp = null;

    public static void main(String[] args) {
        BallMore ballMore = new BallMore();
    }
    public BallMore(){
        mp = new MyPanel();
        this.add(mp);
        this.setSize(400, 300);
        this.addKeyListener(mp);
        //窗口 JFrame 对象可以监听键盘事件，即可以监听到面板发生的键盘事件
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setVisible(true);
    }
}
//面板，可以画出小球
//KeyListener 监听器，可以监听键盘事件
class MyPanel extends JPanel implements KeyListener{
    //为了让小球可以移动，把他的作左上角的坐标(x,y)设置变量
    int x = 10;
    int y = 10;
    @Override
    public void paint(Graphics g) {
        super.paint(g);
        g.fillOval(x, y, 20, 20);
    }
    //有字符输出时，该方法就会触发
    @Override
    public void keyTyped(KeyEvent e) {
    }
    //当某个键按下，该方法会触发
    @Override
    public void keyPressed(KeyEvent e) {
        System.out.println((char)e.getKeyCode() + "被按下了..");
        //根据用户按下的不同键，来处理小球的移动（上下左右的键）
        //在 java 中，会给每一个键，分配一个值（int）
        if(e.getKeyCode() == KeyEvent.VK_DOWN){
            y++;
        }else if(e.getKeyCode() == KeyEvent.VK_UP){
            y--;
        }else if(e.getKeyCode() == KeyEvent.VK_LEFT){
            x--;
        }else if(e.getKeyCode() == KeyEvent.VK_RIGHT){
            x++;
        }
        //让面板重绘
        this.repaint();
    }
    //当某个键释放（松开），该方法会触发
    @Override
    public void keyReleased(KeyEvent e) {
    }
}
```



### Java 事件处理机制基本说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java事件处理机制基本说明.png)

### Java 事件处理机制机制分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java事件处理机制机制分析.png)

### Java 事件处理机制深入了解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java事件处理机制深入了解.png)

### Java 事件处理机制事件类型

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Java事件处理机制事件类型.png)



## 坦克大战游戏（1.0 版）

### 让坦克动起来（ sixteen.tankgame02 包的代码）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\让坦克动起来.png)

### 坦克游戏练习题（ sixteen.tankgame03 包的代码）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克游戏练习题.png)

### 坦克游戏小结

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克游戏小结.png)



# 第十七章       多线程基础



## 线程介绍

### 线程相关概念 - 程序

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程相关概念.png)

### 线程相关概念 - 进程

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程相关概念进程.png)

### 线程相关概念 - 线程

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程相关概念线程.png)

### 线程相关概念 - 其他相关概念

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程相关概念其他相关概念.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程相关概念其他相关概念-2.png)

CpuNum.java（seventeen.one）

```java
package seventeen;

public class CpuNum {
    public static void main(String[] args) {
        Runtime runtime = Runtime.getRuntime();
        //获取当前电脑的 CPU 数量
        int cpuNums = runtime.availableProcessors();
        System.out.println("当前有 CPU 个数：" + cpuNums);
    }
}
```





## 线程创建

### 创建线程的两种方式

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\创建线程的两种方式.png)

### 线程使用案例一（继承 Thread 类）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程使用案例-1.png)

Thread01.java（seventeen.one）

```java
package seventeen.one;

public class Thread01 {
    public static void main(String[] args) throws InterruptedException{
        //创建Cat对象，可以当做线程使用
        Cat cat = new Cat();
        cat.start();//启动线程
        /*
        (1)
        public synchronized void start() {
            start0();
        }
        (2)
        start0() 是本地方法，时JVM调用，底层是 c/c++ 实现
        真正实现多线程的效果，是start0()，而不是 run 方法
        private native void start0();
         */
        //cat.run();//run方法就是一个普通方法，没有真正的启动一个线程，就会把 run 方法执行完毕，才向下执行
        //说明：当main线程启动一个子线程 Thread-0，主线程不会阻塞，会继续执行
        //这时主线程和子线程是交替执行..
        System.out.println("主线程继续执行" + Thread.currentThread().getName());
        for (int i = 0; i < 10; i++) {
            System.out.println("主线程 i：" + i);
            //让主线程休眠
            Thread.sleep(1000);
        }
    }
}
/*
1、当一个类继承了 Thread 类，该类就可以当做线程使用
2、我们会重写 run 方法，写上自己的业务代码
3、run Thread 类实现了 Runnable 接口的 run 方法
@Override
    public void run() {
        if (target != null) {
            target.run();
        }
    }
 */
class Cat extends Thread{
    int times = 0;
    @Override
    public void run() {//重写 run 方法，写上自己的业务逻辑
        while (true) {
            //该线程每隔1秒，在控制台输出“喵喵，我是小猫咪”
            System.out.println("喵喵，我是小猫咪" + (++times) + Thread.currentThread().getName());
            //让该线程休眠1秒 ctrl+alt+t
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            if(times == 8){
                break;//当times到80，退出while，这时线程也就退出..
            }
        }
    }
}
```

### 线程使用案例一（图解）

<img src="C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程基本使用案例图解.png" style="zoom:150%;" />



### 线程使用案例二（实现 Runnable 接口）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程基本使用案例-2.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程使用案例实现Runnable接口.png)

Thread02.java（seventeen.one）

```java
package seventeen.one;

public class Thread02 {
    public static void main(String[] args) {
        Dog dog = new Dog();
        //dog.start();这里不能调用start
        //创建了 Thread 对象，把 dog 对象（实现Runnable），放入Thread
        Thread thread = new Thread(dog);
        thread.start();
        Tiger tiger = new Tiger();//实现了 Runnable
        ThreadProxy threadProxy = new ThreadProxy(tiger);
        threadProxy.start();
    }
}
class Dog implements Runnable{//通过实现 Runnable 接口，开发线程
    int count = 0;

    @Override
    public void run() {
        while(true){
            System.out.println("小狗汪汪叫.." + (++count) + Thread.currentThread().getName());
            //休眠1秒
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            if(count == 8){
                break;
            }
        }
    }
}
class Animal{}
class Tiger extends Animal implements Runnable{
    @Override
    public void run() {
        System.out.println("老虎嗷嗷叫...");
    }
}
//线程代理类，模拟了一个极简单的 Thread
class ThreadProxy implements Runnable{//你可以把 Proxy类当做 ThreadProxy
    private Runnable target = null;//属性，类型是 Runnable

    @Override
    public void run() {
        if(target != null){
            target.run();//动态绑定（运行类型Tiger）
        }
    }

    public ThreadProxy(Runnable target) {
        this.target = target;
    }
    public void start(){
        start0();//这个方法是真正实现多线程的方法
    }
    public void start0(){
        run();
    }
}
```



### 线程使用案例三（多线程执行）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程使用案例-多线程执行.png)

Thread03.java（seventeen.one）

````java
package seventeen.one;

public class Thread03 {
    public static void main(String[] args) {
        T1 t1 = new T1();
        T2 t2 = new T2();
        Thread thread1 = new Thread(t1);
        Thread thread2 = new Thread(t2);
        thread1.start();//启动第一个线程
        thread2.start();//启动第二个线程
    }
}
class T1 implements Runnable{
    int count = 0;

    @Override
    public void run() {
        while (true) {
            //每隔一秒输出”hello，world“，输出十次
            System.out.println("hello，world" + (++count));
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            if (count == 10){
                break;
            }
        }
    }
}
class T2 implements Runnable{
    int count = 0;

    @Override
    public void run() {
        while (true) {
            //每隔一秒输出”hi...“，输出十次
            System.out.println("hi..." + (++count));
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            if (count == 10){
                break;
            }
        }
    }
}
````



### 线程如何理解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程如何理解.png)

### 继承 Thread 和实现 Runnable 的区别

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\继承Thread和实现Runnable的区别.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\继承Thread和实现Runnable的区别-1.png)

SellTicket.java（seventeen.one）

```java
package seventeen.one;
@SuppressWarnings({"all"})
public class SellTicket {
    public static void main(String[] args) {
        //测试
//        SellTicket01 sellTicket01 = new SellTicket01();
//        SellTicket01 sellTicket02 = new SellTicket01();
//        SellTicket01 sellTicket03 = new SellTicket01();

//        sellTicket01.start();//启动售票线程
//        sellTicket02.start();//启动售票线程
//        sellTicket03.start();//启动售票线程
        //简写
        SellTicket02 sellTicket02 = new SellTicket02();
        new Thread(sellTicket02).start();
        new Thread(sellTicket02).start();
        new Thread(sellTicket02).start();
    }
}
//使用 Thread 方式
@SuppressWarnings({"all"})
class SellTicket01 extends Thread{
    private static int ticketNum = 100;//让多个线程共享 ticketNum
    @Override
    public void run() {
        while(true){
            if (ticketNum <= 0){
                System.out.println("售票结束...");
                break;
            }
            //休眠50毫秒
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("窗口 " + Thread.currentThread().getName() + " 售出一张票" + "剩下余票：" + (--ticketNum));
        }
    }
}
//实现接口的方式
@SuppressWarnings({"all"})
class SellTicket02 implements Runnable{
    private static int ticketNum = 100;//让多个线程共享 ticketNum
    @Override
    public void run() {
        while(true){
            if (ticketNum <= 0){
                System.out.println("售票结束...");
                break;
            }
            //休眠50毫秒
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("窗口 " + Thread.currentThread().getName() + " 售出一张票" + "剩下余票：" + (--ticketNum));
        }
    }
}
```



### 线程终止基本说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程终止基本说明.png)

### 线程终止应用案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程终止应用案例.png)

ThreadExit.java（seventeen.one）

```java
package seventeen.one;

public class ThreadExit {
    public static void main(String[] args) throws InterruptedException{
        T t1 = new T();
        t1.start();
        /*
        如果希望 main 线程去控制 t1 线程的终止，必须可以修改 loop
        让 t1 退出 run 方法，从而终止 t1 线程 -> 通知方式
        让主线程休眠10秒，再通知 t1 线程退出
         */
        System.out.println("main线程休眠10秒...");
        Thread.sleep(10*1000);
        t1.setLoop(false);
    }
}
class T extends Thread{
    private int count = 0;
    private boolean loop = true;
    @Override
    public void run() {
        while(loop){
            try {
                Thread.sleep(50);
            }catch(InterruptedException e){
                e.printStackTrace();
            }
            System.out.println("T 运行中 ..." + (++count));
        }
    }

    public boolean isLoop() {
        return loop;
    }

    public void setLoop(boolean loop) {
        this.loop = loop;
    }
}
```



## 线程方法

### 线程常用方法（第一组）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程常用方法.png)

### 线程常用方法注意事项和细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程常用方法注意事项和细节.png)

### 线程常用方法（第一组）应用案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程常用方法应用案例.png)

ThreadMethod01.java（seventeen.two）

```java
package seventeen.two;

public class ThreadMethod01 {
    public static void main(String[] args) throws InterruptedException{
        T3 t3 = new T3();
        t3.start();
        //主线程打印 5 个 hi，然后我就中断子线程的休眠
        for (int i = 0; i < 5; i++) {
            Thread.sleep(1000);
            System.out.println("hi" + i);
        }
        System.out.println(t3.getName() + "线程的优先级：" + t3.getPriority());//1
        t3.interrupt();
    }
}
class T3 extends Thread{//自定义的线程类

    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            //Thread.currentThread().getName() 获取当前线程的名称
            System.out.println(Thread.currentThread().getName() + " 吃包子~~~");
        }
        try {
            System.out.println(Thread.currentThread().getName() + " 休眠中~~~");
            Thread.sleep(20000);//休眠20秒
        } catch (InterruptedException e) {
//            e.printStackTrace();
            //当线程执行到一个 interrupt 方法时，就会 catch 一个异常，可以加入自己的业务代码
            //InterruptedException 是捕获到一个中断异常
            System.out.println(Thread.currentThread().getName() + "被 Interrupt 了");
        }
    }
}
```



### 线程常用方法（第二组）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程常用方法-2.png)

### 线程常用方法（第二组）应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程常用方法第二组应用实例.png)

ThreadMethod02.java（seventeen.two）

```java
package seventeen.two;

public class ThreadMethod02 {
    public static void main(String[] args) throws InterruptedException{
        T4 t4 = new T4();
        t4.start();
        for (int i = 0; i < 10; i++) {
            Thread.sleep(1000);
            System.out.println("主线程吃了 " + i + " 包子");
            if(i == 5){
                System.out.println("主线程（小弟）让子线程（老大）先吃");
//                t4.join();//这里相当于让 t4 线程先执行完毕
                Thread.yield();//礼让，不一定成功..
                System.out.println("线程（老大）吃完了主线程（小弟）接着吃..");
            }
        }
    }
}
class T4 extends Thread{
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("子线程吃了 " + i + " 包子");
        }
    }
}
```



### 线程常用方法练习题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程常用方法练习题.png)

ThreadMethodExercise.java（seventeen.two）

```java
package seventeen.two;

public class ThreadMethodExercise {
    public static void main(String[] args) throws InterruptedException{
        Thread t5 = new Thread(new T5());//创建子线程
        for (int i = 0; i < 10; i++) {
            System.out.println("hi " + i);
            if(i == 5){//说明主线程输出了5次 hi
                t5.start();//启动子线程输出 hello...
                t5.join();//立即将t5子线程，插入到main线程，让t5先执行
            }
            Thread.sleep(1000);//输出一次 hi，让main线程也休眠1秒
        }
    }
}
class T5 implements Runnable{
    private int count = 0;

    @Override
    public void run() {
        while(true){
            System.out.println("hello " + (++count));
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            if(count == 10){
                break;
            }
        }
    }
}
```



### 线程常用方法（第三组）

**用户线程和守护线程**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\用户线程和守护线程.png)

### 线程常用方法（第三组）应用案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程常用方法第三组应用案例.png)

ThreadMethod03.java（seventeen.two）

```java
package seventeen.two;

public class ThreadMethod03 {
    public static void main(String[] args) throws InterruptedException{
        /*
        如果我们希望当main线程结束后，子线程自动结束
        只需要子线程设为守护线程即可
         */
        MyDaemonThread myDaemonThread = new MyDaemonThread();
        myDaemonThread.setDaemon(true);
        myDaemonThread.start();
        for (int i = 0; i < 10; i++) {//main
            System.out.println("渍渍渍渍~~~");
            Thread.sleep(1000);
        }
    }
}
class MyDaemonThread extends Thread{
    @Override
    public void run() {
        for (; ; ){//无限循环
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("哈哈哈哈~~~");
        }
    }
}
```



## 线程的生命周期

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程的生命周期.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程的生命周期官方.png)

### 线程的生命周期状态转换图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程的生命周期状态转换图.png)

ThreadState.java（seventeen.two)

```java
package seventeen.two;

public class ThreadState {
    public static void main(String[] args) throws InterruptedException{
        T6 t6 = new T6();
        System.out.println(t6.getName() + " 状态 " + t6.getState());
        t6.start();
        while(Thread.State.TERMINATED != t6.getState()){
            System.out.println(t6.getName() + " 状态 " + t6.getState());
            Thread.sleep(500);
        }
        System.out.println(t6.getName() + " 状态 " + t6.getState());
    }
}
class T6 extends Thread{
    @Override
    public void run() {
        for (int i = 0; i < 10; i++) {
            System.out.println("hi " + i);
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```





## Synchronized

### 线程同步问题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程同步问题.png)

### 线程同步机制

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\线程同步机制.png)

### 同步具体方法 - Synchronized

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\同步具体方法-Synchronized.png)

SynSellTicket.java（seventeen.three）

```java
package seventeen.three;
@SuppressWarnings({"all"})
public class SynSellTicket {
    public static void main(String[] args) {
        //简写
        SellTicket03 sellTicket03 = new SellTicket03();
        new Thread(sellTicket03).start();
        new Thread(sellTicket03).start();
        new Thread(sellTicket03).start();
    }
}
//实现接口的方式，使用 synchronized 实现线程同步
@SuppressWarnings({"all"})
class SellTicket03 implements Runnable{
    private static int ticketNum = 100;//让多个线程共享 ticketNum
    private boolean loop = true;//控制run方法变量

    public synchronized void sell(){//同步方法，在同一时刻，只能有一个线程来执行 sell 方法
        if(ticketNum <= 0){
            System.out.println("售票结束...");
            loop = false;
            return;
        }
        //休眠50毫秒
        try {
            Thread.sleep(50);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("窗口 " + Thread.currentThread().getName() + " 售出一张票" + "剩下余票：" + (--ticketNum));
    }

    @Override
    public void run() {
        while(loop){
            sell();//sell 方法是一个同步方法
        }
    }
}
```

### 分析同步原理

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\分析同步原理.png)



## 互斥锁

### 互斥锁基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\互斥锁基本介绍.png)

### 使用互斥锁来解决售票问题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\使用互斥锁来解决售票问题.png)

### 互斥锁注意事项和细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\互斥锁注意事项和细节.png)

MutualLock.java（seventeen.three）

```java
package seventeen.three;
@SuppressWarnings({"all"})
public class MutualLock {
    public static void main(String[] args) {
        //简写
        SellTicket04 sellTicket04 = new SellTicket04();
        new Thread(sellTicket04).start();
        new Thread(sellTicket04).start();
        new Thread(sellTicket04).start();
    }
}
//实现接口的方式，使用 synchronized 实现线程同步
@SuppressWarnings({"all"})
class SellTicket04 implements Runnable{
    private static int ticketNum = 100;//让多个线程共享 ticketNum
    private boolean loop = true;//控制run方法变量
    Object object = new Object();

    //1、public synchronized static void m1(){} 锁是加在 SellTicket04.class
    //2、如果在静态方法中，实现一个同步代码块（同步方法（静态的）的锁为当前类本身）
    /*
            synchronized (SellTicket04.class){
                System.out.println("m2");
            }
     */
    public synchronized static void m1(){}
    public static void m2(){
        synchronized (SellTicket04.class){
            System.out.println("m2");
        }
    }

    /*
    1、public synchronized void sell(){} 就是一个同步方法
    2、这时锁在 this 对象
    3、也可以在代码块上写 synchronized，同步代码块，互斥锁还是在 this 对象
     */
    public /*synchronized*/ void sell(){//同步方法，在同一时刻，只能有一个线程来执行 sell 方法
        synchronized (/*this*/ object){
            if(ticketNum <= 0){
                System.out.println("售票结束...");
                loop = false;
                return;
            }
            //休眠50毫秒
            try {
                Thread.sleep(50);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            System.out.println("窗口 " + Thread.currentThread().getName() + " 售出一张票" + "剩下余票：" + (--ticketNum));
        }
    }

    @Override
    public void run() {
        while(loop){
            sell();//sell 方法是一个同步方法
        }
    }
}
//使用 Thread 方式（则会不是同一个对象）
//new SellTicket05().start()
//new SellTicket05().start()
class SellTicket05 extends Thread{
    private static int ticketNum = 100;//让多个线程共享 ticketNum
    public void m1(){
        synchronized (this){
            System.out.println("m2");
        }
    }
}
```



## 死锁

### 死锁基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\死锁基本介绍.png)

### 死锁的应用案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\死锁的应用案例.png)

DeadLock.java（seventeen.three）

```java
package seventeen.three;
@SuppressWarnings({"all"})
public class DeadLock {
    public static void main(String[] args) {
        //模拟死锁现象
        DeadLockDemo A = new DeadLockDemo(true);
        A.setName("A线程");
        DeadLockDemo B = new DeadLockDemo(false);
        B.setName("B线程");
        A.start();
        B.start();
    }
}
@SuppressWarnings({"all"})
class DeadLockDemo extends Thread{
    static Object o1 = new Object();//保证多线程，共享一个对象，这里使用 static
    static Object o2 = new Object();
    boolean flag;

    public DeadLockDemo(boolean flag) {
        this.flag = flag;
    }
    /*
    下面业务逻辑的分析
    1、如果 flag 为 T，线程A就会先得到/持有o1对象锁，然后尝试去获取o2对象锁
    2、如果线程A得不到o2对象锁，就会Blocked
    3、如果 flag 为 F，线程A就会先得到/持有o2对象锁，然后尝试去获取o1对象锁
    4、如果线程A得不到o1对象锁，就会Blocked
     */
    @Override
    public void run() {
        if(flag){
            synchronized (o1){
                System.out.println(Thread.currentThread().getName() + "进入1");
                synchronized (o2){//这里获得li对象的监视权
                    System.out.println(Thread.currentThread().getName() + "进入2");
                }
            }
        }else{
            synchronized (o2){
                System.out.println(Thread.currentThread().getName() + "进入3");
                synchronized (o1){//这里获得li对象的监视权
                    System.out.println(Thread.currentThread().getName() + "进入4");
                }
            }
        }
    }
}
```



## 释放锁

### 什么时候会释放锁

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\释放锁操作.png)

### 什么时候不会释放锁

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\释放锁分析.png)





# 第十八章       坦克大战 - 2



## 坦克大战 - 线程应用

### 坦克大战增加功能 0.3

**（代码在 eighteen.tankgame04 包）**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克大战-线程应用.png)



**分析如何实现当用户按下 J 键，我们的坦克就发射一颗子弹**

1、当发射一颗子弹后，就相当于启动一个线程。

2、Hero 有子弹的对象，当按下 J 时，我们就启动一个发射行为（线程），让子弹不停的移动，形成一个射击的效果。

3、我们 MyPanel 需要不停的重绘子弹，才能出现该效果。

4、当子弹移动到面板的边界时，就应该销毁（把启动的子弹的线程销毁）



### 坦克大战增加功能 0.4

**（代码在 eighteen.tankgame05 包）**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克大战增加功能.png)

**让敌人的坦克也能够发射子弹（可以有多个子弹）**

1、在敌人坦克类，使用 Vector 保存多个 Shot。

2、当每创建一个敌人对象，给该敌人坦克对象初始化一个 Shot 对象，同时启动 Shot。

3、在绘制敌人坦克时，需要遍历敌人坦克对象 Vector，绘制所有的子弹，当子弹 isLive == false 时，就从 Vector 移除。

**让敌人的坦克也可以自由随机的上下左右移动**

1、因为要求敌人的坦克，可以自由移动，因此需要将敌人坦克当做线程使用。

2、我们需要EnemyTank implements Runnable。

3、在 run 方法写上我们相应的业务代码。

4、在创建敌人坦克对象时，启动线程。



### 坦克大战增加功能 0.5

**（代码在 eighteen.tankgame05 包）**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克大战增加功能-2.png)

**我方坦克在发射的子弹消亡后，才能发射新的子弹 -> 扩展（发射多颗子弹怎么办）**

1、在按下 J 键，我们判断当前 hero 对象的子弹，是否已经销毁。

2、如果没有销毁，就不去触发 shotEnemyTank。

3、如果已经销毁，才会触发 shotEnemyTank。

4、如果要发射多个子弹，就使用 Vector 保存。

5、在绘制我方子弹时，需要遍历该 Vector 集合。





# 第十九章       IO 流



## 文件的基本使用

### 什么是文件

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\什么是文件.png)



### 文件流

**输入流：**数据从数据源（文件）到程序（内存）的路径

**输出流：**数据从程序（内存）到数据源（文件）的路径

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\文件流.png)



## 常用的文件操作

### 创建文件对象相关构造器和方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\创建文件对象相关构造器和方法.png)

### 案例演示

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\创建文件对象相关构造器和方法案例演示.png)

FileCreate.java（nineteen.one）

```java
package nineteen.one;

import org.junit.jupiter.api.Test;

import java.io.File;
import java.io.IOException;

public class FileCreate {
    public static void main(String[] args) {

    }
    //方式一：new File(String pathname)
    @Test
    public void create01(){
        String filePath = "d:\\fileTest\\news01.txt";
        File file = new File(filePath);
        try {
            file.createNewFile();
            System.out.println("文件创建成功");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
    //方式二：new File(File parent, String child)：根据父目录文件+子路径构建
    //d:\\fileTest\\new02.txt
    @Test
    public void create02(){
        File parentFile = new File("d:\\fileTest\\");
        String fileName = "news.txt";
        //这里的 file 对象，在 java 程序中，只是一个对象
        //只有执行了 createNewFile 方法，才会真正的，在磁盘创建该文件
        File file = new File(parentFile, fileName);
        try {
            file.createNewFile();
            System.out.println("文件创建成功");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
    //方式三：new File(String parent, String child)：根据父目录+子路径构建
    @Test
    public void create03(){
        String parentPath = "d:\\fileTest\\";
        String fileName = "news03.txt";
        File file = new File(parentPath, fileName);
        try {
            file.createNewFile();
            System.out.println("文件创建成功");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```



### 获取文件的相关信息

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取文件的相关信息.png)

### 案例演示

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取文件的相关信息案例演示.png)

FileInformation.java（nineteen.one）

```java
package nineteen.one;

import org.junit.jupiter.api.Test;

import java.io.File;

public class FileInformation {
    public static void main(String[] args) {

    }
    //获取文件的信息
    @Test
    public void info(){
        //创建文件对象
        File file = new File("d:\\fileTest\\news01.txt");
        //调用相应的方法，得到对应信息
        //getName、getAbsolutePath、getParent、length、exists、isFile、isDirectory
        System.out.println("文件名字：" + file.getName());
        System.out.println("文件绝对路径：" + file.getAbsolutePath());
        System.out.println("文件父级目录：" + file.getParent());
        System.out.println("文件大小（字节）：" + file.length());
        System.out.println("文件是否存在：" + file.exists());
        System.out.println("是不是一个文件：" + file.isFile());
        System.out.println("是不是一根目录：" + file.isDirectory());
    }
}
```



### 目录的操作和文件删除

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\目录的操作和文件删除.png)

```java
//判断d:\\fileTest\\new03.txt 是否存在，存在就删除，否则提示不存在
//这里我们需要体会到，在 java 编程中，目录也被当作文件
@Test
public void deleteFile(){
    String filePath = "d:\\fileTest\\news03.txt";
    File file = new File(filePath);
    if(file.exists()){
        if (file.delete()){
            System.out.println(filePath + "删除成功");
        }else{
            System.out.println(filePath + "删除失败");
        }
    }else{
        System.out.println("该文件不存在...");
    }
}
//判断 d:\\fileTest\\a\\b\\c 目录是否存在，如果存在就提示已经存在，否则就创建
@Test
public void mkdirsFile(){
    String directoryPath = "d:\\fileTest\\a\\b\\c";
    File file = new File(directoryPath);
    if(file.exists()){
        System.out.println(directoryPath + "存在...");
    }else{
        if(file.mkdirs()){//创建一级目录使用 mkdir()，创建多级目录使用 mkdirs()
            System.out.println(directoryPath + "创建成功");
        }else{
            System.out.println(directoryPath + "创建失败");
        }
    }
}
```



## IO 原理及流的分类

### Java IO流原理

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JavaIO流原理.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JavaIO流原理续.png)



### 流的分类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\流的分类.png)



### IO流体系图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\IO流体系图.png)

**InputStream : 字节输入流**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\InputStream字节输入流.png)

**OutputStream : 字节输出流**

**Reader : 字符输入流**

**Writer : 字符输出流**



## FileInputStream 和 FileOutputStream

### FileInputStream 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileInputStream介绍.png)



### FileInputStream 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileInputStream应用实例.png)

FileInputStream_.java（nineteen.two）

```java
package nineteen.two;

import org.junit.jupiter.api.Test;

import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;

public class FileInputStream_ {
    public static void main(String[] args) {

    }

    /**
     * 单个字节的读取，效率比较低
     * -> 使用 read(byte[] b)
     */
    @Test
    public void readFile01(){
        String filePath = "d:\\fileTest\\news01.txt";
        int readData = 0;
        FileInputStream fileInputStream = null;
        try {
            //创建 FileInputStream 对象，用于读取文件
            fileInputStream = new FileInputStream(filePath);
            //从该输入流读取一个字节的数据。如果没有输入可用，此方法阻止
            //如果返回-1，表示读取完毕
            while((readData = fileInputStream.read()) != -1){
                System.out.print((char)readData);//转成char显示
            }
        } catch (IOException e) {
            e.printStackTrace();
        }finally {
            //关闭文件流，释放资源
            try {
                fileInputStream.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

    }

    /**
     * 使用 使用 read(byte[] b) 读取文件，提高效率
     */
    @Test
    public void readFile02(){
        String filePath = "d:\\fileTest\\news01.txt";
        //字节数组
        byte[] buf = new byte[8];//一次读取8个字节
        int readLen = 0;
        FileInputStream fileInputStream = null;
        try {
            //创建 FileInputStream 对象，用于读取文件
            fileInputStream = new FileInputStream(filePath);
            //从该输入流读取一个字节的数据。如果没有输入可用，此方法阻止
            //如果返回-1，表示读取完毕
            while((readLen = fileInputStream.read(buf)) != -1){
                System.out.print(new String(buf, 0, readLen));//转成char显示
            }
        } catch (IOException e) {
            e.printStackTrace();
        }finally {
            //关闭文件流，释放资源
            try {
                fileInputStream.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

    }
}
```



### FileOutputStream 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileOutputStream介绍.png)



### FileOutputStream 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileOutputStream应用实例.png)

FileOutputStream_.java（nineteen.two）

```java
package nineteen.two;

import org.junit.jupiter.api.Test;

import java.io.FileNotFoundException;
import java.io.FileOutputStream;
import java.io.IOException;

public class FileOutputStream_ {
    public static void main(String[] args) {

    }

    /**
     * 演示使用FileOutputStream将数据写到文件中
     * 如果该文件不存在，则创建该文件
     */
    @Test
    public void writeFile(){
        String filePath = "d:\\fileTest\\news03.txt";
        //创建 FileOutputStream 对象
        FileOutputStream fileOutputStream = null;
        try {
            //得到 FileOutputStream 对象
            //new FileOutputStream(filePath);创建方式，当写入内容时，会覆盖原来的内容
            //new FileOutputStream(filePath, true);创建方式，当写入内容时，会在文件后面追加内容
            fileOutputStream = new FileOutputStream(filePath);
            //写入一个字节
            //fileOutputStream.write('H');
            //写入字符串
            String str = "Hello World";
            //str.getBytes()可以把字符串 -> 字节数组
            //write(byte[] b)
            fileOutputStream.write(str.getBytes());
            /*
            write(byte[] b, int off, int len)
            将 len 个字节从位于偏移量 off 的指定字节数组写入此文件输出流
             */
            //fileOutputStream.write(str.getBytes(), 0, str.length());
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                fileOutputStream.close();
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```



### FileOutputStream 拷贝应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileOutputStream拷贝应用实例.png)

FileCopy.java（nineteen.two）

```java
package nineteen.two;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

public class FileCopy {
    public static void main(String[] args) {
        //完成文件拷贝，将 d:\\fileTest\\雪.jpg
        //思路分析
        //1、创建文件的输入流，将文件读入到程序
        //2、创建文件的输出流，将读取到的文件数据，写入到指定的文件
        String srcFilePath = "d:\\fileTest\\雪.jpg";
        String destFilePath = "d:\\fileTest\\拷贝\\雪.jpg";
        FileInputStream fileInputStream = null;
        FileOutputStream fileOutputStream = null;
        try {
            fileInputStream = new FileInputStream(srcFilePath);
            fileOutputStream = new FileOutputStream(destFilePath);
            //定义一个字节数组，提高读取效果
            byte[] buf = new byte[1024];
            int readLen = 0;
            while((readLen = fileInputStream.read(buf)) != -1){
                //读取到后，就写入到文件，通过 fileOutputStream
                //即，一边读一边写
                fileOutputStream.write(buf, 0, readLen);//一定要使这个方法
            }
            System.out.println("拷贝完成");
        } catch(IOException e) {
            e.printStackTrace();
        }finally{
            try {
                //关闭输入流和输出流，释放资源
                if (fileInputStream != null) {
                    fileInputStream.close();
                }
                if (fileOutputStream != null) {
                    fileOutputStream.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```







## FileReader 和 FileWriter

### FileReader 和 FileWriter 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileReader和FileWriter介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileReader和FileWriter介绍续.png)



### FileReader 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileReader和FileWriter应用实例.png)

FileReader_.java（nineteen.three）

```java
package nineteen.three;

import org.junit.jupiter.api.Test;

import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.io.Reader;
import java.sql.SQLOutput;

public class FileReader_ {
    public static void main(String[] args) {
    }
    @Test
    public void readFile01(){
        String filePath = "src\\nineteen\\three\\FileReader_.java";
        FileReader fileReader = null;
        int data = 0;
        //1、创建 FileReader 对象
        try {
            fileReader = new FileReader(filePath);
            //循环读取使用 read，单个字符读取
            while((data = fileReader.read()) != -1){
                System.out.print((char) data);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if (fileReader != null) {
                    fileReader.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
    @Test
    public void readFile02(){
        String filePath = "src\\nineteen\\three\\FileReader_.java";
        FileReader fileReader = null;
        char[] buf = new char[8];
        int readLen = 0;
        //1、创建 FileReader 对象
        try {
            fileReader = new FileReader(filePath);
            //循环读取使用 read(buf)，返回的是实际读取得到字符数
            //如果返回-1，说明读取结束
            while((readLen = fileReader.read(buf)) != -1){
                System.out.print(new String(buf, 0, readLen));
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                if (fileReader != null) {
                    fileReader.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```



### FileWriter 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\FileWriter应用实例.png)

FileWriter_java（nineteen.three）

```java
package nineteen.three;

import java.io.FileWriter;
import java.io.IOException;

public class FileWriter_ {
    public static void main(String[] args) {
        String filePath = "d:\\fileTest\\news03.txt";
        //创建 FileWriter 对象
        FileWriter fileWriter = null;
        String str = "风雨之后，定见彩虹";
        try {
            fileWriter = new FileWriter(filePath);//默认是覆盖写入
            //1、write(int):写入单个字符
            fileWriter.write('H');
            //2、write(char[]):写入指定数组
            fileWriter.write(str.toCharArray());
            //3、write(char[],off,len):写入指定数组的指定部分
            fileWriter.write(str.toCharArray(),0,str.toCharArray().length);
            //4、write(string):写入整个字符串
            fileWriter.write(str);
            //5、write(string,off,len):写入字符串的指定部分
            fileWriter.write(str,0, str.length());
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            try {
                //fileWriter.flush();
                //关闭输出流，释放资源
                //关闭文件流，等价 flush() + 关闭
                if(fileWriter != null){
                    fileWriter.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }

    }
}
```





## 节点流和处理流

### 节点流和处理流介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\节点流和处理流介绍.png)



### 节点流和处理流一览表

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\节点流和处理流一览表.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\节点流和处理流一览表介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\节点流和处理流一览表介绍续.png)



### 节点流和处理流的区别和联系

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\节点流和处理流的区别和联系.png)

### 模拟节点流和处理流关系（nineteen.three.one）



## BufferedReader 和 BufferedWriter

### 处理流 BufferedReader 和 BufferedWriter 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\处理流BufferedReader和BufferedWriter.png)

### BufferedReader应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\处理流BufferedReader应用实例.png)

BufferedReader_.java（nineteen.four）

```java
package nineteen.four;

import java.io.BufferedReader;
import java.io.FileReader;

public class BufferedReader_ {
    public static void main(String[] args) throws Exception{
        String filePath = "d:\\fileTest\\news03.txt";
        //创建 bufferedReader 对象
        BufferedReader bufferedReader = new BufferedReader(new FileReader(filePath));
        //读取
        String line;//按行读取，效率高
        /*
        说明
        1、bufferedReader.readLine() 是按行读取文件
        2、当返回 null 时，表示文件读取完毕
         */
        while((line = bufferedReader.readLine()) != null){
            System.out.println(line);
        }
        //关闭流，这里注意，只需要关闭 BufferedReader，因为底层会自动的去关闭节点流
        //FileReader.
        bufferedReader.close();
        /*
            public void close() throws IOException {
                synchronized (lock) {
                    if (in == null)
                        return;
                    try {
                        in.close();//in 就是我们传入的 new FileReader(filePath)节点流
                    } finally {
                        in = null;
                        cb = null;
                    }
                }
            }
         */
    }
}
```



### BufferedWriter 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\BufferedWriter应用实例.png)

BufferedWriter_.java（nineteen.four）

```java
package nineteen.four;

import java.io.BufferedWriter;
import java.io.FileWriter;

public class BufferedWriter_ {
    public static void main(String[] args) throws Exception{
        String filePath = "d:\\fileTest\\news03.txt";
        //创建 BufferedWriter
        //new BufferedWriter(filePath,true)：表示以追加的方式写入
        //new BufferedWriter(filePath)：表示以覆盖的方式写入
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(filePath));
        bufferedWriter.write("Hello World!");
        bufferedWriter.newLine();//插入一个换行
        bufferedWriter.write("Hello China!");
        bufferedWriter.newLine();//插入一个换行
        bufferedWriter.write("Hello GuangDong!");
        bufferedWriter.newLine();//插入一个换行

        //说明：关闭外层流即可，传入的 new FileWriter(filePath)，会在底层关闭
        bufferedWriter.close();
    }
}
```



### BufferedReader 和 BufferedWriter 综合应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\BufferedReader和BufferedWriter综合应用实例.png)

BufferedCopy.java（nineteen.four）

```java
package nineteen.four;

import java.io.*;
/*
1、BufferedReader 和 BufferedWriter 是按字符操作
2、不要去操作二进制文件【声音，视频，doc，pdf等等】，可能会造成文件损失。
 */
public class BufferedCopy {
    public static void main(String[] args) {
        String srcFilePath = "src\\nineteen\\four\\BufferedCopy.java";
        String destFilePath = "d:\\fileTest\\news03.txt";
        BufferedReader br = null;
        BufferedWriter bw = null;
        String line;
        try {
            br = new BufferedReader(new FileReader(srcFilePath));
            bw = new BufferedWriter(new FileWriter(destFilePath));
            //说明：readLine 读取一行内容，但是没有换行
            while((line = br.readLine()) != null){
                //每读取一行，就写入
                bw.write(line);
                //插入一个换行
                bw.newLine();
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            //关闭流
            try {
                if (br != null){
                    br.close();
                }
                if(bw != null){
                    bw.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```





## BufferedInputStream 和 BufferedOutputStream

### 处理流 BufferedInputStream 和 BufferedOutputStream 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\处理流BufferedInputStream和BufferedOutputStream介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\BufferedOutputStream介绍.png)



### BufferedInputStream 和 BufferedOutputStream 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\BufferedInputStream和BufferedOutputStream应用实例.png)

BufferedStreamCopy.java（nineteen.five）

```java
package nineteen.five;

import java.io.*;
import java.nio.Buffer;

public class BufferedStreamCopy {
    public static void main(String[] args) {
        String srcFilePath = "d:\\fileTest\\雪.jpg";
        String destFilePath = "d:\\fileTest\\拷贝\\冬.jpg";
        BufferedInputStream bis = null;
        BufferedOutputStream bos = null;
        String line;
        try {
            bis = new BufferedInputStream(new FileInputStream(srcFilePath));
            bos = new BufferedOutputStream(new FileOutputStream(destFilePath));
            //循环的读取文件，并写入到 destFilePath
            byte[] buf = new byte[1024];
            int readLen = 0;
            while((readLen = bis.read(buf)) != -1){
                bos.write(buf, 0, readLen);
            }
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            //关闭流
            try {
                if (bis != null){
                    bis.close();
                }
                if(bos != null){
                    bos.close();
                }
            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```





## 对象流 - ObjectInputStream 和 ObjectOutputStream

### 对象流 ObjectInputStream 和 ObjectOutputStream 应用的需求分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\对象流ObjectInputStream和ObjectOutputStream介绍.png)

### 序列化和反序列化介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\序列化和反序列化介绍.png)

### 对象流 ObjectInputStream 和 ObjectOutputStream 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\对象流ObjectInputStream和ObjectOutputStream介绍续.png)



### ObjectOutStream 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ObjectOutStream应用实例.png)

ObjectOutputStream_.java（nineteen.six）

```java
package nineteen.six;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;
import java.io.Serializable;

public class ObjectOutputStream_ {
    public static void main(String[] args) throws IOException {
        //序列化后，保存的文件格式，不是存在文本，而是按照他的格式来保存
        String filePath = "d:\\fileTest\\data.dat";
        ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(filePath));

        //序列化数据到 d:\fileTest\data.dat
        oos.write(100);//int -> Integer(实现了 Serializable)
        oos.writeBoolean(true);//boolean -> Boolean(实现了 Serializable)
        oos.writeChar('a');//char -> Character(实现了 Serializable)
        oos.writeDouble(9.5);//double ->Double(实现了 Serializable)
        oos.writeUTF("Hello World!");//String
        //保存一个dog对象
        oos.writeObject(new Dog("旺财",10));//需要继承实现了 Serializable
        oos.close();
        System.out.println("数据保存完毕（序列化形式）");
    }
}
//如果需要序列化某个类的对象，实现 Serializable
class Dog implements Serializable {
    private String name;
    private int age;

    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return "Dog{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
```



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ObjectInputStream应用实例.png)

ObjectInputStream_.java（nineteen.six）

```java
package nineteen.six;
import java.io.FileInputStream;
import java.io.ObjectInputStream;

public class ObjectInputStream_ {
    public static void main(String[] args) throws Exception{
        //指定反序列化的文件
        String filePath = "d:\\fileTest\\data.dat";
        ObjectInputStream ois = new ObjectInputStream(new FileInputStream(filePath));
        /*
        读取
        1、读取（反序列化）的顺序需要和你保存数据（序列化）的顺序一致
        2、否则会出现异常
         */
        System.out.println(ois.readInt());
        System.out.println(ois.readBoolean());
        System.out.println(ois.readChar());
        System.out.println(ois.readDouble());
        System.out.println(ois.readUTF());
        //1、如果我们希望调用Dog的方法，需要向下转型
        //2、需要我们将Dog类的定义，拷贝到可以引用的位置
        Object dog = ois.readObject();
        System.out.println("运行类型：" + dog.getClass());
        System.out.println("dog信息："+ dog);//底层 Object -> Dog
        //关闭流，关闭外层流即可，底层会关闭 FileInputStream 流
        ois.close();
    }
}
```



### 对象流注意事项和细节说明

Dog.java（nineteen.six）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\对象流注意事项和细节说明.png)



## 标准输入输出流

### 标准输入输出流介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\标准输入输出流介绍.png)

InputAndOutput.java（nineteen.six）

```java
package nineteen.six;

import java.util.Scanner;

public class InputAndOutput {
    public static void main(String[] args) {
        /*
        System 类 public final static InputStream in = null;
        System.in 编译类型 InputStream
        System.in 运行类型 BufferedInputStream
         */
        System.out.println(System.in.getClass());
        /*
        System 类 public final static InputStream out = null;
        System.out 编译类型 PrintStream
        System.out 运行类型 printStream
         */
        System.out.println(System.out.getClass());
        System.out.println("Hello World!");
        Scanner scanner = new Scanner(System.in);
        String next = scanner.next();
        System.out.println(next);
    }
}
```



### 标准输入输出流应用案例

InputAndOutput.java（nineteen.six）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\标准输入输出流应用案例.png)





## 转换流 - InputStreamReader 和 OutputStreamWriter

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\转换流InputStreamReader和OutputStreamWriter引用分析.png)

CodeQuestion.java（nineteen.seven）

```java
package nineteen.seven;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class CodeQuestion {
    public static void main(String[] args) throws IOException {
        /*
        1、创建字符串输入流 bufferedReader[处理流]
        2、使用 BufferedReader 对象读取 news03.txt
         */
        String filePath = "d:\\fileTest\\news04.txt";
        BufferedReader br = new BufferedReader(new FileReader(filePath));
        String s = br.readLine();
        System.out.println("读取到的内容：" + s);
        br.close();
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\转换流的引用乱码的解决.png)



### 转换流 InputStreamReader 和 OutputStreamWriter 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\转换流InputStreamReader和OutputStreamWriter介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\转换流的构造函数.png)



### 转换流 InputStreamReader 的应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\转换流的应用实例.png)

InputStreamReader_.java（nineteen.seven）

```java
package nineteen.seven;
import java.io.BufferedReader;
import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStreamReader;

/**
 * 演示使用 InputStreamReader 转换流解决中文乱码的问题
 * 将字节流 FileInputStream 转成字符流 InputStreamReader，指定编码 GB2312
 */
public class InputStreamReader_ {
    public static void main(String[] args) throws IOException {
        String filePath = "d:\\fileTest\\news04.txt";
        /*
        1、把 FileInputStream 转成 InputStreamReader
        2、指定编码 GB2312
         */
        InputStreamReader isr = new InputStreamReader(new FileInputStream(filePath),"GB2312");
        //3、把 InputStreamReader 传入 BufferedReader
        BufferedReader br = new BufferedReader(isr);
        //4、读取
        String s = br.readLine();
        System.out.println("读取的内容：" + s);
        //5、关闭外层流
        br.close();
    }
}
```



### 转换流 OutputStreamWriter  应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\转换流应用实例续.png)

OutputStreamWriter_.java（nineteen.seven）

```java
package nineteen.seven;

import java.io.FileOutputStream;
import java.io.IOException;
import java.io.OutputStreamWriter;

/**
 * 演示 OutputStreamWriter 使用
 * 把 FileOutputStream 字节流，转成字符流 OutputStreamWriter
 * 指定处理的编码 gbk、utf-8、utf8
 */
public class OutputStreamWriter_ {
    public static void main(String[] args) throws IOException {
        String filePath = "d:\\fileTest\\code.txt";
        String charSet = "gbk";
        OutputStreamWriter osw = new OutputStreamWriter(new FileOutputStream(filePath),charSet);
        osw.write("湛江欢迎你！");
        osw.close();
        System.out.println("按照 " + charSet + " 保存文件成功！");
    }
}
```



## 打印流 PrintStream 和 PrintWriter

### 打印流 PrintStream 和 PrintWriter 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\打印流PrintStream和PrintWriter应用实例.png)

PrintStream_.java（nineteen.seven）

```java
package nineteen.seven;

import java.io.IOException;
import java.io.PrintStream;

public class PrintStream_ {
    public static void main(String[] args) throws IOException {
        PrintStream out = System.out;
        //在默认情况下，PrintStream 输出数据的位置是标准输出，及显示器
        /*
            public void print(String s) {
                if (s == null) {
                    s = "null";
                }
                write(s);
            }
         */
        out.print("john,hello!");
        //因为 print 底层使用的是 write，所以我们可以直接调用 write 进行打印/输出
        out.write("smith,hi!!".getBytes());
        out.close();
        /*
        我们可以去修改打印流输出的位置/设备
        1、输出修改到 "d:\\fileTest\\news01.txt"
        2、
            public static void setOut(PrintStream out) {
                checkIO();
                setOut0(out);//native 方法，修改了 out
            }
         */
        System.setOut(new PrintStream("d:\\fileTest\\news01.txt"));
        System.out.println("smith,hi!!");
    }
}
```

PrintWriter_.java（nineteen.seven）

```java
package nineteen.seven;

import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;

public class PrintWriter_ {
    public static void main(String[] args) throws IOException {
        //PrintWriter printWriter = new PrintWriter(System.out);
        PrintWriter printWriter = new PrintWriter(new FileWriter("d:\\fileTest\\news01.txt"));
        printWriter.print("smith，hi！！!");
        printWriter.close();
    }
}
```





## Properties 类

### Properties 引用的需求分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Properties引用的需求分析.png)

Properties01.java（nineteen.eight）

```java
package nineteen.eight;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Properties01 {
    public static void main(String[] args) throws IOException {
        //读取 sql.properties 文件，并得到 ip，user 和 pwd
        BufferedReader br = new BufferedReader(new FileReader("src\\mysql.properties"));
        String line= "";
        while((line = br.readLine()) != null){//循环读取
            //System.out.println(line);
            String[] split = line.split("=");
            //如果我们要求指定的 ip 值
            System.out.println(split[0] + "值是：" + split[1]);
        }
        br.close();
    }
}
```



### Properties的基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Properties的基本介绍和常用方法.png)



### Properties的应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Properties的应用实例.png)

Properties02.java（nineteen.eight）

```java
package nineteen.eight;

import java.io.FileReader;
import java.io.IOException;
import java.util.Properties;

public class Properties02 {
    public static void main(String[] args) throws IOException {
        //使用 Properties 来读取 mysql.properties 文件
        //1、创建 Properties 对象
        Properties properties = new Properties();
        //2、加载指定配置文件
        properties.load(new FileReader("src\\mysql.properties"));
        //3、把 k-v 显示控制台
        properties.list(System.out);
        //4、根据key获取对应的值
        String user = properties.getProperty("user");
        String pwd = properties.getProperty("pwd");
        System.out.println("用户名：" + user);
        System.out.println("密码：" + pwd);
    }
}
```



Properties03.java（nineteen.eight）

```java
package nineteen.eight;

import java.io.FileOutputStream;
import java.io.IOException;
import java.util.Properties;

public class Properties03 {
    public static void main(String[] args) throws IOException {
        //使用 Properties 类创建配置文件，修改配置文件内容
        Properties properties = new Properties();
        //创建
        /*
        1、如果该文件没有 key，就是创建
        2、如果该文件有 key，就是修改
            Properties 父类是 Hashtable，底层就是 Hashtable 核心方法
            public synchronized V put(K key, V value) {
                // Make sure the value is not null
                if (value == null) {
                    throw new NullPointerException();
                }

                // Makes sure the key is not already in the hashtable.
                Entry<?,?> tab[] = table;
                int hash = key.hashCode();
                int index = (hash & 0x7FFFFFFF) % tab.length;
                @SuppressWarnings("unchecked")
                Entry<K,V> entry = (Entry<K,V>)tab[index];
                for(; entry != null ; entry = entry.next) {
                    if ((entry.hash == hash) && entry.key.equals(key)) {
                        V old = entry.value;
                        entry.value = value;//如果 key 存在，就替换
                        return old;
                    }
                }

                addEntry(hash, key, value, index);//如果是新 key，就 addEntry
                return null;
            }
         */
        properties.setProperty("charset", "utf8");
        properties.setProperty("user","tom");
        properties.setProperty("pwd","123456");
        //将 k-v 存放文件中即可
        //properties.store(new FileOutputStream("src\\mysql2.properties"),null);
        properties.store(new FileOutputStream("src\\mysql2.properties"),"Hello World!");
        System.out.println("保存配置文件成功");
    }
}
```





# 第二十章       坦克大战 - 3

## 坦克大战 - IO流应用

### 坦克大战0.6版

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克大战0.6版.png)

### 防止敌人坦克重叠思路图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\防止敌人坦克重叠思路图.png)

**（代码在 twenty.tankgame06 包）**



### 记录我方击毁敌方坦克总数分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\记录我方击毁敌方坦克总数分析.png)

### 坦克大战 0.6 版增加功能

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\坦克大战0.6版增加功能.png)



# 第二十一章       网络编程



## 网络的相关概念

### 网络通信

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网络通信.png)

### 网络概念

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网络概念.png)

### IP 地址介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\IP地址介绍.png)

### ipv4 地址分类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ipv4地址分类.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\IP为唯一标识.png)

### 域名介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\域名介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\域名和端口.png)

### 网络通信协议

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网络通信协议介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网络协议的图解.png)

#### 网络协议的理解

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网络协议的理解.png)

#### 网络同通信协议模型对应层

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网络同通信协议模型对应层.png)

#### TCP 和 UDP 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\TCP和UDP介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\TCP和UDP区别图解.png)



## InetAddress类

### InetAddress 类相关方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\InetAddress类相关方法.png)

### InetAddress 类应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\InetAddress类相关方法应用实例.png)

API_.java（twentyOne.one）

```java
package twentyOne.one;
import java.net.InetAddress;
import java.net.UnknownHostException;

public class API_ {
    public static void main(String[] args) throws UnknownHostException {
        //1、获取本机的InetAddress 对象
        InetAddress localHost = InetAddress.getLocalHost();
        System.out.println(localHost);
        //2、根据指定主机名，获取 InetAddress 对象
        InetAddress host1 = InetAddress.getByName("LAPTOP-PIOB2453");
        System.out.println("host1：" + host1);
        //3、根据域名返回 InetAddress 对象，比如 www.baidu.com 对应
        InetAddress host2 = InetAddress.getByName("www.baidu.com");
        System.out.println("host2：" + host2);
        //4、通过 InetAddress 对象，获取对应的地址
        String hostAddress = host2.getHostAddress();
        System.out.println("host2 对应的ip：" + hostAddress);
        //5、通过 Inetaddress 对象，获取对应的主机名/或者于域名
        String hostName = host2.getHostName();
        System.out.println("host2对应的主机名/域名：" + hostName);
    }
}
```



## TCP 网络通信编程

### Socket基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Socket基本介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Socket基本介绍图解.png)



### Socket - TCP 网络通信编程基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SocketTCP网络通信编程基本介绍.png)

### Socket - TCP网络通信编程应用实例 - 1

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SocketTCP网络通信编程应用实例.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\socket入门使用.png)

SocketTCP01Server.java（twentyOne.two）

```java
package twentyOne.two;

import java.io.IOException;
import java.io.InputStream;
import java.net.ServerSocket;
import java.net.Socket;

public class SocketTCP01Server {
    public static void main(String[] args) throws IOException {
        /*
        1、在本机的9999端口监听，等待连接
        细节：要求在本机没有其它服务在监听9999
        细节：这个 ServerSocket 可以通过 accept() 返回多个 Socket[多个客户端连接服务器的并发]
        */
        ServerSocket serverSocket = new ServerSocket(9999);
        /*
        2、当没有客户端连接9999端口时，程序会阻塞等待连接，如果有客户端连接
           ，则返回 Socket 对象，程序继续
        */
        Socket socket = serverSocket.accept();
        System.out.println("socket：" + socket.getClass());
        /*
        3、通过 socket.getInputStream() 读取客户端写入到数据通道的数据，显示
         */
        InputStream inputStream = socket.getInputStream();
        //IO读取
        byte[] buf = new byte[1024];
        int readLen = 0;
        while((readLen = inputStream.read(buf)) != -1){
            System.out.println(new String(buf, 0, readLen));
        }
        //关闭流和 socket
        inputStream.close();
        socket.close();
        serverSocket.close();

    }
}
```

SocketTCP01Client.java（twentyOne.two）

```java
package twentyOne.two;

import java.io.IOException;
import java.io.OutputStream;
import java.net.InetAddress;
import java.net.Socket;

public class SocketTCP01Client {
    public static void main(String[] args) throws IOException {
        //1、连接服务器（ip，端口）
        //连接本机的 9999 端口，如果连接成功，返回 Socket 对象
        Socket socket = new Socket(InetAddress.getLocalHost(), 9999);
        System.out.println("客户端 socket 返回：" + socket.getClass());
        //2、连接上后，生成 Socket，通过 socket.getOutputStream()
        //得到和 socket 对象关联的输出流对象
        OutputStream outputStream = socket.getOutputStream();
        //3、通过输出流，写入数据到数据通道
        outputStream.write("hello,server".getBytes());
        //4、关闭对象流和 socket，必须关闭
        outputStream.close();
        socket.close();
        System.out.println("客户端退出...");
    }
}
```



### Socket - TCP网络通信编程应用实例 - 2

**(在 twentyOne.two 包)**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SocketTCP网络通信编程应用实例续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SocketTCP网络通信编程应用实例续图解.png)



### Socket - TCP网络通信编程应用实例 - 3

**(在 twentyOne.two 包)**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SocketTCP网络通信编程应用实例续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SocketTCP网络通信编程应用实例续续图解.png)



### Socket - TCP网络通信编程应用实例 - 4

**(在 twentyOne.two 包)**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SocketTCP网络通信编程应用实例续续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SocketTCP网络通信编程应用实例续续续图解.png)



### netstat 指令

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\netstat指令的使用.png)

### TCP 网络通讯不为人知的密码

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\TCP网络通讯不为人知的密码.png)



## UDP 网络通信编程

### UDP 网络通信编程基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\UDP网络通信编程基本介绍.png)

### UDP 网络通信编程基本流程

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\UDP网络通信编程基本流程.png)

### UDP 网络通信编程原理图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\UDP网络通信编程原理图.png)

### UDP 网络通信编程应用实例

**(在 twentyOne.three 包)**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\UDP网络通信编程应用实例.png)



## 网络通信编程题

**(在 twentyOne.four 包)**

### 网路通信编程题 - 1

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网络通信作业-1.png)

### 网路通信编程题 - 2

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网路通信编程题-2.png)

### 网路通信编程题 - 3

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网路通信编程题-3.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\网络通信作业-3图解.png)



# 第二十二章       多用户即时通信系统



## QQ 聊天项目演示

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\QQ聊天项目演示.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\QQ聊天项目演示续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\QQ聊天项目演示续续.png)



## 多用户即时通信系统涉及技术

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统涉及技术.png)



## 多用户即时通信系统项目开发流程

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统项目开发流程.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统项目开发流程图解.png)



## 多用户即时通信系统需求分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统需求分析.png)



## 多用户即时通信系统界面设计

### 用户登录

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统界面设计.png)

### 拉取在线用户列表

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统拉取在线用户列表.png)

### 私聊

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\私聊.png)

### 群聊

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\群聊.png)

### 发文件

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\发文件.png)

### 文件服务器推送新闻

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\文件服务器推送新闻.png)



## 多用户即时通信系统功能图解分析

**(在 twentyTwo 包)**

### 多用户即时通信系统登录

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统图解分析.png)

### 多用户即时通信系统无异常退出

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用即时通信系统无异常退出.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用即时通信系统无异常退出图解.png)

### 多用户即时通信系统私聊

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用即时通信系统私聊图解.png)

### 多用户即时通信系统发文件

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统发文件.png)

### 多用户即时通信系统文件服务推送

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统文件服务推送.png)

### 多用户即时通信系统离线信息存储

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统离线信息存储.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\多用户即时通信系统离线信息存储图解.png)



# 第二十三章       反射（reflection）



## 反射介绍

### 一个需求引出反射

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\一个需求引出反射.png)

（主方法）ReflectionQuestion.java（twentyThree.one）及相关代码在包里

```java
package twentyThree.one;

import java.io.FileInputStream;
import java.io.IOException;
import java.lang.reflect.Method;
import java.util.Properties;

public class ReflectionQuestion {
    public static void main(String[] args) throws Exception {
        //根据配置文件 re.properties 指定信息，创建 Cat 对象并调用方法 hi
        //传统的方式 new 对象 -> 调用方法
        Cat cat = new Cat();
        cat.hi();

        /*
        传统的方式 new 对象 -> 调用方法
        Cat cat = new Cat();
        cat.hi(); --> cat.cry() 修改源码
         */

        //我们尝试做一做，明白反射
        //1、使用 Properties 类
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\twentyThree\\one\\re.properties"));
        String classfullpath = properties.get("classfullpath").toString();
        String methodName = properties.get("method").toString();
        System.out.println("classfullpath:" + classfullpath);
        System.out.println("method:"+ methodName);

        //2、创建对象，传统的方法，行不通->反射机制
        //new classfullpath();
        //3、使用反射机制解决
        //(1)加载类，返回 Class 类型的对象 cls
        Class<?> cls = Class.forName(classfullpath);
        //(2)通过 cls 得到你加载的类 twentyThree.one.Cat 的对象实例
        Object o = cls.newInstance();
        System.out.println("o 的运行类型：" + o.getClass());
        //(3)通过 cls 得到你加载的类 twentyThree.one.Cat 的 methodName “hi” 的方法对象
        //   即：在反射中可以把方法视为对象（万物皆对象）
        Method method = cls.getMethod(methodName);
        //(4)通过 method 调用方法：即通过方法对象来实现调用方法
        System.out.println("-----------------");
        method.invoke(o);//传统方法：对象.方法() ， 反射机制：方法.invoke(对象)
    }
}
```



## 反射机制

### Java Reflection

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\反射机制JavaReflection.png)



### 反射机制 Java 程序在计算机有三阶段

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\反射机制Java程序在计算机有三阶段.png)



### 反射机制 Java 的使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\反射机制Java的使用.png)



### 反射机制相关的主要类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\反射机制相关的主要类.png)

Reflection01.java（twentyThree.one）

```java
package twentyThree.one;

import java.io.FileInputStream;
import java.lang.reflect.Constructor;
import java.lang.reflect.Field;
import java.lang.reflect.Method;
import java.util.Properties;

public class Reflection01 {
    public static void main(String[] args) throws Exception{
        //使用反射
        //1、使用 Properties 类
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\twentyThree\\one\\re.properties"));
        String classfullpath = properties.get("classfullpath").toString();
        String methodName = properties.get("method").toString();
        System.out.println("classfullpath:" + classfullpath);
        System.out.println("method:"+ methodName);

        //2、创建对象，传统的方法，行不通->反射机制
        //new classfullpath();
        //3、使用反射机制解决
        //(1)加载类，返回 Class 类型的对象 cls
        Class<?> cls = Class.forName(classfullpath);
        //(2)通过 cls 得到你加载的类 twentyThree.one.Cat 的对象实例
        Object o = cls.newInstance();
        System.out.println("o 的运行类型：" + o.getClass());
        //(3)通过 cls 得到你加载的类 twentyThree.one.Cat 的 methodName “hi” 的方法对象
        //   即：在反射中可以把方法视为对象（万物皆对象）
        Method method = cls.getMethod(methodName);
        //(4)通过 method 调用方法：即通过方法对象来实现调用方法
        System.out.println("-----------------");
        method.invoke(o);//传统方法：对象.方法() ， 反射机制：方法.invoke(对象)

        //java.lang.reflect.Field：代表类的成员变量，Field 对象表示某个类的成员变量
        //得到 name 变量
        //getField 不能得到私有的属性
        Field ageField = cls.getField("age");
        System.out.println(ageField.get(o));//传统写法，对象.成员变量，反射：成员变量对象.get(对象)
        //java.lang.reflect.Constructor：代表类的构造方法，Constructor 对象表示构造器
        Constructor<?> constructor = cls.getConstructor();//()中可以指定构造器参数类型，返回有参构造器
        System.out.println(constructor);

        Constructor<?> constructor1 = cls.getConstructor(String.class);//(String.class)中可以指定参数类型，就是String有参构造器
        System.out.println(constructor1);
    }
}
```



### 反射优点和缺点

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\反射优点和缺点.png)

Reflection02.java （twentyThree.one）

```java
package twentyThree.one;

import java.lang.reflect.Method;

public class Reflection02 {
    public static void main(String[] args) throws Exception{
        m1();
        m2();
        m3();
    }
    //传统方法来调用方法 cry
    public static void m1(){
        Cat cat = new Cat();
        long start = System.currentTimeMillis();
        for (int i = 0; i < 900000000; i++) {
            cat.cry();
        }
        long end = System.currentTimeMillis();
        System.out.println("m1() 耗时：" + (end - start));
    }
    //反射机制来调用方法 cry
    public static void m2() throws Exception{
        Class<?> cls = Class.forName("twentyThree.one.Cat");
        Object o = cls.newInstance();
        Method cry = cls.getMethod("cry");
        long start = System.currentTimeMillis();
        for (int i = 0; i < 900000000; i++) {
            cry.invoke(o);
        }
        long end = System.currentTimeMillis();
        System.out.println("m2() 耗时：" + (end - start));
    }
    //反射调用优化 + 关闭访问检查
    public static void m3() throws Exception{
        Class<?> cls = Class.forName("twentyThree.one.Cat");
        Object o = cls.newInstance();
        Method cry = cls.getMethod("cry");
        cry.setAccessible(true);//在反射调用方法时，取消访问检查
        long start = System.currentTimeMillis();
        for (int i = 0; i < 900000000; i++) {
            cry.invoke(o);
        }
        long end = System.currentTimeMillis();
        System.out.println("m3() 耗时：" + (end - start));
    }
}
```



### 反射调用优化 - 关闭访问检查

Reflection02.java （twentyThree.one）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\反射调用优化-关闭访问检查.png)



## Class 类

### Class 类基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Class类基本介绍.png)

### Class 类关系图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Class类关系图.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Class对象在内存只加载一次.png)

Class01.java（twentyThree.two）

```java
package twentyThree.two;

import twentyThree.one.Cat;

public class Class01 {
    public static void main(String[] args) throws Exception{
        /*
        看看 Class 类图
        1、Class 也是类，因此也继承 Object 类
        2、Class 类对象不是 new 出来的，而是系统创建的
           (1)传统 new 对象
              ClassLoader 类
        public Class<?> loadClass(String name) throws ClassNotFoundException {
            return loadClass(name, false);
        }
        Cat cat = new Cat();

        (2)反射方式，刚才没有 debug 到 ClassLoader 类的 loadClass，原因是，没有注销 Cat cat = new Cat()
        ClassLoader 类仍然是通过 ClassLoader 类加载 Cat 类的 Class 对象
        public Class<?> loadClass(String name) throws ClassNotFoundException {
            return loadClass(name, false);
        }
         */
        Class<?> cls1 = Class.forName("twentyThree.one.Cat");

        //3、对于某个类的 Class 类对象，在内存中只有一份，因此类只加载一次
        Class<?> cls2 = Class.forName("twentyThree.one.Cat");
        System.out.println(cls1.hashCode());
        System.out.println(cls2.hashCode());
        Class cls3 = Class.forName("twentyThree.one.Dog");
        System.out.println(cls3.hashCode());
    }
}
```



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\反射机制Java程序在计算机有三阶段续.png)



### Class 类的常用方法

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Class类的常用方法.png)



### Class 类的应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Class类的常用方法应用实例.png)

Class02.java（twentyThree.two）

```java
package twentyThree.two;

import twentyThree.one.Cat;

import java.lang.reflect.Field;

public class Class02 {
    public static void main(String[] args) throws Exception{
        String classAllPath = "twentyThree.one.Cat";
        //1、获取到 Cat 类对应的 Class 对象
        //<?> 表示不确定的 Java 类型
        Class<?> cls = Class.forName(classAllPath);
        //2、输出 cls
        System.out.println(cls);//显示 cls 对象，是哪个类的 Class 对象 twentyThree.one.Cat
        System.out.println(cls.getClass());//输出 cls 运行类型 java.lang.Class
        //3、得到包名
        System.out.println(cls.getPackage());
        //4、得到全包名
        System.out.println(cls.getName());
        //5、通过 cls 创建对象实例
        Cat cat = (Cat)cls.newInstance();
        System.out.println(cat);//cat.toString()
        //6、通过反射获取属性 age
        Field age = cls.getField("age");
        System.out.println(age.get(cat));//18
        //7、通过反射给属性赋值
        age.set(cat, 28);
        System.out.println(age.get(cat));
        //8、我们希望大家可以得到所有的属性（字段）
        Field[] fields = cls.getFields();
        for (Field f : fields){
            System.out.println(f.getName());//名称
        }
    }
}
```



### 获取 Class 对象

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取Class对象.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取Class类对象续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取Class类对象续续.png)

GetClass_.java（twentyThree.two）

```java
package twentyThree.two;

import twentyThree.one.Cat;

public class GetClass_ {
    public static void main(String[] args) throws Exception{
        //1、Class.forName
        String classAllPath = "twentyThree.one.Cat";//通过读取配置文件获取
        Class<?> cls1 = Class.forName(classAllPath);
        System.out.println(cls1);
        //2、类名.class，应用场景：用于参数传递
        Class<Cat> cls2 = Cat.class;
        System.out.println(cls2);
        //3、对象.getClass()，应用场景，有对象实例
        Cat cat = new Cat();
        Class cls3 = cat.getClass();
        System.out.println(cls3);
        //4、通过类加载器【4种】类获取到类的Class对象
        //(1)先得到类加载器 cat
        ClassLoader classLoader = cat.getClass().getClassLoader();
        //(2)通过类加载器得到 Class 对象
        Class<?> cls4 = classLoader.loadClass(classAllPath);
        System.out.println(cls4);
        //cls1,cls2,cls3,cls4其实是同一对象
        System.out.println(cls1.hashCode());
        System.out.println(cls2.hashCode());
        System.out.println(cls3.hashCode());
        System.out.println(cls4.hashCode());
        //5、基本数据(int , char , boolean , float , double , byte , long , short)按如下方式得到 Class 类对象
        Class<Integer> integerClass = int.class;
        Class<Character> characterClass = char.class;
        Class<Boolean> booleanClass = boolean.class;
        System.out.println(integerClass);
        //6、基本数据类型对应的包装类，可以通过，TYPE 得到 Class 对象
        Class<Integer> type1 = Integer.TYPE;
        Class<Character> type2 = Character.TYPE;
        System.out.println(type1);
    }
}
```



### 那些类型有 Class 对象

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\那些类型有Class对象.png)

AllTypeClass.java（twentyThree.two）

```java
package twentyThree.two;

import java.io.Serializable;

public class AllTypeClass {
    public static void main(String[] args) {
        Class<String> cls1 = String.class;//外部类
        Class<Serializable> cls2 = Serializable.class;//接口
        Class<Integer[]> cls3 = Integer[].class;//数组
        Class<float[][]> cls4 = float[][].class;//二维数组
        Class<Deprecated> cls5 = Deprecated.class;//注解
        Class<Thread.State> cls6 = Thread.State.class;//枚举
        Class<Long> cls7 = long.class;//基本数据类型
        Class<Void> cls8 = void.class;//void类型
        Class<Class> cls9 = Class.class;
        System.out.println(cls1);
        System.out.println(cls2);
        System.out.println(cls3);
        System.out.println(cls4);
        System.out.println(cls5);
        System.out.println(cls6);
        System.out.println(cls7);
        System.out.println(cls8);
        System.out.println(cls9);
    }
}
```



## 类加载

### 类加载基本说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类加载基本说明.png)

ClassLoad_.java（twentyThree.two）

```java
package twentyThree.two;

import java.lang.reflect.Method;
import java.util.Scanner;

public class ClassLoad_ {
    public static void main(String[] args) throws Exception{
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入 key");
        String key = scanner.next();
        switch(key){
            case "1":
                //Cat cat = new Cat();//静态加载
                //cat.cry();
                break;
            case "2":
                Class<?> cls = Class.forName("twentyThree.one.Person");//加载Person类[动态加载]
                Object o = cls.newInstance();
                Method m = cls.getMethod("cry");
                m.invoke(o);
                System.out.println("ok");
                break;
            default:
                System.out.println("do nothing...");
        }
    }
}
//因为 new Cat() 是静态加载，因此必须编写 Cat
//Person 类是动态加载，所以，没有编写 Person 类也不会报错，只有当动态加载该类时，才会报错
```



### 类加载过程图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类加载过程图.png)

### 类加载各阶段完成任务

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类加载各阶段完成任务.png)

### 类加载加载阶段

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类加载加载阶段.png)

### 类加载连接阶段 - 验证

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类加载连接阶段-验证.png)

### 类加载连接阶段 - 准备

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类加载连接阶段-准备.png)

ClassLoad02.java（twentyThree.two）

```java
package twentyThree.two;

public class ClassLoad02 {
    public static void main(String[] args) {

    }
}
class A{
    /*
    属性-成员变量-字段
    类加载的连接阶段-准备，属性是如何处理
    1、n1 是实例属性，不是静态变量，因此在准备阶段，是不会分配内存
    2、n2 是静态变量，分配内存 n2 是默认初始化 0，而不是 20
    3、n3 是 static final 是常量，他和静态变量不一样，因为一旦赋值就不变，n3 = 30
     */
    public int n1 = 10;
    public static int n2 = 20;
    public static final int n3 = 30;
}
```



### 类加载连接阶段 - 解析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类加载连接阶段-解析.png)



### 类加载初始化

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\类加载初始化.png)

ClassLoad03.java（twentyThree.two）

```java
package twentyThree.two;

public class ClassLoad03 {
    public static void main(String[] args) {
        /*
        1、加载B类，并生成B的class对象
        2、连接 num = 0;
        3、初始化阶段
           依次自动收集类中的所有静态变量的赋值动作和静态代码块种的语句，并合并
           clinit(){
                System.out.println("B 静态代码块被执行");
                num = 300;
                num = 100;
           }
           合并：num = 100

         protected Class<?> loadClass(String name, boolean resolve)
                throws ClassNotFoundException
            {
                //正因为这个机制，才能保证某个类在内存中，只有一份 Class 对象
                synchronized (getClassLoadingLock(name)) {
                //...
                }
            }
     */
        new B();//类加载
        System.out.println(B.num);//100
    }
}
class B{
    static{
        System.out.println("B 静态代码块被执行");
        num = 300;
    }
    static int num = 100;

    public B() {
        System.out.println("B() 构造器被执行");
    }
}
```



## 通过反射获取类的结构信息

### 第一组

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射获取类的结构信息第一组.png)

ReflectionUtils.java（twentyThree.three）

```java
package twentyThree.three;

import org.junit.jupiter.api.Test;

import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;
import java.lang.reflect.Field;
import java.lang.reflect.Method;

public class ReflectionUtils {
    public static void main(String[] args) {

    }
    //第一组方法 API
    @Test
    public void api_01() throws ClassNotFoundException{

        //得到 Class 对象
        Class<?> personCls = Class.forName("twentyThree.three.Person");
        //getName:获取全类名
        System.out.println(personCls.getName());//twentyThree.three.Person
        //getSimpleName:获取简单类名
        System.out.println(personCls.getSimpleName());//Person
        //getFields:获取所有 public 修饰的属性，包含本类以及父类的
        Field[] fields = personCls.getFields();
        for (Field field : fields){
            System.out.println("本类以及父类的public属性：" + field.getName());
        }
        //getDeclaredFields:获取本类中所有属性
        Field[] declaredFields = personCls.getDeclaredFields();
        for (Field declaredField : declaredFields){
            System.out.println("本类中所有属性：" + declaredField.getName());
        }
        //getMethods:获取所有 public 修饰的方法，包含本类以及父类的
        Method[] methods = personCls.getMethods();
        for (Method method : methods){
            System.out.println("本类的以及父类的public方法" + method.getName());
        }
        //getDeclaredMethods:获取本类中所有方法
        Method[] declaredMethods = personCls.getDeclaredMethods();
        for (Method declaredMethod : declaredMethods){
            System.out.println("本类中所有的方法" + declaredMethod.getName());
        }
        //getConstructors:获取所有 public 修饰的构造器，包含本类以及父类的
        Constructor<?>[] constructors = personCls.getConstructors();
        for (Constructor constructor : constructors){
            System.out.println("本类以及父类的public构造器：" + constructor.getName());
        }
        //getDeclaredConstructors：获取本类中所有构造器
        Constructor<?>[] declaredConstructors = personCls.getDeclaredConstructors();
        for (Constructor declaredConstructor : declaredConstructors){
            System.out.println("本类中所有的构造器：" + declaredConstructor.getName());
        }
        //getPackage:以 Package 形式返回包信息
        System.out.println(personCls.getPackage());//
        //getSuperClass:以Class形式返回父类信息
        Class<?> superclass = personCls.getSuperclass();
        System.out.println("父类的class对象：" + superclass);
        //getInterfaces:以Class[]形式返回接口信息
        Class<?>[] interfaces = personCls.getInterfaces();
        for (Class<?> anInterface : interfaces){
            System.out.println("接口信息：" + anInterface);
        }
        //getAnnotations:以Annotation[] 形式返回注解信息
        Annotation[] annotations = personCls.getAnnotations();
        for (Annotation annotation : annotations){
            System.out.println("注解信息：" + annotation);//注解
        }
    }
}
class A{
    public String hobby;
    public A(){}
    public A(String hobby){}
}
interface IA{}
interface IB{}
@Deprecated
class Person extends A implements IA,IB{
    //属性
    public String name;
    protected int age;
    String job;
    private double sal;
    //方法
    public void m1(){}
    protected void m2(){}
    void m3(){}
    private void m4(){}
    //构造器
    public Person(){}
    public Person(String name){}
}
```



### 第二组

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射获取类的结构信息第二组.png)



### 第三组

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射获取类的结构信息第三组.png)



### 第四组

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射获取类的结构信息第四组.png)

```java
@Test
public void api02() throws ClassNotFoundException{
    //得到Class对象
    Class<?> personCls = Class.forName("twentyThree.three.Person");
    //getDeclaredFields:获取本类中所有的属性
    Field[] declaredFields = personCls.getDeclaredFields();
    for (Field declaredField : declaredFields){
        System.out.println("本类中所有属性：" + declaredField.getName() +
                           " 该属性的修饰符值：" + declaredField.getModifiers() +
                           " 该属性的类型：" + declaredField.getType());
    }
    //getDeclaredMethods:获取本类中所有的属性
    Method[] declaredMethods = personCls.getDeclaredMethods();
    for (Method declaredMethod : declaredMethods){
        System.out.println("本类中所有方法：" + declaredMethod.getName() +
                           " 该方法的访问修饰符值：" + declaredMethod.getModifiers() +
                           " 该方法的返回类型：" + declaredMethod.getReturnType());
        //输出当前这个方法的形参组情况
        Class<?>[] parameterTypes = declaredMethod.getParameterTypes();
        for (Class<?> parameterType : parameterTypes){
            System.out.println("该方法的形参类型：" + parameterType);
        }
    }
    //getDeclaredConstructors:获取本类中所有的属性
    Constructor[] declaredConstructors = personCls.getDeclaredConstructors();
    for (Constructor declaredConstructor : declaredConstructors){
        System.out.println("本类中所有构造器：" + declaredConstructor.getName());
        //输出当前这个方法的形参组情况
        Class<?>[] parameterTypes = declaredConstructor.getParameterTypes();
        for (Class<?> parameterType : parameterTypes){
            System.out.println("该构造器的形参类型：" + parameterType);
        }
    }
}
```



### 通过反射创建对象

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射创建对象.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射创建对象案例演示.png)

ReflecCreateInstance.java（twentyThree.three）

```java
package twentyThree.three;

import java.lang.reflect.Constructor;

public class ReflecCreateInstance {
    public static void main(String[] args) throws Exception{
        //1、先获取到 User 类的 Class 对象
        Class<?> userClass = Class.forName("twentyThree.three.User");
        //2、通过 public 的无参构造器创建实例
        Object o = userClass.newInstance();
        System.out.println(o);
        //3、通过 public 的有参构造器创建实例
        /*
        constructor 对象就是
            public User(String name) {//public有参构造器
                this.name = name;
            }
         */
        Constructor<?> constructor = userClass.getConstructor(String.class);
        Object smith = constructor.newInstance("smith");
        System.out.println(smith);
        //4、通过 public 的有参构造器创建实例
        //4.1 得到 private 的构造器对象
        Constructor<?> constructor1 = userClass.getDeclaredConstructor(int.class, String.class);
        //4.2 创建实例
        //暴破[暴力破解]，使用反射可以访问 private 构造器/方法/属性，反射面前，都是纸老虎
        constructor1.setAccessible(true);
        Object mike = constructor1.newInstance(100, "mike");
        System.out.println("user:" + mike);
    }
}
class User{//User类
    private int age;
    private String name;

    public User() {//无参构造器
    }

    public User(String name) {//public有参构造器
        this.name = name;
    }

    private User(int age, String name) {//public无参构造器
        this.age = age;
        this.name = name;
    }

    @Override
    public String toString() {
        return "User{" +
                "age=" + age +
                ", name='" + name + '\'' +
                '}';
    }
}
```



### 通过反射访问类中的成员（属性）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射访问类中的成员.png)

ReflecAccessProperty.java（twentyThree.three）

```java
package twentyThree.three;

import java.lang.reflect.Field;

public class ReflecAccessProperty {
    public static void main(String[] args) throws Exception{
        //得到Student类对应的Class对象
        Class<?> stuClass = Class.forName("twentyThree.three.Student");
        //2、创建对象
        Object o = stuClass.newInstance();//o 的运行类型就是 Student
        System.out.println(o.getClass());
        //3、使用反射得到 age 属性对象
        Field age = stuClass.getField("age");
        age.set(o,88);//通过反射来操作属性
        System.out.println(o);

        //4、使用反射操作name属性
        Field name = stuClass.getDeclaredField("name");
        //对 name 进行暴破，可以操作 private 属性
        name.setAccessible(true);
        //==name.set(o, "smith");
        name.set(null, "smith");//因为name是static属性，因此 o 也可以写成 null
        System.out.println(o);
        System.out.println(name.get(o));//获取属性值
        System.out.println(name.get(null));//获取属性值，要求name是static
    }
}
class Student{
    public int age;
    private static String name;
    public Student(){//构造器
    }

    @Override
    public String toString() {
        return "Student{" +
                "age=" + age +
                "name=" + name +
                '}';
    }
}
```



### 通过反射访问类中的成员（方法）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射访问类中的成员访问方法.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\通过反射访问类中的成员-方法案例演示.png)

ReflecAccessMethod.java（twentyThree.three）

```java
package twentyThree.three;

import java.lang.reflect.Method;

public class ReflecAccessMethod {
    public static void main(String[] args) throws Exception{
        //得到 Boss 类对应的 Class 对象
        Class<?> bossCls = Class.forName("twentyThree.three.Boss");
        //2、创建对象
        Object o = bossCls.newInstance();
        //3、调用 public 的 hi 方法
        Method hi1 = bossCls.getMethod("hi",String.class);
        Method hi2 = bossCls.getDeclaredMethod("hi",String.class);
        //3.1 得到 hi 方法对象调用
        hi1.invoke(o,"smith");

        //4、调用 private static 方法
        //4.1 得到say方法对象
        Method say = bossCls.getDeclaredMethod("say", int.class, String.class, char.class);
        //4.2 因为say方法是private，所以需要暴破。原理和前面的构造器和属性一样
        say.setAccessible(true);
        System.out.println(say.invoke(o, 100, "smith", '男'));
        //4.3 因为say方法是static的，还可以这样调用，可以传入null
        System.out.println(say.invoke(null, 100, "smith", '男'));

        //5、在反射中，如果方法有返回值，统一返回Object，但是他的运行类型和方法定义的返回类型一致
        Object reVal = say.invoke(null, 100, "mike", '男');
        System.out.println("reVal 的运行类型：" + reVal.getClass());//String
    }
}
class Boss{
    public int age;
    private static String name;

    public Boss() {
    }
    private static String say(int n, String s, char c){//静态方法
        return n + " " + s + " " + c;
    }
    public void hi(String s){//普通 public 方法
        System.out.println("hi " + s);
    }
}
```



# 第二十四章       零基础学 MySQL



## MySQL 认识介绍

### 数据库简单原理图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库简单原理图.png)

### 连接 MySQL 的指令

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\连接MySQL的指令.png)



### SQLyog 安装和使用

SQLyog  下载地址：https://sqlyog.en.softonic.com/

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SQLyog 安装和使用.png)

### 数据库三层结构-破除 MySQL 神秘

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库三层结构-破除MySQL神秘.png)

### 数据在数据库中的存储方式

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据在数据库中的存储方式.png)

### SQL语句分类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SQL语句分类.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\SQL语句分类续.png)

### MySQL 的三层结构

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL的三层结构.png)



## MySQL 创建库和表

### 创建数据库

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\创建数据库.png)

```sql
创建一个名称为fy_db的数据库。
#使用指令创建数据库
CREATE DATABASE fy_db01;
#删除数据库指令
DROP DATABASE fy_db03
#创建一个使用utf8字符集的fy_db02数据库
CREATE DATABASE fy_db02 CHARACTER SET utf8
#创建一个使用utf8字符集，并带校对规则的fy_db03数据库
CREATE DATABASE fy_db03 CHARACTER SET utf8 COLLATE utf8_bin
#校对规则 utf8_bin 区分大小，默认utf8_general_ci 不区分大小写
```



### 查看、删除数据库

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\查看删除数据库.png)

```sql
#查看当前数据库服务器中的所有数据库
SHOW DATABASES
#查看前面创建的 fy_db03 数据库的定义信息
SHOW CREATE DATABASE fy_db03
#在创建数据库，表的时候，为了规避关键字，可以使用反引号解决
DROP DATABASE `fy_db03`
```



### 备份、恢复数据库

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\备份恢复数据库.png)

```sql
#备份，要在Dos下执行mysqldump指令其实在mysql安装目录\bin
mysqldump -u root -p -B fy_db03 fy_db02 > d:\\fileTest\\bak.sql
DROP DATABASE fy_db03
#恢复数据库信息（注意：进入Mysql命令行再执行）
source d:\\fileTest\\bak.sql
#第二个恢复方法，直接将bak.sql的内容放到查询编辑器中，执行
```



### 备份、恢复数据库的表

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\备份恢复数据库的表.png)



### 创建表（重点）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\创建表.png)

### 修改表

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\修改表.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\修改表练习.png)





## MySQL 常用数据类型

### MySQL 常用数据类型一览表

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型.png)

### ![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型树状图续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型树状图.png)



### 数值型

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型数值型.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型数值型续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型数值型续续.png)



### 字符串

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型字符串.png)

### 字符串使用细节（重点）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型字符串续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型字符串续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型字符串续续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型字符串续续续续.png)



### 日期类型

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL常用数据类型日期类型.png)





## 数据库 CRUD 语句

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库CRUD语句.png)

### Insert 语句

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Insert语句.png)

### Insert 语句细节说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Insert语句细节说明.png)

### update 语句

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\update语句.png)

### update 语句细节说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\update语句细节说明.png)

### delete 语句

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\delete语句.png)

### delete 语句细节说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\delete语句细节说明.png)



## select 查询语句

### select 语句

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\select语句.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\select语句续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\select语句续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\select语句续续续.png)

### select语句 - where

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\select语句where.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\select语句where续.png)

### select 语句 order by

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\select语句orderby.png)

### select 语句 group by

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\select语句groupby.png)





## 合计/统计函数

### 合计统计函数 count

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\合计-统计函数count.png)

### 合计统计函数 sum

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\合计-统计函数sum.png)

### 合计统计函数 avg

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\合计-统计函数avg.png)

### 合计统计函数 Max、Min

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\合计-统计函数MaxMin.png)



## 相关函数

### 字符串相关函数

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\字符串相关函数.png)

### 数学相关函数

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数学相关函数.png)

### 时间日期相关函数

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\时间日期相关函数.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\时间日期相关函数续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\时间日期相关函数续续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\时间日期相关函数续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\时间日期相关函数续续续续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\时间日期相关函数续续续续.png)



### 加密和系统函数

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\加密和系统函数.png)



### 流程控制函数

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\流程控制函数.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\流程控制函数续.png)



## MySQL 表查询 - 加强

### 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表查询-加强.png)

### 引用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表查询-加强续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表查询-加强续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表查询-加强续续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表查询-加强续续续续.png)

### 数据分组 group by 总结

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据分组总结.png)



## MySQL 多表查询

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL多表查询.png)

### 说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL多表查询说明.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL多表查询说明分析.png)



### MySQL 多表查询自连接

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL多表查询自连接.png)



## MySQL 表子查询

### 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表子查询.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表子查询续.png)



### MySQL 表子查询中使用 all 操作符（重点）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表子查询中使用all操作符.png)



### MySQL 表子查询中使用 any 操作符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表子查询中使用any操作符.png)



### MySQL 表多列子查询

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表多列子查询.png)



### MySQL 表子查询练习

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表子查询练习.png)



## 合并查询

### 合并查询 union all

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\合并查询.png)

### 合并查询 union

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\合并查询union.png)



## MySQL 表外连接

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表外连接.png)

### 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表外连接介绍续.png)

### 使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表外连接介绍.png)

### 练习

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表外连接练习.png)



## MySQL 约束

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL约束基本介绍.png)

### 主键 primary key

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL约束主键.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL约束主键续.png)

### not null（非空） 和 unique（唯一）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL约束notnull和unique.png)

### 外键 foreign key

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL约束外键.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL约束外键示意图.png)



### check（范围）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL约束check.png)



### MySQL 约束练习

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL约束练习.png)



## 自增长

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自增长基本介绍.png)

### 使用细节

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\自增长使用细节.png)



## MySQL 索引

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL索引.png)

### 索引原理

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL索引原理.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL索引原理示意图.png)



### 索引类型

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL索引类型.png)



### 索引使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL索引使用.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL索引使用续.png)



### 索引使用练习

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL索引使用练习.png)



### MySQL 索引小结

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL索引小结.png)



## MySQL 事务

### 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务理解.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务操作示意图.png)



### 相关事务介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL相关事务介绍.png)



### 事务细节讨论

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务细节讨论.png)



### 事务隔离级别介绍（重点）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务隔离级别介绍.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务隔离级别介绍续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务隔离级别介绍续续.png)



### 事务隔离级别案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务隔离级别案例.png)



### 事务隔离级别相关操作

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务隔离级别相关操作.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务隔离级别全局修改.png)



### 事务 ACID 特性

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务ACID特性.png)



### 事务练习

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL事务练习.png)



## MySQL表类型和存储引擎

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表类型和存储引擎基本介绍.png)



### 特点

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表类型和存储引擎特点.png)



### 细节说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL表类型和存储引擎细节说明.png)



### 三种存储引擎使用案例（重点）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\三种存储引擎使用案例.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\三种存储引擎使用案例续.png)



### 修改存储引擎

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\修改存储引擎.png)



## 视图

### 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\视图介绍.png)



### 基本概念

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\视图基本概念.png)



### 视图和对应的真实表的关系

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\视图和对应的真实表的关系.png)



### 基本使用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\视图基本使用.png)



### 细节讨论

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\视图细节讨论.png)



### 最佳实践

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\视图最佳实践.png)



### 练习

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\视图练习.png)



## MySQL 管理

### MySQL 管理 - 用户

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL管理-用户.png)



### 创建和删除 MySQL 用户

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\创建和删除MySQL用户.png)



### MySQL 用户修改密码

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL用户修改密码.png)



### MySQL 用户权限管理

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL用户权限管理.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL中的权限管理.png)



### 给用户授权

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL用户权限管理-1.png)

### 回收用户授权

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL用户权限管理-2.png)



### MySQL 管理练习

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL管理练习.png)



### 细节说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\MySQL管理细节说明.png)





# 第二十五章       JDBC 和 数据库连接池



## JDBC概述

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC概述基本介绍.png)

MysqlJdbcImpl.java（twentyFive.one）

```java
```



### JDBC 的原理示意图

![]()![JDBC的原理示意图](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC的原理示意图.png)

### JDBC带来的好处

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC带来的好处.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC带来的好处续.png)



### JDBC - API 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBCAPI介绍.png)



## JDBC 快速入门

### 编程步骤

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC快速入门编程步骤.png)

### JDBC 第一个程序

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC第一个程序.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC第一个程序续.png)

Jdbc01.java（twentyFive.jdbc）

```java
package twentyFive.jdbc;


import com.mysql.cj.jdbc.Driver;

import java.sql.Connection;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;

public class Jdbc01 {
    public static void main(String[] args) throws SQLException {
        //前置工作：在项目下创建一个文件夹比如 libs
        //将 mysql.jar 拷贝到该项目下，点击 add to project ..加入到项目中

        //1、注册驱动
        Driver driver = new Driver();//创建对象

        //2、得到连接
        //(1) jdbc:mysql:// 规定好表示协议，通过 jdbc 的方式连接 mysql
        //(2) localhost 主机，可以是 ip 地址
        //(3) 3306 表示 mysql 监听的端口
        //(4) db_student 连接到 mysql dbms 的那个数据库
        String url = "jdbc:mysql://localhost:3306/db_student?serverTimezone=GMT%2B8";
        //将用户名和密码放入到 Properties 对象
        Properties properties = new Properties();
        //说明 user 和 password 是规定好的，后面的值根据实际情况写
        properties.setProperty("user", "root");
        properties.setProperty("password", "123456");
        Connection connect = driver.connect(url, properties);

        //3、执行 sql
        String sql = "insert into stu_info values (100, '赵六', '123456',null, '19111@qq.com',null )";
        //statement 用于执行静态 SQL 语句返回其生成的结果的对象
        Statement statement = connect.createStatement();
        int rows = statement.executeUpdate(sql);//如果是 dml 语句，返回的就是影响的行数

        System.out.println(rows > 0 ? "成功" : "失败");
        //4、关闭连接资源
        statement.close();
        connect.close();
    }
}
```



### 获取数据库连接 5 种方式

**方式一**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取数据库连接5种方式.png)

JdbcConn.java（twentyFive.jdbc）

```java
//方式一
    @Test
    public void connect01() throws SQLException{
        Driver driver = new Driver();//创建对象
        //2、得到连接
        //(1) jdbc:mysql:// 规定好表示协议，通过 jdbc 的方式连接 mysql
        //(2) localhost 主机，可以是 ip 地址
        //(3) 3306 表示 mysql 监听的端口
        //(4) db_student 连接到 mysql dbms 的那个数据库
        String url = "jdbc:mysql://localhost:3306/db_student?serverTimezone=GMT%2B8";
        //将用户名和密码放入到 Properties 对象
        Properties properties = new Properties();
        //说明 user 和 password 是规定好的，后面的值根据实际情况写
        properties.setProperty("user", "root");
        properties.setProperty("password", "123456");
        Connection connect = driver.connect(url, properties);
        System.out.println("方式一：" + connect);
    }
```

**方式二**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取数据库连接5种方式-2.png)

JdbcConn.java（twentyFive.jdbc）

```java
//方式二
    @Test
    public void connect02() throws Exception{
        //使用反射加载 Driver 类，动态加载，更加的灵活，减少依赖性
        Class<?> aClass = Class.forName("com.mysql.cj.jdbc.Driver");//创建对象
        Driver driver = (Driver)aClass.newInstance();
        String url = "jdbc:mysql://localhost:3306/db_student?serverTimezone=GMT%2B8";
        //将用户名和密码放入到 Properties 对象
        Properties properties = new Properties();
        //说明 user 和 password 是规定好的，后面的值根据实际情况写
        properties.setProperty("user", "root");
        properties.setProperty("password", "123456");
        Connection connect = driver.connect(url, properties);
        System.out.println("方式二：" + connect);
    }
```

**方式三**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取数据库连接5种方式-3.png)

JdbcConn.java（twentyFive.jdbc）

```java
//方式三
    @Test
    public void connect03() throws Exception{
        //使用反射加载 Driver 类，动态加载，更加的灵活，减少依赖性
        Class<?> aClass = Class.forName("com.mysql.cj.jdbc.Driver");//创建对象
        Driver driver = (Driver)aClass.newInstance();
        String url = "jdbc:mysql://localhost:3306/db_student?serverTimezone=GMT%2B8";
        //创建 url 和 user 和 password
        String user = "root";
        String password = "123456";
        DriverManager.registerDriver(driver);
        Connection connect = DriverManager.getConnection(url, user, password);
        System.out.println("方式三：" + connect);
    }
```

**方式四**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取数据库连接5种方式-4.png)

JdbcConn.java（twentyFive.jdbc）

```java
//方式四
    @Test
    public void connect04() throws Exception{
        //使用反射加载 Driver 类，动态加载，更加的灵活，减少依赖性
        //在加载 Driver 类时，完成注册
        /*
        源码：1、静态代码块，在类加载时，会执行一次
             2、DriverManager.registerDriver(new Driver());
             3、因此注册 driver 的工作已经完成
            static {
                try {
                    DriverManager.registerDriver(new Driver());
                } catch (SQLException var1) {
                    throw new RuntimeException("Can't register driver!");
                }
            }
         */
        Class.forName("com.mysql.cj.jdbc.Driver");
        String url = "jdbc:mysql://localhost:3306/db_student?serverTimezone=GMT%2B8";
        //创建 url 和 user 和 password
        String user = "root";
        String password = "123456";
        Connection connect = DriverManager.getConnection(url, user, password);
        System.out.println("方式四：" + connect);
    }
```

**方式五**

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\获取数据库连接5种方式-5.png)

JdbcConn.java（twentyFive.jdbc）

```java
//方式五
    @Test
    public void connect05() throws Exception{
        //通过 Properties 对象获取配置文件的信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\twentyFive\\jdbc\\mysql.properties"));
        //获取相关的值
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");
        String url = properties.getProperty("url");
        Class.forName(driver);//建议写上去
        Connection connect = DriverManager.getConnection(url, user, password);
        System.out.println("方式五：" + connect);
    }
```



## ResultSet结果集

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ResultSet结果集基本介绍.png)

### 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ResultSet结果集应用实例.png)

ResultSet_.java（twentyFive.resultset）

```java
package twentyFive.resultset;

import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;
import java.util.Properties;

public class ResultSet_ {
    public static void main(String[] args) throws Exception{
        //1、注册驱动
        //通过 Properties 对象获取配置文件的信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\twentyFive\\jdbc\\mysql.properties"));
        //获取相关的值
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");
        String url = properties.getProperty("url");
        Class.forName(driver);//建议写上去
        //2、得到连接
        Connection connection = DriverManager.getConnection(url, user, password);
        //3、得到 Statement
        Statement statement = connection.createStatement();
        //4、组织 sql
        String sql = "select stu_id, stu_name, email, address from stu_info";
        //执行给定的 SQL 语句，该语句返回单个 ResultSet 对象
        /*
        +--------+----------+----------------+-----------+
        | stu_id | stu_name | email          | address   |
        +--------+----------+----------------+-----------+
        |      1 | 张三     | 19111@qq.com   | 湛江市    |
        |     11 | 李四     | 8568232@qq.com | 湛江市    |
        |     21 | 王五     | 19111@qq.com   | 湛江市    |
        |    100 | 赵六     | 19111@qq.com   | NULL      |
        +--------+----------+----------------+-----------+
         */
        ResultSet resultSet = statement.executeQuery(sql);

        //5、使用 while 取出 数据
        while(resultSet.next()){
            int id = resultSet.getInt(1);
            String name = resultSet.getString(2);
            String email = resultSet.getString(3);
            String address = resultSet.getString(4);
            System.out.println(id + "\t" + name + "\t" + email + "\t" + address);
        }

        //6、关闭连接
        resultSet.close();
        statement.close();
        connection.close();
    }
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\ResultSet数据存放结构.png)



## Statement

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Statement基本介绍.png)

### 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Statement应用实例.png)

Statement_.java（twentyFive.resultset）

```java
package twentyFive.resultset;

import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;
import java.util.Properties;
import java.util.Scanner;

@SuppressWarnings({"all"})
public class Statement_ {
    public static void main(String[] args) throws Exception{
        Scanner scanner = new Scanner(System.in);
        //让用户数据管理员名和密码
        System.out.println("请输入管理员的名字：");//next()：当做收到空格或者 '就是表示结束
        String admin_name = scanner.nextLine();//如果希望看到 SQL 注入，这里需要用 nextLine
        System.out.println("请输入管理员的密码：");
        String admin_pwd = scanner.nextLine();


        //通过 Properties 对象获取配置文件的信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\twentyFive\\jdbc\\mysql.properties"));
        //获取相关的值
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");
        String url = properties.getProperty("url");
        Class.forName(driver);//建议写上去

        //2、得到连接
        Connection connection = DriverManager.getConnection(url, user, password);
        //3、得到 Statement
        Statement statement = connection.createStatement();
        //4、组织 sql
        String sql = "select stu_id, stu_name, email, address from stu_info where stu_name = '" + admin_name + "' and password = '" + admin_pwd + "'";

        ResultSet resultSet = statement.executeQuery(sql);
        if (resultSet.next()){
            System.out.println("恭喜，登陆成功");
        }else{
            System.out.println("对不起，登录失败");
        }
        /*
        请输入管理员的名字：
        1' or
        请输入管理员的密码：
        or '1' = '1
        恭喜，登陆成功
        */
        
        //5、关闭连接
        resultSet.close();
        statement.close();
        connection.close();
    }
}
```



## PreparedStatement

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\PreparedStatem基本介绍.png)



### 预处理好处

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\PreparedStatement预处理好处.png)



### 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\PreparedStatement应用实例.png)

PreparedStatement_.java（twentyFive.resultset）

```java
package twentyFive.resultset;

import java.io.FileInputStream;
import java.sql.*;
import java.util.Properties;
import java.util.Scanner;

public class PreparedStatement_ {
    public static void main(String[] args) throws Exception{
        Scanner scanner = new Scanner(System.in);
        //让用户数据管理员名和密码
        System.out.println("请输入管理员的名字：");//next()：当做收到空格或者 '就是表示结束
        String admin_name = scanner.nextLine();//如果希望看到 SQL 注入，这里需要用 nextLine
        System.out.println("请输入管理员的密码：");
        String admin_pwd = scanner.nextLine();


        //通过 Properties 对象获取配置文件的信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\twentyFive\\jdbc\\mysql.properties"));
        //获取相关的值
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String driver = properties.getProperty("driver");
        String url = properties.getProperty("url");
        Class.forName(driver);//建议写上去

        //2、得到连接
        Connection connection = DriverManager.getConnection(url, user, password);
        //3、得到 PreparedStatement
        //3.1 组织 sql，sql 语句的 ? 就相当于占位符
        String sql = "select * from stu_info where stu_name = ? and password = ?";
        //String sql = "insert into stu_info values(?, ?)";
        //String sql = "update stu_info set password = ? where stu_name = ?";
        //3.2 preparedStatement 对象实现了 PreparedStatement 接口的实现类的对象
        PreparedStatement preparedStatement = connection.prepareStatement(sql);
        //3.3 给 ? 赋值
        preparedStatement.setString(1,admin_name);
        preparedStatement.setString(2,admin_pwd);

        //4、执行 select 语句使用 executeQuery
        //   如果执行的是 dml(update, insert, delete) executeUpdate()
        //   这里执行 executeQuery，不要在写 sql
        ResultSet resultSet = preparedStatement.executeQuery();
        //int rows = preparedStatement.executeUpdate();
        if (resultSet.next()){
            System.out.println("恭喜，登陆成功");
        }else{
            System.out.println("对不起，登录失败");
        }
        //System.out.println(rows > 0 ? "执行成功" : "执行失败");

        //5、关闭连接
        resultSet.close();
        preparedStatement.close();
        connection.close();
    }
}
```



## JDBC 的相关 API 小结

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC的相关API小结.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC的相关API小结续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\JDBC的相关API小结续续.png)



## 封装 JDBCUtils

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\封装JDBCUtils.png)

JDBCUtils.java（twentyFive.utils）

```java
package twentyFive.utils;

import java.io.FileInputStream;
import java.io.IOException;
import java.io.InputStreamReader;
import java.sql.*;
import java.util.Properties;

public class JDBCUtils {
    //定义相关的属性（4个），因为只需要一份，因此，我们做出 static
    private static String user;//用户名
    private static String password;//密码
    private static String url;//url
    private static String driver;//驱动名

    //在static代码块去初始化
    static{
        try {
            Properties properties = new Properties();
            properties.load(new FileInputStream("src\\twentyFive\\mysql.properties"));
            //读取相关的属性值
            user = properties.getProperty("user");
            password = properties.getProperty("password");
            url = properties.getProperty("url");
            driver = properties.getProperty("driver");
        } catch (IOException e) {
            //在实际开发中，我们可以这样处理
            //1、将编译异常转成运行异常
            //2、这是调用者，可以选择捕获该异常，也可以选择默认处理该异常，比较方便
            throw new RuntimeException(e);
        }
    }

    //连接数据库，返回 Connection
    public static Connection getConnection(){
        try {
            return DriverManager.getConnection(url, user, password);
        } catch (SQLException e) {
            //1、将编译异常转成运行异常
            //2、这是调用者，可以选择捕获该异常，也可以选择默认处理该异常，比较方便
            throw new RuntimeException(e);
        }
    }
    //关闭相关资源
    /*
    1、ResultSet 结果集
    2、Statement 或者 PreparedStatement
    3、Connection
    4、如果需要关闭资源，就传入，否则传入 null
     */
    public static void close(ResultSet set, Statement statement, Connection connection){
        //判断是否为 null
        try {
            if(set != null){
                set.close();
            }
            if (statement != null){
                statement.close();
            }
            if(connection != null){
                connection.close();
            }
        } catch(SQLException e) {
            //将编译异常转成运行异常输出
            throw new RuntimeException(e);
        }
    }
}
```



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\封装JDBCUtils续.png)

JDBCUtils_Use.java（twentyFive.utils）

```java
package twentyFive.utils;

import org.junit.jupiter.api.Test;
import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class JDBCUtils_Use {
    @Test
    public void testDML(){//insert , update , delete
        //1、得到连接
        Connection connection = JDBCUtils.getConnection();
        //2、组织一个sql
        String sql = "update stu_info set stu_name = ? where stu_id = ?";
        //3、创建 PreparedStatement 对象
        PreparedStatement preparedStatement = null;
        try {
            preparedStatement = connection.prepareStatement(sql);
            //给占位符赋值
            preparedStatement.setString(1,"周星驰");
            preparedStatement.setInt(2,1);
            //执行
            preparedStatement.executeUpdate();
        } catch (SQLException e) {
            e.printStackTrace();
        }finally{
            //关闭资源
            JDBCUtils.close(null, preparedStatement, connection);
        }
    }
    @Test
    public void testSelect(){
        //1、得到连接
        Connection connection = null;
        //2、组织一个sql
        String sql = "select stu_id,stu_name from stu_info";
        //3、创建 PreparedStatement 对象
        PreparedStatement preparedStatement = null;
        ResultSet set = null;
        try {
            connection = JDBCUtils.getConnection();
            preparedStatement = connection.prepareStatement(sql);
            //执行,得到结果集
            set = preparedStatement.executeQuery();
            //遍历该结果
            while(set.next()){
                int id = set.getInt("stu_id");
                String name = set.getString("stu_name");
                System.out.println(id + "\t" + name);
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }finally{
            //关闭资源
            JDBCUtils.close(null, preparedStatement, connection);
        }
    }
}
```



## 事务

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\事务基本介绍.png)

### 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\事务应用实例.png)

### 适用场景

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\事务的运行场景.png)

Transaction_.java（twentyFive.transaction）

```java
package twentyFive.transaction;

import org.junit.jupiter.api.Test;
import twentyFive.utils.JDBCUtils;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class Transaction_ {
    @Test
    public void noTransaction(){
        //1、得到连接
        Connection connection = null;
        //2、组织一个sql
        String sql1 = "update stu_info set account = account - 100 where stu_id = 1";
        String sql2 = "update stu_info set account = account + 100 where stu_id = 11";
        //3、创建 PreparedStatement 对象
        PreparedStatement preparedStatement = null;
        try {
            connection = JDBCUtils.getConnection();
            //将 connection 设置不自动自动提交
            connection.setAutoCommit(false);//开启了事务
            preparedStatement = connection.prepareStatement(sql1);
            preparedStatement.executeUpdate();//执行第一条sql
            //int i = 1 / 0;//抛出异常
            preparedStatement = connection.prepareStatement(sql2);
            preparedStatement.executeUpdate();//执行第二条sql

            //这里提交事务
            connection.commit();

        } catch (SQLException e) {
            //这里我么可以进行回滚，即撤销执行的sql
            //默认回滚到事务开始状态
            System.out.println("执行发生了异常，撤销执行的sql");
            try {
                connection.rollback();
            } catch (SQLException ex) {
                ex.printStackTrace();
            }
            e.printStackTrace();
        }finally{
            //关闭资源
            JDBCUtils.close(null, preparedStatement, connection);
        }
    }
}
```



## 批处理

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\批处理基本介绍.png)

### 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\批处理应用实例.png)

Batch_.java（twentyFive.transaction）

```java
package twentyFive.transaction;

import org.junit.jupiter.api.Test;
import twentyFive.utils.JDBCUtils;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLException;

public class Batch_ {
    //传统的方式，添加5000条记录到 stu_info
    @Test
    public void noBatch() throws Exception{
        //1、得到连接
        Connection connection = JDBCUtils.getConnection();
        //2、组织一个sql
        String sql = "insert into stu_info values(null, ?, ?, null, ?, null, ?)";
        //3、创建 PreparedStatement 对象
        PreparedStatement preparedStatement = connection.prepareStatement(sql);
        System.out.println("开始执行");
        long start = System.currentTimeMillis();
        for (int i = 0; i < 5000; i++) {//执行5000次
            //给占位符赋值
            preparedStatement.setString(1,"jack" + i);
            preparedStatement.setString(2,"123456");
            preparedStatement.setString(3,"湛江市");
            preparedStatement.setInt(4,1000);
            //执行
            preparedStatement.executeUpdate();
        }
        long end = System.currentTimeMillis();
        System.out.println("传统的方式耗时：" + (end - start));//15748
        //关闭资源
        JDBCUtils.close(null, preparedStatement, connection);
    }
    //批处理的方式，添加5000条记录到 stu_info
    @Test
    public void batch() throws Exception{
        //1、得到连接
        Connection connection = JDBCUtils.getConnection();
        //2、组织一个sql
        String sql = "insert into stu_info values(null, ?, ?, null, ?, null, ?)";
        //3、创建 PreparedStatement 对象
        PreparedStatement preparedStatement = connection.prepareStatement(sql);
        System.out.println("开始执行");
        long start = System.currentTimeMillis();
        for (int i = 0; i < 100; i++) {//执行5000次
            //给占位符赋值
            preparedStatement.setString(1,"jack" + i);
            preparedStatement.setString(2,"123456");
            preparedStatement.setString(3,"湛江市");
            preparedStatement.setInt(4,1000);
            //将 sql 语句加入到批处理包中 -> 看源码
            preparedStatement.addBatch();
            //当有 1000 条记录时，在批量执行
            if((i + 1) % 10 == 0){//满1000条sql
                preparedStatement.executeBatch();
                //清空一把
                preparedStatement.clearBatch();
            }
        }
        long end = System.currentTimeMillis();
        System.out.println("批处理的方式耗时：" + (end - start));//179
        //关闭资源
        JDBCUtils.close(null, preparedStatement, connection);
    }
    //将 sql 语句加入到批处理包中 -> 看源码
    /*
    1、第一就创建 ArrayList - elementData => Object[]
    2、elementData => Object[] 就会存放我们预处理的sql语句
    3、当 elementData 满后，就按照1.5扩容
    4、当添加到指定的值后，就 executeBatch
    5、批量处理会减少我们发送sql语句的网络开销，而且减少编译次数，因此效率提高
        public void addBatch(String sql) throws SQLException {
            try {
                synchronized(this.checkClosed().getConnectionMutex()) {
                    this.batchHasPlainStatements = true;
                    super.addBatch(sql);
                }
            } catch (CJException var6) {
                throw SQLExceptionsMapping.translateException(var6, this.getExceptionInterceptor());
            }
        }
     */
}
```



## 数据库连接池

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库连接池.png)

ConQuestion.java（twentyFive.datasource）

```java
@Test
    public void testCon(){
        //看看连接-关闭 connection 会耗用多久
        long start = System.currentTimeMillis();
        for (int i = 0; i < 100; i++) {//执行5000次
            //使用传统的 jdbc 方式，得到连接
            Connection connection = JDBCUtils.getConnection();
            //做一些工作，比如得到 PreparedStatement，发送sql
            //......
            //关闭
            JDBCUtils.close(null, null, connection);
        }
        long end = System.currentTimeMillis();
        System.out.println("传统方式耗时：" + (end - start));
    }
```



### 传统获取Connection问题分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\传统获取Connection问题分析.png)



### 数据库连接池基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库连接池基本介绍.png)



### 数据库连接池示意图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库连接池示意图.png)



### 数据库连接池种类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库连接池种类.png)



### 数据库连接池 C3P0 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库连接池C3P0应用实例.png)

C3P0_.java（twentyFive.datasource）

```java
package twentyFive.datasource;

import com.mchange.v2.c3p0.ComboPooledDataSource;
import org.junit.jupiter.api.Test;
import twentyFive.utils.JDBCUtils;

import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.SQLException;
import java.util.Properties;

public class C3P0_ {
    //方式一：相关参数，在程序中指定user，url，password等
    @Test
    public void testC3P0_01() throws Exception{
        //1、创建一个数据源对象
        ComboPooledDataSource comboPooledDataSource = new ComboPooledDataSource();
        //2、通过配置文件 mysql.properties 获取相关连接的信息
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\twentyFive\\jdbc\\mysql.properties"));
        //读取相关的属性值
        String user = properties.getProperty("user");
        String password = properties.getProperty("password");
        String url = properties.getProperty("url");
        String driver = properties.getProperty("driver");
        //给数据源 comboPooledDataSource 设置相关的参数
        //注意：连管理是由 comboPooledDataSource 来管理
        comboPooledDataSource.setDriverClass(driver);
        comboPooledDataSource.setJdbcUrl(url);
        comboPooledDataSource.setUser(user);
        comboPooledDataSource.setPassword(password);
        //设置初始化连接数
        comboPooledDataSource.setInitialPoolSize(10);
        //最大连接数
        comboPooledDataSource.setMaxPoolSize(50);
        //测试连接池的效率，测试对 mysql 5000 次操作
        long start = System.currentTimeMillis();
        for (int i = 0; i < 5000; i++) {//执行5000次
            //使用 c3p0 的 jdbc 方式，得到连接
            Connection connection = comboPooledDataSource.getConnection();
            //System.out.println("连接OK~~");
            connection.close();
        }
        long end = System.currentTimeMillis();
        System.out.println("C3P0 5000次连接 mysql耗时：" + (end - start));//801
    }

    //第二种方式：使用配置文件模板来完成
    //1、将 c3p0 提供的 c3p0.config.xml 拷贝到 src 目录下
    //2、该文件指定了连接数据库和连接池的相关参数
    @Test
    public void testC3P0_02() throws SQLException{
        ComboPooledDataSource comboPooledDataSource = new ComboPooledDataSource("c3p0");
        //测试连接池的效率，测试对 mysql 5000 次操作
        System.out.println("开始执行...");
        long start = System.currentTimeMillis();
        for (int i = 0; i < 5000; i++) {//执行5000次
            //使用 c3p0 的 jdbc 方式，得到连接
            Connection connection = comboPooledDataSource.getConnection();
            //System.out.println("连接OK~~");
            connection.close();
        }
        long end = System.currentTimeMillis();
        System.out.println("C3P0的第二种方式 5000次连接 mysql耗时：" + (end - start));//836
    }
}
```



### Druid 德鲁伊应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库连接池Druid德鲁伊应用实例.png)

Druid_.java（twentyFive.datasource）

```java
package twentyFive.datasource;

import com.alibaba.druid.pool.DruidDataSource;
import com.alibaba.druid.pool.DruidDataSourceFactory;
import org.junit.jupiter.api.Test;

import javax.sql.DataSource;
import java.io.FileInputStream;
import java.io.IOException;
import java.sql.Connection;
import java.util.Properties;

public class Druid_ {
    @Test
    public void testDruid() throws Exception {
        //1、加入 Druid jar包
        //2、加入 配置文件 druid.properties，将该文件拷贝项目的 src 目录
        //3、创建 Properties 对象，读取配置文件
        Properties properties = new Properties();
        properties.load(new FileInputStream("src\\druid.properties"));

        //4、创建一个指定参数的数据库连接池，Druid 连接池
        DataSource dataSource = DruidDataSourceFactory.createDataSource(properties);

        System.out.println("开始执行...");
        long start = System.currentTimeMillis();
        for (int i = 0; i < 5000; i++) {//执行5000次
            //使用 c3p0 的 jdbc 方式，得到连接
            Connection connection = dataSource.getConnection();
            //System.out.println("连接OK~~");
            connection.close();
        }
        long end = System.currentTimeMillis();
        System.out.println("druid连接池 5000次连接 mysql耗时：" + (end - start));

    }
}
```



### 将 JDBCUtils 工具类改成 Druid 德鲁伊实现

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\数据库连接池将JDBCUtils工具类改成Druid德鲁伊实现.png)

JDBCUtilsByDruid.java（twentyFive.datasource）

```java
package twentyFive.datasource;

import com.alibaba.druid.pool.DruidDataSourceFactory;

import javax.sql.DataSource;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Properties;

public class JDBCUtilsByDruid {
    private static DataSource ds;

    //静态代码块完成 ds 初始化
    static{
        Properties properties = new Properties();
        try {
            properties.load(new FileInputStream("src\\druid.properties"));
            ds = DruidDataSourceFactory.createDataSource(properties);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
    //编写 getConnection 方法
    public static Connection getConnection() throws SQLException{
        return ds.getConnection();
    }

    //关闭连接，强调：在数据库连接池技术中，close 不是真的断掉连接
    //而是把使用的 Connection 对象放回连接池
    public static void close(ResultSet resultSet, Statement statement, Connection connection){
        try {
            if(resultSet != null){
                resultSet.close();
            }
            if (statement != null){
                statement.close();
            }
            if (connection != null){
                connection.close();
            }
        } catch (SQLException e) {
            throw new RuntimeException(e);
        }
    }
}
```



JDBCUtilsByDruid_USE.java（twentyFive.datasource）

```java
package twentyFive.datasource;

import org.junit.jupiter.api.Test;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;

public class JDBCUtilsByDruid_USE {
    @Test
    public void testSelect(){
        System.out.println("使用 druid 方式完成");
        //1、得到连接
        Connection connection = null;
        //2、组织一个 sql
        String sql = "select stu_id,stu_name,address from stu_info where stu_id = ?";
        PreparedStatement preparedStatement = null;
        ResultSet set = null;
        //3、创建 PreparedStatement 对象
        try {
            connection = JDBCUtilsByDruid.getConnection();
            System.out.println(connection.getClass());
            preparedStatement = connection.prepareStatement(sql);
            preparedStatement.setInt(1,1);
            //执行，得到结果集
            set = preparedStatement.executeQuery();
            //遍历该结果集
            while(set.next()){
                int id = set.getInt("stu_id");
                String name = set.getString("stu_name");
                String address = set.getString("address");
                System.out.println(id + "\t\t" + name + "\t\t" + address);
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }finally{
            //关闭资源
            JDBCUtilsByDruid.close(set, preparedStatement, connection);
        }
    }
}
```



## Apache - DBUtils

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Apache-DBUtils.png)

![]()![Apache-DBUtils图解](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Apache-DBUtils图解.png)

JDBCUtilsByDruid_USE.java（twentyFive.datasource）

```java
public ArrayList<Student> testSelectToArrayList(){
        System.out.println("使用 druid 方式完成");
        //1、得到连接
        Connection connection = null;
        //2、组织一个 sql
        String sql = "select * from stu_info";
        PreparedStatement preparedStatement = null;
        ResultSet set = null;
        ArrayList<Student> list = new ArrayList<>();//创建ArrayList对象，存放student对象
        //3、创建 PreparedStatement 对象
        try {
            connection = JDBCUtilsByDruid.getConnection();
            System.out.println(connection.getClass());
            preparedStatement = connection.prepareStatement(sql);
            //执行，得到结果集
            set = preparedStatement.executeQuery();
            //遍历该结果集
            while(set.next()){
                int id = set.getInt("stu_id");
                String name = set.getString("stu_name");
                String address = set.getString("address");
                Date createTime = set.getDate("createtime");
                String password = set.getString("password");
                String email = set.getString("email");
                int account = set.getInt("account");
                System.out.println(id + "\t\t" + name + "\t\t" + address);
                //把得到的resultSet的记录，封装到 Student 对象，放入到 list 集合
                list.add(new Student(id, name, password, createTime, email, address, account));
            }
            System.out.println("list集合：" + list);
        } catch (SQLException e) {
            e.printStackTrace();
        }finally{
            //关闭资源
            JDBCUtilsByDruid.close(set, preparedStatement, connection);
        }
        //因为 ArrayList 和 connection 么有关联，所以该集合可以复用
        return list;
    }
```



### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Apache-DBUtils基本介绍.png)



### 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Apache-DBUtils应用实例.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Apache-DBUtils应用实例续.png)

DBUtils_USE.java（twentyFive.ApacheDBUtils）

```java
package twentyFive.ApacheDBUtils;

import com.mysql.cj.QueryResult;
import org.apache.commons.dbutils.QueryRunner;
import org.apache.commons.dbutils.handlers.BeanHandler;
import org.apache.commons.dbutils.handlers.BeanListHandler;
import org.apache.commons.dbutils.handlers.ScalarHandler;
import org.junit.jupiter.api.Test;
import twentyFive.datasource.JDBCUtilsByDruid;
import twentyFive.datasource.Student;

import java.sql.Connection;
import java.sql.SQLException;
import java.util.List;

public class DBUtils_USE {
    //使用 Apache-DBUtils 工具类 + druid 完成对表的 crud 操作
    @Test
    public void testQueryMany() throws SQLException{//返回结果是多行的情况
        //1、得到连接（druid）
        Connection connection = JDBCUtilsByDruid.getConnection();
        //2、使用 DBUtils 类和接口，先引入 DBUtils 相关的 jar，加入到 Project
        //3、创建 QueryRunner
        QueryRunner queryRunner = new QueryRunner();
        //4、就可以执行相关的方法，返回 ArrayList 结果集
        //   注意：sql 语句也可以查询部分列
        String sql = "select * from stu_info where stu_id >= ?";
        //(1) query 方法就是执行 sql 语句，得到 resultSet --- 封装 ---> ArrayList 集合中
        //(2) 返回集合
        //(3) connection：连接
        //(4)sql：执行的 sql 语句
        //(5) new BeanListHandler<>(Student.class)：在将 resultSet -> Student 对象 -> 封装到 ArrayList
        List<Student> list = queryRunner.query(connection, sql, new BeanListHandler<>(Student.class), 1);
        System.out.println("输出集合的信息：");
        for (Student student : list){
            System.out.println(student);
        }
        //释放资源
        JDBCUtilsByDruid.close(null, null, connection);
    }
    /**
     * private <T> T query(Connection conn, boolean closeConn, String sql, ResultSetHandler<T> rsh, Object... params) throws SQLException {
     *         if (conn == null) {
     *             throw new SQLException("Null connection");
     *         } else if (sql == null) {
     *             if (closeConn) {
     *                 this.close(conn);
     *             }
     *
     *             throw new SQLException("Null SQL statement");
     *         } else if (rsh == null) {
     *             if (closeConn) {
     *                 this.close(conn);
     *             }
     *
     *             throw new SQLException("Null ResultSetHandler");
     *         } else {
     *             PreparedStatement stmt = null;//定义 PreparedStatement
     *             ResultSet rs = null;//接收返回的 ResultSet
     *             Object result = null;//返回 ArrayList
     *
     *             try {
     *                 stmt = this.prepareStatement(conn, sql);//创建 PreparedStatement
     *                 this.fillStatement(stmt, params);//对 sql 进行 ? 赋值
     *                 rs = this.wrap(stmt.executeQuery());//执行 sql，返回 resultSet
     *                 result = rsh.handle(rs);//返回的 resultSet --> arrayList[result][使用到反射，对传入class对象处理]
     *             } catch (SQLException var33) {
     *                 this.rethrow(var33, sql, params);
     *             } finally {
     *                 try {
     *                     this.close(rs);
     *                 } finally {
     *                     this.close(stmt);
     *                     if (closeConn) {
     *                         this.close(conn);//关闭 preparedstatement 对象
     *                     }
     *
     *                 }
     *             }
     *
     *             return result;
     *         }
     *     }
     */
    @Test
    public void testQuerySingle() throws SQLException{//返回结果是多行的情况
        //1、得到连接（druid）
        Connection connection = JDBCUtilsByDruid.getConnection();
        //2、使用 DBUtils 类和接口，先引入 DBUtils 相关的 jar，加入到 Project
        //3、创建 QueryRunner
        QueryRunner queryRunner = new QueryRunner();
        //4、就可以执行相关的方法，返回单个对象
        //   注意：sql 语句也可以查询部分列
        String sql = "select * from stu_info where stu_id = ?";
        Student student = queryRunner.query(connection, sql, new BeanHandler<>(Student.class), 11);
        System.out.println(student);
        //释放资源
        JDBCUtilsByDruid.close(null, null, connection);
    }

    //使用 Apache-DBUtils 工具类 + druid 完成查询结果是单行单列-返回的就是object
    @Test
    public void testScalar() throws SQLException{//返回结果是多行的情况
        //1、得到连接（druid）
        Connection connection = JDBCUtilsByDruid.getConnection();
        //2、使用 DBUtils 类和接口，先引入 DBUtils 相关的 jar，加入到 Project
        //3、创建 QueryRunner
        QueryRunner queryRunner = new QueryRunner();
        //4、就可以执行相关的方法，返回单行单列，返回的就是 Object
        String sql = "select count(*) from stu_info";
        Object obj = queryRunner.query(connection, sql, new ScalarHandler<>());
        System.out.println(obj);
        //释放资源
        JDBCUtilsByDruid.close(null, null, connection);
    }

    //使用 Apache-DBUtils 工具类 + druid 完成DML（update，insert，delete）
    @Test
    public void testDML() throws SQLException{//返回结果是多行的情况
        //1、得到连接（druid）
        Connection connection = JDBCUtilsByDruid.getConnection();
        //2、使用 DBUtils 类和接口，先引入 DBUtils 相关的 jar，加入到 Project
        //3、创建 QueryRunner
        QueryRunner queryRunner = new QueryRunner();
        //4、就可以执行相关的方法，完成 update，insert，delete
        String sql = "update stu_info set stu_name = ? where stu_id = ?";
        //String sql = "delete from stu_info where stu_id = ?";
        //String sql = "insert into stu_info values(null, ?, ?, ?, ?, ?, ?)";

        //(1) 执行 dml 操作是 queryRunner.update()
        //(2) 返回的值是受影响的行数（affected：受影响）
        int affectedRow = queryRunner.update(connection, sql, "张三丰", 1);
        System.out.println(affectedRow > 0 ? "执行成功" : "执行没有影响列表");
        //释放资源
        JDBCUtilsByDruid.close(null, null, connection);
    }
}
```



### 表和 JavaBean 的类型映射关系

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Apache-DBUtils表和javaBean的类型映射关系.png)



## DAO 和增删改查通用方法 - BasicDao

### 先分析一个问题

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\DAO和增删改查通用方法-BasicDao.png)

### 基本说明

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\DAO和增删改查通用方法-BasicDao基本说明.png)

### 应用实例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\DAO和增删改查通用方法-BasicDao应用实例.png)

BasicDao.java（twentyFive.dao）

```java
package twentyFive.dao;

import org.apache.commons.dbutils.QueryRunner;
import org.apache.commons.dbutils.handlers.BeanListHandler;
import org.apache.commons.dbutils.handlers.ScalarHandler;
import twentyFive.datasource.JDBCUtilsByDruid;

import java.sql.Connection;
import java.sql.SQLException;
import java.util.List;

public class BasicDao<T>{//泛型指定具体类型
    private QueryRunner qr = new QueryRunner();

    //开发通用的 dml 方法，针对任意的表
    /**
     *
     * @param sql sql语句，可以有 ?
     * @param parameters 传入 ? 的具体的值，可以是多个
     * @return 根据 Student.class 返回对应的 ArrayList 集合
     */
    public int update(String sql, Object... parameters){
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            int update = qr.update(connection, sql, parameters);
            return update;
        } catch (SQLException e) {
            throw new RuntimeException(e);//将编译异常->运行异常，抛出
        }finally{
            JDBCUtilsByDruid.close(null, null, connection);
        }
    }

    /**
     *
     * @param sql sql语句，可以有 ?
     * @param clazz 传入一个类的 Class 对象，比如 Student.class
     * @param parameters 传入 ? 的具体的值，可以是多个
     * @return 根据 Student.class 返回对应的 ArrayList 集合
     */
    public List<T> queryMuti(String sql, Class<T> clazz, Object... parameters){
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection, sql, new BeanListHandler<>(clazz), parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);//将编译异常->运行异常，抛出
        } finally {
            JDBCUtilsByDruid.close(null, null, connection);
        }
    }
    //查询单行结果的通用方法
    public List<T> querySingle(String sql, Class<T> clazz, Object... parameters){
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection, sql, new BeanListHandler<>(clazz), parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);//将编译异常->运行异常，抛出
        } finally {
            JDBCUtilsByDruid.close(null, null, connection);
        }
    }
    //查询单行单列结果的通用方法，返回单值结果
    public Object queryScalar(String sql, Object... parameters){
        Connection connection = null;
        try {
            connection = JDBCUtilsByDruid.getConnection();
            return qr.query(connection, sql, new ScalarHandler(), parameters);
        } catch (SQLException e) {
            throw new RuntimeException(e);//将编译异常->运行异常，抛出
        } finally {
            JDBCUtilsByDruid.close(null, null, connection);
        }
    }
}
```



TestDao.java（twentyFive.dao）

```java
package twentyFive.dao;

import org.junit.jupiter.api.Test;
import twentyFive.datasource.Student;

import java.util.List;

public class TestDao {
    //测试 StudentDao 对 student 表 crud 操作
    @Test
    public void testStudentDao(){
        StudentDao studentDao = new StudentDao();
        //1、查询多行记录
        List<Student> students = studentDao.queryMulti("select * from stu_info where stu_id >= ?", Student.class, 1);
        System.out.println("====查询结果====");
        for (Student student : students){
            System.out.println(student);
        }

        //2、查询单行记录
        Student student = studentDao.querySingle("select * from stu_info where stu_id = ?", Student.class, 1);
        System.out.println("====查询结果====");
        System.out.println(student);

        //3、查询单行单列
        Object o = studentDao.queryScalar("select count(*) from stu_info");
        System.out.println("====查询结果====");
        System.out.println(o);

        //4、dml操作，insert，update，delete
        int affectedRow = studentDao.update("insert into stu_info values(null,?,?,?,?,?,?)", "smith", "123456", "2021-09-21 10:25:20", "1911531@qq.com", "湛江市", 21000);
        System.out.println(affectedRow > 0 ? "执行成功" : "执行没有影响列表");
    }
}
```



## 整体结构分析图

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\整体结构分析图续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\整体结构分析图.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\整体结构分析图续.png)





# 第二十六章       满汉楼



# 第二十七章       正则表达式（regular expression）



## 为什么要学习正则表达式

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\为什么要学习正则表达式.png)

Regexp_.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Regexp_ {
    public static void main(String[] args) {
        //假定，编写了爬虫，从百度页面得到如下文本
        String content = "20世纪90年代，硬件领域出现了单片式计算机系统，" +
                "这种价格低廉的系统一出现就立即引起了自动控制领域人员的注" +
                "意，因为使用它可以大幅度提升消费类电子产品（如电视机顶盒、" +
                "面包烤箱、移动电话等）的智能化程度。Sun公司为了抢占市场" +
                "先机，在1991年成立了一个称为Green的项目小组，帕特里克、" +
                "詹姆斯·高斯林、麦克·舍林丹和其他几个工程师一起组成的工作" +
                "小组在加利福尼亚州门洛帕克市沙丘路的一个小工作室里面研究" +
                "开发新技术，专攻计算机在家电产品上的嵌入式应用。由于C++所" +
                "具有的优势，该项目组的研究人员首先考虑采用C++来编写程序。" +
                "但对于硬件资源极其匮乏的单片式系统来说，C++程序过于复杂和" +
                "庞大。另外由于消费电子产品所采用的嵌入式处理器芯片的种类繁" +
                "杂，如何让编写的程序跨平台运行也是个难题。为了解决困难，他" +
                "们首先着眼于语言的开发，假设了一种结构简单、符合嵌入式应用" +
                "需要的硬件平台体系结构并为其制定了相应的规范，其中就定义了" +
                "这种硬件平台的二进制机器码指令系统（即后来成为“字节码”的指" +
                "令系统），以待语言开发成功后，能有半导体芯片生产商开发和生" +
                "产这种硬件平台。对于新语言的设计，Sun公司研发人员并没有开" +
                "发一种全新的语言，而是根据嵌入式软件的要求，对C++进行了改" +
                "造，去除了留在C++的一些不太实用及影响安全的成分，并结合嵌入" +
                "式系统的实时性要求，开发了一种称为Oak的面向对象语言。";


        //(1)传统方法，使用遍历方式，代码量大，效率不高
        //(2)正则表达式技术
        //1、先创建一个Pattern 对象，模式对象，可以理解成就是一个正则表达式对象
        //提取文章中所有的英文单词
        //Pattern pattern = Pattern.compile("[a-zA-Z]");
        //提取文章中所有的数字
        //Pattern pattern = Pattern.compile("[0-9]+");
        //提取文章中所有的英文单词和数字
        Pattern pattern = Pattern.compile("([0-9]+)|([a-zA-Z]+)");
        //2、创建一个匹配器对象
        //理解：就是 matcher 匹配器按照 pattern（模式/样式），到 content 文本中去匹配
        //找到就返回 true，否则就返回 false
        int no = 0;
        Matcher matcher = pattern.matcher(content);
        //3、可以开始循环匹配
//        while(matcher.find()){
//            //匹配内容，文本，放到 ，m.group(0)
//            System.out.println("找到：" + (++no) + " " + matcher.group(0));
//        }
        
        String content1 = "以下列出留用的内容私有地址\n" +
                "A类 10.0.0.0 -- 10.255.255.255\n" +
                "B类 172.16.0.0 -- 172.31.255.255\n" +
                "C类 192.168.0.0 -- 192.168.255.255";
        Pattern pattern1 = Pattern.compile("\\d+\\.\\d+\\.\\d+\\.\\d+");
        Matcher matcher1 = pattern1.matcher(content1);
        while(matcher1.find()){
            System.out.println("找到："+ (++no) + " " + matcher1.group(0));
        }

    }
}
```



### 学习正则表达式问题提出

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\学习正则表达式问题提出.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\学习正则表达式问题提出续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\学习正则表达式的引出.png)



## 正则表达式

### 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式基本介绍.png)



### 底层实现实例分析

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式底层实现.png)

RegTheory.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegTheory {
    public static void main(String[] args) {
        String content = "20世纪90年代，硬件领域出现了单片式计算机系统，" +
                "这种价格低廉的系统一出现就立即引起了自动控制领域人员的注" +
                "意，因为使用它可以大幅度提升消费类电子产品（如电视机顶盒、" +
                "面包烤箱、移动电话等）的智能化程度。Sun公司为了抢占市场" +
                "先机，在1991年成立了一个称为Green的项目小组，帕特里克、" +
                "詹姆斯·高斯林、麦克·舍林丹和其他几个工程师一起组成的工作" +
                "小组在加利福尼亚州门洛帕克市沙丘路的一个小工作室里面研究" +
                "开发新技术，专攻计算机在家电产品上的嵌入式应用。由于C++所" +
                "具有的优势，该项目组的研究人员首先考虑采用C++来编写程序。" +
                "但对于硬件资源极其匮乏的单片式系统来说，C++程序过于复杂和" +
                "庞大。";
        //目标：匹配所有的四个数字
        //说明
        //1、\\d 表示一个任意的数字
        String regStr = "(\\d\\d)(\\d\\d)";
        //2、创建模式对象
        Pattern pattern = Pattern.compile(regStr);
        //3、创建匹配器
        //说明：创建匹配器 matcher，按照正则表达式的规则去匹配 content 字符串
        Matcher matcher = pattern.matcher(content);
        //4、开始匹配
        /**
         * matcher.find() 完成的任务 （考虑分组）
         * 1、根据指定的规则，定位满足规则的子字符串（比如1991）
         * 2、找到后，将子字符串的开始的索引记录到 matcher 对象的属性 int[] groups;
         *    2.1 groups[0] = 0，把该子字符串的结束的索引+1的值记录到 groups[1] = 4
         *    2.2 记录 1 组()匹配到的字符串 groups[2] = 0 , groups[3] = 2
         *    2.3 记录 2 组()匹配到的字符串 groups[4] = 2 , groups[5] = 4
         *    2.4 如果有更多的分组......
         * 3、同时记录 oldLast 的值为子字符串的结束的索引+1的值即4，即下次执行 find 时，就从4开始匹配
         *
         * matcher.group(0) 分析
         *
         * 源码：
         * public String group(int group) {
         *         if (first < 0)
         *             throw new IllegalStateException("No match found");
         *         if (group < 0 || group > groupCount())
         *             throw new IndexOutOfBoundsException("No group " + group);
         *         if ((groups[group*2] == -1) || (groups[group*2+1] == -1))
         *             return null;
         *         return getSubSequence(groups[group * 2], groups[group * 2 + 1]).toString();
         *     }
         *  1、根据 groups[0] = 0 和 groups[1] = 4 的记录的位置，从 content 开始截取子字符串返回
         *     就是 [0,4) 包含 0 但是不包含索引为 4 的位置
         *
         */
        //小结
        //1、如果正则表达式有()即分组
        //2、取出匹配的字符串规则如下：
        //3、group(0) 表示匹配的子字符串
        //4、group(1) 表示匹配的子字符串的第一组字串
        //5、group(2) 表示匹配的子字符串的第二组字串
        //6、... 但是分组的数不能越界。
        //
        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
            System.out.println("第 1 组()匹配到的字符串的值：" + matcher.group(1));
            System.out.println("第 2 组()匹配到的字符串的值：" + matcher.group(2));
        }
    }
}
```





## 正则表达式语法

### 基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法基本介绍.png)



### 元字符-转义号

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-转义号.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式元字符-转义符续.png)

RegExp02.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp02 {
    public static void main(String[] args) {
        String content = "abc$(abc(123(";
        //匹配(
        String regStr = "\\(";
        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);
        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}
```



### 元字符-字符匹配符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-字符匹配符.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-字符匹配符续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-字符匹配符续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-字符匹配符续续续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-字符匹配符续续续续.png)

RegExp03.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp03 {
    public static void main(String[] args) {
        String content = "a11cBabcABC";
        //String regStr = "[a-z]";//匹配 a-z 之间任意一个字符
        //String regStr = "[A-Z]";//匹配 A-Z 之间任意一个字符
        //String regStr = "abc";//匹配 abc 字符串[默认区分大小写]
        //String regStr = "(?i)abc";//匹配 abc 字符串[不区分大小写]
        //String regStr = "[0-9]";//匹配 0-9 之间任意一个字符
        //String regStr = "[^a-z]";//匹配不在 a-z 之间任意一个字符
        //String regStr = "[^0-9]";//匹配不在 0-9 之间任意一个字符
        //String regStr = "[abcd]";//匹配在 abcd 中的任意一个字符
        //String regStr = "\\D";//匹配不在 0-9 中的任意一个字符
        //String regStr = "[\\w]";//匹配 大小写英文字母，数字，下划线
        //String regStr = "[\\W]";//匹配 等价于 [^a-zA-Z0-9_]
        //String regStr = "[\\s]";//匹配任何空白字符（空格，制表符等）
        String regStr = "[\\S]";//匹配任何非空白字符，和\\s刚好相反


        //当创建 Pattern 对象时，指定 Pattern.CASE_INSENSITIVE，表示匹配是不区分字母大小写
        Pattern pattern = Pattern.compile(regStr, Pattern.CASE_INSENSITIVE
        );
        Matcher matcher = pattern.matcher(content);

        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}
```



### 元字符-选择匹配符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-选择匹配符.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-选择匹配符续.png)

RegExp04.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp04 {
    public static void main(String[] args) {
        String content = "hanshunping 韩 寒冷";
        String regStr = "han|韩|寒";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}
```



### 元字符-限定符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-限定符.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-限定符续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-限定符续续.png)

RegExp05.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp05 {
    public static void main(String[] args) {
        String content = "1111111aaahello";
        //a{3},1{4},\\d{2}
        //String regStr = "a{3}";//表示匹配 aaa
        //String regStr = "1{4}";//表示匹配 1111
        //String regStr = "\\d{2}";//表示匹配两位的的任意数字字符

        //a{3,4},1{4,5},\\d{2,5}
        //细节：java匹配默认贪婪匹配，即尽可能匹配多的
        //String regStr = "a{3,4}";//表示匹配 aaa 或者 aaaa
        //String regStr = "1{4,5}";//表示匹配 1111 或者 11111
        //String regStr = "\\d{2,5}";//匹配两位数或者3，4，5位数

        //1+
        //String regStr = "1+";//匹配一个1或者多个1
        //String regStr = "\\d+";//匹配一个数字或者多个数字

        //1*
        //String regStr = "1*";//匹配0个1或者多个1

        //演示?的使用，遵守贪婪匹配
        String regStr = "a1?";//匹配 a 或者 a1


        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while(matcher.find()){
            System.out.println("找到 " + matcher.group(0));
        }
    }
}
```



### 元字符-定位符

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法元字符-定位符.png)

RegExp06.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp06 {
    public static void main(String[] args) {
        String content = "hanshunping sphan nnhan";
        //String content = "123abc12";
        //以至少1个数字开头，后接任意个小写字母的字符串
        ///String regStr = "^[0-9]+[a-z]*";
        //以至少1个数字开头，必须以至少一个小写字母结束
        //String regStr = "^[0-9]+[a-z]+$";

        //表示匹配边界的han[这里的边界指的是：
        //被匹配的字符串最后，也可以是空格的子字符串的后面]
        //String regStr = "han\\b";

        //和 \\b 的含义刚刚相反
        String regStr = "han\\B";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}
```



### 分组（常用分组）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法分组.png)

RegExp07.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp07 {
    public static void main(String[] args) {
        String content = "hanshunping s7789 nn1189han";

        //下面就是非命名分组
        //说明
        //1、matcher.group(0) 得到匹配到的字符串
        //2、matcher.gruop(1) 得到匹配的字符串的第1个分组内容
        //3、matcher.group(2) 得到匹配的字符串的第2个分组内容
        //一、通过
        String regStr = "(?<g1>\\d\\d)(?<g2>\\d\\d)";//匹配4个数组的字符串

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);

        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
            System.out.println("第1个分组内容：" + matcher.group(1));
            System.out.println("第1个分组内容[通过组名]：" + matcher.group("g1"));
            System.out.println("第2个分组内容：" + matcher.group(2));
            System.out.println("第2个分组内容[通过组名]：" + matcher.group("g2"));
        }
    }
}
```



### 分组（特殊分组）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法分组续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式语法分组续续.png)

RegExp08.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp08 {
    public static void main(String[] args) {
        String content = "hello韩顺平教育 jack韩顺平老师 韩顺平同学hello";
        //找到 韩顺平教育、韩顺平老师、韩顺平同学 子字符串
        //String regStr = "韩顺平教育|韩顺平老师|韩顺平同学";

        //上面的写法可以等价非捕获分组，注意：不能 matcher.group(1)
        //String regStr = "韩顺平(?:教育|老师|同学)";

        //找到 韩顺平 这个关键字，但是要求只是查找韩顺平教育和韩顺平老师中包含有的韩顺平
        //下面也是非捕获分组，不能使用 ，matcher.group(1)
        String regStr = "韩顺平(?=教育|老师)";

        //找到 韩顺平 这个关键字，但是要求只是查找 不是 (韩顺平教育和韩顺平老师) 中包含有的韩顺平
        //下面也是非捕获分组，不能使用 ，matcher.group(1)
        //String regStr = "韩顺平(?!教育|老师)";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);
        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}
```



### 更多元字符一览表

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式更多元字符一览表.png)

RegExp09.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp09 {
    public static void main(String[] args) {
        String content = "hello111111 ok";
        //String regStr = "\\d+";//默认是贪婪匹配
        String regStr = "\\d+?";//非贪婪匹配

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);
        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
    }
}
```



### 对进行如下验证

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式对进行如下验证.png)

RegExp10.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp10 {
    public static void main(String[] args) {
        String content = "韩顺平教育";
        //汉字
        //String regStr = "^[\u0391-\uffe5]";

        //邮政编码
        //要求：1、是1-9开头的一个六位数，比如：123890
        //     2、
        //     3、
        //String regStr = "^[1-9]\\d{5}$";

        //QQ号码
        //要求：是1-9开头的一个(5位数-10位数) 比如：12306，14852325
        //String regStr = "^[1-9]\\d{4,9}$";

        //手机号码
        //要求：必须以 13，14，15，18 开头的 11位数，比如 13547999999
        //String regStr = "^1[3|4|5|8]\\d{9}";

        String content1 = "https://www.bilibili.com/video/BV1fh411y7R8?p=881";
        /**
         * 1、先确定 url 的开始部分 https:// | http://
         * 2、然后通过 ([\w-]+\.)+[\w-]+ 匹配 www.bilibili.com
         * 3、/video/BV1fh411y7R8?p=881 匹配
         */
        //String regStr = "^((http|https)://)([\\w-]+\\.)+[\\w-]+(\\/[\\w-?=&/%.#]*)?$";//注意：[.]表示匹配就是，本身

        String content2 = "hello abc 11.1";
        //String regStr = "."//匹配除了 \n 的所有字符
        //String regStr = "[.]";//匹配 .本身
        String regStr = "\\.";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content2);
        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
        if (matcher.find()){
            System.out.println("满足格式");
        }else{
            System.out.println("不满足格式");
        }
    }
}
```



## 正则表达式三个常用类

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则表达式三个常用类.png)



### Pattern 类的方法 matchers

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则三个常用类Pattern类的方法matchers.png)

PatternMethod.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class PatternMethod {
    public static void main(String[] args) {
        String content = "hello abc hello, hanshunpingjiaoyu";
        //String regStr = "hello";
        String regStr = "hello.*";

        boolean matches = Pattern.matches(regStr, content);
        System.out.println("整体匹配：" + matches);
    }
}
```



### Matcher 类方法一览

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Matcher类方法一览.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Matcher类方法一览续.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\Matcher类方法应用实例.png)

MatcherMethod.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class MatcherMethod {
    public static void main(String[] args) {
        String content = "hello abc hello, hanshunpingjiaoyu";
        String regStr = "hello";

        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);
        while(matcher.find()){
            System.out.println("----------");
            System.out.println(matcher.start());
            System.out.println(matcher.end());
            System.out.println("找到：" + content.substring(matcher.start(), matcher.end()));
        }

        //整体匹配方法，常用于，去校验某个字符是否满足某个规则
        System.out.println("整体匹配：" + matcher.matches());
        //完成如果 content 有 hello 替换成 apple
        regStr = "hello";
        pattern = Pattern.compile(regStr);
        matcher = pattern.matcher(content);
        //注意：返回的字符串才是替换后的字符串，原来的 content 不变化
        String newContent = matcher.replaceAll("apple");
        System.out.println("newContent:" + newContent);
    }
}
```



## 分组、捕获、反向引用

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则分组捕获反向引用.png)

### 介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则分组捕获反向引用介绍.png)

### 案例

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\正则分组捕获反向引用案例.png)

RegExp12.java（twentySeven.regexp）

```java
package twentySeven.regexp;

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegExp12 {
    public static void main(String[] args) {
        String content = "h1234el9876lo33333 j12324-333999111a1551ck14 tom11 jack2345";
        //要匹配两个连接的相同数字：(\\d)\\1
        //String regStr = "(\\d)\\1";
        //要匹配五个连接的相同的数字：(\\d)\\1{4}
        //String regStr = "(\\d)\\1{4}";
        //要匹配个位与千位相同，十位与百位相同的数 3223，1551 (\\d)(\\d)\\2\\1
        //String regStr = "(\\d)(\\d)\\2\\1";

        /**
         * 请在字符串中检索商品编号，形式如 12321-333999111 这样的号码
         * 要求满足前面是五位数，然后一个“-”号，然后是一个就一个九位数，连续的每三位要相同
         */
        String regStr = "\\d{5}-(\\d)\\1{2}(\\d)\\2{2}(\\d)\\3{2}";
        Pattern pattern = Pattern.compile(regStr);
        Matcher matcher = pattern.matcher(content);
        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }

        //2、去掉重复的字，我我要学学学学学编程程java！
        String content1 = "我我要学学学学学编程程java！";
        //思路
        //(1) 使用 (.)\\1+
        //(2) 使用 反向引用 $1 来替换匹配到的内容
        //注意：因为正则表达式变化，所以需要重置 matcher
        pattern = Pattern.compile("(.)\\1+");//分组的捕获内容记录到 $1
        matcher = pattern.matcher(content1);
        while(matcher.find()){
            System.out.println("找到：" + matcher.group(0));
        }
        //使用 反向引用 $1 来替换匹配到的内容
        content1 = matcher.replaceAll("$1");
        System.out.println("content1：" + content1);

        //3、使用一条语句去掉重复的字
        content1 = Pattern.compile("(.)\\1+").matcher(content1).replaceAll("$1");
        System.out.println("content1：" + content1);
    }
}
```



## String 类中使用正则表达式

### 替换功能

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类中使用正则表达式替换功能.png)

### 判断功能

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类中使用正则表达式判断功能.png)

### 分割功能

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaSE_image\String类中使用正则表达式分割功能.png)

StringReg.java（twentySeven.regexp）

```java
package twentySeven.regexp;

public class StringReg {
    public static void main(String[] args) {
        String content = "1994年6、7月间，JDK1.3在经历了一场历时三天的讨论之后，" +
                "团队决定再一次改变了努力的目标，这次他们决定将该技术应用于万" +
                "维网。他们认为随着Mosaic浏览器的到来，因特网正在向同样的高度" +
                "互动的远景演变，而这一远景正是他们在有线电视网中看到的。JDK1.4作为原" +
                "型，帕特里克·诺顿写了一个小型万维网浏览器WebRunner。";
        //使用 正则表达式方式，将 JDK1.3 和 JDK1.4 替换成 JDK
        content = content.replaceAll("JDK1\\.3|JDK1\\.4","JDK");
        System.out.println(content);

        //要求 验证一个手机号，要求必须是以 138、139 开头的
        content = "13945722678";
        if (content.matches("1(38|39)\\d{8}")){
            System.out.println("验证成功");
        }else{
            System.out.println("验证失败");
        }

        //要求按照 # 或者 - 或者 ~ 或者 数字 来分割
        System.out.println("-------------");
        content = "hello#abc-jack~smith2324北京";
        String[] split = content.split("#|-|~|\\d+");
        for (String s : split){
            System.out.println(s);
        }
    }
}
```

