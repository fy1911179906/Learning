# 第一章       Java Web 预备基础知识



## Java / DB / JDBC

## HTML / CSS / JS

1.CSS

  1) CSS的角色：页面显示的美观风格
  2) CSS的基础语法：标签样式；类样式；ID样式；组合样式；嵌入式样式表；内部样式表；外部样式表
  3) 盒子模型：border、margin、padding
  4) 定位和浮动：position、float、DIV+CSS布局

2.JS
  1) JS是客户端（浏览器端）运行的脚本语言，语法风格和java比较类似
  2) JS是弱类型的语言 var str = 99 ;
  3) JS的函数  function hello(var num){}
  4) DOM技术:
	4-1) 鼠标悬浮：onmouseover,event.srcElement,事件传递,parentElement,style.backgroundColor
	     鼠标离开：onmouseout
	4-2) 鼠标点击：hand/pointer,onclick , td.innerText , td.innerHTML="<input type='text'/>", td.firstChild.value=oldPrice
	     失去焦点：onblur , input.parentElement.innerText = newPrice ;
	     更新小计：input = event.srcElement , tr = input.parentElement.parentElement ; tr.cells , parseInt
	     更新总计：document.getElementById("fruit_tbl") , fruitTbl.rows 
	4-3) 删除一行：img , img.parentElement.parentElement.rowIndex , table.deleteRow(rowIndex)

## CS ：客户端服务器架构模式

### 优点

充分利用客户端及其的资源，减轻服务器的负荷（一部分安全要求不高的计算任务存储任务放在客户端执行，不需要把所有的计算和存储都在服务器端执行，从而能够减轻服务器的压力，也能够减轻网络负荷）

### 缺点

需要安装；升级维护成本较高



## BS：浏览器服务器架构模式

### 优点

客户端不需要安装；维护成本较低。

### 缺点

所有的计算和存储任务都是放在服务器端的，服务器的负荷较重；在服务端计算完成之后把结果再传输给客户端，因此客户端和服务器端会进行非常频繁的数据通信，从而网络负荷较重。





# 第二章      Servlet 入门



## Tomcat 的安装和配置

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\02-servlet入门\Tomcat的安装和配置.png)



## 第一次使用 Servlet

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\02-servlet入门\03.第一次使用Servlet.png)



1. 新建项目 - 新建模块
2. 在模块中添加web
3. 创建artifact - 部署包
4. lib - artifact
   先有artifact，后来才添加的mysql.jar。此时，这个jar包并没有添加到部署包中
   那么在projectSettings中有一个Problems中会有提示的,我们点击fix选择add to...
   另外，我们也可以直接把lib文件夹直接新建在WEB-INF下。
   这样不好的地方是这个lib只能是当前这个moudle独享。如果有第二个moudle我们需要再次重复的新建lib。
5. 在部署的时候，修改application Context。然后再回到server选项卡，检查URL的值。
   URL的值指的是tomcat启动完成后自动打开你指定的浏览器，然后默认访问的网址。
   启动后，报错404.404意味着找不到指定的资源。
   如果我们的网址是：http://localhost:8080/pro01/ , 那么表明我们访问的是index.html.
   我们可以通过<welcome-file-list>标签进行设置欢迎页(在tomcat的web.xml中设置，或者在自己项目的web.xml中设置)
6. 405问题。当前请求的方法不支持。比如，我们表单method=post , 那么Servlet必须对应doPost。否则报405错误。
7. 空指针或者是NumberFormatException 。因为有价格和库存。如果价格取不到，结果你想对null进行Integer.parseInt()就会报错。错误的原因大部分是因为 name="price"此处写错了，结果在Servlet端还是使用request.getParameter("price")去获取。
8. <url-pattern>中以斜杠开头

   

### 项目代码（code-4servletIntroduction）



# 第三章       Servlet 之 - Http - Session



## 设置编码

tomcat8之前，设置编码：
  1)get请求方式：
    //get方式目前不需要设置编码（基于tomcat8）
    //如果是get请求发送的中文数据，转码稍微有点麻烦（tomcat8之前）
    String fname = request.getParameter("fname");
    //1.将字符串打散成字节数组
    byte[] bytes = fname.getBytes("ISO-8859-1");
    //2.将字节数组按照设定的编码重新组装成字符串
    fname = new String(bytes,"UTF-8");
  2)post请求方式：
    request.setCharacterEncoding("UTF-8");
tomcat8开始，设置编码，只需要针对post方式
    request.setCharacterEncoding("UTF-8");
注意：
    需要注意的是，设置编码(post)这一句代码必须在所有的获取参数动作之前



## Servlet 的继承关系 - 重点查看的是服务方法（service()）



![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\03-servlet-http-session\01.Servlet是线程不安全的.png)



### 继承关系

javax.servlet.Servlet接口
 	javax.servlet.GenericServlet抽象类
    	 javax.servlet.http.HttpServlet抽象子类

### 相关方法

javax.servlet.Servlet接口:
	void init(config) - 初始化方法
	void service(request,response) - 服务方法
	void destory() - 销毁方法

  javax.servlet.GenericServlet抽象类：
    		void service(request,response) - 仍然是抽象的

 		 javax.servlet.http.HttpServlet 抽象子类：
 				void service(request,response) - 不是抽象的
 	
 	1. String method = req.getMethod(); 获取请求的方式
 	    2. 各种if判断，根据请求方式不同，决定去调用不同的do方法
 	    
 	       ```java
 	       if (method.equals("GET")) {
 	        this.doGet(req,resp);
 	       } else if (method.equals("HEAD")) {
 	        this.doHead(req, resp);
 	       } else if (method.equals("POST")) {
 	    this.doPost(req, resp);
 	   } else if (method.equals("PUT")) {
 	   ```


​       
​       
​        3. 在HttpServlet这个抽象类中，do方法都差不多:
​    
​    ```java
​    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
​            String protocol = req.getProtocol();
​            String msg = lStrings.getString("http.method_get_not_supported");
​            if (protocol.endsWith("1.1")) {
​                resp.sendError(405, msg);
​            } else {
​                resp.sendError(400, msg);
​            }
​        }
​    ```

### 小结

