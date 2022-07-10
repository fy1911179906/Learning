# 1、Spring 框架概述



1、Spring 是轻量级的开源的 JavaEE 框架

2、Spring 可以解决企业应用开发的复杂性

3、Spring 有两个核心部分：IOC 和 Aop

（1）IOC：控制反转，把创建对象过程交给 Spring 进行管理

（2）：面向切面，不修改源代码进行功能增强

4、Spring 特点

（1）方便解耦，简化开发

（2）Aop 编程支持

（3）方便程序测试

（4）方便和其他框架进行整合

（5）方便进行事务操作

（6）降低 API 开发难度

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\Spring5模块.bmp)





**Spring5 入门案例**



**1、下载Spring5**

（1）使用 Spring 最新稳定版本 5.2.6

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\Spring依赖下载.png)

（2）下载地址

https://repo.spring.io/release/org/springframework/spring/

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\Spring依赖下载地址.png)



**2、打开idea工具，创建普通Java工程**

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\idea创建项目.png)



**3、导入Spring5相关jar包**

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\导入Spring5相关依赖.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\向模块导入依赖.png)



**4、创建普通类，在这个类创建普通方法**

```java
public class User {

 public void add() {

 System.out.println("add......");

 	} 

}
```



**5、创建 Spring 配置文件，在配置文件配置创建的对象** 

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\创建xml配置文件.png)



（1）Spring 配置文件使用 xml 格式

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">

    <!--配置 User 对象创建-->
    <bean id="user" class="com.spring5_IOC.User"></bean>
</beans>
```



**6、进行测试代码编写**

```java
@Test

