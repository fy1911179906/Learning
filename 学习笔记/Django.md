

## Django 配置

### Django 终端的基本命令

startproject #创建一个 Django项目// django-admin startproject 文件名

startapp #创建一个Django 应用//

check #校验项目完整性//

runserver #本地简单运行 Django 项目//python manage.py runserver

shell #进入Django 项目的 Python shell 环境//

test #执行 Django 用例测试//

### Django 终端的基本命令（数据库相关）

makemigrations #创建模型变更的迁移文件//

migrate #执行上一个命令创建的迁移文件//

dumpdata #把数据库数据导出到文件//

loaddata #把文件数据导入到数据库//



### Django 应用目录介绍

views.py：视图处理的地方

models.py：定义应用模型的地方

admin.py：定义 Admin 模块管理对象的地方

apps.py：声明应用的地方

tests.py：编写应用测试用例的地方

urls.py：（自行创建）管理应用路由的地方



### Django 模型层

 **模型层：**位于 Django 视图层和数据库之间，Python 对象和数据库表之间转换。可以屏蔽不同数据库之间的差异，开发者更加专注与业务逻辑的开发，提供很多便捷工具有助开发。例如，数据库迁移、结构变更等等。

**模型层定义字段：**数字类型：IntegerField；文本类型：TextField；日期类型：DateTimeField；字符类型：CharField；自增ID：AutoField；主键定义：primary_key 属性

**Django Shell：**Python Shell，用于交互式的 Python 编程。Django Shell也类似，继承 Django项目环境。



### 模块系统基本语法

变量标签：{{变量}}

for 循环标签：{% for x in list %},{% endfor %}

if-else分支标签：{% if %}，{% else %}，{% endif %}

模块视图渲染

![image-20211014230647577](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014230647577.png)

通过（split()）换行符切分成列表

![image-20211014231459963](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014231459963.png)

迭代器 enumerate() 函数

![image-20211014232622513](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014232622513.png)

![image-20211014232640654](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014232640654.png)



### paginator()组件进行分页

p=Paginator(列表参数，分页每页数目)

p.num_pages 可以打印分页的数量

p.count 可以打印列表的数量

page1=p.page(1) 可以获取第一页的分页

page1.object_list 可以打印第一页分页的列表

page1.has_previous() 判断是否有上一页

page1.has_next() 判断是否有下一页

![image-20211014234319279](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014234319279.png)

![image-20211014234351323](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014234351323.png)

![image-20211014234500371](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014234500371.png)

page = request.GET.get('page')获取 html 传递的 page 参数值

![image-20211014235046019](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014235046019.png)

![image-20211014235130947](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014235130947.png)

order_by('需按照排序的参数')

order_by('-需按照排序的参数')，加减号表示倒序排序

![image-20211014235638897](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014235638897.png)

![image-20211014235952454](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211014235952454.png)





**URL 的一般语法格式为：**

protocol://hostname[:post]/path[?query] [#fragment]

http://tts.tmooc.cn/video/showVideo?menuld=65421&version=AID999#subject

protocol(协议)、hostname(主机名)、post(端口号)、path(路由地址)、query(查询，传递信息)、fragment(信息片段，即锚点)



### Setting.py 配置文件

**BASE_DIR：**用于判定当前项目的绝对路径（动态计算出来的），所有文件夹都可以依赖此路径。

**DEBUG：**用于配置 Django 项目的启动模式，取值：

True 表示开发环境中使用 开发调试模式（用于开发中），1、可检测代码改动后，立即重启服务。2、报错页面。

False 表示当前项目运行在生产环境中

**ALLOWED_HOSTS：**设置允许访问本项目的 host 头值，[]空列表，表示只有请求中 host 127.0.0.1 ，localhost 能访问本项目 -DEBUG = TRUE 时有效，['*']，表示任何请求头的 host 都能访问到当前项目，['192.168.1.3','127.0.0.1'] 表示只有当前两个 host 头的值能访问当前项目。

**INSTALLED_APPS：**指定当前项目中安装的应用列表。

**MIDDLEWERE：**用于注册中间件。

**TEMPLATES：**用于指定模板的配置信息。

**DATABASES：**用于指定数据库的配置信息。

**LANGUAGE_CODE：**用于指定语言配置。英文："en-us"，中文："zh-Hans"

**TIME_ZONE：**用于指定当前服务器段时区。

**ROOT_URLCONF：**用于配置主 url 配置 'mysite1.urls'，ROOT_URLCONF='mysite1.urls'



### 视图函数

视图函数是用于接收一个浏览器请求（HttpRequest 对象）并通过 HttpResponse 对象返回相应的函数。此函数可以接收浏览器请求并根据业务逻辑返回相应的响应内容给浏览器。语法如下。

```python
def xxx_view(request[,其他参数]):

return HttpResponse 对象
```

view.py模块引用 locals() 函数会以字典类型返回当前位置的全部局部变量。

**path 转换器**

语法：<转换器类型：自定义名>

作用：若转换器类型匹配到对应类型的数据，则将数据按照关键字传参的方式传递给视图函数。

例子：path('page/< int:page >',views.xxx)

![](C:\Users\FY\Desktop\笔记\学习笔记\PythonWeb_image\path传参.png)

**re_path() 函数**

在 url 的匹配过程中可以使用正则表达式进行精确匹配。

语法：re_path(reg,view,name=xxx)

正则表达式为命名分组模式(?P< name >pattern);匹配提取参数后用关键字传参方式传递给视图函数。



## 请求中的方法



根据 HTTP 标准，HTTP 请求可以使用多种请求方法。

HTTP1.0定义了三种请求方法：GET、POST 和 HEAD 方法（最常用）

HTTP1.1新增了五种请求方法：OPTIONS、PUT、DELETE、TRACE 和 CONNECT 方法。

| 方法    | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| GET     | 请求指定的页面信息，并返回实体主体。                         |
| HEAD    | 类似于get请求，只不过返回的响应中没有具体的内容，用于获取报头。 |
| POST    | 向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST 请求可能会导致新的资源的建立和/或已有的资源的修改。 |
| PUT     | 从客户端向服务器传送的数据取代指定的文档的内容。             |
| DELETE  | 请求服务器删除指定的页面。                                   |
| CONNECT | HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器。     |
| OPTIONS | 允许客户端查看服务器的性能。                                 |
| TRACE   | 回显服务器收到的请求，主要用于测试或诊断。                   |



### Django 中的请求

请求在 Django 中实则就是视图函数的第一个参数，即 HttpRequest 对象。Django 接收到 http 协议的请求后，会根据请求数据报文创建 HttpRequest 对象。HttpRequest 对象通过属性描述了请求的所有相关信息。

path_info：URL 字符串

method：字符串，表示 HTTP 请求方法，常用值：'GET'、'POST'。

GET：QueryDict 查询字典的对象，包含 get 请求方式的所有数据。

POST：QueryDict 查询字典的对象，包含 post 请求方式的所有数据。

FILES：类似于字典的对象，包含所有的上传文件信息。

COOKIES：Python 字典，包含所有的 cookie，键和值都为字符串。

session：类似于字典的对象，表示当前的会话。

body：字符串，请求体的内容（POST 或 PUT）。

schema：请求协议（'http'/'https'）。

request.get_full_path：请求的完整路径。

request.META：请求中的元数据（消息头）。

request.META['REMOVE ADDR']：客户端 IP 地址。



### 响应状态码

HTTP 状态码的英文为 HTTP Status Code

下面是常见的 HTTP 状态码：

-200 -请求成功

-301 -永久重定向-资源（网页等）被永久转移到其它 URL

-302 -临时重定向

-404 -请求的资源（网页等）不存在

-500 -内部服务器错误

HTTP 状态码由三个十进制数字组成，第一个十进制数字定义了状态码的类型，后两个数字没有分类的作用。HTTP 状态码共分为5种类型：

| 分类 | 分类描述                                       |
| ---- | ---------------------------------------------- |
| 1**  | 信息，服务器收到请求，需要请求者继续执行操作   |
| 2**  | 成功，操作被成功接收并处理                     |
| 3**  | 重定向，需要进一步的操作或无法完成请求         |
| 4**  | 客户端错误，请求包含语法错误或无法完成请求     |
| 5**  | 服务器错误，服务器在处理请求的过程中发生了错误 |



构造函数格式：HttpRequest(content=响应体,content_type=响应体数据类型,status=状态码)。作用：向客户端浏览器返回响应，同时携带响应体内容。

常用的 Content-Type 如下

-'text/html' （默认的，html 文件）

-'text/plain' （纯文本）

-'text/css' (css 文件)

-'text/javascript' （js 文件）

-'multipart/form-data' （文件提交）

-'application/json' （json 传输）

-'application/xml' （xml 文件）



### HttpRequest 子类

| 类型                    | 作用           | 状态码 |
| ----------------------- | -------------- | ------ |
| HttpResponseRedirect    | 重定向         | 302    |
| HttpResponseNotModified | 未修改         | 304    |
| HttpResponseBadRequest  | 错误请求       | 400    |
| HttpResponseNotFound    | 没有对应的资源 | 404    |
| HttpResponseForbidden   | 请求被禁止     | 403    |
| HttpResponseServerError | 服务器错误     | 500    |



无论是 GET 还是 POST，统一都由视图函数接收请求，通过判断 request.method 区别具体的请求动作。

```python
样例：
if request.method == 'GET':
    处理 GET 请求时的业务逻辑
elif request.method == 'POST':
    处理 POST 请求时的业务逻辑
else:
    其他请求时的业务逻辑
```



### **GET 处理**

GET 请求动作，一般用于向服务器获取数据，能够产生 GET 请求的场景：

-浏览器地址栏中输入 URL，回车后

-<a href="地址?参数=值&参数=值">

-form表单中的 method 为 get

GET 请求方式中，如果有数据需要传递给服务器，通常会用查询字符串（Query String）传递【注意不要传递敏感数据】