1) 继承关系： HttpServlet -> GenericServlet -> Servlet
2) Servlet中的核心方法： init() , service() , destroy()
3) 服务方法： 当有请求过来时，service方法会自动响应（其实是tomcat容器调用的）
        在HttpServlet中我们会去分析请求的方式：到底是get、post、head还是delete等等
        然后再决定调用的是哪个do开头的方法
        那么在HttpServlet中这些do方法默认都是405的实现风格-要我们子类去实现对应的方法，否则默认会报405错误
4) 因此，我们在新建Servlet时，我们才会去考虑请求方法，从而决定重写哪个do方法



## Servlet 的生命周期

1） 生命周期：从出生到死亡的过程就是生命周期。对应Servlet中的三个方法：init(),service(),destroy()
2） 默认情况下：
    第一次接收请求时，这个Servlet会进行实例化(调用构造方法)、初始化(调用init())、然后服务(调用service())
    从第二次请求开始，每一次都是服务
    当容器关闭时，其中的所有的servlet实例会被销毁，调用销毁方法
3） 通过案例我们发现：
    - Servlet实例tomcat只会创建一个，所有的请求都是这个实例去响应。
    - 默认情况下，第一次请求时，tomcat才会去实例化，初始化，然后再服务.这样的好处是什么？ 提高系统的启动速度 。 这样的缺点是什么？ 第一次请求时，耗时较长。
    - 因此得出结论： 如果需要提高系统的启动速度，当前默认情况就是这样。如果需要提高响应速度，我们应该设置Servlet的初始化时机。
4） Servlet的初始化时机：
    - 默认是第一次接收请求时，实例化，初始化
    - 我们可以通过<load-on-startup>来设置servlet启动的先后顺序,数字越小，启动越靠前，最小值0
5） Servlet在容器中是：单例的、线程不安全的
    - 单例：所有的请求都是同一个实例去响应
    - 线程不安全：一个线程需要根据这个实例中的某个成员变量值去做逻辑判断。但是在中间某个时机，另一个线程改变了这个成员变量的值，从而导致第一个线程的执行路径发生了变化
    - 我们已经知道了servlet是线程不安全的，给我们的启发是： 尽量的不要在servlet中定义成员变量。如果不得不定义成员变量，那么不要去：①不要去修改成员变量的值 ②不要去根据成员变量的值做一些逻辑判断



## Http 协议

1） Http 称之为 超文本传输协议
2） Http是无状态的
3） Http请求响应包含两个部分：请求和响应

  - 请求：
    请求包含三个部分： 1.请求行 ； 2.请求消息头 ； 3.请求主体
    1)请求行包含是三个信息： 1. 请求的方式 ； 2.请求的URL ； 3.请求的协议（一般都是HTTP1.1）
    2)请求消息头中包含了很多客户端需要告诉服务器的信息，比如：我的浏览器型号、版本、我能接收的内容的类型、我给你发的内容的类型、内容的长度等等
    3)请求体，三种情况
      get方式，没有请求体，但是有一个queryString
      post方式，有请求体，form data
      json格式，有请求体，request payload
  - 响应：
    响应也包含三本： 1. 响应行 ； 2.响应头 ； 3.响应体
    1)响应行包含三个信息：1.协议 2.响应状态码(200) 3.响应状态(ok)
    2)响应头：包含了服务器的信息；服务器发送给浏览器的信息（内容的媒体类型、编码、内容长度等）
    3)响应体：响应的实际内容（比如请求add.html页面时，响应的内容就是<html><head><body><form....）





## 会话



### Http 是无状态的

    - HTTP 无状态 ：服务器无法判断这两次请求是同一个客户端发过来的，还是不同的客户端发过来的
        - 无状态带来的现实问题：第一次请求是添加商品到购物车，第二次请求是结账；如果这两次请求服务器无法区分是同一个用户的，那么就会导致混乱
        - 通过会话跟踪技术来解决无状态的问题。



### 会话跟踪技术

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\03-servlet-http-session\02.会话跟踪技术.png)

​    - 客户端第一次发请求给服务器，服务器获取session，获取不到，则创建新的，然后响应给客户端
​    - 下次客户端给服务器发请求时，会把sessionID带给服务器，那么服务器就能获取到了，那么服务器就判断这一次请求和上次某次请求是同一个客户端，从而能够区分开客户端
​    - 常用的API：
​      request.getSession() -> 获取当前的会话，没有则创建一个新的会话
​      request.getSession(true) -> 效果和不带参数相同
​      request.getSession(false) -> 获取当前会话，没有则返回null，不会创建新的

```
  session.getId() -> 获取sessionID
  session.isNew() -> 判断当前session是否是新的
  session.getMaxInactiveInterval() -> session的非激活间隔时长，默认1800秒
  session.setMaxInactiveInterval()
  session.invalidate() -> 强制性让会话立即失效
  ....
```



### session 保存作用域

  - session保存作用域是和具体的某一个session对应的
  - 常用的API：
    void session.setAttribute(k,v)
    Object session.getAttribute(k)
    void removeAttribute(k)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\03-servlet-http-session\03.session保存作用域.png)





### 服务器内部转发以及客户端重定向

1） 服务器内部转发 : request.getRequestDispatcher("...").forward(request,response);

  - 一次请求响应的过程，对于客户端而言，内部经过了多少次转发，客户端是不知道的
  - 地址栏没有变化
    2） 客户端重定向： response.sendRedirect("....");
  - 两次请求响应的过程。客户端肯定知道请求URL有变化
  - 地址栏有变化

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\03-servlet-http-session\04.服务器内部转发.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\03-servlet-http-session\05.客户端重定向.png)



## 小结

1. post提交方式下的设置编码，防止中文乱码
   request.setCharacterEncoding("utf-8");
   get提交方式，tomcat8开始，编码不需要设置
   tomcat8之前，get方式设置比较麻烦：
   String fname = request.getParameter("fname");
   byte[] bytes = fname.getBytes("iso-8859-1");
   fname = new String(bytes,"UTF-8");

2. Servlet继承关系以及生命周期
   1） Servlet接口 ： init() , service() , destroy()
       GenericServlet抽象子类： abstract service();
       HttpServlet抽象子类：实现了service方法，在service方法内部通过request.getMethod()来判断请求的方式，
            然后根据请求的方式去调用内部的do方法。每一个do方法进行了简单实现，主要是如果请求方式不符合，则报405错误。
            目的是让我们的Servlet子类去重写对应的方法（如果重写的不对，则使用父类的405错误实现）
   2） 生命周期：实例化、初始化、服务、销毁
        - Tomcat负责维护Servlet实例的生命周期
        - 每个Servlet在Tomcat容器中只有一个实例，它是线程不安全的
        - Servlet的启动时机：<load-on-startup>
        - Servlet3.0开始支持注解: @WebServlet