public void testAdd() {

 //1 加载 spring 配置文件

 ApplicationContext context =

 new ClassPathXmlApplicationContext("bean1.xml");

 //2 获取配置创建的对象

 User user = context.getBean("user", User.class);

 System.out.println(user);

 user.add();
```





# 2、IOC 容器



## IOC 的引出

原始方式和工厂模式



![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\图1.png)



# IOC 概念和原理

1、什么是 IOC

（1）控制反转，把对象创建和对象之间的调用过程，交给 Spring 进行管理

（2）使用 IOC 目的：为了耦合度降低

（3）做入门案例就是 IOC 实现

2、IOC 底层原理

（1）xml 解析、工厂模式、反射

3、画图讲解 IOC 底层原理

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\图2.png)



## IOC （接口）

1、IOC 思想基于 IOC 容器完成，IOC 容器底层就是对象工厂

2、Spring 提供 IOC 实现两种方式：（两个接口）

（1）BeanFactory：IOC 容器基本实现，是 Spring 内部的使用接口，不提供开发人员进行使用（*加载配置文件时候不会创建对象，在获取对象（使用）才去创建对象）

（2）ApplicationContext：BeanFactory 接口的子接口，提供更多更强大的功能，一般由开发人员进行使用（*加载配置文件时候就会把在配置文件对象进行创建）

3、ApplicationContext 接口有实现类：

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\ApplicationContext接口实现类.png)



## IOC 操作 Bean 管理

1、什么是 Bean 管理

Bean 管理指的是两个操作

（1）Spring 创建对象

（2）Spring 注入属性

2、Bean 管理操作两种方式

（1）基于 xml 配置文方式实现

（2）基于注解方式实现

### IOC 操作 Bean 管理（基于 xml 方式）

1、基于 xml 方式创建对象

```xml
<!--配置 User 对象创建-->
<bean id="user" class="com.atguigu.spring5.User"></bean>
```

（1）在 Spring 配置文件中，使用 bean 标签，标签里面添加对应属性，就可以实现对象创建

（2）在 bean 标签有很多属性，介绍常用的属性：

----- id 属性：唯一标识

----- class 属性：类全路径（包类路径）

（3）创建对象时侯，默认也是执行无参构造器方法完成对象创建

2、基于 xml 方式注入属性

（1）DI：依赖注入，就是注入属性

3、第一种注入方式：使用 set 方法进行注入

（1）创建类，定义属性和对应的 set 方法

```java
package com.spring5_IOC;

public class Book {
    //创建属性
    private String bname;
    private String bauthor;
    //创建属性对应的 set 方法

    public void setBname(String bname) {
        this.bname = bname;
    }

    public void setBauthor(String bauthor) {
        this.bauthor = bauthor;
    }

    public Book() {
    }

    @Override
    public String toString() {
        return "Book{" +
                "bname='" + bname + '\'' +
                ", bauthor='" + bauthor + '\'' +
                '}';
    }

    public static void main(String[] args) {
        Book book = new Book();
        book.setBname("abc");
    }
}
```



（2）在 Spring 配置文件对象创建，配置属性注入

```xml
<!--2、set 方法注入属性-->
<bean id="book" class="com.spring5_IOC.Book">
    <!-- 使用 property 完成属性注入
            name：类里面属性名称
            value：向属性注入的值
        -->
    <property name="bname" value="易筋经"></property>
    <property name="bauthor" value="少林"></property>
</bean>
```



4、第二种注入方法：使用有参数构造进行注入

（1）创建类，定义定义有参构造方法

```java
package com.spring5_IOC;

public class Orders {
    private String oname;
    private String address;

    public Orders(String oname, String address) {
        this.oname = oname;
        this.address = address;
    }
}
```



（2）在 Spring 配置文件中进行配置

```xml
<!-- 3、有参数构造注入属性-->
    <bean id="orders" class="com.spring5_IOC.Orders">
        <constructor-arg name="oname" value="电脑"></constructor-arg>
        <constructor-arg name="address" value="China"></constructor-arg>
        <!-- 使用 index 属性注入-->
<!--        <constructor-arg index="0" value="手机"></constructor-arg>-->
<!--        <constructor-arg index="1" value="USE"></constructor-arg>-->
    </bean>
```



5、p 名称空间注入（了解）

（1）使用 p 名称空间注入，可以简化基于 xml 配置方式

第一步：添加 p 名称空间在配置文件中

```xml
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       <!-- 添加 p 名称空间在配置文件中 -->
       xmlns:p="http://www.springframework.org/schema/p"
       
      xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd">
```



第二步：进行属性注入，在 bean 标签里面进行操作

```xml
<!--2、set 方法注入属性-->
    <bean id="book" class="com.spring5_IOC.Book" p:bname="独孤九剑" p:bauthor="令狐冲"></bean>
```



### IOC 操作 Bean 管理（xml 注入其它类型的属性）

1、字面量

（1）null 值

```xml
<!-- null 值 -->
<property name="address">
    <null/>
</property>
```

（2）属性值包含特殊符号

```xml
<!--属性值包含特殊符号
            1、把（）进行转义
            2、把带特殊符号内容写到 CDATA
        -->
<property name="address">
    <value><![CDATA[<<南京>>]]></value>
</property>
```

2、注入属性 - 外部 bean

（1）创建两个类 service 类和 dao 类

```java
package com.spring5_IOC.service;

import com.spring5_IOC.dao.UserDAO;

public class UserService {
    //创建 UserDAO 类型属性，生成 set 方法
    private UserDAO userDAO;
    public void setUserDAO(UserDAO userDAO){
        this.userDAO = userDAO;
    }
    public void add(){
        System.out.println("service add......");
        userDAO.update();
    }
}
```



（2）在 service 调用 dao 里面方法

（3）在 Spring 配置文件中进行配置

```xml
<!-- service 和 dao 对象创建-->
    <bean id="userService" class="com.spring5_IOC.service.UserService">
        <!-- 注入 userDAO 对象
            name 属性：类里面属性名称
            ref 属性：创建 userDAO 对象 bean 标签 id 值
        -->
        <property name="userDAO" ref="userDAOImpl"></property>
    </bean>
    <bean id="userDAOImpl" class="com.spring5_IOC.dao.impl.UserDAOImpl"></bean>
```



3、注入属性 - 内部 bean

（1）一对多关系：部门和员工

一个部门有多个员工，一个员工属于一个部门。部门是一，员工是多。

（2）在实体类之间表示一对多关系，员工表示所属部门，使用对象类型属性进行表示

```java
package com.spring5_IOC.pojo;
//部门类
public class Dept {
    private String dname;

    public void setDname(String dname) {
        this.dname = dname;
    }
}
```

```java
package com.spring5_IOC.pojo;
//员工类
public class Emp {
    private String ename;
    private String gender;
    //员工属性某个部门，适用对象形式表示
    private Dept dept;

    public void setDept(Dept dept) {
        this.dept = dept;
    }

    public void setEname(String ename) {
        this.ename = ename;
    }

    public void setGender(String gender) {
        this.gender = gender;
    }
}
```

（3）在 Spring 配置文件中进行配置

```xml
<!-- 内部 bean-->
<bean id="emp" class="com.spring5_IOC.pojo.Emp">
    <!-- 设置两个普遍属性-->
    <property name="ename" value="lucy"></property>
    <property name="gender" value="女"></property>
    <!-- 设置对象类型属性-->
    <property name="dept">
        <bean id="dept" class="com.spring5_IOC.pojo.Dept">
            <property name="dname" value="安保部"></property>
        </bean>
    </property>
</bean>
```



4、注入属性 - 级联赋值

（1）第一种写法

```xml
<!-- 级联赋值-->
<bean id="emp" class="com.spring5_IOC.pojo.Emp">
    <!-- 设置两个普遍属性-->
    <property name="ename" value="lucy"></property>
    <property name="gender" value="女"></property>
    <!-- 级联赋值-->
    <property name="dept" ref="dept"></property>
</bean>
<bean id="dept" class="com.spring5_IOC.pojo.Dept">
    <property name="dname" value="安保部"></property>
</bean>
```



（2）第二种写法

```xml
<!-- 级联赋值-->
<bean id="emp" class="com.spring5_IOC.pojo.Emp">
    <!-- 设置两个普遍属性-->
    <property name="ename" value="lucy"></property>
    <property name="gender" value="女"></property>
    <!-- 级联赋值-->
    <property name="dept" ref="dept"></property>
    <property name="dept.dname" value="财务部"></property>
</bean>
<bean id="dept" class="com.spring5_IOC.pojo.Dept">
    <property name="dname" value="安保部"></property>
</bean>
```



### IOC 操作 Bean 管理（xml 注入集合属性）

1、注入数组类型属性

2、注入 List 集合类型属性

3、注入 Map 集合类型属性

（1）创建类，定义数组、list、map、set 类型属性，生成对应 set 方法

```java
package com.spring5_IOC.pojo;

import java.util.Arrays;
import java.util.List;
import java.util.Map;
import java.util.Set;

public class Stu {
    //1、数组类型属性
    private String[] courses;

    //2、list 集合类型属性
    private List<String> list;

    //3、map 集合类型属性
    private Map<String, String> maps;

    //4、set 集合类型属性
    private Set<String> sets;

    public void setSets(Set<String> sets) {
        this.sets = sets;
    }

    public void setCourses(String[] courses) {
        this.courses = courses;
    }

    public void setList(List<String> list) {
        this.list = list;
    }

    public void setMaps(Map<String, String> maps) {
        this.maps = maps;
    }

    @Override
    public String toString() {
        return "Stu{" +
                "courses=" + Arrays.toString(courses) +
                ", list=" + list +
                ", maps=" + maps +
                ", sets=" + sets +
                '}';
    }
}
```



（2）在 Spring 配置文件进行配置

```xml
<bean id="stu" class="com.spring5_IOC.pojo.Stu">
    <property name="courses">
        <!--数组类型属性注入-->
        <array>
            <value>Java 课程</value>
            <value>数据库课程</value>
        </array>
    </property>
    <!--list 类型属性注入-->
    <property name="list">
        <list>
            <value>smith</value>
            <value>mike</value>
        </list>
    </property>
    <!--map 类型属性注入-->
    <property name="maps">
        <map>
            <entry key="JAVA" value="java"></entry>
            <entry key="PHP" value="php"></entry>
        </map>
    </property>
    <!--set 类型属性注入-->
    <property name="sets">
        <set>
            <value>MySQL</value>
            <value>Redis</value>
        </set>
    </property>
</bean>
```



4、在集合里面设置对象类型值

```xml
<!--创建多个 course 对象-->
<bean id="course1" class="com.spring5_IOC.pojo.Course">
    <property name="cname" value="Spring框架"></property>
</bean>
<bean id="course2" class="com.spring5_IOC.pojo.Course">
    <property name="cname" value="MyBatis框架"></property>
</bean>

<!--注入 list 集合类型，值为对象-->
<bean id="stu" class="com.spring5_IOC.pojo.Stu">
    <property name="courseList">
        <list>
            <ref bean="course1"></ref>
            <ref bean="course2"></ref>
        </list>
    </property>
</bean>
```



5、把集合注入部分提取出来

（1）在 Spring 配置文件中引入名称空间 util

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:p="http://www.springframework.org/schema/p"
       xmlns:util="http://www.springframework.org/schema/util"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
                          http://www.springframework.org/schema/util http://www.springframework.org/schema/util/spring-util.xsd">
</beans>
```

（2）使用 util 标签完成 list 集合注入提取

```xml
<!--1、提取 list 集合类型属性注入-->
<util:list id="carList">
    <value>奥迪</value>
    <value>丰田</value>
    <value>宝马</value>
</util:list>
<!--2、提取 list 集合类型属性注入使用-->
<bean id="car" class="com.spring5_IOC.pojo.Car">
    <property name="carList" ref="carList"></property>
</bean>
```

```java
package com.spring5_IOC.pojo;
import java.util.List;

public class Car {
    private List<String> carList;

    public void setCarList(List<String> carList) {
        this.carList = carList;
    }
    public void test(){
        System.out.println(carList);
    }
}
```



### IOC 操作 Bean 管理（FactoryBean）

1、Spring 有两种类型 bean，一种普通 bean，另外一种工厂 bean（FactoryBean）

2、普通 bean：在配置文件中定义 bean 类型就是返回类型

3、工厂 bean：在配置文件定义 bean 类型可以和返回类型不一样

第一步：创建类，让这个类作为工厂 bean，实现接口 FactoryBean

```java
public class MyBean implements FactoryBean<Course> {
    //定义返回 bean
    @Override
    public Course getObject() throws Exception {
        Course course = new Course();
        course.setCname("abc");
        return course;
    }

    @Override
    public Class<?> getObjectType() {
        return null;
    }

    @Override
    public boolean isSingleton() {
        return FactoryBean.super.isSingleton();
    }
}
```



第二步：实现接口里面的方法，在实现的方法中定义返回的 bean 类型

```xml
<bean id="myBean" class="com.spring5_IOC.factorybean.MyBean">
    </bean>
```

```java
@Test
    public void testMyBean() {
        ApplicationContext context =
                new ClassPathXmlApplicationContext("bean5.xml");
        //返回的是 Course 类型
        Course course = context.getBean("myBean", Course.class);
        System.out.println(course);
    }
```



### IOC 操作 Bean 管理（bean 作用域）

1、在 Spring 里面，设置创建 bean 实例是单实例还是多实例

2、在 Spring 里面，默认情况下，bean 是单实例对象

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\bean作用域默认情况下是单实例.png)



