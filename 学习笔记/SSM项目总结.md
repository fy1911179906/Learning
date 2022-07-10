

# SSM项目



web项目的开发：如何分析，设计，编码，测试

## CRM 的技术架构

CRM 的技术架构：

​	视图层（View）：展示数据，跟用户交互。

​									html，css，js，jQuery，bootstrap（ext|easyUI），jsp

​	控制层（Controller）：控制业务处理流程（接收请求，接收参数，封装参数；根据不同的请求调用业务层处理业务；根据处理结果，返回响应信息。

​											（servlet，）springMVC（，webwork，struts1，struts2）

​	业务层（Servlet）：处理业务逻辑（处理业务的步骤以及操作的原子性。

​										JAVASE（工作流：activiti|JBPM）

​										1、添加学生

​										2、记录操作日志

​	持久层（Dao/Mapper）：操作数据库。

​												（jdbc，）mybatis（，hibernate，ibatis）

​												tbl_table------------------pojo

​	整合层：维护类资源，维护数据库资源

​					spring（IOC，AOP）（，ejb，corba）



## 软件开发的生命周期

1）招标：

​	投标：-----------标书（甲方，乙方）

2）可行性分析：------------可行性分析报告（技术，经济方面）

3）需求分析：--------------需求文档（产品经理，需求调研），（项目原型：容易确定需求，开发项目时作为jsp网页）

4）分析与设计：

​	架构设计：

​		物理架构设计：

​				应用服务器：tomcat（apache），weblogic（bea-->oracle），websphere（ibm），jboss（redhat），resin（MS）

​				数据库服务器：mysql，oracle，DB2，sqlserver，达梦

​		逻辑架构设计：代码分层

​				视图层-->控制层-->业务层-->持久层-->数据库

​		项目设计：---------项目设计文档

​				物理模型设计：那个表，那些字段，字段的类型和长度，以及表和表之间的关系

​				powerdesigner

​				逻辑模型设计：那些表，哪些属性和方法，方法的参数和返回值，以及表和表之间的关系

​				rational rose---------.pdl

​		界面设计：企业级应用 朴素-------项目原型

​							互联网应用 炫酷

​		算法设计：---------算法设计文档

5）搭建开发环境：--------技术架构文档

​		创建项目，添加 jar 包，添加配置文件，添加静态页面，添加公共类以及其他资源能够正常启动运行。

6）编码实现：---注释

7）测试：---------测试用例

8）试运行：------使用手册

9）上线：---------实施文档

10）运维：--------运维手册

11）文档编纂：





## CRM项目的核心业务

CRM项目的核心业务：

1）CRM项目的简介：Customer Relationship Management 客户关系管理系统

2）CRM项目的和业务：

​		系统管理功能：不是直接处理业务数据，为了保证业务管理的功能正常安全运行而设计的功能。

​									用户登录，安全退出，登录验证等

​									给超级管理员，开发和运维人员使用。

​		业务管理功能：处理业务数据

​									市场活动：市场部，设计市场活动营销活动

​									线索：销售部（初级销售），增加线索

​									客户和联系人：销售部（高级销售），有效地区分和跟踪客户和联系人

​									交易：销售部（高级销售），更好地区分和统计交易的各个阶段

​									售后回访：客服部，妥善安排售后回访。主动提醒

​									统计图表：管理层，统计交易表中各个阶段数据量





## CRM的表结构

```
tbl_user 		用户表


tbl_dic_type		数据字典类型表

tbl_dic_value		数据字典值


tbl_activity		市场活动表
tbl_activity_remark		市场活动备注表

tbl_clue		线索表
tbl_clue_remark		线索备注表

tbl_customer		客户表
tbl_customer_remark		客户备注表

tbl_contacts		联系人表
tbl_contacts_remark		联系人备注表

tbl_tran		交易表
tbl_tran_remark			交易备注表
tbl_tran_history		交易历史表

tbl_task		任务表
```

1）主键字段：在数据库表中，如果有一组字段能够唯一确定一条记录，则可以把它们设计成表的主键

​							推荐使用一个字段做主键，而且推荐使用没有业务含义的字段做主键，比如：id等。

​							主键字段的类型和长度由主键值的生成方式来决定：