3. HTTP协议：
   1） 由 Request 和 Response 两部分组成
   2） 请求包含了三部分：请求行、请求消息头、请求主体： 普通的get方式请求-query string；post方式- form data ； json格式 - request payload
   3） 响应包含了三部分：响应行、响应消息头、响应主体

4. HttpSession
   1） HttpSession ：表示 会话
   2） 为什么需要HttpSession ， 原因是因为 Http协议是无状态的
   3） Session保存作用域 ：一次会话范围都有效 ； void session.setAttribute(k,v) ,Object session.getAttribute(k)
   4） 其他的API： session.getId() , session.isNew() , session.getCreationTime() , session.invalidate() 等等

5. 服务器端转发和客户端重定向
   1) 服务器端转发 ： request.getRequestDispatcher("index.html").forward(request,response);
   2) 客户端重定向： response.sendRedirect("index.html");



# 第四章       Thymeleaf 的使用



## Thymeleaf - 视图模板技术

​	1） 添加thymeleaf的jar包
​	2） 新建一个Servlet类ViewBaseServlet
​	3） 在web.xml文件中添加配置

   - ​	配置前缀 view-prefix
   - 配置后缀 view-suffix

​	4） 使得我们的Servlet继承ViewBaseServlet

​	5） 根据逻辑视图名称 得到 物理视图名称
​	//此处的视图名称是 index
​	//那么thymeleaf会将这个 逻辑视图名称 对应到 物理视图 名称上去
​	//逻辑视图名称 ：   index
​	//物理视图名称 ：   view-prefix + 逻辑视图名称 + view-suffix
​	//所以真实的视图名称是：      /       index       .html
​	super.processTemplate("index",request,response);
​	6） 使用thymeleaf的标签
 	th:if   ,  th:unless   , th:each   ,   th:text

// 200 : 正常响应
// 404 : 找不到资源
// 405 : 请求方式不支持
// 500 : 服务器内部错误



## 保存作用域

原始情况下，保存作用域我们可以认为有四个： page（页面级别，现在几乎不用） , request（一次请求响应范围） , session（一次会话范围） , application（整个应用程序范围）

### 	 request：一次请求响应范围

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\04-thymeleaf使用\01.Request保存作用域.png)

### 	

### 	 session：一次会话范围有效

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\04-thymeleaf使用\02.Session保存作用域.png)



### 	application： 一次应用程序范围有效

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\04-thymeleaf使用\03.Application保存作用域.png)





## 路径问题

​	1） 相对路径
​	2） 绝对路径

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\04-thymeleaf使用\04.相对路径_绝对路径_base标签_@{}.png)



### 项目代码（code-6-thymeleaf-fruit） 

# 第五章       servlet - mvc



## 原始

### 项目代码（code-6-thymeleaf-fruit）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\05-servlet-mvc\01.mvc01.png)

### 结构

每项业务对应一个 servlet 组件，通过



## 优化一

### 项目代码（code-7-servlet-mvc）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\05-servlet-mvc\02.mvc02.png)





## 优化二

### 项目代码（code-8-mvc-dispatcherServlet）

## 优化三

### 项目代码（code-9-mvc-controller）

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\05-servlet-mvc\03.MVC03.png)



## 小结

1. 最初的做法是： 一个请求对应一个Servlet，这样存在的问题是servlet太多了
2. 把一些列的请求都对应一个Servlet, IndexServlet/AddServlet/EditServlet/DelServlet/UpdateServlet -> 合并成FruitServlet
   通过一个operate的值来决定调用FruitServlet中的哪一个方法
   使用的是switch-case
3. 在上一个版本中，Servlet中充斥着大量的switch-case，试想一下，随着我们的项目的业务规模扩大，那么会有很多的Servlet，也就意味着会有很多的switch-case，这是一种代码冗余
   因此，我们在servlet中使用了反射技术，我们规定operate的值和方法名一致，那么接收到operate的值是什么就表明我们需要调用对应的方法进行响应，如果找不到对应的方法，则抛异常
4. 在上一个版本中我们使用了反射技术，但是其实还是存在一定的问题：每一个servlet中都有类似的反射技术的代码。因此继续抽取，设计了中央控制器类：DispatcherServlet
   DispatcherServlet这个类的工作分为两大部分：
   1.根据url定位到能够处理这个请求的controller组件：
    1)从url中提取servletPath : /fruit.do -> fruit
    2)根据fruit找到对应的组件:FruitController ， 这个对应的依据我们存储在applicationContext.xml中
      <bean id="fruit" class="com.atguigu.fruit.controllers.FruitController/>
      通过DOM技术我们去解析XML文件，在中央控制器中形成一个beanMap容器，用来存放所有的Controller组件
    3)根据获取到的operate的值定位到我们FruitController中需要调用的方法
   2.调用Controller组件中的方法：
    1) 获取参数
       获取即将要调用的方法的参数签名信息: Parameter[] parameters = method.getParameters();
       通过parameter.getName()获取参数的名称；
       准备了Object[] parameterValues 这个数组用来存放对应参数的参数值
       另外，我们需要考虑参数的类型问题，需要做类型转化的工作。通过parameter.getType()获取参数的类型
    2) 执行方法
       Object returnObj = method.invoke(controllerBean , parameterValues);
    3) 视图处理
       String returnStr = (String)returnObj;
       if(returnStr.startWith("redirect:")){
        ....
       }else if.....





# 第六章       servlet - ioc



## servlet - api

### 再次学习Servlet的初始化方法

 1) Servlet生命周期：实例化、初始化、服务、销毁
 2) Servlet中的初始化方法有两个：init() , init(config)
      其中带参数的方法代码如下：
      public void init(ServletConfig config) throws ServletException {
     this.config = config ;
     init();
      }
      另外一个无参的init方法如下：
      public void init() throws ServletException{
      }
      如果我们想要在Servlet初始化时做一些准备工作，那么我们可以重写init方法
      我们可以通过如下步骤去获取初始化设置的数据
   - 获取config对象：ServletConfig config = getServletConfig();
   - 获取初始化参数值： config.getInitParameter(key);
 3) 在web.xml文件中配置Servlet
    <servlet>
        <servlet-name>Demo01Servlet</servlet-name>
        <servlet-class>com.atguigu.servlet.Demo01Servlet</servlet-class>
        <init-param>
            <param-name>hello</param-name>
            <param-value>world</param-value>
        </init-param>
        <init-param>
            <param-name>uname</param-name>
            <param-value>jim</param-value>
        </init-param>
    </servlet>
    <servlet-mapping>
        <servlet-name>Demo01Servlet</servlet-name>
        <url-pattern>/demo01</url-pattern>
    </servlet-mapping>
 4) 也可以通过注解的方式进行配置：
 @WebServlet(urlPatterns = {"/demo01"} ,
     initParams = {
         @WebInitParam(name="hello",value="world"),
         @WebInitParam(name="uname",value="jim")
     })