3、如何设置单实例还是多实例

（1）在 Spring 配置文件 bean 标签里面有属性（scope）用于设置单实例还是多实例

（2）scope 属性值

第一个值：默认值，singleton，表示是单实例对象

第二个值：prototype，表示是多实例对象

```xml
<!--bean作用域设置为多实例，即设置scope属性为prototype-->
<bean id="car" class="com.spring5_IOC.pojo.Car" scope="prototype">
        <property name="carList" ref="carList"></property>
    </bean>
```

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\bean作用域设置为多实例prototype属性.png)



```java
@Test
public void testSingleCar(){
    //1、加载 Spring 配置文件
    ApplicationContext context = new ClassPathXmlApplicationContext("bean5.xml");
    //2、获取配置创建的对象
    Car car1 = context.getBean("car", Car.class);
    Car car2 = context.getBean("car", Car.class);
    System.out.println(car1);
    System.out.println(car2);
}
```



（3）singleton 和 prototype 区别

第一：singleton 单实例，prototype 多实例

第二：设置 scope 值是 singleton 时候，加载 Spring 配置文件时候就会创建单实例对象，设置 scope 值是 prototype 时候，不是在加载 Spring 配置文件时候创建对象，在调用 getBean 方法时候创建多实例对象



### IOC 操作 Bean 管理（bean 生命周期）

1、生命周期

（1）从对象创建到对象销毁的过程

2、bean 生命周期

（1）通过构造器创建 bean 实例（无参构造）

（2）为 bean 的属性设置值和其他 bean 引用（调用 set 方法）

（3）调用 bean 的初始化的方法（需要进行配置初始化的方法）

（4）bean 可以使用了（对象获取到了）

（5）当容器关闭时候，调用 bean 的销毁的方法（需要进行配置销毁的方法）

3、演示 bean 生命周期

```java
package com.spring5_IOC.pojo;

public class Animal {
    private String aname;

    public void setAname(String aname) {
        this.aname = aname;
        System.out.println("第二步调用 set 方法设置属性值");
    }

    //无参构造
    public Animal() {
        System.out.println("第一步执行无参构造创建 bean 实例");
    }
    //创建执行的初始化的方法
    public void initMethod(){
        System.out.println("第三步执行初始化的方法");
    }
    //创建执行的销毁的方法
    public void destroyMethod(){
        System.out.println("第五步执行销毁的方法");
    }
}
```

```xml
<bean id="animal" class="com.spring5_IOC.pojo.Animal" init-method="initMethod" destroy-method="destroyMethod">
        <property name="aname" value="老虎"></property>
    </bean>
```

```java
@Test
public void testLifeCycle(){
    //1、加载 Spring 配置文件
    ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("bean6.xml");
    //2、获取配置创建的对象
    Animal animal = context.getBean("animal", Animal.class);
    System.out.println("第四步获取创建 bean 实例对象");
    System.out.println(animal);

    //手动让 bean 实例销毁
    context.close();
}
```

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\bean生命周期执行过程.png)



4、bean 的后置处理器，bean 生命周期有七步

（1）通过构造器创建 bean 实例（无参构造）

（2）为 bean 的属性设置值和其他 bean 引用（调用 set 方法）

**（3）把 bean 实例传递 bean 后置处理器的方法 postProcessBeforeInitialization**

（4）调用 bean 的初始化的方法（需要进行配置初始化的方法）

**（5）把 bean 实例传递 bean 后置处理器的方法 postProcessAfterInitialization**

（6）bean 可以使用了（对象获取到了）

（7）当容器关闭时候，调用 bean 的销毁的方法（需要进行配置销毁的方法）



5、演示添加后置处理器效果

```java
public class MyBeanPost implements BeanPostProcessor {
    @Override
    public Object postProcessBeforeInitialization(Object bean, String beanName) throws BeanExpressionException{
        System.out.println("在初始化之前执行的方法");
        return bean;
    }
    @Override
    public Object postProcessAfterInitialization(Object bean, String beanName) throws BeanExpressionException{
        System.out.println("在初始化之后执行的方法");
        return bean;
    }
}
```