​									主键值的生成方式：

​											1）自增：借助数据库自身主键生成机制

​																数值型长度由数据量来决定

​																运行效率低

​																开发效率高

​											2）assigned：程序员手动生成主键值，唯一非空，算法生成

​																	hi/low：数值型长度由数据量决定

​																	UUID：字符串长度是32位

​											3）共享主键：

​																	tbl_person					tbl_card

​																	id	 name            		id	 name

 																  1001	zs					  1001   card1

​																   1002    ls

​											4）联合主键：由多个字段的类型和长度决定

2）外键字段：用来确定表和表之间的关系。

​							1）一对多：一张表（A）中的一条记录可以对应另一张表的（B）中的多条记录；

​												  另一张表（B）中的一条记录只能对应一张表（A）的一条记录。

​												  添加数据时，先添加父表记录，再添加子表记录；

​												  删除数据时，先删除子表记录，再删除父表记录；



内连接：查询所有符合条件的数据，并且要求结果在两张表中都有相应的记录

左外连接：查询左侧表中所有符合条件的数据，即使在右侧表中没有相对应的记录

如果外键不能为空，优先使用内连接

如果外键可以为空，

​							--假如只需要查询那些在另一张表中有相应的记录，使用内连接

​							--假如需要查询左侧表中所有符合条件的记录，使用做左外连接







## 资源安全注意事项

```
添加静态页面资源
webapps
	|-->stumgr
	|-->crm
		|-->.html，.css，.js，.img
		|-->WEB-INF
			|-->web.xml
			|-->classes
			|-->lib
			
*web应用根目录下的内容都是不安全的，外界可以通过url直接访问；
所以，一般为了数据安全，都会把页面放到WEB-INF下，因为WEB-INF目录下的资源是受保护的，外界不能直接访问。

http://127.0.0.1:8080/crm/test.jsp

webapps
	|-->stumgr
	|-->crm
		|-->.css，.js，.img
		|-->WEB-INF
			|-->web.xml
			|-->classes
			|-->lib
			|-->pages test.jsp

```





## 同步请求和异步请求的区别

同步请求：浏览器窗口发出的请求，响应信息返回到浏览器窗口，所以会进行全局刷新。

异步请求：ajax发出的请求，响应信息返回到ajax的回调函数，既可以进行全局刷新，也可以进行局部刷新。



小结：如果需要进行全局刷新，推荐使用同步请求，当然也可以使用异步请求；

​			如果需要进行局部刷新，只能使用异步请求；

​			如果既可能进行全局刷新，也可能进行局部刷新，也只能使用异步请求。





## mybatis逆向工程

1）简介：根据表生成mapper层三部分代码：实体类，mapper接口，映射文件。

2）使用mybatis逆向工程：

​	a）创建工程：crm-mybatis-generator

​	b）添加插件：

```xml
<!--mybatis逆向工程插件-->
<plugin>
    <groupId>org.mybatis.generator</groupId>
    <artifactId>mybatis-generator-maven-plugin</artifactId>
    <version>1.3.2</version>
    <configuration>
        <verbose>true</verbose>
        <overwrite>true</overwrite>
    </configuration>
</plugin>
```

c）添加配置信息文件：

​	数据库连接信息

​	代码保存的目录

​	表的信息

d）运行 mybatis 的逆向工程，根据指定表生成 java 代码，保存到指定的目录中。





## 作用域传递

1、把控制层（controller）代码中处理好的数据传递到视图层（jsp），使用作用于传递

pageContext：用来在同一个页面的不同标签之间传递数据

request：在同一个请求过程中间传递数据

session：在同一个浏览器窗口的不同请求之间传递数据

application：所有用户共享的数据，并且长久频繁使用的数据





## 记住密码

记住密码：



后台（这个方案安全性有待商讨）：

​	上次登录成功，判断是否需要记住密码：如果需要记住密码，则往cookie里面添加属性，而且 cookie 的值必须是该用户的 loginAct 和 login Pwd

​	下次登录时，判断该用户有没有 cookie：如果有，则自动填写账号，而且填写的是 cookie 的值



浏览器显示：

​	1、使用 java 代码获取 cookie：