GET 传递参数的长度本身没有限制，即入口没有限制。但是特定的浏览器会对其传递的长度有所限制，即出口有限制。

GET 请求通常用于查询。POST 请求通常用于增加（删除、修改也可以）。UPDATE 请求通常用于修改。DELETE 请求通常用于删除。

URL 格式：xxx？参数名1=值1&参数名2=值2...

-如 http://127.0.0.1:8000/page1?a=100&b=200

服务器端接收参数，获取客户端请求 GET 请求提交的数据，方法示例：

```python
request.GET['参数名']    #QueryDict
request.GET.get('参数名','默认值')
request.GET.getlist('参数名')
# mypage?a=100&b=200&c=300&b=400
# request.GET=QueryDict({'a':[100],'b':['200','400'],'c':['300']})
# a=request.GET['a']
# b=request.GET['b']  #Error
```

request.GET['参数名'] 比较暴力，无参数则会报错。?a=400&a=200&a=100，则request.GET['a'] 取最后一个。即100。

request.GET.get('参数名','默认值') 比较温柔，无参数也不会报错。

request.GET.getlist('参数名')，如果传参为?a=400&a=200&a=100。

就会返回[400,200,100]，该方法可用于问卷调查-兴趣爱好-复选框



### **POST 处理**

POST 请求动作，一般用于向服务器提交大量/隐私数据数据

客户端通过表单等 POST 请求将数据传递给服务器端，如

```html
<form method='post' action="/login">
    姓名：<input type="text" name="username">
    <input type="submit" value="登陆">
</form>
```

使用 post 方式接收客户端数据

```python
request.POST['参数名']  #request.POST 绑定 QueryDict
request.POST。get('参数名'，'默认值')
request.POST.getlist('参数名')
```

取消 csrf 验证，否则 Django 将会拒绝客户端发来的 POST 请求，报403响应

-禁止掉 setting.py 中 MIDDLEWARE 中的 CsrfViewMiddleWare 的中间件

```python
MIDDLEWARE = [
    ...
    # 'django.middleware.csrf.CsrfViewMiddleware',
]
```



## Django 的设计模型及模板层



### 传统的 MVC

MVC 代表 Model-View-Controller （模型-视图-控制器）模式

M 模型层（Model），主要用于对数据库层的封装

V 视图层 （View），用于向用户展示结果（What + How）

C 控制（Controller），用于处理请求、获取数据、返回结果（重要）

作用：降低模块间的耦合度（解耦）

![image-20211019232933914](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211019232933914.png)



### 模板配置

创建模板文件夹<项目名>/templates

在 setting.py 中 TEMPLATES 配置项

1、BACKEND：指定模板的引擎

2、DIRS：模板的搜索目录（可以是一个或多个）

3、APP_DIRS：是否要在应用中的 templates 文件夹中搜索模板文件

4、OPTIONS：有关模板的选项

配置项中需要修改部分

设置 DIRS - 'DIRS':[os.path.join(BASE_DIR,'templates')],



### 模板加载方式

方案一：通过 loader 获取模板，通过 HttpResponse 进行响应。在视图函数中：

```python
from django.templates import loader
# 1、通过 loader 加载模板
t = loader.get_template("模板文件名")
# 2、将 t 转换成 HTML 字符串
html = t.render(字段数据)
# 3、用响应对象将转换的字符串内容返回给浏览器
return HttpResponse(html)
```

方案二：使用 render() 直接加载并响应模板。在视图函数中：

```python
from django.shortcuts import render
return render(request,'模板文件名'，字段数据)
```



### 视图层与模板层之间的交互

1、视图函数中可以将 Python 变量封装到字典中传递到模板，样例：

```python
def xxx_view(request):
    dic={
        "变量1":"值1",
        "变量2":"值2"，
    }
    return render(request,'xxx.html',dic)
```

2、模板中，我们可以用 {{变量名}} 的语法调用视图传进来的变量，在模板中使用变量语法

{{变量名}}；{{变量名.index}}；{{变量名.key}}；{{对象.方法}}；{{函数名}}。样例：

```python
def test_html_param(request):
    dic={}
    dic['int'] = 88
    dic['str'] ='guoxiaonao'
    dic['lst'] = ['Tom','Jack','Lily']
    dic['dict'] = {'a':9,'b':8}
    dic['func'] = say_hi
    dic['class_obj'] = Dog()
    return render(request,'test_html_param.html',dic)
```



## 模板层 - 变量和标签



### 模板标签 - if 标签

**注意：**

1、if 条件表达式里可以用的运算符 ==，!=，<，>，<=，>=，in，not in，is，is not，not ，and，or

2、在 if 标记中使用实际括号是无效的语法。如果你需要它们指示优先级，则应使用嵌套的 if 标记。

官方文档：https://docs.djangoproject.com/zh-hans/2.2/ref/templates/builtins/#if

```html
<form action='/mycal' method="post">
    <input type="text" name="x" value="{{x}}">
    <select name="op">
        <option value="add" {% if op == 'add' %} selected{% endif %}>+加</option>
        <option value="sub" {% if op == 'sub' %} selected{% endif %}>-减</option>
        <option value="mul" {% if op == 'mul' %} selected{% endif %}>*乘</option>
        <option value="div" {% if op == 'div' %} selected{% endif %}>/除</option>
    </select>
    <input type="text" name="y" value="{{y}}">=<span>{{result}}</span>
    <div><input type="submit" value="开始计算"></div>   
</form>
```

```python
def test_mycal(request):
    if request.method == 'GET':
        return render(requeest,'mycal.html')
    elif: request.method == 'POST':
            # 处理计算
            x = int(request.POST['x'])
            y = int(request.POST['y'])
            op = request.POST['op']
            result = 0
            if op == 'add':
                result = x + y
            elif op == 'sub':
                result = x - y
            elif op == 'mul':
                result = x * y
            else op == 'div':
                result = x / y
     return render(request,'mycal.html',locals())
                
```



### 模板标签 - for 标签

语法：

```html
{% for 变量 in 可迭代对象 %}
    ... 循环语句
{% empty %}
    ... 可迭代对象无数据时填充的语句
{% endfor %}
```

官方文档：https://docs.djangoproject.com/zh-hans/2.2/ref/templates/builtins/#for

内置函数 - forloop

| 变量                | 描述                                |
| ------------------- | ----------------------------------- |
| forloop.counter     | 循环的当前迭代（从1开始索引）       |
| forloop.counter0    | 循环的当前迭代（从0开始索引）       |
| forloop.revcounter  | counter 值的倒序                    |
| forloop.revcounter0 | revcounter 值的倒序                 |
| forloop.first       | 如果这是第一次通过循环，则为真      |
| forloop.last        | 如果这是最后一次循环，则为真        |
| forloop.parentloop  | 当嵌套循环，parentloop 表示外层循环 |

```html
{% for name in lst %}
{% if forloop.first %}&&&&&{% endif %}
      <p>{{forloop.counter}}  {{name}}</p>
{% if forloop.last %}====={% endif %}
{% empty %}
当前无数据
{% endfor %}
```



## 模板层 - 过滤器和继承



### 模板过滤器

定义：在变量输出时对变量的值进行处理

作用：可以通过使用过滤器来改变变量的输出显示

语法：{{变量 | 过滤器1:'参数值1' | 过滤器2:'参数值2'...}}

官方文档：https://docs.djangoproject.com/en/2.2/ref/templates/builtins

常用过滤器

| 过滤器            | 说明                                                         |
| ----------------- | ------------------------------------------------------------ |
| lower             | 将字符串转换为全部小写                                       |
| upper             | 将字符串转换为大写形式                                       |
| safe              | 默认不对变量内的字符串进行html转义                           |
| add:"n"           | 将从 value 的值增加 n                                        |
| truncatechars:"n" | 如果字符串字符多于指定的字符数量，那么会被截断。阶段的字符串将可以翻译的省略号序列（“...”）结尾 |



### 模板的继承

模板继承可以是父模板的内容重用，子模板直接继承父模板的全部内容并可以覆盖父模板中相应的块

语法  - 父模板中：

定义父模板中的块 block 标签

标识出哪些在子模板中是允许被修改的

block 标签：在父模板中定义，可以在子模板中覆盖

语法 - 子模板中：

继承模板 extends 标签（写在模板文件的第一行）。例如：{% extends 'base.html' %}

子模板重写父模板中的内容块

{% block block_name %}

子模板块用来覆盖父模板中 block_name 块的内容

{% endblock %}

重写的覆盖规则：不重写，将按照父模板的效果显示；重写，则按照重写效果显示。

**注意：**模板继承时，服务器端的动态内容无法继承。即父模板接收的参数，子模板无法继承。



## url 反向解析



### 代码中 url 出现位置

1、模板【html 中】

```html
1、<a href="url"> 超链接 </a>  //点击后页面跳转至 url
2、<form action="url" method="post"></form> //form 表单中的数据用 post 方法提交至 url
```

2、视图函数中 - 302跳转 HttpResponseRedirect('url') 将用户地址栏中的地址跳转到 url



### 代码中 url 书写规范

1、绝对地址：http://127.0.0.1:8000/page/1

2、相对地址：

一、'/page/1'，以 ‘/’ 开头的相对地址，浏览器会把当前地址栏里的协议，IP 端口号加上这个地址，作为最终访问地址，即如果当前页面地址栏为 http://127.0.0.1:8000/page/3；当前相对地址最终结果为 http://127.0.0.1:8000 + /page/1

二、'page/1'，没有 ‘/’ 开头的相对地址，浏览器会根据当前 url 的最后一个 / 之前的内容加上该相对地址作为最终访问地址，例如当前地址栏地址为 http://127.0.0.1:8000/topic/detail；则该相对地址最终结果为 http:127.0.0.1:8000/topic/ + page/1



### url 反向解析