```xml
<!-- 配置后置处理器-->
    <bean id="myBeanPost" class="com.spring5_IOC.bean.MyBeanPost"></bean>
```



### IOC 操作 Bean 管理（xml 自动装配）

1、什么是自动装配

（1）根据指定装配规则（属性名称或者属性类型），Spring 自动将匹配的属性值进行注入

2、演示自动装配过程

（1）根据属性名称自动注入

```xml
<!--实现自动装配
        bean 标签属性 autowire，配置自动装配
        autowire 属性常用两个值：
            byName 根据属性名称注入，注入值 bean 的 id 值和类属性名称一样
            byType 根据属性类型注入
    -->
    <bean id="emp" class="com.spring5_IOC.autowire.Emp" autowire="byName">
<!--        <property name="dept" ref="dept"></property>-->
    </bean>
    <bean id="dept" class="com.spring5_IOC.autowire.Dept"></bean>
```

（2）根据属性类型自动注入

```xml
<!--实现自动装配
        bean 标签属性 autowire，配置自动装配
        autowire 属性常用两个值：
            byName 根据属性名称注入，注入值 bean 的 id 值和类属性名称一样
            byType 根据属性类型注入
    -->
    <bean id="emp" class="com.spring5_IOC.autowire.Emp" autowire="byType">
<!--        <property name="dept" ref="dept"></property>-->
    </bean>
    <bean id="dept" class="com.spring5_IOC.autowire.Dept"></bean>
```



### IOC 操作 Bean 管理（外部属性文件）

1、直接配置数据库信息

（1）配置德鲁伊连接池

（2）引入德鲁伊连接池依赖 jar 包

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\druid依赖.png)

2、引入外部属性文件配置数据库连接池

（1）创建外部属性文件，properties 格式文件，写数据库信息

```properties
prop.driverClass=com.mysql.cj.jdbc.Driver
prop.url=jdbc:mysql://localhost:3306/bookdb?serverTimezone=GMT%2B8&rewriteBatchedStatements=true
prop.userName=root
prop.password=123456
```

（2）把外部 properties 属性文件引入到 Spring 配置文件中

**xmlns:context="http://www.springframework.org/schema/context"**

**http://www.springframework.org/schema/context/spring-context.xsd**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:p="http://www.springframework.org/schema/p"
       xmlns:util="http://www.springframework.org/schema/util"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
                          http://www.springframework.org/schema/util http://www.springframework.org/schema/util/spring-util.xsd
                        http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">
    
<!--引入外部属性文件-->
    <context:property-placeholder location="classpath:jdbc.properties"></context:property-placeholder>
    <!--配置连接池-->
    <bean id="dataSource" class="com.alibaba.druid.pool.DruidDataSource">
        <property name="driverClassName" value="${prop.driverClass}"></property>
        <property name="url" value="${prop.url}"></property>
        <property name="username" value="${prop.username}"></property>
        <property name="password" value="${prop.password}"></property>
    </bean>
</beans>
```



### IOC 操作 Bean 管理（基于注解方法）

1、什么是注解

（1）注解是代码特殊标记，格式：@注解名称（属性名称=属性值，属性名称=属性值）

（2）使用注解，注解作用在类上面，方法上面，属性上面

（3）使用注解目的：简化 xml 配置

2、Spring 针对 Bean 管理中创建对象提供注解

（1）@Component

（2）@Service

（3）@Controller

（4）@Repository

上面四个注解功能一样的，都可以用来创建 bean 实例

3、基于注解方法实现对象创建

第一步：引入依赖

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\注解方式的依赖.png)

第二步：开启组件扫描

```xml
<!--开启组件扫描
        1、如果扫描多个包，多个包使用逗号隔开
        2、扫描包上层目录
    -->
    <context:component-scan base-package="com.spring5_IOC"></context:component-scan>
```

第三步：创建类，在类上面添加创建对象注解

```java
//在注解里面 value 属性值可以省略不写
//默认值是类名称，首字母小写
//OrdersService -> ordersService
@Service(value = "ordersService")//<bean id="ordersService" class=".."/>
public class OrdersService {
    public void add(){
        System.out.println("service add.....");
    }
}
```

测试方法

```java
@Test
public void testOrdersServiceAndDao(){
    //1、加载 Spring 配置文件
    ApplicationContext context = new ClassPathXmlApplicationContext("bean9.xml");
    //2、获取配置创建的对象
    OrdersService ordersService = context.getBean("ordersService", OrdersService.class);
    ordersService.add();
}
```



4、开启组件扫描细节配置

```xml
<!--示例1
        use-default-filters="false" 表示现在不是用默认 filter，自己配置 filter
        context:include-filter，设置扫描那些内容
    -->
    <context:component-scan base-package="com.spring5_IOC" use-default-filters="false">
        <context:include-filter type="annotation" expression="org.springframework.stereotype.Controller"/>
        <context:include-filter type="annotation" expression="org.springframework.stereotype.Service"/>
        <context:include-filter type="annotation" expression="org.springframework.stereotype.Repository"/>
        <context:include-filter type="annotation" expression="org.springframework.stereotype.Component"/>
    </context:component-scan>

    <!--示例2
        下面配置扫描包所有内容
        context:exclude-filter：设置那些内容不进行扫描
    -->
    <context:component-scan base-package="com.spring5_IOC">
        <context:exclude-filter type="annotation" expression="org.springframework.stereotype.Component"/>
    </context:component-scan>
```



5、基于注解方式实现属性注入

（1）@Autowired：根据属性类型进行自动装配

第一步：把 service 和 dao 对象创建，在 service 和 dao 类添加创建对象注解

第二步：在 service 注入 dao 对象，在 service 类 添加 dao 类型属性，在属性上面使用注解

```java
//在注解里面 value 属性值可以省略不写
//默认值是类名称，首字母小写
//BookService -> bookService
@Service(value = "bookService")//<bean id="bookService" class=".."/>
public class BookService {
    //定义dao类型属性
    //不需要添加 set 方法
    //添加注入属性注解
    @Autowired
    private BookDAO bookDAO;