## Servlet 中的 ServletContext

### 学习Servlet中的ServletContext和<context-param>

1) 获取ServletContext，有很多方法
   在初始化方法中： ServletContxt servletContext = getServletContext();
   在服务方法中也可以通过request对象获取，也可以通过session获取：
   request.getServletContext(); session.getServletContext()
2) 获取初始化值：
   servletContext.getInitParameter();



## 业务层 service

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\06-servlet-mvc-ioc\01.MVC04.png)

### 什么是业务层 - 项目代码（code-11-servlet-filter）

1) Model1和Model2
   MVC : Model（模型）、View（视图）、Controller（控制器）
   视图层：用于做数据展示以及和用户交互的一个界面
   控制层：能够接受客户端的请求，具体的业务功能还是需要借助于模型组件来完成
   模型层：模型分为很多种：有比较简单的pojo/vo(value object)，有业务模型组件，有数据访问层组件
    1) pojo/vo : 值对象
    2) DAO ： 数据访问对象
    3) BO ： 业务对象
2) 区分业务对象和数据访问对象：
    1） DAO中的方法都是单精度方法或者称之为细粒度方法。什么叫单精度？一个方法只考虑一个操作，比如添加，那就是insert操作、查询那就是select操作....
    2） BO中的方法属于业务方法，也实际的业务是比较复杂的，因此业务方法的粒度是比较粗的
      注册这个功能属于业务功能，也就是说注册这个方法属于业务方法。
      那么这个业务方法中包含了多个DAO方法。也就是说注册这个业务功能需要通过多个DAO方法的组合调用，从而完成注册功能的开发。
      注册：
            1. 检查用户名是否已经被注册 - DAO中的select操作
            2. 向用户表新增一条新用户记录 - DAO中的insert操作
            3. 向用户积分表新增一条记录（新用户默认初始化积分100分） - DAO中的insert操作
            4. 向系统消息表新增一条记录（某某某新用户注册了，需要根据通讯录信息向他的联系人推送消息） - DAO中的insert操作
            5. 向系统日志表新增一条记录（某用户在某IP在某年某月某日某时某分某秒某毫秒注册） - DAO中的insert操作
            6. ....
3) 在库存系统中添加业务层组件



## IOC

### IOC 项目代码（code-10-servlet-ioc）

1) 耦合/依赖
    依赖指的是某某某离不开某某某
    在软件系统中，层与层之间是存在依赖的。我们也称之为耦合。
    我们系统架构或者是设计的一个原则是： 高内聚低耦合。
    层内部的组成应该是高度聚合的，而层与层之间的关系应该是低耦合的，最理想的情况0耦合（就是没有耦合）
2) IOC - 控制反转 / DI - 依赖注入



## 小结

1. Servlet生命周期中的初始化方法： init() ， init(config)
   public void init(ServletConfig config) throws ServletException {
        this.config = config ;
        init();
   }
   因此，如果我们需要在初始化时执行一些自定义的操作，那么我们可以重写无参的init方法。
   我们可以通过getConfig()获取ServletConfig对象
   可以通过config.getInitParameter()获取初始化参数

2. 通过ServletContext获取配置的上下文参数

3. MVC ： V：view 视图 ； C：Controller 控制器  ； M：Model 模型
   模型有很多种类：数据访问模型（DAO）；业务逻辑模型（BO）；值对象模型（POJO）；数据传输对象（DTO）

4. IOC
    IOC - 控制反转 / DI - 依赖注入
    控制反转：
    1) 之前在Servlet中，我们创建service对象 ， FruitService fruitService = new FruitServiceImpl();
       这句话如果出现在servlet中的某个方法内部，那么这个fruitService的作用域（生命周期）应该就是这个方法级别；
       如果这句话出现在servlet的类中，也就是说fruitService是一个成员变量，那么这个fruitService的作用域（生命周期）应该就是这个servlet实例级别
    2) 之后我们在applicationContext.xml中定义了这个fruitService。然后通过解析XML，产生fruitService实例，存放在beanMap中，这个beanMap在一个BeanFactory中
       因此，我们转移（改变）了之前的service实例、dao实例等等他们的生命周期。控制权从程序员转移到BeanFactory。这个现象我们称之为控制反转

    依赖注入：
    1) 之前我们在控制层出现代码：FruitService fruitService = new FruitServiceImpl()；
       那么，控制层和service层存在耦合。
    2) 之后，我们将代码修改成FruitService fruitService = null ;
       然后，在配置文件中配置:
       <bean id="fruit" class="FruitController">
            <property name="fruitService" ref="fruitService"/>
       </bean>



# 第七章       servlet - filter - transaction - listener



## 过滤器 Filter

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\07-mvc-filter-transaction-listener\01.Filter.png)

### 过滤器 Filter 项目代码（code-11-servlet-filter）

1) Filter也属于Servlet规范
2) Filter开发步骤：新建类实现Filter接口，然后实现其中的三个方法：init、doFilter、destroy
   配置Filter，可以用注解@WebFilter，也可以使用xml文件 <filter> <filter-mapping>
3) Filter在配置时，和servlet一样，也可以配置通配符，例如 @WebFilter("*.do")表示拦截所有以.do结尾的请求
4) 过滤器链
   1）执行的顺序依次是： A B C demo03 C2 B2 A2
   2）如果采取的是注解的方式进行配置，那么过滤器链的拦截顺序是按照全类名的先后顺序排序的
   3）如果采取的是xml的方式进行配置，那么按照配置的先后顺序进行排序





## 事务管理 (TransactionManager、ThreadLocal、OpenSessionInViewFilter)