url 反向解析是指在视图或模板中，用 path 定义的名称来动态查找或计算出相应路由

path 函数的语法

path(route,view,name="别名")

path('/page',views.page_view,name="page_url")

根据 path 中的 name=关键字传参给 url 确定了一个唯一确定的名字，在模板或视图中，可以通过这个名字反向推断出 url 信息

模板中 - 通过 url 标签实现地址的反向解析

{% url '别名' %}

{% url '别名' '参数值1' '参数值2' %}

样例：

{% url 'pagen' '400' %}

{% url 'person' age='18' name='gxn' %}

```python
html: <a href="{% url 'tr' '18' %}">url 反向解析</a>
url.py: path('/test_url_result/<int:age>',views.test_url_result,name='tr')
```

**在重定向的时候使用反向解析用 reverse方法**，在视图函数中 --> 可以调用 django 中的 reverse 方法进行反向解析

```python
from django.urls import reverse
reverse('别名',args=[],kwargs={})
样例：
print(reverse('pagen',args=[300]))
print(reverse('person',kwargs={'name':'xixi','age':18}))
```



## 静态文件



### 静态文件配置

静态文件配置 - setting.py 中

1、配置静态文件的访问路径【该配置默认存在】

通过哪个 url 地址找静态文件

STATIC_URL = '/static/'

说明：指定访问静态文件时是需要通过 /static/xxx 或 http://127.0.0.1:8000/static/xxx [xxx 表示具体的静态资源位置]

2、配置静态文件的存储路径 STATICFILES_DIRS，STATICFILES_DIRS 保存的是静态文件在服务器端的存储位置

 #  file: setting.py

STATICFILES_DIRS =(os.path.join(BASE_DIR,"static"),)



### 静态文件访问

模板中访问静态文件 - img 标签为例

方案：通过{% static %}标签访问静态文件

1、加载 static - {% load static %}

2、使用静态资源 - {% static '静态资源路径' %}

3、样例：<img src="{% static 'images/logo.jpg' %}">



## Django 应用及分布式路由



### Django 应用

什么是应用：应用在 Django 项目中是一个独立的业务模块，可以包含自己的路由，视图，模板，模型。

创建应用步骤

步骤一：用 manage.py 中的子命令 startapp 创建应用文件夹 - python manage.py startapp music

步骤二：在 setting.py 的 INSTALLED_APPS 列表中配置安装此应用

setting.py 配置样例 INSTALLED_APPS = ['user','music']



### 分布式路由

Django 中，主路由配置文件（url.py）可以不处理用户具体路由，主路由配置文件的可以做请求的分支（分布式请求处理）。具体的请求可以由各自的应用来进行处理。

![image-20211020211959019](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211020211959019.png)



### 配置分布式路由

步骤一：主路由中调用 include 函数

语法：include('app名字.url模块名')

作用：用于将当前路由转到各个应用的路由配置文件的 urlpatterns 进行分布式处理

样例：

```python
# 主路由 urls.py
urlpattern = [
    path('admin/',admin.site.urls),
    path('test_static',views.test.static),
    path('music/',include('music.urls'))
]
# music 路由 urls.py
urlpattern = [
    #http://127.0.0.1:8000/music/index
    path('index/',views.index_view)
]
```



### 应用下的模板

应用内部可以配置模板目录

1、应用下手动创建 templates 文件

2、setting.py 中开启应用模板功能 - TEMPLATE 配置中的 'APP_DIRS' 值为 TRUE 即可

应用下 templates 和 外层 templates 都存在时，django 得查找模板规则

1、优先查找外层 templates 目录下的模板

2、按 INSTALLED_APPS 配置下的应用顺序逐层查找



## Django 模型层及ORM介绍



### Django 配置 MySQL

安装 mysqlclient [版本 mysqlclient 1.3.13 以上，官网目前为1.4x]

安装前确认 ubuntu 是否安装 python3-dev 和 default-libmysqlclient-dev

1、sudo apt list -- installedgrep -E 'libmysqlclient-dev|python3-dev'

2、sudo pip3 freeze|grep -i 'mysql' 语句可以查看安装版本

3、若命令无输出则需要安装 - sudo apt -get install python3-dev default-libmysqlclient-dev

4、sudo pip3 install mysqlclient



**创建数据库，进入 mysql 数据库执行**

create database 数据库名 default charset utf8

通常数据库名跟项目名保持一致

**setting.py 里进行数据库的配置**

修改 DATABASES 配置项的内容，由 sqlite3 变成 mysql

```python
DATABASES = {
    'default':{
        'ENGINE':'django.db.backends.mysql', #ENGINE - 指定数据库存储引擎/sqlite3/oracle/postgresql
        'NAME':'tb_admin',                   #NAME - 指定要连接的数据库名称
        'USER':'root',                       #USER - 指定登录到数据库的用户名
        'PASSWORD':'123456',                 #PASSWORD - 数据库的密码
        'HOST':'127.0.0.1',                  #HOST/POST - 连接具体数据库的 IP 和 端口 
        'POST':'3306'
    }
}
```



### 什么是模型

模型是一个 Python 类，它是由 django.db.models.Model 派生出得子类

一个模型类代表数据库中的一张数据表

模型类中每一个类属性都代表数据库的一个字段

模型是数据交互的接口，是表示和操作数据库的方法和方式



### ORM 框架

定义：ORM（Object Relational Mapping）即对象关系映射，它是一种程序技术，它允许你使用类和对象对数据库进行操作，从而避免通过 SQL 语句操作数据库。

作用：

1、建立模型类和表之间的对应关系，允许我们通过面向对象的方式来操作数据库。

2、根据设计的模型类生成数据库中的表格。

3、通过简单的配置就可以进行数据库的切换。

优点：

只需要面向对象编程，不需要面向数据库编写代码。

---对数据库的操作都转化成对类属性和方法的操作

---不用编写各种数据库的 sql 语句

实现了数据模型与数据库的解耦，屏蔽了不同数据库操作上的差异。

---不再关注用的是 MySQL、oracle... 等数据库的内部细节

---通过简单的配置就可以轻松更换数据库，而不需要修改代码

模型类代码示例：

```python
# file : bookstore/models.py
from django.db import models
class Book(models.Model):
    title = models.CharField("书名",max_length=50,default='')
    price = models.DecimalField("定价",max_digits=7,decimal_place=2,default=0.0)
    
即模型类 - 创建方式
from django.db import models
class 模型类名(models.Model):
    字段名 = models.字段类型(字段选项)
```

MySQL 显示的表名为（应用名_模型类名）全小写



## ORM - 基本字段及选项



### 模型类 - 字段类型

**BooleanField()**

数据库类型：tinyint(1)

编程语言中：使用 True 或 False 来表示值

在数据库中：使用 1 或 0 类表示具体的值

**CharField()**

数据库类型：varchar

注意：必须要指定 max_length 参数值

**DateField()**

数据库类型：date

作用：表示日期

参数：

auto_now：每次保存对象时，自动设置该字段为当前时间（取值：True/False）。

auto_now_add：当对象第一次被创建时自动设置当前时间（取值：True/False）。

default：设置当前时间（取值：字符串格式时间如：'2019-6-1'）。-------------------以上三个参数只能多选一

**DateTimeField()**

数据库类型：datetime(6)

作用：表示日期和时间

参数同DateField

**FloatField()**

数据库类型：double

编程语言中和数据库中都使用小数表示值

**DecimalField()**

数据库类型：decimal(x,y)

编程语言中：使用小数表示该列的值

在数据库中：使用小数

参数：

max_digits：位数总数，包括小数点后的位数。该值必须大于等于 decimal_places

decimal_places：小数点后的数字数量

**EmailField()**

数据库类型：varchar--------------------**虽然是 varchar 类型，但是 Django 给 EmailField 加了正则表达式约束**

编程语言和数据库中使用字符串

**IntegerField()**

数据库类型：int

编程语言和数据库中使用整数

**ImageField()**

数据库类型：varchar(100)

作用：在数据库中为了保存图片的路径

编程语言和数据库中使用字符串

**TextField()**

数据库类型：longtext

作用：表示不定长的字符数据



### 模型类 - 字段选项

字段选项，指定创建的列的额外的信息

允许出现多个字段选项，多个选项之间使用，隔开

**primary_key**

如果设置为 True，表示该列为主键，如果指定一个字段为主键，则此数据库不创建 id 字段

**blank**

设置为 True 时，字段可以为空。设置为 False 时，字段是必须填写的。 ------------**blank 为空与 null 不一样，blank 是在 admin 后台编辑时是否可以为空**

**null**

如果设置为 True，表示该列值允许为空。

默认为 False，如果此选项为 False 建议加入 default 选项来设置默认值（即最好加上 defaultt）

**default**

设置所在列的默认值，如果字段选项 null=False 建议添加此项

**db_index**

如果设置为 True，表示为该列增加索引

**unique**

如果设置为 True，表示该字段在数据库中的值必须是唯一（不能重复出现的）

**db_column**

指定列的名称，如果不指定的话，则采用属性名作为列名

**verbose_name**

设置此字段在 admin 界面上的显示名称



字段选项样例：

```python
#创建一个属性，表示用户名称，长度三十个字符，必须是唯一的，不能为空，添加索引
name = models.CharField(max_length=30,unique=True,null=False,db_index=True)
```



## ORM - 基本操作及创建数据



### Meta 类 - 定义

使用内部 Meta 类，来给模型赋予属性，Meta 类下有很多内建的类属性，可对模型类做一些控制

示例：

```python
# file : bookstore/models.py
from django.db import models

class Book(models.Model):
    title = models.CharField("书名",max_length=50,default='')
    price = models.DecimalField("定价",max_digits=7,decimal_places=2,default=0.0)
    
    class Meta:
        db_table = 'book'  #可改变当前模型类对应的表名
```



### 常见问题处理一

![image-20211022212009761](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022212009761.png)