    public void add(){
        System.out.println("service add.....");
        bookDAO.add();
    }
}
```



（2）@Qualifer：根据属性名称进行注入

这个 @Qualifer 注解的使用，和上面 @Autowired 一起使用

```java
//在注解里面 value 属性值可以省略不写
//默认值是类名称，首字母小写
//BookService -> bookService
@Service(value = "bookService")//<bean id="bookService" class=".."/>
public class BookService {
    //定义dao类型属性
    //不需要添加 set 方法
    //添加注入属性注解
    @Autowired//根据类型进行注入
    @Qualifier(value = "bookDAOImpl")//根据名称进行注入
    private BookDAO bookDAO;

    public void add(){
        System.out.println("service add.....");
        bookDAO.add();
    }
}
```



（3）@Resource：可以根据类型注入，可以根据名称注入

```java
//在注解里面 value 属性值可以省略不写
//默认值是类名称，首字母小写
//BookService -> bookService
@Service(value = "bookService")//<bean id="bookService" class=".."/>
public class BookService {
    //定义dao类型属性
    //不需要添加 set 方法
    //添加注入属性注解
    //@Autowired//根据类型进行注入
    //@Qualifier(value = "bookDAOImpl")//根据名称进行注入
    @Resource(name = "bookDAOImpl")//根据名称进行注入
    private BookDAO bookDAO;

    public void add(){
        System.out.println("service add.....");
        bookDAO.add();
    }
}
```



（4）@Value：注入普通类型属性

```java
@Value(value = "abc")
private String name;
```



6、完全注解开发

（1）创建配置类，替代 xml 配置文件

```java
@Configuration//作为配置类，替代 xml 配置文件
@ComponentScan(basePackages = {"com.spring5_IOC"})
public class SpringConfig {
}
```

（2）编写测试类

```java
@Test
public void testSpringConfig(){
    //1、加载 Spring 配置文件
    ApplicationContext context = new AnnotationConfigApplicationContext(SpringConfig.class);
    //2、获取配置创建的对象
    BookService bookService = context.getBean("bookService", BookService.class);
    bookService.add();
}
```



# 3、AOP

1、什么是 AOP

（1）面向切面编程（方法），利用 AOP 可以对业务逻辑的各个部分进行隔离，从而使得业务逻辑各部分之间的耦合度降低，提高程序的可重用性，同时提高了开发的效率。

（2）通俗描绘：不通过修改源代码方法，在主干功能里面添加新功能

（3）使用登录例子说明 AOP

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\AOP.png)



### AOP（底层原理）

1、AOP 底层使用动态代码

（1）有两种情况动态代理

第一种：有接口情况，使用 JDK 动态代理

创建接口实现类代理对象，增强类的方法

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\JDK动态代理.png)

第二种：没有接口情况，使用 CGLIB 动态代理

创建类的代理对象，增强类的方法

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\CGLIB动态代理.png)





### AOP（JDK 动态代理）

1、使用 JDK 动态代理，使用 Proxy 类里面的方法创建代理对象

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\JDK动态代理Proxy类.png)



（1）调用 newProxyInstance 方法

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\JDK动态代理Proxy类实例化.png)

方法有三个参数：

第一参数，类加载器

第二参数，增强方法所在的类，这个类实现的接口，支持多个接口

第三参数，实现这个接口 InvocationHandler，创建代理对象，写增强的部分



2、编写 JDK 动态代理代码

（1）创建接口，定义方法

```java
public interface UserDAO {
    public int add(int a, int b);
    public String update(String id);
}
```

（2）创建接口实现类，实现方法

```java
public class UserDAOImpl implements UserDAO {
    @Override
    public int add(int a, int b) {
        return a-b;
    }

    @Override
    public String update(String id) {
        return id;
    }
}
```

（3）使用 Proxy 类创建接口代理对象

```java
public class JDKProxy {
    public static void main(String[] args) {
        //创建接口实现类代理对象
        Class[] interfaces = {UserDAO.class};
        Proxy.newProxyInstance(JDKProxy.class.getClassLoader(),interfaces,new InvocationHandler(){
            @Override
            public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
                return null;
            }
        });
        UserDAOImpl userDAO = new UserDAOImpl();
        UserDAO dao = (UserDAO) Proxy.newProxyInstance(JDKProxy.class.getClassLoader(),interfaces,new UserDAOProxy(userDAO));
        int result = dao.add(1,2);
        System.out.println("result：" + result);
    }
}

class UserDAOProxy implements InvocationHandler {

    //1、把创建的是谁的代理对象，把谁传递过来
    //有参构造传递
    private Object obj;
    public UserDaoProxy(Object obj){
        this.obj = obj;
    }

    //增强的逻辑
    @Override
    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
        //方法之前
        System.out.println("方法之前执行..." + method.getName() + "：传递的参数..." + Arrays.toString(args));
        //被增强的方法执行
        Object res = method.invoke(obj, args);
        //方法之后
        System.out.println("方法之后执行..." + obj);
        return res;
    }
}
```





### AOP（术语）

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\AOP术语.png)

1、连接点

类里面那些方法可以被增强，这些方法称为连接点

2、切入点

实际被真正增强的方法，称为切入点

3、通知（增强）

（1）实际增强的逻辑部分称为通知（增强）

（2）通知有多种类型

-----前置通知

-----后置通知

-----环绕通知

-----异常通知

-----最终通知

4、切面

是动作

（1）把通知应用到切入点过程



### AOP 操作（准备工作）

1、Spring 框架一般都是基于 AspectJ 不是 Spring 组成部分，独立 AOP 框架，一般把 AspectJ 和 Spring 框架一起使用，进行 AOP 操作

2、基于 AspectJ 实现 AOP 操作

（1）基于 xml 配置文件实现

（2）基于注解方式实现（使用）

3、在项目工程里面引入 AOP 相关依赖

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\AOP相关依赖.png)

4、切入点表达式

（1）切入点表达式作用：知道对那个类里面的那个方法进行增强

（2）语法结构：execution([权限修饰符][返回类型][类全路径][方法名称]([参数列表]))

举例1：对 com.spring5_AOP.dao.BookDAO 类里面的 add 进行增强

execution( * com.spring5_AOP.dao.BookDAO.add(..))

举例2：对 com.spring5_AOP.dao.BookDAO 类里面的所有方法进行增强

execution( * com.spring5_AOP.dao.BookDAO.*(..))

举例3：对 com.spring5_AOP.dao 包里的所有类，类里面的所有方法进行增强

execution( * com.spring5_AOP.dao. * .*(..))



### AOP 操作（AspectJ 注解）

1、创建类，在类里面定义方法

```java
public class User {
    public void add(){
        System.out.println("add.......");
    }
}
```



2、创建增强类（编写增强逻辑）

（1）在增强类里面，创建方法，让不同方法代表不同通知类型

```java
//增强的类
public class UserProxy {
    public void before(){//前置通知
        System.out.println("before........");
    }
}
```



3、进行通知的配置

（1）在 Spring 配置文件中，开启注解扫描

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd
                        http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">

    <!--开启注解扫描-->
    <context:component-scan base-package="com.spring5_AOP"></context:component-scan>

</beans>
```