### 编程式事务管理

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\07-mvc-filter-transaction-listener\03.编程式事务管理.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\07-mvc-filter-transaction-listener\04.编程式事务管理02.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\07-mvc-filter-transaction-listener\05.编程式事务管理03.png)



### 事务管理项目代码（code-12-mvc-transaction）

1) 涉及到的组件：
  - OpenSessionInViewFilter
  - TransactionManager
  - ThreadLocal
  - ConnUtil
  - BaseDAO



## ThreadLocal

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\07-mvc-filter-transaction-listener\06.ThreadLocal.png)



### get() , set(obj)

  - ThreadLocal称之为本地线程 。 我们可以通过set方法在当前线程上存储数据、通过get方法在当前线程上获取数据
  - set方法源码分析：
      public void set(T value) {
      Thread t = Thread.currentThread(); //获取当前的线程
      ThreadLocalMap map = getMap(t);    //每一个线程都维护各自的一个容器（ThreadLocalMap）
      if (map != null)
          map.set(this, value);          //这里的key对应的是ThreadLocal，因为我们的组件中需要传输（共享）的对象可能会有多个（不止Connection）
      else
          createMap(t, value);           //默认情况下map是没有初始化的，那么第一次往其中添加数据时，会去初始化
        }
        -get方法源码分析：
        public T get() {
      Thread t = Thread.currentThread(); //获取当前的线程
      ThreadLocalMap map = getMap(t);    //获取和这个线程（企业）相关的ThreadLocalMap（也就是工作纽带的集合）
      if (map != null) {
          ThreadLocalMap.Entry e = map.getEntry(this);   //this指的是ThreadLocal对象，通过它才能知道是哪一个工作纽带
          if (e != null) {
              @SuppressWarnings("unchecked")
              T result = (T)e.value;     //entry.value就可以获取到工具箱了
              return result;
          }
      }
      return setInitialValue();
        }



## 监听器 (Listener , ContextLoaderListener)

### 监听器项目代码（code-11-servlet-filter）

1) ServletContextListener - 监听ServletContext对象的创建和销毁的过程
2) HttpSessionListener - 监听HttpSession对象的创建和销毁的过程
3) ServletRequestListener - 监听ServletRequest对象的创建和销毁的过程
4) ServletContextAttributeListener - 监听ServletContext的保存作用域的改动(add,remove,replace)
5) HttpSessionAttributeListener - 监听HttpSession的保存作用域的改动(add,remove,replace)
6) ServletRequestAttributeListener - 监听ServletRequest的保存作用域的改动(add,remove,replace)
7) HttpSessionBindingListener - 监听某个对象在Session域中的创建与移除
8) HttpSessionActivationListener - 监听某个对象在Session域中的序列化和反序列化

### 项目应用

ServletContextListener的应用 - **ContextLoaderListener --- 项目代码（code-11-servlet-filter）**



## 最终版结构

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\08-qqzone\01.MVC各个层的设计.png)







# 第八章       qqzone





![02.QQZone-ER图](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\08-qqzone\02.QQZone-ER图.png)

![03.查询好友列表](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\08-qqzone\03.查询好友列表.png)



1.熟悉QQZone业务需求

  1) 用户登录
  2) 登录成功，显示主界面。左侧显示好友列表；上端显示欢迎词。如果不是自己的空间，显示超链接：返回自己的空间；下端显示日志列表
  3) 查看日志详情：
        - 日志本身的信息（作者头像、昵称、日志标题、日志内容、日志的日期）
        - 回复列表（回复者的头像、昵称、回复内容、回复日期）
        - 主人回复信息
  4) 删除日志
  5) 删除特定回复
  6) 删除特定主人回复
  7) 添加日志、添加回复、添加主人回复
  8) 点击左侧好友链接，进入好友的空间
    2.数据库设计

    1） 抽取实体 : 用户登录信息、用户详情信息 、 日志 、 回贴  、 主人回复
    2） 分析其中的属性：
    
    - 用户登录信息：账号、密码、头像、昵称
    - 用户详情信息：真实姓名、星座、血型、邮箱、手机号.....
    - 日志：标题、内容、日期、作者
    - 回复：内容、日期、作者、日志
    - 主人回复：内容、日期、作者、回复
  3） 分析实体之间的关系
    - 用户登录信息 ： 用户详情信息      1：1 PK
    - 用户 ： 日志                   1：N
    - 日志 ： 回复                   1：N
    - 回复 ： 主人回复                1：1 UK
    - 用户 ： 好友                   M ： N
3.数据库的范式：
  1） 第一范式：列不可再分
  2） 第二范式：一张表只表达一层含义（只描述一件事情）
  3） 第三范式：表中的每一列和主键都是直接依赖关系，而不是间接依赖
4.数据库设计的范式和数据库的查询性能很多时候是相悖的，我们需要根据实际的业务情况做一个选择：
  - 查询频次不高的情况下，我们更倾向于提高数据库的设计范式，从而提高存储效率
  - 查询频次较高的情形，我们更倾向于牺牲数据库的规范度，降低数据库设计的范式，允许特定的冗余，从而提高查询的性能

5.QQZone登录功能实现出现的四个错误：

​	1）URL没修改，用的还是fruitdb
​	2）
​    3）rsmd.getColumnName() 和 rsmd.getColumnLabel()
​    4）Can not set com.atguigu.qqzone.pojo.UserBasic field com.atguigu.qqzone.pojo.Topic.author to java.lang.Integer

  1) left.html页面没有样式，同时数据也不展示，原因是：我们是直接去请求的静态页面资源，那么并没有执行super.processTemplate()，也就是thymeleaf没有起作用

    (之前的表单也是这个原因)
    解决方法：
    - 新增PageController，添加page方法:
    public String page(String page){
        return page ;       // frames/left
    }
    目的是执行super.processTemplate()方法，让thymeleaf生效



昨日内容：

1. top.html页面显示登录者昵称、判断是否是自己的空间
   1)显示登录者昵称： ${session.userBasic.nickName}
   2)判断是否是自己的空间 : ${session.userBasic.id!=session.friend.id}
     如果不是期望的效果，首先考虑将两者的id都显示出来

2. 点击左侧的好友链接，进入好友空间
   1) 根据id获取指定userBasic信息，查询这个userBasic的topicList，然后覆盖friend对应的value
   2) main页面应该展示friend中的topicList，而不是userBasic中的topicList
   3) 跳转后，在左侧（left）中显示整个index页面
      - 问题：在left页面显示整个index布局
      - 解决：给超链接添加target属性：   target="_top" 保证在顶层窗口显示整个index页面

   4) top.html页面需要修改： "欢迎进入${session.friend}"
      top.html页面的返回自己空间的超链接需要修改：
      <a th:href="@{|/user.do?operate=friend&id=${session.userBasic.id}|}" target="_top">