![image-20211022212035939](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022212035939.png)

![image-20211022212053286](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022212053286.png)



### 常见问题处理二

![image-20211022212221779](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022212221779.png)

![image-20211022212241198](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022212241198.png)



### ORM 操作

基本操作包括增删改查操作，即（CRUD操作）

CRUD 是指在做计算处理时得增加（Create）、读取查询（Read）、更新（Update）和删除（Delete）

ORM CRUD 核心 -> 模型类.管理器对象

**管理器对象**

每个继承自 models.Model 模型类，都会有一个 objects 对象被同样继承下来。这个对象叫管理器对象

数据库的增删改查可通过模型的管理器实现

```python
# file/models.py
class MyModel(models.Model):
    ...
# file/views.py
def show_model(request):
    MyModel.objects.create(...)   # objects 是管理器对象
```

**创建数据**

Django ORM 使用一种直观的方式把数据库表中的数据表示成 Python 对象。创建数据中的每一条记录就是创建一个数据对象。

方案1：

```python
MyModel.objects.create(属性1=值1,属性2=值2,...)
#成功：返回创建好的实体对象
#失败：抛出异常
```

方案2：

创建 MyModel 实例对象，并调用 save() 进行保存

```python
obj = MyModel(属性1=值1,属性2=值2)
obj.属性=值
obj.save()
```



### Django Shell

在 Django 提供了一个交互式操作项目叫 Django Shell 它能够在交互模式用项目工程的代码执行相应的操作。利用 Django Shell 可以代替编写 view 的代码来进行直接操作

**注意：**项目代码发生变化时，重新进入 Django Shell

启动方式：python3 manage.py shell



## ORM - 查询操作



### 查询方法

数据库的查询需要使用管理器对象进行，通过 MyModel.objects 管理器方法调用查询方法。

| 方法      | 说明                                 |
| --------- | ------------------------------------ |
| all()     | 查询全部记录，返回 QuerySet 查询对象 |
| get()     | 查询符合条件的单一记录               |
| filter()  | 查询符合条件的多条记录               |
| exclude() | 查询符合条件之外的全部记录           |



**all() 方法**

用法：MyModel.objects.all()

作用：查询 MyModel 实体中所有的数据

等同于 select * from table

返回值：QuerySet 容器对象，内部存放 MyModel 实例

```python
from bookstore.models import Book
books = Book.objects.all()
for book in books:
    print("书名",book.title,"出版社：",book.pub)
```

 可以在模型类中定义 __ str __ 方法，自定义 QuerySet 中的输出格式例如在 Book 模型类下定义如下：

```python
def __str__(self):
    return '%s_%s_%s_%s'%(self.title,self.price,self.pub,self.market_price)
```

![image-20211022220157385](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022220157385.png)



**values('列1','列2'...)**

用法：MyModel.objects.values(...)

作用：查询部分列的数据返回

等同于 select 列1，列2 from xxx

返回值：QuerySet。返回查询结果容器，容器内存字典，每个字点代表一条数据，格式为：{'列1':值1，'列2':值2}

![image-20211022220224415](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022220224415.png)



**values_list('列1','列2'...)**

用法：MyModel.objects.values_list(...)

作用：返回元组形式的查询结果

等同于 select 列1,列2 from xxx

返回值：QuerySet 容器对象，内部存放 ‘元组’。会将查询出来的数据封装到元组中，再封装到查询集合 QuerySet 中

![image-20211022220843083](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022220843083.png)



**order_by()**

用法：MyModel.objects.order_by('-列','列')

作用：与 all() 方法不同，它会用 SQL 语句的 ORDER BY 字句对查询结果进行根据某个字段选择性的进行排序

说明：默认是按照升序排序，降序排序则需要在列前增加 ‘-’ 表示

![image-20211022221322515](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211022221322515.png)



**filter(条件)**

语法：MyModel.objects.filter(属性1=值1,属性2=值2)

作用：返回包含此条件的全部的数据集

返回值：QuerySet 容器对象，内部存放 MyModel 实例

说明：当多个属性在一起时为“与”关系，即当

filter 样例：

```python
# 查询书中出版社为“清华大学出版社”的图书
from bookstore.models import Book
books = Book.objects.filter(pub="清华大学出版社")
for book in books:
    print("书名",book.title)
# 查询 Author 实体中 name 王老师并且 age 是28岁的
authors = Author.objects.filter(name="王老师",age=28)
```



**exclude(条件)**

语法：MyModel.objects.exclude(条件)

作用：返回不包含此条件的全部的数据集

示例：查询清华大学出版社，定价等于50以外的全部图书

```python
books = models.Book.objects.exclude(pub="清华大学出版社",price=50)
for book in books:
    print(book)
```



**get(条件)**

语法：MyModels.objects.get(条件)

作用：返回满足条件的唯一一条数据

说明：该方法只能返回一条数据，查询结果多于一条数据则抛出 Model.MultipleObjectsReturned 异常，查询结果如果没有数据则抛出 Model.DoesNotExist 异常



### 查询谓词

定义：做更加灵活的条件查询时需要使用查询谓词

说明：每一个查询谓词是一个独立的查询功能

**__exact：等值匹配**

示例：

```python
Author.objects.filter(id__exact=1)  #等同于 select * from author where id=1;
```

**__contains：包含指定值**

示例：

```python
Author.objects.filter(name__contains="w")  #等同于 select * from author where name like '%w%';
```

**__startswith：以 XXX 开始**

示例：

```python
Author.objects.filter(name__startswith="w")  #等同于 select * from author where name like 'w%';
```

**__endswith：以 XXX 结束**

示例：

```python
Author.objects.filter(name__endswith="w")  #等同于 select * from author where name like '%w';
```

**__gt：大于指定值**

示例：

```python
Author.objects.filter(age__gt=50)  #等同于 select * from author where age > 50;
```

**__gte：大于等于指定值**

**__lt：小于指定值**

**__lte：小于等于指定值**

**__in：查找数据是否在指定范围内**

示例：

```python
Author.objects.filter(country__in=["中国","日本","韩国"])
# 等同于 select * from author where country in ("中国","日本","韩国");
```

**__range：查找数据是否在指定的区间范围内**

示例：

```python
# 查找年龄在某一区间内的所有作者
Author.objects.filter(age__range(35,50))
# 等同于 select * from author where author between 35 and 50;
```

更多精彩，请参考官方文档

https://docs.djangoproject.com/en/2.2/ref/models/querysets/#field-lookups



### 更新方法

**更新单个数据**

修改单个实体的某些字段值的步骤：

1、查：通过 get() 得到要修改的实体对象

2、改：通过对象.属性的方式修改数据

3、保存：通过对象.save() 保存数据

```python
b1 = Book.objects.get(id=1)
b1.price=22
b1.save()
```

**批量更新数据**

直接调用 QuerySet 的 update(属性=值)实现批量修改

```python
# 将 id 大于3的所有的图书价格定为0元
books = Book.objects.filter(id__gt=3)
books.update(price=0)
# 将所有属的零售价定为100元
books = Book.objects.all()
books.update(market_price=100)
```



### 删除方法

**单个数据删除**

步骤：1、查找查询结果对应的一个数据对象。2、调用这个数据对象的 delete() 方法实现删除

```python
try:
    auth = Author.objects.get(id=1)
    auth.delete()
except:
    print('删除失败')
```

**批量删除**

步骤：1、查找查询结果集中满足条件的全部 QuerySet查询集合对象。2、调用查询集合对象的 delete() 方法实现删除

```python
# 删除全部作者中，年龄大于65的全部信息
auths = Author.objects.filter(age__gt=65)
auths.delete()
```

**伪删除**

通常不会轻易在业务里把数据真正删除，取而代之的是做伪删除，即在表中添加一个布尔型字段（is_active）默认是 True；执行删除时，将欲删除数据的 is_active 字段设置为 False

注意：用伪删除时，确保显示数据的地方，均加了 is_active=True 的过滤查询

```python
try:
    book = Book.objects.get(id=book_id,is_active=True)
except Exception as e:
    print('delete book get error %s'%(e))
    return HttpResponse('---The book id is error')
book.is_active = False
book.save()
return HttpResponseRedirect('/boostore/all_book')
```



## F 对象和 Q 对象



### F 对象

一个 F 对象代表数据库中某条记录的字段信息

作用：通常是对数据库的字段值再不获取的情况下进行操作，用于类属性（字段）之间的比较。

语法：

```python
from django.db.models import F
F('列名')
```

示例1：更新 Book 实例中所有的零售价涨10元

```python
Book.objects.all().update(market_price=F('market_price')+10)
# update 'bookstore_book' set 'market_price' = ('bookstore_book'.'market_price'+10);
#以上做法好于如下代码
books = Book.objects.all()
for book in books:
    book.market_price=book.market_price+10
    book.save()
```

示例2：点赞增加

```python
def add_like(request,topic_id):
    topic = Topic.objects.get(id=topic_id)
    #更新 old->  update topic set like = 1 where id = xxx;
    new_like = topic.like + 1
    topic.like = new_like
    topic.save()
    #F 对象  F ->  update topic set like = like + 1 where id = xxx;
    topic.like=F('like') + 1
    topic.save()
```

示例三：对数据库中两个字段的值进行比较，列出哪儿些书的零售价高于定价？

```python
from django.db.models import F
from bookstore.models import Book
books = Book.objects.filter(market_price__gt=F('price'))
# select * from 'bookstore_book' where 'bookstore_book'.'market_price' > ('bookstore_book'.'price')
for book in books:
    print(book.title,'定价：',book.price,'现价：',book.market_price)
```



### Q 对象

当在获取查询结果集使用复杂的逻辑或 |、逻辑非 ~ 等操作时可以借助于 Q 对象进行操作

如：想找出定价低于20元 或 清华大学出版社的全部书，可以写成

```python
Book.objects.filter(Q(price__lt=20) | Q(pub="清华大学出版社"))
```