（2）使用注解创建 User 和 UserProxy 对象

```java
//被增强的类
@Component
public class User {}
//增强的类
@Component
public class UserProxy {}
```



（3）在增强类上面添加注解 @Aspect

```java
//增强的类
@Component
@Aspect
public class UserProxy {
    public void before(){//前置通知
        System.out.println("before........");
    }
}
```



（4）在 Spring 配置文件中开启生成代理对象

```xml
<!--开启 Aspect 生成代理对象-->
<aop:aspectj-autoproxy></aop:aspectj-autoproxy>
```



4、配置不同类型的通知

（1）在增强类的里面，在作为通知方法上面添加通知类型注解，使用切入点表达式配置

```java
//增强的类
@Component
@Aspect//生成代理对象
public class UserProxy {

    //相同切入点抽取
    @Pointcut(value = "execution(* com.spring5_AOP.pojo.User.add(..))")
    public void pointDemo(){}

    //前置通知
    //@Before注解表示作为前置通知
    @Before(value = "pointDemo()")
    public void before(){//前置通知
        System.out.println("before........");
    }
    //后置通知（返回通知）
    @AfterReturning(value = "execution(* com.spring5_AOP.pojo.User.add(..))")
    public void afterReturning(){//前置通知
        System.out.println("afterReturning........");
    }
    //最终通知
    @After(value = "execution(* com.spring5_AOP.pojo.User.add(..))")
    public void after(){//前置通知
        System.out.println("after........");
    }
    //异常通知
    @AfterThrowing(value = "execution(* com.spring5_AOP.pojo.User.add(..))")
    public void afterThrowing(){//前置通知
        System.out.println("afterThrowing........");
    }
    //环绕通知
    @Around(value = "execution(* com.spring5_AOP.pojo.User.add(..))")
    public void around(){//前置通知
        System.out.println("around........");
    }
}
```



5、相同的切入点抽取

```java
//相同切入点抽取
@Pointcut(value = "execution(* com.spring5_AOP.pojo.User.add(..))")
public void pointDemo(){}
```



6、在多个增强类多同一个方法进行增强，设置增强类优先级

（1）在增强类上面添加注解 @Order(数字类型值),数字类型值越小优先级越高

```java
@Component
@Aspect
@Order(1)
public class PersonProxy{}
```



7、完全使用注解开发

（1）创建配置类，不需要创建 xml 配置文件

```java
@Configuration
@ComponentScan(basePackages = "com.spring5_AOP")
@EnableAspectJAutoProxy(proxyTargetClass = true)
public class ConfigAop {
}
```

### AOP 操作（AspectJ 配置文件）

1、创建两个类，增强类和被增强类，创建方法

2、在 Spring 配置文件中创建两个类对象

```xml
<!--创建对象-->
    <bean id="book" class="com.spring5_AOP.pojo.Book"></bean>
    <bean id="bookProxy" class="com.spring5_AOP.jdkproxy.BookProxy"></bean>
```



3、在 Spring 配置文件中配置切入点

```xml
<!--配置aop增强-->
<aop:config>
    <!--切入点-->
    <aop:pointcut id="p" expression="execution(* com.spring5_AOP.pojo.Book.buy(..))"/>
    <!--配置切面-->
    <aop:aspect ref="bookProxy">
        <!--增强作用在具体的方法上-->
        <aop:before method="before" pointcut-ref="p"/>
    </aop:aspect>
</aop:config>
```

# 4、JdbcTemplate



JdbcTemplate（概念和准备）

1、什么是 JdbcTemplate

（1）Spring 框架对 JDBC 进行封装，使用 JdbcTemplate 方便实现对数据库操作

2、准备工作

（1）引入相关 jar 包

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\JdbcTemplate相关jar包.png)



（2）在 Spring 配置文件数据库连接池

```xml
<!--数据库连接池-->
<bean id="dataSource" class="com.alibaba.druid.pool.DruidDataSource" destroy-method="close">
    <property name="url" value="${prop.url}"/>
    <property name="username" value="${prop.userName}"/>
    <property name="password" value="${prop.password}"/>
    <property name="driverClassName" value="${prop.driverClass}"/>
</bean>
```



（3）配置 JdbcTemplate 对象，注入 DataSource

```xml
<!--JdbcTemplate 对象-->
<bean id="jdbcTemplate" class="org.springframework.jdbc.core.JdbcTemplate">
    <!--注入 dataSource-->
    <property name="dataSource" ref="dataSource"></property>
</bean>
```



（4）创建 service 类，创建 dao 类，在 dao 注入 JdbcTemplate 对象

*配置文件

```java
<!--开启注解扫描-->
<context:component-scan base-package="com.spring5_JdbcTemplate"</context:component-scan>
```

*DAO

```java
public interface BookDAO {
}
```

*DAOImpl

```java
@Repository
public class BookDAOImpl implements BookDAO {
    //注入 JdbcTemplate
    @Autowired
    private JdbcTemplate jdbcTemplate;
}
```

*Service

```java
@Service
public class BookService {
    //注入 dao
    @Autowired
    private BookDAO bookDAO;
}
```



### JdbcTemplate 操作数据库（添加）

1、对应数据库创建实体类

```java
public class Book {
    private String bookId;
    private String bookName;
    private String status;

    public String getBookId() {
        return bookId;
    }

    public void setBookId(String bookId) {
        this.bookId = bookId;
    }

    public String getBookName() {
        return bookName;
    }

    public void setBookName(String bookName) {
        this.bookName = bookName;
    }

    public String getStatus() {
        return status;
    }

    public void setStatus(String status) {
        this.status = status;
    }
}
```



2、编写 service 和 dao

（1）在 dao 进行数据库添加操作

（2）调用 JdbcTemplate 对象里面 update 方法实现添加操作

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\JdbcTemplate对象里面update.png)

有两个参数

第一个参数：sql 语句

第二个参数：可变参数，设置 sql 语句值