```java
Cookie[] cs = request.getCookie();
for(Cookie c : cs){
    if(c.getName().equals("loginAct")){
        String loginAct = c.getValue();
    }else if(c.getName().equals("loginPwd")){
        String loginPwd = c.getValue();
    }
}
```

2、使用 EL 表达式获取 cookie：

​	${cookie.loginAct.value}s

​	${cookie.loginPwd.value}



## 登录验证

登陆验证：

```
1）过滤器：
		a）implements Filter{
				--init
				--doFilter
				--destroy
			}
		b）配置过滤器：web.xml
	2）拦截器：
		a）提供拦截器类：implements HandlerInterceptor{
                                --pre
                                --post
                                --after
						}
		b）配置拦截器：springmvc.xml
```





## 为什么要使用函数

函数：如果一段用来完成特定功能的代码到处出来，封装成函数。

函数的参数：在编写函数的过程中，如果有一个或者多个数据无法确定，可以把这些数据定义成函数。





## 分页查询市场活动

演示分页查询市场活动的过程

queryActivityByConditionForPage(pageNo,pageSize)前端函数实现：

```
1、queryActivityByConditionForPage(1,10)
		|-->把pageNo，pageSize和查询条件一起发送到后台，查询数据
		|-->data
			|-->activityList：遍历list，显示列表
			|-->totalRows：调用工具函数，显示翻页信息
2、当用户切换页号或者每页显示条数时：pageNo，pageSize
		|-->翻页信息会自动变化
		|-->手动刷新列表：
			|-->把pageNo，pageSize和查询条件一起发送到后台，查询数据
			|-->data
				|-->activityList：遍历list，显示列表
				|-->totalRows：调用的工具函数，显示翻页信息
```



## 封装参数

封装参数：

​	1）如果做查询条件，或者参数之间不是属于一个实体类对象，封装成 map；

​	2）如果做写数据，并且参数本来就是属于一个实体类对象，封装成实体类对象。





## 导出文件

导出市场活动：

​	1）给“批量导出”按钮添加单击事件，发送导出请求

​	2）查询所有的市场活动

​	3）创建一个 excel 文件，并且把市场活动写到 excel 文件中

​	4）把生成的 excel 文件输出到浏览器（文件下载）

​	技术准备：

​		1）使用 java 生成 excel 文件：iText，apache-poi --------- 图形化 API（办公文档）

​				关于办公文档插件使用的基本思想：把办公文档的所有元素封装成普通的 Java 类，程序员通过操作这些类达到操作办公文档目的。

​				文件--------------HSSFWorkbook

​				页-----------------HSSFSheet

​				行-----------------HSSFRow

​				列-----------------HSSFCell

​				样式--------------HSSFCellStyle

​				使用 apache-poi 生成 excel：

​						a）添加依赖：

```xml
<!--poi依赖-->
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi</artifactId>
    <version>3.15</version>
</dependency>
```

​						b）使用封装类生成 excel 文件：

​		2）文件下载：







## 前端小知识

### 使用 jQuery 获取指定元素的指定属性的值

使用 jQuery 获取指定元素的指定属性的值：

选择器.attr("属性名");//用来获取那些值不是true/false的属性值。

选择器.prop("属性名");//用来获取那些值是true/false的属性值。例如：checked，selected，readonly，disabled等



### jQuery 事件函数的用法

jQuery 事件函数的用法：

```
选择器.click(function(){//给指定的元素添加事件
	//js代码
})
选择器.click();//在指定的元素上模拟发生一次事件
```



### 页面切割技术

```
1）<frameset>和<frame>
		<frameset>：用来切割页面
			<frameset cols="20%,60%,20%" rows="10%,80%,10%">
		<frame>：显示页面
			<frame src="url">
			
			<frameset cols="20%,60%,20%">
				<frame src="url1">
				<frame src="url2">
				<frame src="url3">
			</frameset>
			
			每一个<frame>标签就是一个独立的浏览器窗口。
2）<div>和<iframe>
		<div>：切割页面
			<div style="height:10%;width=20%">
		<iframe>：显示页面
			<div style="height:10%;width=20%">
				<iframe href="url">
			</div>
```



### 模态窗口控制

模态窗口：模拟的窗口，本质上是<div>，通过设置z-index大小来实现的；