Q 对象在数据包 django.db.models 中。需要先导入再使用

作用在条件中用来实现除 and(&) 以外的 or(|) 或 not(~) 操作

运算符： & 与操作；| 或操作；~ 非操作。

语法：

```python
from django.db.models import Q
Q(条件1) | Q(条件2)   #条件1成立或条件2成立
Q(条件1) & Q(条件2)   #条件1和条件2同时成立
Q(条件1) &~ Q(条件2)  #条件1成立且条件2不成立
...
```

示例：

```python
from django.db.models import Q
#  查找清华大学出版社的书或价格低于50的书
Book.objects.filter(Q(market_price__lt=50) | Q(pub_house='清华大学出版社'))
#  查找不是机械工业出版社的书且价格低于50的书
Book.objects.filter(Q(market_price__lt=50) &~ Q(pub_house='机械工业出版社'))
```



## 聚合查询和原生数据库操作



### 聚合查询 - 整表聚合

不带分组的聚合查询是指导将全部数据进行集中统计查询

聚合函数[需要导入]：

导入方法：from django.db.models import *

聚合函数：Sum、Avg、Count、Max、Min

语法：MyModel.objects.aggregate(结果变量名=聚合函数('列'))

返回结果：结果变量名和值组成的字典

格式为：{"结果变量名":值}



### 聚合查询 - 分组聚合

分组聚合是指通过计算查询结果中每一个对象所关联的对象集合，从而得出总计值（也可以是平均值或总和），即为查询集的每一项生成聚合。

语法： - QuerySet.annotate(结果变量名=聚合函数('列'))

返回值： - QuerySet

通过先使用查询结果 MyModel.objects.values 查找查询要分组聚合的列：MyModel.objects.values('列1','列2')，如

```python
pub_set = Book.objects.values('pub')
print(pub_set)
```

![image-20211023123154130](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211023123154130.png)

![image-20211023123123097](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211023123123097.png)



### 原生数据库操作

Django 也可以支持直接用 sql 语句的方式通信数据库

查询：使用 MyModel.objects.raw() 进行数据库查询操作查询

语法：MyModel.objects.raw(sql语句,拼接参数)

返回值：RawQuerySet 集合对象【只支持基础操作，比如循环】

```python
books = models.Book.objects.raw('select * from bookstore_book')
for book in books:
    print(book)
```



### 原生数据库操作 - SQL 注入

使用原生语句时小心 SQL 注入

定义：用户通过数据上传，将恶意的 SQL 语句提交服务器，从而达到攻击效果。

案例1：用户在搜索好友的表单框里输入 ‘1 or 1=1’

```python
s1 = Book.objects.raw('select * from bookstore_book where id=%s'%('1 or 1 = 1'))
```

攻击结果：可查询所有用户数据

sql 注入防范：

```python
错误 -> s1 = Book.objects.raw('select * from bookstore_book where id=%s'%('1 or 1 = 1'))
# SQL 语句，where int型id='1 or 1 = 1'，匹配的是字符串的第一个字符
正确 -> s1 = Book.objects.raw('select * from bookstore_book where id=%s',['1 or 1 = 1'])
```



### 原生数据库操作 - cursor

完全跨过模型类操作数据库 - 查询/更新/删除

1、导入 cursor 所在的包：from django.db import connection

2、用创建 cursor 类的构造函数创建 cursor 对象，再使用 cursor 对象，为保证再出现异常时能释放 cursor 资源，通常使用 with 语句 进行创建操作

```python
from django.db import connection
with connection.cursor() as cur:
    cur.execute('执行 SQL 语句','拼接参数')

示例：
# 用SQL语句将id为10的书的出版社改为"XXX出版社"
from django.db import connection
with connection.cursor() as cur:
    cur.execute('update bookstore_book set pub_house="XXX出版社" where id = 10;')
    
with connection.cursor() as cur:
    # 删除id为1的一条记录
    cur.execute('delete from bookstore_book where id = 1;')
```



## admin 后台管理



### 模型管理器类

使用方法

1、在<应用app>/admin.py 里定义模型管理器类

```python
class XXXXManage(admin.ModelAdmin):
...
```

2、绑定注册模型管理器和模型类

```python
from django.contrib import admin
from .models import *
admin.site.register(YYYY,XXXXManager)  #绑定 YYYY 模型类与管理器类 XXXXManage
```

作用：为后台管理界面添加便于操作的新功能

说明：后台管理器类继承自 django.contrib.admin 里的 ModelAdmin 类



### 注册自定义模型类

若要自定义的模型类也能在 /admin 后台管理器中显示和管理，需要将自己的类注册到后台管理界面

注册步骤：

1、在应用 app 中的 admin.py 中导入注册要管理的模型 models 类，如：from .models import Book

2、调用 admin.site.register 方法进行注册，如：admin.site.register(自定义模型类)

案例：

```python
# file:bookstore/admin.py
from django.contrib import admin
from .models import Book
class BookManage(admin.ModelAdmin):
    list_display = ['id','title','price','market_price']
admin.site.register(Book,BookManager)
# file:bookstore/models.py
class Book(models.Model):
    title = models.CharField(verbose="书名",max_length=50,default='',unique=True)
    pub = models.CharField("出版社名称",max_length=100,default='')
    price = models.DecimalField("价格",max_digits=7,decimal_places=2)
    market_price = models.DecimalField("零售价",max_digits=7,decimal_places=2,default=0.0)
    is_active = models.BooleanField("是否活跃",default=True)
    
    class Meta:
        db_table = 'book'
```



模型管理器类

1、list_display：去控制哪些字段会显示在 Admin 的修改列表页面中

2、list_display_links：可以控制 list_display 中的字段是否应该链接到对象的“更改”页面

3、list_filter：设置激活 Admin 修改列表页面右侧栏中的过滤器

4、search_fields：设置启用 Admin 更改列表页面上的搜索框。

5、list_editable：设置为模型上的字段名称列表，这将允许在更改列表页面上进行编辑

参考官方文档：https://docs.djangoproject.com/en/2.2/ref/contrib/admin/

```python
# file:bookstore/admin.py
class BookManager(admin.ModelAdmin):
    #列表页显示哪些字段的列
    list_display = ['id','title','pub','price']
    #控制 list_display 中的字段，那些可以链接到修改页
    list_display_links = ['title']
    #添加过滤器
    list_filter = ['pub']
    #添加搜索框[模糊查询]
    search_fields = ['title']
    #添加可在列表页编辑的字段
    list_editable = ['price']
```



### 再谈Meta 类

通过 Meta 内嵌类定义模型类的属性，用法如下：

```python
class Book(models.Model):
    title = CharField(...)
    
    class Meta:
        db_table = '数据表名' #该模型所用的数据表的名称。（设置完成后需要立马更新同步数据库）
        verbose_name = '单数名' #给模型对象的一个易于理解的名称（单数），用于显示在 admin 管理界面中
        verbose_name_plural = '复数名' #该对象复数形式的名称（复数），用于显示在 admin 管理界面中
```



## 关系映射

在关系型数据库中，通常不会把所有数据都放在同一张表中，不易于扩展，常见关系映射：

1、一对一映射

2、一对多映射

3、多对多映射



### 一对一映射

语法：OneToOneField(类名，on_delete=xxx)

```python
class A(model.Model):
    ...
class B(model.Model):
    属性 = models.OneToOneField(A,on_delete=xxx)
```

**特殊字段选项【必须】**

on_delete - 级联删除

1、models.CASCADE 级联删除。Django 模拟 SQL 约束 ON DELETE CASCADE 的行为，并删除包含 ForeignKey 的对象

2、models.PROTECT 抛出 ProtectError 以阻止被引用对象的删除；[等同于 mysql 默认的 RESTRICT]

3、SET_NULL 设置 ForeignKey null；需要指定 null = True

4、SET_DEFAULT 将 ForeignKey 设置为其默认值；必须设置 ForeignKey 的默认值

更多精彩，请参考官方文档：https://docs.djangoproject.com/en/2.2/ref/models/fields/#foreignkey

示例：

```python
from django.db import models
class Author(models.Model):
    # 作家模型类
    name = models.CharField("作家",max_length=50)
class wife(models.Model):
    # 作家妻子模型类
    name = models.CharField("妻子",max_length=50)
    author = models.OneToOneField(Author,on_delete=models.CASCADE) #增加一对一属性
```

**一对一【创建数据】**

无外键的模型类[Author]：

```python
author1 = Author.objects.create(name="王老师")
```

有外键的模型类[Wife]

```python
wife1 = Wife.objects.create(name="王夫人",author=author1)  #关联王老师obj
wife1 = Wife.objects.create(name="王夫人",author_id=1)     #关联王老师对应主键值
```

**一对一【查询数据】**

1、正向查询：直接通关外键查询，则称为正向查询

```python
# 通过 wife 找 author
from .models import Wife
wife = Wife.objects.get(name="王夫人")
print(wife.name,"的老公是",wife.author.name)
```

2、反向查询：没有外键属性的一方，可以通过调用反向属性查询到关联的另一方。反向关联属性为 ‘实例对象.引用类名（小写）’，如作家的反向引用为 ‘作家对象.wife’。当反向引用不存在时，则会触发异常

```python
author1 = Author.objects.get(name="王老师")
author.wife.name
```

**一对一【模型创建】**

```python
# models.py
class Author(models.Model):
    #wife反向属性
    name = models.CharField('姓名',max_length = 11)
class Wife(models.Model):
    name = models.CharField('姓名',max_length=11)
    author = models.OneToOneField(Author,on_delete = models.CASCADE)
```



### 一对多映射



**一对多 - 定义**

一对多是表示现实事物间存在的一对多的对应关系。

如：一个学校有多个班级，一个班级有多名学生，一本图书只能属于一个出版社，一个出版社允许出版多本图书。