```java
@Repository
public class BookDAOImpl implements BookDAO {
    //注入 JdbcTemplate
    @Autowired
    private JdbcTemplate jdbcTemplate;

    //添加的方法
    @Override
    public void add(Book book) {
        //1、创建sql语句
        String sql = "insert into t_book values(?,?,?)";
        //2、调用方法实现
        //Object[] args = {book.getBookId(),book.getBookName(), book.getStatus()};
        //int update = jdbcTemplate.update(sql,args);
        int update = jdbcTemplate.update(sql, book.getBookId(),book.getBookName(), book.getStatus());
        System.out.println(update);
    }
}
```



3、测试类

```java
@Test
public void testJdbcTemplate(){
    ApplicationContext context = new ClassPathXmlApplicationContext("bean1.xml");
    BookService bookService = context.getBean("bookService", BookService.class);
    Book book = new Book();
    book.setBookId("1");
    book.setBookName("Java");
    book.setStatus("1");
    bookService.addBook(book);
}
```



## JdbcTemplate 操作数据库（修改和删除）



1、修改

```java
@Override
public void update(Book book) {
    String sql = "update t_book set bookName = ?, status = ? where bookId = ?";
    Object[] args = {book.getBookName(), book.getStatus(), book.getBookId()};
    int update = jdbcTemplate.update(sql, args);
    System.out.println(update);
}
```

2、删除

```java
@Override
public void delete(String id) {
    String sql = "delete from t_book where bookName = ?";
    int update = jdbcTemplate.update(sql, id);
    System.out.println(update);
}
```



### JdbcTemplate 操作数据库（查询返回某个值）

1、查询表里面有多少条记录，返回是某个值

2、使用 JdbcTemplate 实现查询返回某个值代码

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\JdbcTemplate查询返回某个值.png)

有两个参数

第一个参数：sql 语句

第二个参数：返回类型 Class

```java
@Override
public int selectCount() {
    String sql = "select count(*) from t_book";
    Integer count = jdbcTemplate.queryForObject(sql, Integer.class);
    return count;
}
```

### JdbcTemplate 操作数据库（查询返回对象）

1、场景：查询图书详情

2、JdbcTemplate 实现查询返回对象

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\JdbcTemplate查询返回对象.png)

有三个参数

第一个参数：sql 语句

第二个参数：RowMapper 是接口，针对返回不同类型数据，使用这个接口里面实现完成数据封装

第三个参数：sql 语句值

```java
@Override
public List<Book> findAllBook() {
    String sql = "select * from t_book";
    //调用方法
    List<Book> bookList = jdbcTemplate.query(sql, new BeanPropertyRowMapper<Book>(Book.class));
    return bookList;
}
```

### JdbcTemplate 操作数据库（查询返回集合）

1、场景：查询图书列表分页...

2、调用 JdbcTemplate 方法实现实现查询返回集合

有三个参数

第一个参数：sql 语句

第二个参数：RowMapper 是接口，针对不同类型数据，使用这个接口里面实现类完成数据封装

第三个参数：sql 语句值

```java
@Override
public List<Book> findAllBook() {
    String sql = "select * from t_book";
    //调用方法
    List<Book> bookList = jdbcTemplate.query(sql, new BeanPropertyRowMapper<Book>(Book.class));
    return bookList;
}
```



### JdbcTemplate 操作数据库（批量操作）

1、批量操作：操作表里面多条记录

2、JdbcTemplate 实现批量添加操作

有两个参数

第一个参数：sql 语句

第二个参数：List 集合，添加多条记录数据

```java
@Override
public void batchAddBook(List<Object[]> batchArgs) {
    String sql = "insert into t_book values(?,?,?)";
    int[] ints = jdbcTemplate.batchUpdate(sql, batchArgs);
    System.out.println(Arrays.toString(ints));
}
```



3、JdbcTemplate 实现批量修改操作

```java
@Override
public void batchUpdateBook(List<Object[]> batchArgs) {
    String sql = "update t_book set bookName = ?, status = ? where bookId = ?";
    int[] ints = jdbcTemplate.batchUpdate(sql, batchArgs);
    System.out.println(Arrays.toString(ints));
}
```



4、JdbcTemplate 实现批量删除操作

```java
@Override
public void batchDeleteBook(List<Object[]> batchArgs) {
    String sql = "delete from t_book where bookId = ?";
    int[] ints = jdbcTemplate.batchUpdate(sql, batchArgs);
    System.out.println(Arrays.toString(ints));
}
```



# 5、事务管理

### 事务操作（事务概念）

1、什么事务

（1）事务是数据库操作最基本单元，逻辑上一组操作，要么都成功，如果有一个失败所有操作都失败

（2）典型场景：银行转账

lucy 转账 100 元给 mary

lucy 少 100，mary 多 100

2、事务四个特性（ACID）

（1）原子性

（2）一致性

（3）隔离性

（4）持久性

### 事务操作（搭建事务操作环境）

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\事务操作环境搭建.png)

1、创建数据库表，添加记录

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\事务操作环境搭建添加记录.png)

2、创建 service，搭建 dao，完成对象创建和注入关系

（1）service 注入 dao，在 dao 注入 JdbcTemplate，在 JdbcTemplate 注入 DataSource

```java
@Service
public class BookService {
    //注入 dao
    @Autowired
    private BookDAO bookDAO;
}

@Repository
public class BookDAOImpl implements BookDAO {
    //注入 JdbcTemplate
    @Autowired
    private JdbcTemplate jdbcTemplate;
}
```



3、在 dao 创建两个方法：多钱和少钱的方法，在 service 创建方法（转账的方法）

```java
@Repository
public class BookDAOImpl implements BookDAO {
    //注入 JdbcTemplate
    @Autowired
    private JdbcTemplate jdbcTemplate;


    @Override
    public void addMoney() {
        String sql = "UPDATE t_book SET STATUS = STATUS + ? WHERE bookName = ?";
        int update = jdbcTemplate.update(sql,100,"lucy");
        System.out.println(update);
    }

    @Override
    public void reduceMoney() {
        String sql = "UPDATE t_book SET STATUS = STATUS - ? WHERE bookName = ?";
        int update = jdbcTemplate.update(sql,100,"smith");
        System.out.println(update);
    }
}
```



4、上面代码，如果正常执行没有问题的，但是如果代码执行过程中出现异常，有问题

```java
//转账的方法
public void accountMoney(){
    try{
        //第一步 开启事务
        //第二步 进行业务操作
        bookDAO.addMoney();
        bookDAO.reduceMoney();
        //lucy 少 100
    }catch(Exception e){
        e.printStackTrace();
    }
}
```