3. 日志详情页面实现
   1) 已知topic的id，需要根据topic的id获取特定topic
   2) 获取这个topic关联的所有的回复
   3) 如果某个回复有主人回复，需要查询出来
   - 在TopicController中获取指定的topic
   - 具体这个topic中关联多少个Reply，由ReplyService内部实现
   4) 获取到的topic中的author只有id，那么需要在topicService的getTopic方法中封装，在查询topic本身信息时，同时调用userBasicService中的获取userBasic方法，给author属性赋值
   5) 同理，在reply类中也有author，而且这个author也是只有id，那么我们也需要根据id查询得到author，最后设置关联

4. 添加回复

5. 删除回复
   1) 如果回复有关联的主人回复，需要先删除主人回复
   2) 删除回复
   Cannot delete or update a parent row: a foreign key constraint fails
   (`qqzonedb`.`t_host_reply`, CONSTRAINT `FK_host_reply` FOREIGN KEY (`reply`) REFERENCES `t_reply` (`id`))
    我们在删除回复表记录时，发现删除失败，原因是：在主人回复表中仍然有记录引用待删除的回复这条记录
    如果需要删除主表数据，需要首先删除子表数据

6. 删除日志
   1) 删除日志，首先需要考虑是否有关联的回复
   2) 删除回复，首先需要考虑是否有关联的主人回复
   3) 另外，如果不是自己的空间，则不能删除日志



今日内容：

1. 日期和字符串之间的格式化
    /*
    // String -> java.util.Date
    String dateStr1 = "2021-12-30 12:59:59";
    SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
    try {
        Date date1 = sdf.parse(dateStr1);
    } catch (ParseException e) {
        e.printStackTrace();
    }

    // Date -> String
    Date date2 = new Date();
    String dateStr2 = sdf.format(date2);
    */
2. thymeleaf中使用#dates这个公共的内置对象
   ${#dates.format(topic.topicDate ,'yyyy-MM-dd HH:mm:ss')}

3. 系统启动时，我们访问的页面是： http://localhost:8080/pro23/page.do?operate=page&page=login
   为什么不是： http://localhost:8080/pro23/login.html  ?
   答： 如果是后者，那么属于直接访问静态页面。那么页面上的thymeleaf表达式（标签）浏览器是不能识别的
       我们访问前者的目的其实就是要执行 ViewBaseServlet中的processTemplete()

4. http://localhost:8080/pro23/page.do?operate=page&page=login 访问这个URL，执行的过程是什么样的？
   答：
   http://  localhost   :8080   /pro23          /page.do                        ?operate=page&page=login
   协议       ServerIP   port    context root    request.getServletPath()         query string
   1) DispatcherServlet -> urlPattern :  *.do  拦截/page.do
   2) request.getServletPath() ->  /page.do
   3) 解析处理字符串，将/page.do -> page
   4) 拿到page这个字符串，然后去IOC容器（BeanFactory）中寻找id=page的那个bean对象   -> PageController.java
   5) 获取operate的值 -> page    因此得知，应该执行 PageController中的page()方法
   6) PageController中的page方法定义如下：
      public String page(String page){
        return page ;
      }
   7) 在queryString:   ?operate=page&page=login 中 获取请求参数，参数名是page，参数值是login
      因此page方法的参数page值会被赋上"login"
      然后return "login" , return 给 谁？？
   8) 因为PageController的page方法是DispatcherServlet通过反射调用的
      method.invoke(....) ;
      因此，字符串"login"返回给DispatcherServlet
   9) DispatcherServlet接收到返回值，然后处理视图
      目前处理视图的方式有两种： 1.带前缀redirect:    2.不带前缀
      当前，返回"login"，不带前缀
      那么执行  super.processTemplete("login",request,response);
   10) 此时ViewBaseServlet中的processTemplete方法会执行，效果是：
         在"login"这个字符串前面拼接 "/"  (其实就是配置文件中view-prefixe配置的值)
         在"login"这个字符串后面拼接 ".html" (其实就是配置文件中view-suffix配置的值)
         最后进行服务器转发

5. 目前我们进行javaweb项目开发的“套路”是这样的：
   1. 拷贝 myssm包
   2. 新建配置文件applicationContext.xml或者可以不叫这个名字，在web.xml中指定文件名
   3. 在web.xml文件中配置：
      1) 配置前缀和后缀，这样thymeleaf引擎就可以根据我们返回的字符串进行拼接，再跳转
          <context-param>
                                    <param-name>view-prefix</param-name>
                                    <param-value>/</param-value>
          </context-param>
          <context-param>
            <param-name>view-suffix</param-name>
            <param-value>.html</param-value>
          </context-param>
      2) 配置监听器要读取的参数，目的是加载IOC容器的配置文件（也就是applicationContext.xml）
          <context-param>
            <param-name>contextConfigLocation</param-name>
            <param-value>applicationContext.xml</param-value>
          </context-param>
   4. 开发具体的业务模块：
      1） 一个具体的业务模块纵向上由几个部分组成：
         - html页面
         - POJO类
         - DAO接口和实现类
         - Service接口和实现类
         - Controller 控制器组件
      2） 如果html页面有thymeleaf表达式，一定不能够直接访问，必须要经过PageController
      3） 在applicationContext.xml中配置 DAO、Service、Controller，以及三者之间的依赖关系
      4） DAO实现类中 ， 继承BaseDAO，然后实现具体的接口, 需要注意，BaseDAO后面的泛型不能写错。
      
          例如：
          public class UserDAOImpl extends BaseDAO<User> implements UserDAO{}
      5） Service是业务控制类，这一层我们只需要记住一点：
          - 业务逻辑我们都封装在service这一层，不要分散在Controller层。也不要出现在DAO层（我们需要保证DAO方法的单精度特性）
              - 当某一个业务功能需要使用其他模块的业务功能时，尽量的调用别人的service，而不是深入到其他模块的DAO细节
              6） Controller类的编写规则
              ① 在applicationContext.xml中配置Controller
              <bean id="user" class="com.atguigu.qqzone.controllers.UserController>
              那么，用户在前端发请求时，对应的servletpath就是   /user.do   , 其中的“user”就是对应此处的bean的id值
              ② 在Controller中设计的方法名需要和operate的值一致
              public String login(String loginId , String pwd , HttpSession session){
              return "index";
              }
              因此，我们的登录验证的表单如下：
          <form th:action="@{/user.do}" method="post">
            <inut type="hidden" name="operate" value="login"/>
          </form>
      ​    ③ 在表单中，组件的name属性和Controller中方法的参数名一致
      ​    <input type="text" name="loginId" />
      ​    public String login(String loginId , String pwd , HttpSession session){
      ​    ④ 另外，需要注意的是： Controller中的方法中的参数不一定都是通过请求参数获取的
      ​    if("request".equals...) else if("response".equals....) else if("session".equals....){
      ​      直接赋值
      ​    }else{
      ​      此处才是从request的请求参数中获取
      ​      request.getParameter("loginId") .....
      ​    }
      7）  DispatcherServlet中步骤大致分为：
          0. 从application作用域获取IOC容器
              1. 解析servletPath ， 在IOC容器中寻找对应的Controller组件
              2. 准备operate指定的方法所要求的参数
              3. 调用operate指定的方法
              4. 接收到执行operate指定的方法的返回值，对返回值进行处理 - 视图处理
      
      8) 为什么DispatcherServlet能够从application作用域获取到IOC容器？
         ContextLoaderListener在容器启动时会执行初始化任务，而它的操作就是：
         1. 解析IOC的配置文件，创建一个一个的组件，并完成组件之间依赖关系的注入
         2. 将IOC容器保存到application作用域
   