一对多需要明确出具体角色，在多表上设置外键

**一对多 - 创建**

语法：当一个A类对象可以关联多个B类对象时

```python
class A(models.Model):
    pass 
class  B(models.Model):
    属性 = models.ForeignKey("一"的模型类,on_delete = xx)
```

**一对多【模型创建】**

```python 
# models.py
class Publisher(models.Model):
    #出版社[一]
    name = models.CharField('出版社名称',max_length = 50)
class Book(models.Model):
    #书名[多]
    title = models.CharField('书名',max_length=50)
    publisher = models.ForeignKey(Publisher,on_delete = models.CASCADE)
```

**注意：ForeignKey 必须指定 on_delete 模式**



**一对多【创建数据】**

先创建 “一”，再创建 “多”。

```python
from .models import *
pub1 = Publisher.objects.create(name = "清华大学出版社")
b1 = Book.objects.create(title='C++',publisher = pub1)
b2 = Book.objects.create(title='Java',publisher_id = 1)
```



**一对多【查询数据】**

1、正向查询【通过 Book 查询 Publisher】

通过 publisher 属性查询即可 -- book.publisher

```python
abook = Book.objects.get(id = 1)
print(abook.title,'的出版社时是',abook.publisher.name)
```

2、反向查询【通过 Publisher 查询对应的所有的 Book】。需要用到**反向属性**

```python
# 通过出版社查询对应的书
pub1 = Publisher.objects.get(name='清华大学出版社')
books = pub1.book_set.all() #通过 book_set 获取 pub1 对应的多个 Book 数据对象
# books = Book.objects.filter(publisher = pub1) # 也可以采用此方式获取
print('清华大学出版社的书有：')
for book in books:
    print(book.title)
```



### 多对多映射



**多对多 - 定义**

多对多表达对象之间多对多复杂关系，如：每个人都有不同的学校（小学、初中、高中...），每个学校都不同的学生...

mysql 中创建多对多需要依赖第三张表来实现

Django 中无需手动创建第三张表，Django 自动完成

语法：在关联的两个类中的任意一个类中，增加：

属性 = models.ManyToManyField(MyModel)

**多对多 - 创建**

用法示例 - 创建模型类

```python
class Author(models.Model):
    '''作者模型类'''
    name = models.CharField('作家',max_length=50)
    def __str__(self):
        return self.name
class Book(models.Model):
    '''书模型类'''
    title = models.CharField('书名',max_length=50)
    authors = models.ManyToManyField(Author)
    def __str__(self):
        return self.title
```

**多对多【模型创建】**

```python
class Author(models.Model):
    name = models.CharField('姓名',max_length=11)
class Book(models.Model):
    title = models.CharField('书名',max_length=11)
    authors = models.ManyToManyField(Author)
```

**多对多【创建数据】**

方案1：先创建 author，再关联 book

```python
author1 = Author.objects.create(name='吕老师')
author2 = Author.objects.create(name='王老师')
#吕老师和王老师同时写了一本 Python
book11 = author1.book_set.create(title="Python")
author2.book_set.add(book11)
```

方案2：先创建 book，再关联 author

```python
book = Book.objects.create(title='python1')
# 郭晓闹和吕老师都参与了 python1 的创作
author3 = book.authors.create(name='guoxiaonao')
book.authors.add(author1)
```

**多对多【查询数据】**

1、正向查询有多对多属性的对象查另一方，通过 Book 查询对应的所有的 Author，此时多对多属性等价于 objects。

book.authors.all() -> 获取 book 对应的所有的 author 的信息

book.authors.filter(age__gt=80) -> 获取 book 对应的作者中年龄大于80岁的作者的信息

2、反向查询，通过 Author 查询对应的所有的 Book，利用反向属性 book_set

author.book_set.all()

author.book_set.filter()





## Cookies 和 Session



### 会话定义

打开浏览器访问一个网站，到关闭浏览器结束此次访问，称之为一次会话

HTTP 协议是无状态的，导致会话状态难以保持

试想一下，如果不保持会话状态，在电商网站购物的场景体验？

**Cookies 和 Session 就是为了保持会话状态而诞生的两个存储技术**

![image-20211107223726285](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211107223726285.png)



### Cookies

**Cookies - 定义**

cookies 是保存在客户端浏览器上的存储空间

Chrome 浏览器可能通过开发者工具的 Application >> Storage >> 'Cookies' 查看和操作浏览器端所有的 Cookies 值

火狐浏览器可能通过开发者工具的存储 -> Cookies 查看

**Cookies - 特点**

cookies 在浏览器上是以键 - 值对的形式进行存储的，键和值都是以ASCLL字符串的形式存储（不能是中文字符串）

cookies 中的数据是按域存储隔离的，不同的域之间无法访问

cookies 的内部的数据会在每次访问此网站时都会携带到服务器端，如果 cookies 过大会降低响应速度

**Cookies 的使用 - 存储**

HttpResponse.set_cookies(key,value='',max_age=None,expires=None)

-- key.cookies 的名字

-- value:cookies的值

-- max_age:cookies 存活时间，秒为单位

-- expires:具体过期时间

-- 当不指定 max_age 和 expires 时，关闭浏览器时此数据失效

存储示例：

添加 cookies

```python
#为浏览器添加键为 my_var1，值为123，过期时间为1个小时的cookies
responds = HttpResponse('已添加 my_var1，值为123')
responds.set_cookies('my_var1',123,3600)
return responds
```

修改 cookies

```python
#为浏览器添加键为 my_var1，修改值为456，过期时间为2个小时的cookies
responds = HttpResponse('已修改 my_var1，值为456')
responds.set_cookies('my_var1',456,3600*2)
return responds
```

删除 cookies

```python
# 删除指定的 key 的 Cookies。如果 key 不存在则什么也不发生
HttpResponse.delete_cookies(key)
# 删除浏览器键为 my_var1 的 cookies
response = HTTPResponse('已删除 my_var1')
response.delete_cookies('my_var1')
return response
```

获取 cookies

通过 request.COOKIES 绑定的字典（dict）获取客户端的 COOKIES 数据

```python
# 通过 request.COOKIES 绑定的字典（dict）获取客户端的 COOKIES 数据
value = request.COOKIES.get('cookies名','默认值')
# 获取浏览器中 my_var 变量对应的值
value = request.COOKIES.get('my_var1','没有值')
print('cookies my_var1 =',value)
return HttpResponse('my_var1:'+ value)
```

通过两个方法读写 cookies

```python
def set_cookies(request):
    resp =HttpResponse('set cookies is ok')
    resp.set_cookies('uname','gxn',500)
    return resp
def get_cookies(request):
    value = request.COOKIES.get('uname')
    return HttpResponse('value is %s'%(value))
```

![image-20211108175247831](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211108175247831.png)

![image-20211108175947391](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211108175947391.png)



### Session

![image-20211108180121265](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211108180121265.png)



**session 定义**

session 是服务器上开辟一段空间用于保留浏览器和服务器交互时的重要数据

实现方式

--使用 session 需要在浏览器客户端启动 cookies，且在 cookies 中存储 sessionid

--每个客户端都可以在服务器端有一个独立的 Session

--注意：不同的请求者之间不会共享这个数据，与请求者一一对应。

**session初始配置**

session.py 中配置 session

1、向 INSTALLED_APPS 列表中添加：

```python
INSTALLED_APPS = [
    # 启用 session 应用
    'django.contrib.session',
]
```

2、向 MIDDLEWARE 列表中添加：

```python
MIDDLEWARE = [
    # 启用 session 中间件
    'django.contrib.sessions.middleware.SessionMiddleware',
]
```

**session 的使用**

session 对象是一个类似于字典的 SessionStore 类型的对象，可以用类拟于字典的方式进行操作

session 能够存储如字符串，整型，字典，列表等。

1、保存 session 的值到服务器

```python
request.session['KEY'] = VALUE
```

2、获取 session 的值

```python
value = request.session['KEY']
value = request.session.get('KEY',默认值)
```

3、删除 session

```python
del request.session['KEY']
```

settings.py 中相关配置项

1、SESSION_COOKIES_AGE

作用：指定 sessionid 在 cookies 中保存时长（默认是2周），如下：例如：SESSION_COOKIES_AGE = 60 * 60 * 24 * 7 * 2

2、SESSION_EXPIRE_AT_BROWSER_CLOSE = True

设置只要浏览器关闭时，session 就失效（默认值为False）

注意：Django 中的 session 数据存储在数据库中，所以使用 session 前需要确保已经执行过 migrate

通过两种方法读写 session

```python
def set_session(request):
    request.session['uname'] = 'wwc'
    return HttpResponse('set session is ok')
def get_cookies(request):
    value = request.COOKIES.get('uname')
    return HttpResponse('value is %s'%(value))
```

**Django session 的问题**

1、django_session 表是单表设计；且该表数据量持续增持【浏览器故意删除 sessionid&过期数据未删除】

2、可以每晚执行 python3 manage.py clearsessions 【该命令可删除已过期的 session 数据】

**Cookies vs Session**

| 种类    | 存储   | 安全性     |
| ------- | ------ | ---------- |
| Cookies | 浏览器 | 相对不安全 |
| Session | 服务器 | 相对安全   |





## 缓存



### 缓存的定义

定义：缓存是一类可以更快的读取数据的介质统称，也指其它可以加快数据读取的存储方式。一般用来存储临时数据，常用介质的是读取速度很快的内存。

意义：视图渲染有一定的成本，数据库的频繁查询过高；所以对于低频变动的页面可以考虑使用缓存技术，减少实际渲染次数；用户拿到响应的时间成本会更低。

**缓存案例**

```python
from django.shortcuts import render
def index(request):
    #时间复杂度极高的渲染
    book_list = Book.objects.all() #->此处假设耗时2s
    return render(request,'index.html',locals())
```



### 设置缓存

**Django 中设置缓存 - 数据库缓存**