​					初始时，z-index初始参数是 < 0，所以不显示；

​					需要显示时，z-index值设置成 > 0 即可。

控制模态窗口的显示和隐藏：

​	1）方式一：通过 data-toggle="modal" data-target="模态窗口的id"

​	2）方式二：通过js函数控制：

​							选择器(选中div).modal("show");//显示选中的模态窗口

​							选择器(选中div).modal("hide");//关闭选中的模态窗口

3）方式三：通过标签的属性 data-dismiss=""

​						点击添加了 data-dismiss=""属性的标签，自动关闭该标签所在的模态窗口。

模态窗口的意义：

​	window.open("url","_blank");

​	模态窗口本质生就是原来页面中的一个<div>，只有一个页面；所有的操作都是在同一个页面中完成。



### 前端插件使用

一类问题：

​	1）实现起来比较复杂

​	2）跟业务无关

1、日历插件：bootstrap-datetimepicker

​		前端插件使用步骤：

​				1）引入开发包：.js，.css

​						下载开发包，拷贝到项目webapp目录下

​						把开发包引入到 jsp 文件中：<link><script>

​				2）创建容器：<input type="text"><div>

​				3）当容器加载完成之后，对容器调用工具函数。

​		在指定的标签中显示 jsp 页面片段：

​		选择器.html(jsp页面片段的字符串);//覆盖显示

​		选择器.append(jsp页面片段的字符串);//追加显示

​		选择器.after(jsp页面片段的字符串);

​		选择器.before(jsp页面片段的字符串);

​		选择器.text(jsp页面片段的字符串);



​	2、分页查询插件：bs_pagination

​			前端插件使用步骤：

​				1）引入开发包：.js，.css

​						下载开发包，拷贝到项目webapp目录下

​						把开发包引入到 jsp 文件中：<link><script>

​				2）创建容器：<input type="text"><div>

​				3）当容器加载完成之后，对容器调用工具函数。



​	3、js 的系统函数：

​			1）eval()：eval() 函数计算 JavaScript 字符串，并把它作为脚本代码来执行。

​			2）parseInt()：获取小数的整数部分



### 给页面中的元素添加事件注意事项

在页面中给元素添加事件语法：

1）使用元素的事件属性：onxxxx="f()"

2）使用 jQuery 对象：选择器.xxxx(function(){//js代码});

​		*只能给**固定元素**添加事件

​		固定元素：当调用事件函数给元素添加事件时，如果元素已经生成，则这些元素叫作固定元素；

​		动态生成的元素：当调用事件函数给元素添加事件时，如果元素还没有生成，后来生成的元素叫作动态生成的元素。

```javascript
$("#tBody input[type='checkbox']").click(function () {
    //js代码
}
```



3）使用 jQuery 的 on 函数：父选择器.on("事件类型",子选择器,function(){//js代码});

​		父元素：必须是固有元素，可以直接父元素，也可以是间接父元素

​		事件类型：跟时间属性和事件函数一一对应。

​		子选择器：目标元素，跟父元素器构成一个父子选择器。

​		*不但能给固有元素添加事件，还能够给动态生成的元素添加事件。

```javascript
$("#tBody").on("click","input[type='checkbox']",function () {
    //js代码
}
```



### 使用 jQuery 设置指定元素的 value 属性值

使用 jQuery 获取或者设置指定元素的 value 属性值：

获取：选择器.val();

设置：选择器.val(属性值);



### ajax 请求参数 data 的数据格式

ajax向后台发送请求的时，可以通过 data 提交参数，data 的数据格式有三种格式：

```
1）data:{
		k1:v1,
		k2:v2,
		...
	}
	*劣势：只能向后台提交一个参数名对应一个参数值的数据，不能向后台提交一个参数名对应多个参数值的数据。
	 优势：操作简单
2）data:k1=v1&k2=v2&...
	*优势：不但能够向后台提交一个参数名对应一个参数值的数据，还能向后台提交一个参数名对应多个参数的数据
	 劣势：操作麻烦，只能向后台提交字符串数据
3）data:FormData 对象
	 优势：不但能提交字符串数据，还能提交二进制数据
	 劣势：操作更加复杂
	
	
```