6. 修改BaseDAO，让其支持properties文件以及druid数据源连接池
   讲解了两种方式：
   
   1) 直接自己配置properties，然后读取，然后加载驱动.....
   2) 使用druid连接池技术，那么properties中的key是有要求的



# 第九章       Book_Project



## 项目代码（code-14-BookProject)



## 数据库设计

![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\09-book\01.数据库设计.png)

昨日内容：
1. 需求分析
2. 数据库设计
 1） 实体分析
    - 图书                Book
    - 用户                User
    - 订单                OrderBean
    - 订单详情             OrderItem
    - 购物车项             CartItem
     2） 实体属性分析
    - 图书 : 书名、作者、价格、销量、库存、封面、状态
    - 用户 : 用户名、密码、邮箱
    - 订单 : 订单编号、订单日期、订单金额、订单数量、订单状态、用户
    - 订单详情 : 图书、数量、所属订单
    - 购物车项 : 图书、数量、所属用户

今日内容：
1. 显示主页面(index页面)
  - 新建BookDAO 、 BookDAOImpl ： getBookList()
  - 新建BookService 、 BookServiceImpl : getBookList()
  - 新建BookController : index()
  - 编辑index.html
2. 首页上登录成功之后显示欢迎语和购物车数量
3. 点击具体图书的添加到购物车按钮
4. 购物车详情
5. 结账
   1) 订单表添加一条记录
   2) 订单详情表添加7条记录
   3) 购物车项表中需要删除对应的7条记录
6. 关于订单信息中的订单数量问题
7. 编辑购物车
8. 关于金额的精度问题
9. 过滤器判断是否是合法用户：
   - 解决方法：新建SessionFilter ， 用来判断session中是否保存了currUser
   - 如果没有currUser，表明当前不是一个登录合法的用户，应该跳转到登录页面让其登录

   - 现在添加了过滤器之后，出现了如下错误：
   localhost 将您重定向的次数过多。
   尝试清除 Cookie.
   ERR_TOO_MANY_REDIRECTS



昨日内容：
1. 显示主页面(index页面)
  - 新建BookDAO 、 BookDAOImpl ： getBookList()
  - 新建BookService 、 BookServiceImpl : getBookList()
  - 新建BookController : index()
  - 编辑index.html
2. 首页上登录成功之后显示欢迎语和购物车数量
3. 点击具体图书的添加到购物车按钮
4. 购物车详情
5. 结账
   1) 订单表添加一条记录
   2) 订单详情表添加7条记录
   3) 购物车项表中需要删除对应的7条记录
6. 关于订单信息中的订单数量问题
7. 编辑购物车
8. 关于金额的精度问题
9. 过滤器判断是否是合法用户：
   - 解决方法：新建SessionFilter ， 用来判断session中是否保存了currUser
   - 如果没有currUser，表明当前不是一个登录合法的用户，应该跳转到登录页面让其登录
   - 现在添加了过滤器之后，出现了如下错误：
   localhost 将您重定向的次数过多。
   尝试清除 Cookie.
   ERR_TOO_MANY_REDIRECTS



昨日内容：：
  1. 在注册页面显示验证码
   1) 添加jar
   2) 在web.xml文件中配置KaptchaServlet，以及配置相关的属性
   3) 在页面上访问这个Servlet，然后这个Servlet做两件事情：
      - 在页面上显示验证码图片
      - 在session作用域中保存验证码信息，对应的key存储在Constans这个常量接口中
   4) 用户在注册页面中输入验证码发送给服务器，那么需要和session中保存的进行比较
  2. 注册功能实现
  3. js中的正则表达式
   1) 三步骤：定义正则表达式对象（两种方式）；定义待校验的字符串；校验
   2) 正则表达式的规则：
      g  i  m
      . , \w , \W , \d , \D , \b , \s , \S , ^ , $
      [] , [^] , [-]
      * , + , ? , {n} , {n,} , {n,m}
      |

今日内容：
  1. 注册页面表单验证

    1) <form>有一个事件 onsubmit ,
        onsubmit="return false" , 那么表单点击提交按钮时不会提交
        onsubmit="return true" ,  那么表单点击提交按钮时会提交
    
    2) 获取文档中某一个节点的方式：
        //DOM:Document
        //var unameTxt = document.getElementById("unameTxt");
        //BOM:Browser
        //document.forms[0].uname


  2. 原生的Ajax（了解）

    第一步： 客户端发送异步请求；并绑定对结果处理的回调函数
    1) <input type="text" name="uname" onblur="ckUname()"/>
    2) 定义ckUname方法：
       - 创建XMLHttpRequest对象
       - XMLHttpRequest对象操作步骤：
         - open(url,"GET",true)
         - onreadyStateChange 设置回调
         - send() 发送请求
       - 在回调函数中需要判断XMLHttpRequest对象的状态:
         readyState(0-4) , status(200)
    第二步：服务器端做校验，然后将校验结果响应给客户端