将缓存的数据存储在您的数据库中，说明：

尽管存储介质没有更换，但是当把一次负责查询的结果直接存储到表里，比如多个条件的过滤查询结果，可避免重复进行复杂查询，提升效率；

```python
CACHES = {
    'default':{
        'BACKEND':'django.core.cache.backends.db.DatabaseCache',
        'LOCATION':'my_cache_table',
        'TIMEOUT':300,#缓存保存时间，单位秒，默认值为300，
        'OPTIONS':{
            'MAX_ENTRIES':300,#缓存最大数据条数
            'CULL_FREQUENCY':2,#缓存条数达到最大值时，删除1/x的缓存数据
        }
    }
}
```

**Django 中设置缓存 - 本地内存缓存**

数据缓存到服务器内存中，配置样例：

```python
CACHES = {
    'default':{
        'BACKEND':'django.core.cache.backends.locmem.LocMemCache',
        'LOCATION':'unique-snowflake',
    }
}
```

**Django 中设置缓存 - 文件系统缓存**

将缓存的数据存储到本地文件中，配置样例：

```python
CACHES = {
    'default':{
        'BACKEND':'django.core.cache.backends.filebased.FileBasedCache',
        'LOCATION':'/var/tmp.django_cache',#这个是文件夹的路径，例如：'c:\test\cache'
    }
}
```



### 使用缓存

**Django 中使用缓存 - 视图函数中**

样例：

```python
from django.views.decorators.cache import cache_page
@cache_page(30) #->单位s
def my_view(request):
    pass
```

**Django 中使用缓存 - 路由中**

样例：

```python
from django.views.decorators.cache import cache_page
urlpatterns = [
    path('foo/',cache_page(60)(my_view)),
]
```



### 缓存 api 的使用

先引入 cache 对象

方式1：使用 caches['CACHE 配置 key'] 导入具体对象

```python
from django.core.cache import caches
cache1 = caches['myalias']
cache2 = caches['myalias_2']
```

方式2：from django.core.cache import cache 相当于直接引入 CACHES 配置项中的 'default' 项



1、cache.set(key,value,timeout) - 存储缓存

key：缓存的 key，字符串类型

value：Python 对象

timeout：缓存存储时间(s)，默认为 CACHES 的 TIMEOUT 值

返回值：None

2、cache.get(key) - 获取缓存

key：缓存的 key

返回值：为 key 的具体值，如果没有数据，则返回 None

3、cache.add(key,value) - 存储缓存，只在 key 不存在时生效

返回值：True[存储成功] or False [存储失败]

4、cache.get_or_set(key,value,timeout) - 如果未获取到数据，则执行 set 操作

返回值：value

5、cache.set_many(dict,timeout) - 批量存储缓存

dict：key 和 value 的字典

timeout：存储时间(s)

返回值：插入不成功的 key 的数组

6、cache.get_many(key_list) - 批量获取缓存数据

key_list：包含 key 的数组

返回值：取到的 key 和 value 的字典

7、cache.delete(key) - 删除 key 的缓存数据

返回值：None

8、cache.delete_many(key_list) - 批量删除

返回值：None



### 浏览器缓存定义

浏览器也具备缓存技术，对于浏览来说，每次向服务器发出请求都是耗时的操作，如果本身浏览器内部就具备当前 Url 的内容，则一定时间内可以不必给浏览器发消息，从而提升网民体验，降低服务器请求压力

![image-20211110221522837](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211110221522837.png)



### 浏览器缓存 - 强缓存

不会向服务器发送请求，直接从缓存中读取资源

1、响应头 - Expires

定义：缓存过期时间，用来指定资源到期的时间，是服务器端的具体的时间点

样例：Expires:Thu,02 Apr 2030 05:14:08 GMT

2、响应头 - Cache-Control

HTTP/1.1 中，Cache-Control 主要用于控制网页缓存。比如当 ‘Cache-Control:max-age=120’ 代表请求创建时间后的120秒，缓存失效。

说明：目前服务器会带着这两个头同时响应给浏览器，浏览器优先使用 Cache-Control

![image-20211110222859965](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211110222859965.png)



### 协商缓存

强缓存中的数据一旦过期，还需要跟服务器进行通信，从而获取最新数据；

思考？如果强缓存的数据是一些静态文件，大图片等；

解答：考虑到大图片这类比较费带宽且不易变化的数据，强缓存时间到期后，浏览器会去跟服务器协商，当前缓存是否可用，如果可用，服务器不必返回数据，浏览器继续使用原来缓存的数据，如果文件不可用，则返回最新数据。

**1、Last-Modified 响应头和 If-Modified-Since 请求头**

说明：

（1）Last-Modified 为文件的最近修改时间，浏览器第一次请求静态文件时，服务器如果返回 Last-Modified 响应头，则代表该资源为需协商的缓存

（2）当缓存到期后，浏览器将获取到的 Last-Modified 值做为请求头 If-Modified-Since 的值，与服务器请求协商，服务端返回304响应码[响应体为空]，代表缓存继续使用，200响应码代表缓存不可用 [响应体为最新资源]。

**2、ETag 响应头和 If-None-Match 请求头**

说明：

（1）Etag 是服务器响应请求时，返回当前资源文件的一个唯一标识（由服务器生成），只要资源有变化，Etag就会重新生成；

（2）当缓存到期后，浏览器将 ETag 响应头的值做为 If-None-Match 请求头的值，与服务器发请求协商；服务器接到请求头后，比对文件标识，不一致则认为资源不可用，返回200响应码代表缓存不可用 [响应体为最新资源]，可用则服务端返回304响应码[响应体为空]，代表缓存继续使用。



## 中间件



### 中间件的定义

中间件是 Django 请求/响应处理的钩子框架。它是一个轻量级的、低级的 “插件” 系统，用于全局改变 Django 的输入或输出。

中间件以类的形式体现

每个中间件组件负责做一些特定的功能。例如，Django 包含一个中间件组件 AuthenticationMiddleware，它使用会话将用户与请求关联起来。

![image-20211117140033746](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117140033746.png)



### 编写中间件

中间件类须实现下列五个方法中的一个或多个：

process_request(self,request)

执行路由之前被调用，在每个请求上调用，返回 None 或 HttpResponse 对象

process_view(self,request,callback,callback,callback_args,callback_kwargs)

调用视图之前被调用，在每个请求上调用，返回 None 或 HttpResponse 对象

process_response(self,request,response)

所有响应返回浏览器被调用，在每个请求上调用，返回 HttpResponse 对象

process_exception(self,request,exception)

当处理过程中抛出异常时调用，返回一个 HttpResponse 对象

process_template_response(self,request,response)

在视图函数执行完毕且试图返回的对象中包含 render 方法时被调用；该方法需要返回实现了 render 方法的响应对象

**注：**中间件中大多数方法在返回 None 时表示忽略当前操作进入下一项事件，当返回 HttpResponse 对象时表示此请求结束，直接返回给客户端。



### 注册中间件

setting.py 中需要注册一下自定义的中间件

```python
# file : setting.py
MIDDLEWARE = [
    ...
    'middleware.mymiddleware.MyMW',
    'middleware.mymiddleware.MyMW2'
]
```

**注意：**配置为数组，中间件被调用时以 ‘先上到下’ 再 ‘由下到上’ 的顺序调用

创建 mymiddleware 的包，然后创建 __ init __.py 和 mymiddleware.py

![image-20211117141705102](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117141705102.png)

```python
from django.utils.deprecation import MiddlewareMixin
class MyMW(MiddlewareMixin):
    def process_request(self,request):
        print('MyMW process_request do ---')
    def process_view(self,request,callback,callback_args,callback_kwargs):
        print('MyMW process_views do ---')
    def process_response(self,request,response):
        print('MyMW process_response do ---')
        return response #必须返回一个 response
```

```python
# views.py
def test_mw(request):
    print('-s-test_mw view in ---')
    return HttpResponse('--test-mw---')
# urls.py
path('test_mw',views.test_mw)
```

![image-20211117143006307](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117143006307.png)



```python
from django.utils.deprecation import MiddlewareMixin
class MyMW(MiddlewareMixin):
    def process_request(self,request):
        print('MyMW process_request do ---')
    def process_view(self,request,callback,callback_args,callback_kwargs):
        print('MyMW process_views do ---')
    def process_response(self,request,response):
        print('MyMW process_response do ---')
        return response #必须返回一个 response
    
class MyMW2(MiddlewareMixin):
    def process_request(self,request):
        print('MyMW2 process_request do ---')
    def process_view(self,request,callback,callback_args,callback_kwargs):
        print('MyMW2 process_views do ---')
    def process_response(self,request,response):
        print('MyMW2 process_response do ---')
        return response #必须返回一个 response
```

![image-20211117143235555](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117143235555.png)



**练习：**

用中间件实现强制某个 IP 地址只能向 /test 开头的地址发送 5 次请求。

提示：request.META['REMOTE_ADDR'] 可以得到远程客户端的 IP 地址 request.path_info 可以得到客户端访问的请求路由信息。

```python
# mymiddleware.py
class VisitLimit(MiddlewareMixin):
    def process_request(self,request):
        ip_address = request.META['REMOTE_ADDR']
        path_url = request.path_info
        if not re.match('^/test',path_url):
            return
        times = self.visit_times.get(ip_address,0)
        print('ip',ip_address,'已经访问',times)
        self.visit_times[ip_address] = times + 1
        if times < 5:
            return
        return HttpResponse('您已经访问过' + str(times) + '次，访问被禁止')
```



![image-20211117144309424](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117144309424.png)

![image-20211117144349522](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117144349522.png)

![image-20211117144416573](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117144416573.png)



### CSRF 攻击

CSRF - 跨站伪造请求攻击

某些恶意网站上包含链接、表单按钮或者Javascript，它们会利用登陆过的用户在浏览器中的认证信息试图在你的网站上完成某些操作，这就是跨站请求伪造（CSRF，即 Cross-Site Request Forgey）。