（1）上面问题如何解决呢？（使用事务进行解决）

（2）事务操作过程

```java
//转账的方法
public void accountMoney(){
    try{
        //第一步 开启事务
        //第二步 进行业务操作
        bookDAO.addMoney();

        int i = 1 / 0;

        bookDAO.reduceMoney();
        //lucy 少 100
        //第三步 没有发现异常提交
    }catch(Exception e){
        //第四步 有异常就回滚
        e.printStackTrace();
    }
}
```





### 事务操作（Spring 事务管理介绍）（有重点）

1、事务添加到 JavaEE 三层结构里面 Service 层（业务逻辑层）

2、在 Spring 进行事务管理操作

（1）有两种方式：编程式事务管理和声明式事务管理（使用）

3、声明式事务管理

（1）基于注解方式（使用）

（2）基于 xml 配置文件方式

**4、在 Spring 进行声明式事务管理，底层使用 AOP 原理（重点）**

5、Spring 事务管理 API

（1）提供一个接口，代表事务管理器，这个接口针对不同的框架提供不同的实现类

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\Spring 事务管理 API.png)



### 事务操作（注解声明式事务管理）

1、在 Spring 配置文件配置事务管理器

```xml
<!--创建事务管理器-->
<bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
    <!--注入数据源-->
    <property name="dataSource" ref="dataSource"></property>
</bean>
```



2、在 Spring 配置文件，开启事务注解

（1）在 Spring 配置文件引入名称空间 tx

```xml
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xmlns:tx="http://www.springframework.org/schema/tx"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans.xsd
         http://www.springframework.org/schema/context
        http://www.springframework.org/schema/context/spring-context.xsd
         http://www.springframework.org/schema/aop
        http://www.springframework.org/schema/aop/spring-aop.xsd
         http://www.springframework.org/schema/tx
            http://www.springframework.org/schema/tx/spring-tx.xsd">
</beans>
```

（2）开启事务注解

```xml
 <!--开启事务注解-->
<tx:annotation-driven transaction-manager="transactionManager"></tx:annotation-driven>
```



3、在 service 类上面（或者 service 类里面方法上面）添加事务注解

（1）@Transactional，这个注解添加到类上面，也可以添加方法上面

（2）如果把这个注解添加类上面，这个类里面所有的方法都添加事务

（3）如果把这个注解添加方法上面，为这个方法添加事务

```java

```

### 事务操作（声明式事务管理参数配置）

1、在 service 类上面添加注解 @Transactional，在这个注解里面可以配置事务相关参数

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\@Transactional注解配置事务相关参数.png)

2、propagation：事务传播行为

（1）多事务方法直接进行调用，这个过程中事务是如何进行管理的

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\事务传播行为.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\事务传播行为7种.png)



3、ioslation：事务隔离级别

（1）事务有特性成为隔离性，多事务操作之间不会产生影响。不考虑隔离性产生很多问题

（2）有三个读问题：脏读、不可重复读、虚（幻）读

（3）脏读：一个未提交事务读取到另一个未提交事务的数据

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\事务管理脏读.png)



（4）不可重复读：一个未提交事务读取到另一提交修改数据

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\事务管理不可重复读.png)

（5）虚读：一个未提交事务读取到另一提交事务添加数据

（6）解决：通过设置事务隔离级别，解决读问题

![](C:\Users\FY\Desktop\笔记\学习笔记\Spring_image\事务管理隔离级别.png)



4、timeout：超时时间

（1）事务需要在一定时间内进行提交，如果不提交进行回滚

（2）默认值是 -1，设置时间以秒单位进行计算

5、readOnly：是否只读

（1）读：查询操作，写：添加修改删除操作

（2）readOnly 默认值 false，表示可以查询，可以添加修改删除操作

（3）设置 readOnly 值是 true，设置成 true 之后，只能查询

6、rollbackFor：回滚

（1）设置出现那些异常进行事务回滚

7、noRollbackFor：不回滚

（1）设置出现那些异常不进行事务回滚



### 事务操作（XML 声明式事务管理）

1、在 Spring 配置文件中进行配置

第一步 配置事务管理器

第二步 配置通知

第三步 配置切入点和切面

```xml
<!--1、创建事务管理器-->
<bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
    <!--注入数据源-->
    <property name="dataSource" ref="dataSource"></property>
</bean>

<!--2、配置通知-->
<tx:advice id="txactice">
    <!--配置事务参数-->
    <tx:attributes>
        <!--指定那种规则的方法上面添加事务-->
        <tx:method name="accountMoney" propagation="REQUIRED"/>
        <!--<tx:method name="account*"/>-->
    </tx:attributes>
</tx:advice>

<!--3、配置切入点和切面-->
<aop:config>
    <aop:pointcut id="pt" expression="execution(* com.spring5_transaction.service.BookService.*(..))"/>
    <aop:advisor advice-ref="txactice" pointcut-ref="pt"/>
</aop:config>
```

### 事务操作（完全注解声明式事务管理）

1、创建配置类，使用配置类替代 xml 配置文件

```java
@Configuration//配置类
@ComponentScan(basePackages = "com.spring5_transaction")//组件扫描
@EnableTransactionManagement//开启事务
public class TxConfig {
    //创建数据库连接池
    @Bean
    public DruidDataSource getDruidDataSource(){
        DruidDataSource dataSource = new DruidDataSource();
        dataSource.setDriverClassName("com.mysql.cj.jdbc.Driver");
        dataSource.setUrl("jdbc:mysql://localhost:3306/db_book?serverTimezone=GMT%2B8&rewriteBatchedStatements=true");
        dataSource.setUsername("root");
        dataSource.setPassword("123456");
        return dataSource;
    }
    //创建 JdbcTemplate 对象
    @Bean
    public JdbcTemplate getJdbcTemplate(DataSource dataSource){
        //到 ioc 容器中根据类型找到 dataSource
        JdbcTemplate jdbcTemplate = new JdbcTemplate();
        //注入 dataSource
        jdbcTemplate.setDataSource(dataSource);
        return jdbcTemplate;
    }
    //创建事务管理器
    @Bean
    public DataSourceTransactionManager getDataSourceTransactionManager(DataSource dataSource){
        DataSourceTransactionManager transactionManager = new DataSourceTransactionManager(dataSource);
        return transactionManager;
    }
}
```



# 6、Spring5 新特性

### Spring5 框架新功能