# 第十章       cookie - exp - kaptcha



## 项目代码（code-15-cookie-kaptcha-js)



1. Cookie
   1. 创建Cookie对象
   2. 在客户端保存Cookie
   3. 设置Cookie的有效时长
      cookie.setMaxAge(60)  ， 设置cookie的有效时长是60秒
      cookie.setDomain(pattern);
      cookie.setPath(uri);
   4. Cookie的应用：
       4-1: 记住用户名和密码十天 setMaxAge(60 * 60 * 24 * 10)
       4-2: 十天免登录

2. Kaptcha
   1. 为什么需要验证码
   2. kaptcha如何使用:
      - 添加jar
      - 在web.xml文件中注册KaptchaServlet，并设置验证码图片的相关属性
      - 在html页面上编写一个img标签，然后设置src等于KaptchaServlet对应的url-pattern
   3. kaptcha验证码图片的各个属性在常量接口：Constants中
   4. KaptchaServlet在生成验证码图片时，会同时将验证码信息保存到session中
      因此，我们在注册请求时，首先将用户文本框中输入的验证码值和session中保存的值进行比较，相等，则进行注册

3. JS - Exp
   1)正则表达式的使用三步骤：
       1. 定义正则表达式对象
          正则表达式定义有两个方式：
          1) 对象形式
             var reg = new RegExp("abc")
          2) 直接量形式
             var reg = /abc/;
          3) 匹配模式：
           - g 全局匹配
           - i 忽略大小写匹配
           - m 多行匹配
           - gim这三个可以组合使用，不区分先后顺序
             例如： var reg = /abc/gim , var reg = new RegExp("abc","gim");
       2. 定义待校验的字符串
       3. 校验
   2)元字符
     . , \w , \W , \s , \S , \d , \D , \b , ^ , $

   3)[]表示集合
     [abc] 表示 a或者b或者c
     [^abc] 表示取反，只要不是a不是b不是c就匹配
     [a-c] 表示a到c这个范围匹配

   4) 出现的次数
     * 表示多次 （0 ~ n ）
     + 至少一次 ( >=1 )
       ? 最多一次 (0 ~ 1)
       {n} 出现n次
       {n,} 出现n次或者多次
       {n,m} 出现n到m次







# 第十一章       vue - axios - json



## 项目代码（code-16-vue-axios-json)

1. 回顾：
    Ajax : 异步的JavaScript and XML
    目的： 用来发送异步的请求，然后当服务器给我响应的时候再进行回调操作
    好处： 提高用户体验；局部刷新：降低服务器负担、减轻浏览器压力、减轻网络带宽压力
    开发步骤：
    
      1) 创建XMLHttpRequest
      2) 调用open进行设置："GET" , URL , true
      3) 绑定状态改变时执行的回调函数 - onreadystatechange
      4) 发送请求 - send()
      5) 编写回调函数，在回调函数中，我们只对XMLHttpRequest的readystate为4的时候感兴趣
                                我们只对XMLHttpRequest的status为200的时候感兴趣
    
    0: (Uninitialized) the send( ) method has not yet been invoked.
    1: (Loading) the send( ) method has been invoked, request in progress.
    2: (Loaded) the send( ) method has completed, entire response received.
    3: (Interactive) the response is being parsed.
    4: (Completed) the response has been parsed, is ready for harvesting.
    
    0 － （未初始化）还没有调用send()方法
    1 － （载入）已调用send()方法，正在发送请求
    2 － （载入完成）send()方法执行完成，已经接收到全部响应内容
    3 － （交互）正在解析响应内容
    4 － （完成）响应内容解析完成，可以在客户端调用了

今天内容：
1. Vue
    1) {{}} - 相当于innerText
    2) v-bind:attr 绑定属性值。例如，v-bind:value - 绑定value值
       简写：    :value
    3) v-model 双向绑定
       v-model:value   , 简写  v-model
    4) v-if , v-else , v-show
       v-if和v-else之间不能有其他的节点
       v-show是通过样式表display来控制节点是否显示
    5) v-for 迭代
       v-for={fruit in fruitList}
    6) v-on 绑定事件
    7) 其他：
       - trim:去除首尾空格 , split() , join()
       - watch表示侦听属性
       - 生命周期

2. Axios
   
   
   
   ![](C:\Users\FY\Desktop\笔记\学习笔记\JavaWeb_image\12-vue-axios\01.Axios示例.png)
   
   
   
   Axios是Ajax的一个框架,简化Ajax操作
   Axios执行Ajax操作的步骤：
   
   1. 添加并引入axios的js文件
   
   2-1. 客户端向服务器端异步发送普通参数值
    - 基本格式： axios().then().catch()
    - 示例：
      axios({
        method:"POST",
        url:"....",
        params:{
            uname:"lina",
            pwd:"ok"
        }
      })
      .then(function(value){})          //成功响应时执行的回调        value.data可以获取到服务器响应内容
      .catch(function(reason){});       //有异常时执行的回调          reason.response.data可以获取到响应的内容
   
                                                                   reason.message / reason.stack 可以查看错误的信息
   
    2-2. 客户端向服务器发送JSON格式的数据
    - 什么是JSON
      JSON是一种数据格式
      XML也是一种数据格式
      XML格式表示两个学员信息的代码如下：
      <students>
        <student sid="s001">
            <sname>jim</sname>
            <age>18</age>
        </student>
        <student sid="s002">
            <sname>tom</sname>
            <age>19</age>
        </student>
      </students>
      JSON格式表示两个学员信息的代码如下：
      [{sid:"s001",age:18},{sid:"s002",age:19}]
    - JSON表达数据更简洁，更能够节约网络带宽
    - 客户端发送JSON格式的数据给服务器端
    1) 客户端中params需要修改成：  data:
    2) 服务器获取参数值不再是 request.getParameter()...
       而是：
       StringBuffer stringBuffer = new StringBuffer("");
       BufferedReader bufferedReader = request.getReader();
       String str = null ;
       while((str=bufferedReader.readLine())!=null){
           stringBuffer.append(str);
       }
       str = stringBuffer.toString() ;
   
    3) 我们会发现 str的内容如下：
       {"uname":"lina","pwd":"ok"}
   
    -  服务器端给客户端响应JSON格式的字符串，然后客户端需要将字符串转化成js Object