![image-20211117144838448](C:\Users\FY\AppData\Roaming\Typora\typora-user-images\image-20211117144838448.png)



### CSRF 防范

django 采用 ‘比对暗号’ 机制防范攻击

Cookies 中存储暗号1，模板中表单里藏着暗号2，用户只有在本网站下提交数据，暗号2才会随表单提交给服务器，django 对比两个暗号，对比成功，则认为是合法请求，否则是违法请求 - 403响应码

配置步骤：

1、setting.py 中确认 MIDDLEWARE 中 django.middleware.csrf.CsrfViewMiddleware 是否打开

2、模板中，form 标签下添加如下标签 {% csrf_token %}

特殊说明：

如果某个视图不需要 django 进行 csrf 保护，可以用装饰器关闭对此视图的检查

样例：

```python
from django.views.decorators.csrf import csrf_exempt

@csrf_exempt
def my_view(request):
    return HttpResponse('Hello World')
```



## 分页



### 分页定义

分页是指 web 页面有大量数据需要显示，为了阅读方便在每个页面中只显示部分数据。

优点：

1、方便阅读

2、减少数据提取量，减轻服务器压力

--Django 提供了 Paginator 类可以方便的实现分页功能

Paginator 类位于 'django.core.paginator' 模块中。



### Paginator 对象

负责分页数据整体的管理

对象的构造方法

```python
paginator = Paginator(object_list,per_page)
-参数
     -object_list 需要分类数据的对象列表
     -per_page 每页数据个数
-返回值
     -Paginator 的对象
```



### Paginator 属性

--count：需要分页数据的对象总数

--num_pages：分页后的页面总数

--page_range：从1开始的 range 对象，用于记录当前面码数

--per_page：每页数据的个数



### Paginator 方法

paginator对象.page(number)

--参数 number 为页码信息（从1开始）

--返回当前 number 页对应的页信息

--如果提供的页码不存在，抛出 InvalidPage 异常



### Paginator 异常 exception

InvalidPage：总的异常基类，包含以下两个异常子类

--PageNotAnlnteger：当向 page()传入一个不是整数的值时抛出

--EmptyPage：当向 page() 提供一个有效值，但是那个页面上没有任何对象时抛出



### Page 对象方法

has_next()：如果有下一页返回 True

has_previous()：如果有上一页返回 True

has_other_pages()：如果有上一页或下一页返回 True

next_page_number()：返回下一页的页码，如果下一页不存在，抛出 InvalidPage 异常

previous_page_number()：返回上一页的页码，如果上一页不存在抛出 InvalidPage 异常

**使用案例：**

```python
def test_page(request):
    # test_page/4
    # test_page?page=1
    page_num = request.GET.get('page',1)
    all_data = ['a','b','c','d','e']
    # 初始化paginator
    paginator = Paginator(all_data,2)
    # 初始化 具体页码的page对象
    c_page= paginator。page(int(page_num))
    return render(request,'test_page.html',locals())
```

```html
{% for p in c_page %}
<p>{{p}}</p>
{% endfor %}
{% if c_page.has_previous %}
<a href="/test_page?page={{c_page.previous_page_number}}">上一页</a>
{% else %}
上一页
{% endif %}
{% for p_num in paginator.page_range %}
{% if p_num == c_page.number %}
{{p_num}}
{% else %}
<a href="/test_page?page={{p_num}}">{{p_num}}</a>
{% endif %}
{% endfor %}
{% if c_page.has_previous %}
<a href="/test_page?page={{c_page.next_page_number}}">下一页</a>
{% else %}
下一页
{% endif %}
```



## Django 生成 csv 文件



### csv 文件定义

逗号分隔符(Comma-Separated Values，CSV，有时也称为字符分隔值，因为分隔字符也可以不是逗号)，其文件以纯文本形式存储表格数据（数字和文本）

说明：可被常见制表工具，如 Excel 等直接进行读取



### Python 中生成 csv 文件

Python 提供了内建库 - csv；可直接通过该库操作 csv 文件

案例如下：

```python
import csv
with open('eggs.csv','w',newline='') as csvfile:
    writer = csv.writer(csvfile)
    writer.writerow(['a','b','c'])
```



### csv 文件下载

在网站中，实现下载 CSV，注意如下：

--响应 Content-Type 类型需修改为 text/csv。这告诉浏览器该文档时 CSV 文件，而不是 HTML 文件。

--响应会获得一个额外的 Content-Disposition 标头，其中包含 CSV 文件的名称。它将被浏览器用于开启 “另存为...” 对话框

```python
import csv
from django.http import HttpResponse
from .models import Book
def make_csv_view(request):
    response = HttpResponse(content_type='text/csv')
    response['Content-Disposition'] = 'attachment; filename="mybook.csv"'
    all_book = Book.objects.all()
    writer = csv.writer(response)
    writer.writerow(['id','title'])
    for b in all_book:
        writer.writerow([b.id,b.title])
    return response
```



## 内建用户系统



### 定义

Django 带有一个用户认证系统。它处理用户账号、组、权限以及基于 cookies 的用户会话。

用户可以直接使用 Django 自带的用户表

官方文档：https://docs.djangoproject.com/en/2.2/topics/auth/

### 基本字段

模型类位置 from django.contrib.auth.models import User

| 字段名       | 字段中文名                                                   |
| ------------ | ------------------------------------------------------------ |
| username     | 用户名                                                       |
| password     | 密码                                                         |
| email        | 邮箱                                                         |
| first_name   | 名                                                           |
| last_name    | 姓                                                           |
| is_superuser | 是否是管理员账号（/admin）                                   |
| is_staff     | 是否可以访问 admin 管理界面                                  |
| is_active    | 是否是活跃用户，默认 True。一般不删除用户，而是将用户的 is_active 设为 False。 |
| last_login   | 上一次的登陆时间                                             |
| date_joined  | 用户创建的时间                                               |



### 基本模型操作 - 创建用户

1、创建普通用户 create_user

```python
from django.contrib.auth.models import User
user = User.objects.create_user(username="用户名",password="密码",email="邮箱",...)
```

2、创建超级用户 create_superuser

```python
from django.contrib.auth.models import User
user = User.objects.create_superuser(username="用户名",password="密码",email="邮箱",...)
```



### 基本模型操作 - 删除用户

```python
from django.contrib.auth.models import User
try:
    user = User.objects.get(username="用户名")
    user.is_active = False # 记当前用户无效
    user.save()
    print("删除普通用户成功！")
except:
    print("删除普通用户失败！")
```



### 基本模型操作 - 校验密码

```python
from django.contrib.auth import authenticate
user = authenticate(username=username,password=password)
```

说明：如果用户名密码校验成功则返回对应的 user 对象，否则返回 None



### 基本模型操作 - 修改密码

```python
from django.contrib.auth.models import User
try:
    user = User.objects.get(username="xiaonao")
    user.set_password('654321')
    user.save()
    return HttpResponse("修改密码成功！")
except:
    return HttpResponse("修改密码失败！")
```



### 基本模型操作 - 登陆状态保持

```python
from django.contrib.auth import login
def login_view(request):
    user = authenticate(username=username,password=password)
    login(request,user)
```



### 基本模型操作 - 登陆状态校验

```python
from django.contrib.authdecorators import login_required
@login_required
def index_view(request):
    #该视图必须为用户登录状态下才可访问
    #当前登录用户可通过 request.user 获取
    login_user = request.user
    .....
```



### 基本模型操作 - 登陆状态取消

```python
from django.contrib.auth import logout
def logout_view(request):
    logout(request)
```



**使用案例：**

```python
from django.contrib.auth.models import User
from django.contrib.auth import authenticate,login,logout
from django.contrib.auth.decorators import login_required
def register_view(request):
    # 注册
    if request.method == 'GET':
        return render(request,'register.html')
    elif request.methods == 'POST':
        username = request.POST['username']
        password_1 = request.POST['password_1']
        password_2 = request.POST['password_2']
        if password_1 != password_2:
            return Httpresponse('----两次密码输入不一致----')
        #TODO 查询用户名是否已注册
        #务必使用 create_user 创建用户
        user = User.objects.create_user(username=username,password=password_1)
        #如果需要注册后，免登录
        #login(request,user)
        #return HttpResponseRedirect('/index')
        return HttpResponseRedirect('/login')
    
def login_view(request):
    #登录
    if request.method == 'GET':
        return render(request,'login.html')
    elif request.methods == 'POST':
        username = request.POST['username']
        password = request.POST['password']
        user = authenticate(username=username,password=password)
        if not user:
            #用户名或密码错误
            return HttpResponse('---用户名或密码错误---')
        else:
            #校验成功
            #记录会话状态
            login(request,user)
            return HttpResponseRedirect('/index')
 def logout_view(request):
    #退出
    logout(request)
    return HttpResponse('---已退出---')

@login_required
def index_view(request):
    #首页，必须登录才能访问，未登录跳转至 settings.LOGIN_URL
    user = request.user
    return HttpResponse('欢迎%s来到测试内部验证的首页'%(user.username))

# settings.py设置
LOGIN_URL = '/login'
```



### 内建用户表 - 继承内建抽象类

步骤：

1、添加新的应用

2、定义模型类继承 AbstractUser

3、settings.py 中指明 AUTH_USER_MODEL = '应用名.类名'

注意：此操作要在第一次 Migrate 之前进行

示例 - user/models.py - 添加 user 应用

```python
from django.db import models
from django.contrib.auth.models import AbstractUser

#create your models here
class UserInfo(AbstractUser):
    phone = models.CharField(max_length=11,default="")
```

settings.py 添加配置

AUTH_USER_MODEL = 'user.UserInfo'

添加用户

```python
from user.models import UserInfo
UserInfo.objects.create_user(username='guoxiao',password='123456',phone='1345462461')
```

