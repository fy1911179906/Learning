# 第一章       Vue 简介



## Vue 是什么

一套用于构建用户界面的渐进式 Javascript 框架

## Vue 的特点

1、采用组件化模式，提高代码复用率、且让代码更好维护。

2、声明式编码，让编码人员无需直接操作 DOM，提高开发效率。（原生Javascript，即命令式编码）

3、使用虚拟 DOM + 优秀的 Diff 算法，尽量复用 DOM 节点。

4、遵循 MVVM 模式。

5、编程简洁，体积小，运行效率高，适合移动/PC端开发。

6、它本身只关注UI，也可以引入其它第三方库开发项目。

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\原生Javascript实现.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\Vue实现.png)

## 初识 Vue

### 初识 Vue

​    1、想让Vue工作，就必须创建一个Vue实例，且要传入一个配置对象；
​    2、root 容器里的代码依然符合 html 规范，只不过混入了一些特殊的 Vue 语法；
​    3、root 容器里的代码被称为【Vue模板】；
​    4、Vue 实例和容器是一一对应的；
​    5、真实开发中只有一个 Vue 实例，并且会配合着组件一起去使用；
​    6、{{xxx}}中的xxx要写js表达式，且xxx可以自动读取到 data 中的所有属性；
​    7、一旦 data 中的数据发生改变，那么模板中用到该数据的地方也会自动更新；
​    注意区分：js表达式 和 js代码（语句）
​    1、表达式，一个表达式会生成一个值，可以放在任何一个需要值的地方；
​         (1)a
​         (2)a+b
​         (3)demo(1)
​         (4)x===y ? 'a' : 'b'
​    2、js代码（语句）
​         (1)if(){}
​         (2)for(){}

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>初始Vue</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 初识Vue:
        1、想让Vue工作，就必须创建一个Vue实例，且要传入一个配置对象；
        2、root 容器里的代码依然符合 html 规范，只不过混入了一些特殊的 Vue 语法；
        3、root 容器里的代码被称为【Vue模板】；
        4、Vue 实例和容器是一一对应的；
        5、真实开发中只有一个 Vue 实例，并且会配合着组件一起去使用；
        6、{{xxx}}中的xxx要写js表达式，且xxx可以自动读取到 data 中的所有属性；
        7、一旦 data 中的数据发生改变，那么模板中用到该数据的地方也会自动更新；
        注意区分：js表达式 和 js代码（语句）
        1、表达式，一个表达式会生成一个值，可以放在任何一个需要值的地方；
             (1)a
             (2)a+b
             (3)demo(1)
             (4)x===y ? 'a' : 'b'
        2、js代码（语句）
             (1)if(){}
             (2)for(){}
             
     -->
    <div id="root">
        <h1>hello,{{name}}，{{address}},{{Date.now()}}</h1>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                address: 'zhanjiang'
            }
        })
    </script>
</body>

</html>
```

### 模板语法

1、插值语法：
            功能：用于解析标签内容。
            写法：{{xxx}}，xxx是js表达式，且可以直接读取到data中的所有属性。
2、指令语法：
            功能：用于解析标签（包括：标签属性、标签体内容、绑定事件......)。
            举例：v-bind:href="xxx" 或 简写为 :href="xxx",xxx同样要写js表达式。且可以直接读取到data中的所有属性
备注：Vue中有很多的指令，且形式都是：v-????，此时我们只是拿v-bind举个例子。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>模板语法</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- Vue模板语法有2大类
        1、插值语法：
            功能：用于解析标签内容。
            写法：{{xxx}}，xxx是js表达式，且可以直接读取到data中的所有属性。
        2、指令语法：
            功能：用于解析标签（包括：标签属性、标签体内容、绑定事件......)。
            举例：v-bind:href="xxx" 或 简写为 :href="xxx",xxx同样要写js表达式。且可以直接读取到data中的所有属性
            备注：Vue中有很多的指令，且形式都是：v-????，此时我们只是拿v-bind举个例子。
     -->
    <!-- 准备好一个容器 -->
    <div id="root">
        <h1>hello,{{name}}</h1>
        <a v-bind:href="url">点击去百度</a>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                url: "http://www.baidu.com"
            }
        })
    </script>
</body>

</html>
```

### 数据绑定

​            1、单向绑定(v-bind)：数据只能从data流向页面。
​            2、双向绑定(v-model)：数据不仅能从data流向页面，还可以从页面流向data。
​            备注：
​                    1、双向绑定一般应用在表单类元素上（如：input、select等）
​                    2、v-model:value 可以简化为 v-model，因为v-model默认收集的就是value值。

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\数据绑定.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>模板语法</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- Vue中有两种数据绑定的方式：
            1、单向绑定(v-bind)：数据只能从data流向页面。
            2、双向绑定(v-model)：数据不仅能从data流向页面，还可以从页面流向data。
                备注：
                    1、双向绑定一般应用在表单类元素上（如：input、select等）
                    2、v-model:value 可以简化为 v-model，因为v-model默认收集的就是value值。
                -->
    <!-- 准备好一个容器 -->
    <div id="root">
        <!-- 普通写法 -->
        单向数据绑定：<input type="text" v-bind:value="name"><br />
        双向数据绑定：<input type="text" v-model:value="name">
        <!-- 简化写法 -->
        单向数据绑定：<input type="text" :value="name"><br />
        双向数据绑定：<input type="text" v-model="name">
        <!-- 如下代码是错误的，因为v-model智能应用在表单类元素（输入类元素）上 -->
        <!-- <h2 v-model:x="name">你好啊！</h2> -->
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
            }
        })
    </script>
</body>

</html>
```

### el 和 data 两种写法

data与el的两种写法
        1、el有两种写法
        (1)new Vue是配置el属性。
        (2)先创建Vue实例，随后再通过vm.$mount('#root')指定el的值。
        2、data有两种写法
        (1)对象式
        (2)函数式
        如何选择：目前那种写法都可以，以后学习到组件时，data必须使用函数式。否则会报错。
        3、一个重要的原则：
        由Vue管理的函数，一定不要写箭头函数，一旦写了箭头函数，this就不再是Vue实例了

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 
        data与el的两种写法
        1、el有两种写法
        (1)new Vue是配置el属性。
        (2)先创建Vue实例，随后再通过vm.$mount('#root')指定el的值。
        2、data有两种写法
        (1)对象式
        (2)函数式
        如何选择：目前那种写法都可以，以后学习到组件时，data必须使用函数式。否则会报错。
        3、一个重要的原则：
        由Vue管理的函数，一定不要写箭头函数，一旦写了箭头函数，this就不再是Vue实例了
     -->
    <div id="root">
        <h1>Hello {{name}}</h1>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        const v = new Vue({
            // 第一种写法
            // el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            // data第一种写法（对象式）
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
            }
            // data第二种写法（函数式）
            // data:fnction(){
            //     return{
            //         name:'World'
            //     }
            // }
        })
        // 一秒后绑定vue实例，第二种写法
        setTimeout(() => {
            v.$mount('#root')
        }, 1000);
    </script>

</body>

</html>
```

### 回顾Object.defineproperty方法

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <div id="root">

    </div>
    <script type="text/javascript">
        let number = 18
        let person = {
            name: '张三',
            sex: '男',
        }
        Object.defineProperty(person, 'age', {
            //value:18,
            //enumerable:true,//控制属性是否可以枚举，默认值是false
            //writable:true,//控制属性是否可以被修改，默认值是false
            //configurable:true//控制属性是否可以被删除，默认值是false

            //当有人读取 person 的age属性时，get函数（getter）就会被调用，且返回值就是age的值
            get: function () {
                console.log('有人读取age属性了')
                return number
            },
            set(value) {
                console.log('有人修改age属性，且值是', value)
                number = value
            }
        })
    </script>

</body>

</html>
```

### 数据代理

​         1、Vue中的数据代理：
​                通过vm对象来代理data对象中属性的操作（读/写）
​         2、Vue中数据代理的好处
​                更加方便的操作data中的数据
​         3、基本原理：
​                通过Object.defineProperty()把data对象中所有的属性添加到vm上，
​                为每一个添加到vm上的属性，都指定一个getter/setter.
​                在getter/setter内部去操作（读/写）data中对应的属性。

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\数据代理.png)

![数据代理之列表排序](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\数据代理之列表排序.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 数据代理：通过一个对象代理对另一个对象的属性的操作（读/写） -->
    <script type="text/javascript">
        let obj = { x: 100 }
        let obj2 = { y: 200 }
        Object.defineProperty(obj2, 'x', {
            get() {
                return obj.x
            },
            set(value) {
                obj.x = value
            }
        })
    </script>
    <!-- 1、Vue中的数据代理：
                通过vm对象来代理data对象中属性的操作（读/写）
         2、Vue中数据代理的好处
                更加方便的操作data中的数据
         3、基本原理：
                通过Object.defineProperty()把data对象中所有的属性添加到vm上，
                为每一个添加到vm上的属性，都指定一个getter/setter.
                在getter/setter内部去操作（读/写）data中对应的属性。
            -->
</body>

</html>
```

### 事件的基本使用

事件的基本使用：
                1、使用v-on:xxx 或 @xxx 绑定事件，其中xxx事件名
                2、事件的回调需要配置在 methods 对象中，最终会在 vm上
                3、methods中配置的函数，不要用就箭头函数！否则this就不是vm了
                4、methods中的配置的函数，都是被Vue所管理的函数，this的指向是vm 或 组件实例对象
                5、@click="demo" 和 @click="demo($event)" 效果一样，但后者可以传参

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 事件的基本使用：
                1、使用v-on:xxx 或 @xxx 绑定事件，其中xxx事件名
                2、事件的回调需要配置在 methods 对象中，最终会在 vm上
                3、methods中配置的函数，不要用就箭头函数！否则this就不是vm了
                4、methods中的配置的函数，都是被Vue所管理的函数，this的指向是vm 或 组件实例对象
                5、@click="demo" 和 @click="demo($event)" 效果一样，但后者可以传参
             -->
    <div id="root">
        <!-- <button v-on:click="showinfo">点我提示信息</button> -->
        <button @click="showInfo1">点我提示信息1(不传参)</button>
        <button @click="showInfo2($event,66)">点我提示信息2(传参)</button>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        const vm = new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
            },
            methods: {
                showInfo1: function (e) {
                    console.log(e.target)
                },
                showInfo2(e, number) {
                    console.log(number)
                }
            }
        })
    </script>

</body>

</html>
```

### 事件修饰符

Vue中的事件修饰符：
            1、prevent：阻止默认事件（常用）
            2、stop：阻止事件冒泡（常用）
            3、once：事件只触发一次（常用）
            4、capture：使用事件的描述模式
            5、self：只有event.target是当前操作的元素是才触发事件
            6、passive：事件的默认行为立即执行，无需等待事件回调执行完毕

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>
<style>
    .demo1 {
        background-color: burlywood;
        width: 100px;
        height: 100px;
    }

    .box1 {
        background-color: burlywood;
        width: 200px;
        height: 200px;
    }

    .box2 {
        background-color: coral;
        width: 100px;
        height: 100px;
    }

    .list {
        width: 200px;
        height: 200px;
        background-color: cornflowerblue;
        overflow: auto;
    }

    li {
        height: 100px;
    }
</style>

<body>
    <!-- Vue中的事件修饰符：
            1、prevent：阻止默认事件（常用）
            2、stop：阻止事件冒泡（常用）
            3、once：事件只触发一次（常用）
            4、capture：使用事件的描述模式
            5、self：只有event.target是当前操作的元素是才触发事件
            6、passive：事件的默认行为立即执行，无需等待事件回调执行完毕 -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <!-- 阻止默认事件 -->
        <a href="http://www.baidu.com" @click.prevent="showInfo($event)">点我提示信息</a>
        <!-- 事件只能触发一次 -->
        <div class="demo1" @click.once="showInfo1">
            <!-- 阻止冒泡事件 -->
            <button @click.stop="showInfo1">点我提示信息</button>
        </div>
        <!-- 使用事件的捕获模式 -->
        <div class="box1" @click.capture="showMsg(1)">
            <div class="box2" @click="showMsg(2)"></div>
        </div>
        <!-- 只有event.target是当前操作的元素是才触发事件 -->
        <div class="box1" @click.self="showMsg(1)">
            <div class="box2" @click="showMsg(2)"></div>
        </div>
        <!-- @scoll滚动条滚动，@wheel鼠标滚轮滚动，事件的默认行为立即执行，无需等待事件回调执行完毕 -->
        <ul @scroll.passive="demo" class="list">
            <li>1</li>
            <li>2</li>
            <li>3</li>
            <li>4</li>
        </ul>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
            },
            methods: {
                showInfo(e) {
                    // e.preventDefault()
                    alert('同学你好！')
                },
                showInfo1() {
                    alert('你好！')
                },
                showMsg(msg) {
                    alert('您好啊！' + msg)
                },
                demo() {
                    for (let i = 0; i < 100000; i++) {
                        console.log('#')
                    }
                    console.log('累坏了')
                }
            }
        })
    </script>

</body>

</html>
```

### 键盘事件

​        1、Vue中常用的按键别名：
​        回车=>enter
​        删除=>delete（捕获“删除”和“退格”键）
​        退出=>esc
​        空格=>space
​        换行=>tab
​        上=>up
​        下=>down
​        左=>left
​        右=>right
​        2、Vue未提供别名的按键，可以使用按键原始的key值去绑定，但注意要转为kebab-case（短横线命名）
​        3、系统修饰符（用法特殊）：ctrl、alt、shift、meta
​            (1)配合keyup使用：按下修饰符的同时，再按下其他建，随后释放其他键，事件才被触发。
​            (2)配合keydown使用：正常触发事件。
​        4、也可以使用keyCode去指定具体的按键（不推荐）
​        5、Vue.config.keyCode.自定义键名 = 键码，可以去定制按键别名 

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 1、Vue中常用的按键别名：
        回车=>enter
        删除=>delete（捕获“删除”和“退格”键）
        退出=>esc
        空格=>space
        换行=>tab
        上=>up
        下=>down
        左=>left
        右=>right
        2、Vue未提供别名的按键，可以使用按键原始的key值去绑定，但注意要转为kebab-case（短横线命名）
        3、系统修饰符（用法特殊）：ctrl、alt、shift、meta
            (1)配合keyup使用：按下修饰符的同时，再按下其他建，随后释放其他键，事件才被触发。
            (2)配合keydown使用：正常触发事件。
        4、也可以使用keyCode去指定具体的按键（不推荐）
        5、Vue.config.keyCode.自定义键名 = 键码，可以去定制按键别名 
    -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <input type="text" placeholder="按下回车提示输入" @keyup.enter="showInfo">
        <input type="text" placeholder="按下回车提示输入" @keyup.ctrl.y="showInfo">
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
            },
            methods: {
                showInfo() {
                    alert('同学你好！')
                }
            }
        })
    </script>

</body>

</html>
```

## MVVM 模型

1、M：模型(Model)：对应data中的数据

2、V：视图(View)：模板

3、VM：视图模型(ViewModel)：Vue 实例对象

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\MVVM模型.png)

代码观察发现：

1、data中所有的属性，最后都出现在了vm身上。

2、vm身上所有的属性及Vue原型上所有的属性，在Vue模板中都可以直接使用。



## 计算属性与监视

### 计算属性 - computed

1、要显示的数据不存在，要通过计算得来

2、在 computed 对象中定义计算属性

3、在页面中使用（方法名）来显示计算的结果。

### 监视属性 - watch

1、通过 vm 对象的 $watch() 或 watch 配置来监视指定的属性

2、当属性变化时，回调函数自动调用，在函数内部进行计算

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\数据监测.png)

### 计算属性

计算属性：
            1、定义：要用的属性不存在，要通过已有属性计算得来
            2、原理：底层借助了Object.defineProperty方法提供的getter和setter
            3、get函数什么时候执行？
                (1)初次读取时会执行一次
                (2)当依赖的数据发生改变时会被再次调用
            4、优势：与methods实现相比，内部有缓存机制（复用—），效率更高，调式方便
            5、备注：
                (1)计算属性最终会出现在vm上，直接读取使用即可
                (2)如果计算属性要被修改，那必须写set函数去响应修改，且set中要引起计算时依赖的数据发生改变
         computed 和 watch之间的区别：
            1、computed能完成的功能，watch都可以完成
            2、watch能完成的功能，computed不一定能完成，例如：watch可以进行异步操作
         两个重要的小原则：
            1、所被Vue管理的函数，最好写成普通函数，这样this的指向才是vm 或 组件实例对象
            2、所有不被Vue所管理的函数（定时器的回调函数、ajax的回调函数等），最好写成箭头函数，
                这样this的指向才是vm 或 组件实例对象

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 计算属性：
            1、定义：要用的属性不存在，要通过已有属性计算得来
            2、原理：底层借助了Object.defineProperty方法提供的getter和setter
            3、get函数什么时候执行？
                (1)初次读取时会执行一次
                (2)当依赖的数据发生改变时会被再次调用
            4、优势：与methods实现相比，内部有缓存机制（复用—），效率更高，调式方便
            5、备注：
                (1)计算属性最终会出现在vm上，直接读取使用即可
                (2)如果计算属性要被修改，那必须写set函数去响应修改，且set中要引起计算时依赖的数据发生改变
         computed 和 watch之间的区别：
            1、computed能完成的功能，watch都可以完成
            2、watch能完成的功能，computed不一定能完成，例如：watch可以进行异步操作
         两个重要的小原则：
            1、所被Vue管理的函数，最好写成普通函数，这样this的指向才是vm 或 组件实例对象
            2、所有不被Vue所管理的函数（定时器的回调函数、ajax的回调函数等），最好写成箭头函数，
                这样this的指向才是vm 或 组件实例对象
             -->
    <div id="root">
        <!-- 插值语法 -->
        姓：<input type="text" v-model="firstName"><br />
        名：<input type="text" v-model="lastName"><br />
        全名：<span>{{firstName}}-{{lastName}}</span><br />
        <!-- methods方法 -->
        姓：<input type="text" v-model="firstName"><br />
        名：<input type="text" v-model="lastName"><br />
        全名：<span>{{fullName()}}</span><br />
        <!-- computed计算属性 -->
        姓：<input type="text" v-model="firstName"><br />
        名：<input type="text" v-model="lastName"><br />
        全名：<span>{{fullname}}</span><br />
        <!-- watch监视属性 -->
        姓：<input type="text" v-model="firstName"><br />
        名：<input type="text" v-model="lastName"><br />
        全名：<span>{{FullName}}</span>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                firstName: 'Hello',
                lastName: 'World',
                FullName: 'Hello-World',
            },
            methods: {
                fullName() {
                    return this.firstName + '-' + this.lastName
                }
            },
            computed: {
                fullname: {
                    get() {
                        return this.firstName + '-' + this.lastName
                    },
                    set(value) {
                        const arr = value.split("-")
                        this.firstName = arr[0]
                        this.lastName = arr[1]
                    }
                },
                //简写
                // fullname(){
                //     return this.firstName + '-' + this.lastName
                // }
            },
            watch: {
                firstName(val) {
                    setTimeout(() => {
                        this.FullName = val + '-' + this.lastName
                    }, 1000)
                },
                lastName(val) {
                    this.FullName = this.firstName + '-' + val
                }
            }
        })
    </script>

</body>

</html>
```

### 监视属性

监视属性watch：
            1、当被监视的属性变化时，回调函数自动调用，进行相关操作
            2、监视的属性必须存在，才能进行监视！
            3、监视的两种写法：
                (1)new Vue时传入watch配置
                (2)通过vm.$watch监视
            4、深度监视：
                (1)Vue中的watch默认不监视对象内部值的改变（一层）
                (2)配置deep:true 可以监测对象内部值改变（多层）
            备注：
                (1)Vue自身可以监测对象内部值的改变，但Vue提供的watch默认不可以
                (2)使用watch时根据数据的具体结构，决定是否采用深度监视

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 监视属性watch：
            1、当被监视的属性变化时，回调函数自动调用，进行相关操作
            2、监视的属性必须存在，才能进行监视！
            3、监视的两种写法：
                (1)new Vue时传入watch配置
                (2)通过vm.$watch监视
            4、深度监视：
                (1)Vue中的watch默认不监视对象内部值的改变（一层）
                (2)配置deep:true 可以监测对象内部值改变（多层）
                备注：
                    (1)Vue自身可以监测对象内部值的改变，但Vue提供的watch默认不可以
                    (2)使用watch时根据数据的具体结构，决定是否采用深度监视
             -->
    <div id="root">
        <h1>今天天气很{{info}}</h1>
        <button @click="isHot = !isHot">切换天气</button>
        <!-- <button @click="changeWeather">切换天气</button> -->
        <h3>a的值是：{{numbers.a}}</h3>
        <button @click="numbers.a++">点我让a加1</button>
        <h3>b的值是：{{numbers.b}}</h3>
        <button @click="numbers.b++">点我让b加1</button>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        const vm = new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                isHot: true,
                numbers: {
                    a: 1,
                    b: 2,
                }
            },
            // methods: {
            //     chanegWeather() {
            //         this.isHot = !this.isHot
            //     }
            // },
            computed: {
                info() {
                    return this.isHot ? '炎热' : '凉爽'
                }
            },
            watch: {
                isHot: {
                    immediate: true,//初始化时让handler调用一下
                    //handler什么时候调用？当isHot发生改变时
                    handler(newValue, oldValue) {
                        console.log('isHot被修改了', newValue, oldValue)
                    }
                },
                //简写
                // isHot(newValue, oldValue) {
                //     console.log('isHot被修改了', newValue, oldValue)
                // },
                //监视多级结构中的某个属性的变化
                numbers: {
                    immediate: true,//初始化时让handler调用一下
                    deep: true,//深度监视
                    handler() {
                        console.log('numbers改变了')
                    }
                }
            }
        })
        // vm.$watch('isHot', {
        //     immediate: true,//初始化时让handler调用一下
        //     deep: true,//深度监视
        //     //handler什么时候调用？当isHot发生改变时
        //     handler(newValue, oldValue) {
        //         console.log('isHot被修改了', newValue, oldValue)
        //     }
        // })
    </script>

</body>

</html>
```



## class 与 style 绑定

### 理解

1、在应用界面中，某个（些）元素的样式是变化的

2、class/style 绑定就是专门用来实现动态样式效果的技术

### class 绑定

1、class = "xxx"

2、表达式是字符串：'classA'

3、表达式是对象：{classA:isA,classB:isB}

4、表达式是数组：['classA','classB']

### style 绑定

1、:style="{color:activeColor,fontSize:fontSize + 'px'}"

2、:style="[a,b]"其中a，b是样式对象



### 绑定样式

绑定样式：
            1、class样式
                写法：class="xxx",xxx可以是字符串、对象、数组
                字符串写法适用于：类名不确定，要动态获取
                对象写法适用于：要绑定多个样式，个数不确定，名字也不确定
                数组写法适用于：要绑定多个样式，个数确定，名字也确定，但是不确定用不用
            2、style样式
                :style="{fontSize:xxx}"其中xxx是动态值
                :style="[a,b]"其中a，b是样式对象

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>
<style>
    .basic {
        background-color: rgb(224, 233, 221);
        width: 100px;
        height: 100px;
    }

    .happy {
        background-color: darkgoldenrod;
        width: 100px;
        height: 100px;
    }

    .sad {
        background-color: rgb(110, 108, 101);
        width: 100px;
        height: 100px;
    }

    .normal {
        background-color: rgb(11, 149, 184);
        width: 100px;
        height: 100px;
    }
</style>

<body>
    <!-- 绑定样式：
            1、class样式
                写法：class="xxx",xxx可以是字符串、对象、数组
                字符串写法适用于：类名不确定，要动态获取
                对象写法适用于：要绑定多个样式，个数不确定，名字也不确定
                数组写法适用于：要绑定多个样式，个数确定，名字也确定，但是不确定用不用
            2、style样式
                :style="{fontSize:xxx}"其中xxx是动态值
                :style="[a,b]"其中a，b是样式对象 -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <!-- 绑定class样式--字符串写法，适用于：样式的类名不确定，需要动态指定 -->
        <div class="basic" :class="mood" @click="changeMood">Hello {{name}}</div><br />
        <!-- 绑定class样式--数组写法，适用于：要绑定的样式个数不确定、名字不确定 -->
        <div class="basic" :class="classArr">Hello {{name}}</div><br />
        <!-- 绑定class样式--对象写法，适用于：要确定的样式个数确定，名字也确定，但要动态决定用不用 -->
        <div class="basic" :class="classObj">Hello {{name}}</div><br />
        <!-- 绑定style样式--对象写法 -->
        <div class="basic" :class="styleObj">Hello {{name}}</div><br />
        <!-- 绑定style样式--数组写法 -->
        <div class="basic" :class="styleArr">Hello {{name}}</div><br />
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        const vm = new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                mood: '',
                classArr: ['happy', 'sad', 'normal'],
                classObj: {
                    happy: true,
                    sad: false,
                    normal: false,
                },
                styleObj: {
                    fontSize: '40px',
                    color: 'red',
                    backgroundColor: 'orange'
                },
                styleArr: [{
                    fontSize: '40px',
                    color: 'red',
                }, {
                    backgroundColor: 'orange'
                }]
            },
            methods: {
                changeMood() {
                    const arr = ['happy', 'sad', 'normal']
                    const index = Math.floor(Math.random() * 3)
                    this.mood = arr[index]
                }
            }
        })
    </script>

</body>

</html>
```



## 条件渲染

### 条件渲染指令

1、v-if 与 v-else

2、v-show

### 比较 v-if 与 v-show

1、如果需要频繁切换 v-show 较好

2、当条件不成立时，v-if 的所有子节点不会解析(项目中使用)



### 条件渲染

条件渲染：
            1、v-if
                写法：
                    (1)v-if="表达式"
                    (2)v-else-if="表达式"
                    (3)v-else="表达式"
                适用于：切换频率较低的场景
                特点：不展示的DOM元素直接被移除
                注意：v-if可以和：v-else-if、v-else一起使用，但要求结构不能被“打断”
            2、v-show
                写法：v-show="表达式"
                适用于：切换频率较高的场景
                特点：不展示的DOM元素未被移除，仅仅使用样式隐藏掉
            3、备注：使用v-if的时，元素可能无法获取到，而使用v-show一定可以获取到

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 条件渲染：
            1、v-if
                写法：
                    (1)v-if="表达式"
                    (2)v-else-if="表达式"
                    (3)v-else="表达式"
                适用于：切换频率较低的场景
                特点：不展示的DOM元素直接被移除
                注意：v-if可以和：v-else-if、v-else一起使用，但要求结构不能被“打断”
            2、v-show
                写法：v-show="表达式"
                适用于：切换频率较高的场景
                特点：不展示的DOM元素未被移除，仅仅使用样式隐藏掉
            3、备注：使用v-if的时，元素可能无法获取到，而使用v-show一定可以获取到
         -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <h2>当前n的值为{{n}}</h2>
        <button @click="n++">点我n++</button>
        <!-- 使用v-show做条件渲染  -->
        <h2 v-show="false">欢迎来到我的{{name}}</h2>
        <h2 v-show="n===1">欢迎来到我的{{name}}</h2>
        <!-- 使用v-if做条件渲染  -->
        <h2 v-if="false">欢迎来到我的{{name}}</h2>
        <h2 v-if="n===2">欢迎来到我的{{name}}</h2>
        <!-- 使用v-if与v-else做条件渲染  -->
        <div v-if="n===3">happy</div>
        <div v-else-if="n===4">normal</div>
        <div v-else>sad</div>
        <template v-if="n===5">
            <div>你好，朋友</div>
        </template>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                n: 0,
            }
        })
    </script>

</body>

</html>
```



## 列表渲染

### key 的原理

面试题：react、vue中的key有什么作用？（key的内部原理）

1、虚拟DOM中key的作用：

key是虚拟DOM对象的标识，当状态中的数据发生变化时，Vue会根据【新数据】生成【新的虚拟DOM】

随后Vue进行【新虚拟DOM】与【旧虚拟DOM】的差异比较，比较规则如下：

2、对比规则：

（1）旧虚拟DOM中找到了与新虚拟DOM相同的key：

①若虚拟DOM中内容没变，直接使用之前的真实DOM！

②若虚拟DOM中内容改变，则生成新的真实DOM，随后替换页面中之前的真实DOM。

3、用index作为key可能会引发的问题：

（1）若对数组进行：逆序添加、逆序删除等破坏顺序操作：会产生没有必要的真实DOM更新==>界面效果没问题，但效率低。

（2）如果结构中还包括输入类的DOM：会产生错误DOM更新==>界面有问题

4、开发中如何选择key？：

（1）最好使用每条数据的唯一标识作为key，比如id、手机号、身份证号、学号等唯一值。

（2）如果不存在对数据的逆序添加、逆序删除等破坏顺序操作，仅用于渲染列表用于展示，使用index作为key是没有问题的。



### 列表渲染

v-for指令
            1、用于展示列表数据
            2、语法：v-for="(item,index) in xxx" :key="yyy"
            3、可遍历：数组、对象、字符串（用的少）、指定次数（用的少）

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- v-for指令
            1、用于展示列表数据
            2、语法：v-for="(item,index) in xxx" :key="yyy"
            3、可遍历：数组、对象、字符串（用的少）、指定次数（用的少） -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <h2>人员列表</h2>
        <ul>
            <!-- 遍历数组 -->
            <li v-for="(p,index) in persons" :key="p.id">
                {{p.name}}-{{p.age}}
            </li>
        </ul>
        <ul>
            <!-- 遍历对象 -->
            <li v-for="(k,value) in car" :key="k">
                {{k}}-{{value}}
            </li>
        </ul>
        <ul>
            <!-- 遍历字符串 -->
            <li v-for="(char,index) in str" :key="index">
                {{char}}-{{index}}
            </li>
        </ul>
        <ul>
            <!-- 遍历对象 -->
            <li v-for="(a,b) of 5">
                {{a}}-{{b}}
            </li>
        </ul>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                persons: [
                    { id: '001', name: '张三', age: '18' },
                    { id: '002', name: '李四', age: '20' },
                    { id: '003', name: '王五', age: '14' },
                ],
                car: {
                    name: '奥迪',
                    color: 'orange'
                },
                str: 'hello',
            }
        })
    </script>

</body>

</html>
```

### 列表过滤

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <div id="root">
        <h1>Hello {{name}}</h1>
        <input type="text" placeholder="请输入名字" v-model="keyWord">
        <ul>
            <li v-for="(p,index) of filPersons" :key="index">
                {{p.name}}-{{p.age}}-{{p.sex}}
            </li>
        </ul>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                keyWord: '',
                persons: [
                    { id: '001', name: '马冬梅', age: 19, sex: '女' },
                    { id: '002', name: '周冬雨', age: 20, sex: '女' },
                    { id: '003', name: '周杰伦', age: 29, sex: '男' },
                    { id: '004', name: '温兆伦', age: 24, sex: '男' },
                ],
                filPersons: []
            },
            watch: {
                keyWord: {
                    immediate: true,
                    handler(val) {
                        this.filPersons = this.persons.filter((p) => {
                            return p.name.indexOf(val) !== -1
                        })
                    }
                }
            }
        })
    </script>

</body>

</html>
```

### 列表排序

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <div id="root">
        <h1>Hello {{name}}</h1>
        <h2>人员列表</h2>
        <button @click="sortType = 2">年龄升序</button>
        <button @click="sortType = 1">年龄降序</button>
        <button @click="sortType = 0">原顺序</button><br />
        <input type="text" placeholder="请输入名字" v-model="keyWord">
        <ul>
            <li v-for="(p,index) of filPersons" :key="index">
                {{p.name}}-{{p.age}}-{{p.sex}}
            </li>
        </ul>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        const vm = new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                keyWord: '',
                sortType: 0, //0原排序、1降序、2升序
                persons: [
                    { id: '001', name: '马冬梅', age: 19, sex: '女' },
                    { id: '002', name: '周冬雨', age: 20, sex: '女' },
                    { id: '003', name: '周杰伦', age: 29, sex: '男' },
                    { id: '004', name: '温兆伦', age: 24, sex: '男' },
                ],
            },
            computed: {
                filPersons() {
                    const arr = this.persons.filter((p) => {
                        return p.name.indexOf(this.keyWord) !== -1
                    })
                    //判断一下是否需要排序
                    if (this.sortType) {
                        arr.sort((p1, p2) => {
                            return this.sortType === 1 ? p2.age - p1.age : p1.age - p2.age
                        })
                    }
                    return arr
                }
            }
        })
    </script>

</body>

</html>
```

### 模拟一个数据监测

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <script type="text/javascript">
        let data = {
            name: 'Hello World',
            address: '湛江',
        }
        //创建一个监测的实例对象，用于监视data中属性的变化。目前只考虑到一层。
        //如果是多级结构，则需要递归创建监测实例对象。
        const obs = new Observer(data)
        console.log(obs)

        //准备一个vm实例对象
        let vm = {}
        vm._data = data = obj

        function Observer(obj) {
            //汇总对象中的所有属性形成一个数组
            const keys = Object.keys(obj)
            //遍历
            keys.forEach((k) => {
                Object.defineProperty(this, k, {
                    get() {
                        return obj[k]
                    },
                    set(val) {
                        console.log(`${k}被改了，我们要去解析模板，生成虚拟DOM...我们要开始忙了`)
                        obj[k] = val
                    }
                })
            })
        }
        //反例
        // Object.defineProperty(data,'name',{
        //     get(){
        //         return data.name
        //     },
        //     set(val){
        //         data.name = val
        //     }
        // })
    </script>
</body>

</html>
```

### Vue.set的使用与对数组操作

Vue监视数据的原理：
            1、vue会监视data中所有层次的数据。
            2、如何监测对象中的数据？
                通过setter实现监视，且要再new Vue时就传入要监测的数据
                    (1)对象中后追加的属性，Vue 默认不做响应式处理
                    (2)如需给后添加的属性做响应式，请使用如下API：
                        Vue.set(target,propertyName/index,value)或
                        vm.$set(target,propertyName/index,value)
            3、如何监测数组中的数据？
                通过包裹数组更新数组的方法实现，本质就是做了两件事：
                    (1)调用原生对应的方法对数组进行更新
                    (2)重新解析模板，进而更新也也页面
            4、在vue修改数组中的某个元素一定要用如下方法：
                (1)使用这些API：push()/pop()/shift()/unshift()/splice()/sort()/reverse()
                (2)Vue.set()或vm.$set()//Vue.set(vm._data.student.hoddy,1,'打台球')
            特别注意：Vue.set() 和 vm.$set() 不能给 vm 和 vm的根数据对象添加属性

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- Vue监视数据的原理：
            1、vue会监视data中所有层次的数据。
            2、如何监测对象中的数据？
                通过setter实现监视，且要再new Vue时就传入要监测的数据
                    (1)对象中后追加的属性，Vue 默认不做响应式处理
                    (2)如需给后添加的属性做响应式，请使用如下API：
                        Vue.set(target,propertyName/index,value)或
                        vm.$set(target,propertyName/index,value)
            3、如何监测数组中的数据？
                通过包裹数组更新数组的方法实现，本质就是做了两件事：
                    (1)调用原生对应的方法对数组进行更新
                    (2)重新解析模板，进而更新也也页面
            4、在vue修改数组中的某个元素一定要用如下方法：
                (1)使用这些API：push()/pop()/shift()/unshift()/splice()/sort()/reverse()
                (2)Vue.set()或vm.$set()//Vue.set(vm._data.student.hoddy,1,'打台球')
            特别注意：Vue.set() 和 vm.$set() 不能给 vm 和 vm的根数据对象添加属性 -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <h2>姓名：{{student.name}}</h2>
        <h2>性别：{{student.sex}}</h2>
        <h2>年龄：真实{{student.age.rAge}},对外{{student.age.sAge}}</h2>
        <h2>爱好</h2>
        <ul>
            <li v-for="(h,index) in student.hoddy" :key="index">
                {{h}}
            </li>
        </ul>
        <h2>朋友</h2>
        <ul>
            <li v-for="(f,index) in student.friends" :key="index">
                {{f.name}}-{{f.age}}
            </li>
        </ul>
        <button @click=" addSex">追加性别属性</button>
        <button @click="addHobby">追加爱好</button>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        const vm = new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                student: {
                    name: 'Tom',
                    age: {
                        rAge: 40,
                        sAge: 29,
                    },
                    hoddy: ['抽烟', '喝酒', '打架'],
                    friends: [{
                        name: 'jerry', age: 35
                    }, {
                        name: 'Tony', age: 34
                    }],
                }
            },
            methods: {
                addSex() {
                    //set方法用于追加属性，不能再根vm或data上追加
                    Vue.set(this.student, 'sex', '男')
                    this.$set(this.student, 'sex', '男')
                },
                addHobby() {
                    //对数组操作，添加信息，此push是Vue包装的push，与Array的push不等
                    this.student.hoddy.push('学习')
                }
            }
        })
    </script>

</body>

</html>
```

### 收集表单数据

收集表单数据：
            若：<input type="text"/>,则v-model收集的是value值，用户输入的就是value值。
            若：<input type="radio"/>,则v-model收集的是value值，且要给标签配置value值。
            若：<input type="checkbox"/>
                1、没有配置input的value属性，那么收集的就是checked（勾选 or 未勾选，是布尔值）
                2、配置input的value属性：
                    (1)v-model的初始值是非数组，那么收集的就是checked（勾选 or 未勾选，是布尔值）
                    (2)v-model的初始值是数组，那么收集的就是value组成的数组
            备注：v-model的三个修饰符：
                lazy：失去焦点在再集数据
                number：输入字符串转为有效的数字
                trim：输入首尾空格过滤

````html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 收集表单数据：
            若：<input type="text"/>,则v-model收集的是value值，用户输入的就是value值。
            若：<input type="radio"/>,则v-model收集的是value值，且要给标签配置value值。
            若：<input type="checkbox"/>
                1、没有配置input的value属性，那么收集的就是checked（勾选 or 未勾选，是布尔值）
                2、配置input的value属性：
                    (1)v-model的初始值是非数组，那么收集的就是checked（勾选 or 未勾选，是布尔值）
                    (2)v-model的初始值是数组，那么收集的就是value组成的数组
            备注：v-model的三个修饰符：
                lazy：失去焦点在再集数据
                number：输入字符串转为有效的数字
                trim：输入首尾空格过滤
             -->
    <div id="root">
        <form>
            账号：<input type="text" v-model.trim="userInfo.account"><br /><br />
            密码：<input type="password" v-model="userInfo.password"><br /><br />
            年龄：<input type="number" v-model.number="userInfo.age"><br /><br />
            性别：
            男<input type="radio" v-model="userInfo.sex" name="sex" value="male">
            女<input type="radio" v-model="userInfo.sex" name="sex" value="female"><br /><br />
            爱好：
            学习<input type="checkbox" v-model="userInfo.hoddy" value="study">
            打游戏<input type="checkbox" v-model="userInfo.hoddy" value="game">
            吃饭<input type="checkbox" v-model="userInfo.hoddy" value="eat"><br /><br />
            所属校区
            <select v-model="userInfo.city">
                <option value="">请选择校区</option>
                <option value="beijing">北京</option>
                <option value="shanghai">上海</option>
                <option value="shenzhen">深圳</option>
                <option value="wuhan">武汉</option>
            </select><br /><br />
            其他信息：
            <textarea v-model.lazy="userInfo.other"></textarea><br /><br />
            <input type="checkbox" v-model="userInfo.agree">阅读并接受<a href="http://www.baidu.com">《用户协议》</a>
            <input type="submit" value="提交" name="submit">
        </form>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        const vm = new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                userInfo: {
                    account: '',
                    password: '',
                    age: '',
                    sex: 'female',
                    hoddy: [],
                    city: 'beijing',
                    other: '',
                    agree: ''
                }
            },
            methods: {
                demo() {
                    console.log(JSON.stringfy(this.userInfo))
                }
            }
        })
    </script>

</body>

</html>
````

### 过滤器

过滤器：
            定义：对要显示的数据进行特定格式后再显示（适用于一些简单逻辑的处理
            语法：
                1、注册过滤器：Vue.filter(name.callback) 或 new Vue{filters:{}}
                2、使用过滤器：{{xxx | 过滤器名}} 或 v-bind:属性 = "xxx | 过滤器"
            备注：
                1、过滤器也可以接收额外参数、多个过滤器也可以串联
                2、并没有改变原本的数据，是产生新的对应的数据

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
    <script src="https://cdn.bootcdn.net/ajax/libs/dayjs/1.4.1/dayjs.min.js"></script>
</head>

<body>
    <!-- 过滤器：
            定义：对要显示的数据进行特定格式后再显示（适用于一些简单逻辑的处理
            语法：
                1、注册过滤器：Vue.filter(name.callback) 或 new Vue{filters:{}}
                2、使用过滤器：{{xxx | 过滤器名}} 或 v-bind:属性 = "xxx | 过滤器"
            备注：
                1、过滤器也可以接收额外参数、多个过滤器也可以串联
                2、并没有改变原本的数据，是产生新的对应的数据
             -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <h2>显示格式化后的时间</h2>
        <!-- 计算属性实现 -->
        <h3>现在是：{{fmtTime}}</h3>
        <!-- methods实现 -->
        <h3>现在是：{{getFmtTime()}}</h3>
        <!-- 过滤器实现 -->
        <h3>现在是：{{time | timeFormater}}</h3>
        <!-- 过滤器实现（传参） -->
        <h3>现在是：{{time | timeFormater('YYYY年MM月DD日') | mySlice}}</h3>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                time: 1621561377603,//时间戳
            },
            methods: {
                getFmtTime() {
                    return dayjs(this.time).format('YYYY年MM月DD日 HH:mm:ss')
                }
            },
            computed: {
                fmtTime() {
                    return dayjs(this.time).format('YYYY年MM月DD日 HH:mm:ss')
                }
            },
            filters: {
                timeFormater(value, str = 'YYYY年MM月DD日 HH:mm:ss') {
                    return dayjs(value).format(str)
                },
                mySlice(value) {
                    return value.slice(0, 4)
                }
            }
        })
        //写法二
        // Vue.filters('mySlice',function(value){
        //     return value.slice(0, 4)
        // })
    </script>

</body>

</html>
```

### 内置指令

我们学过的指令：
            v-bind：单向绑定解析表达式，可简写为xxx
            v-model：双向数据绑定
            v-for：遍历数组、对象、字符串
            v-on：绑定事件监听，可简化为@
            v-if：条件渲染（动态控制节点是否存在）
            v-else：条件渲染（动态控制节点是否存在）
            v-show：条件渲染（动态控制节点是否展示）
        v-text指令：
            1、作用：向其所在的节点中渲染文本内容。
            2、与插值语法的区别：v-text会替换掉节点中的内容，{{xx}}则不会
        v-html指令：
            1、作用：向指定节点中渲染包含html结构的内容
            2、与插值语法的区别：
                (1)v-html会替换掉节点中所有的内容，{{xx}}则不会
                (2)v-html可以识别html结构
            3、严重注意：v-html有安全性问题：
                (1)在网站上动态渲染任意HTML，是非常危险的，容易导致XSS攻击
                (2)一定要在可靠可信的内容上使用v-html，用不要用在用户提交的内容上
        v-cloak指令(没有值):
            1、本质是一个特殊属性，Vue实例创建完毕并接管容器后，会删除v-cloak属性
            2、使用css配合v-cloak可以解决网速慢时页面展示出{{xxx}}的问题
        v-once指令：
            1、v-once所在节点在初次动态渲染后，就视为静态内容了
            2、以后数据的改变不会引起v-once所在结构的更新，可用于优化性能
        v-pre指令：
            1、跳过其所在节点的编译过程
            2、可利用它跳过：没有使用指令语法、没有使用插值语法的节点，会加快编译

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>
<style>
    [v-cloak] {
        display: none;
    }
</style>

<body>
    <!-- 
        我们学过的指令：
            v-bind：单向绑定解析表达式，可简写为xxx
            v-model：双向数据绑定
            v-for：遍历数组、对象、字符串
            v-on：绑定事件监听，可简化为@
            v-if：条件渲染（动态控制节点是否存在）
            v-else：条件渲染（动态控制节点是否存在）
            v-show：条件渲染（动态控制节点是否展示）
        v-text指令：
            1、作用：向其所在的节点中渲染文本内容。
            2、与插值语法的区别：v-text会替换掉节点中的内容，{{xx}}则不会
        v-html指令：
            1、作用：向指定节点中渲染包含html结构的内容
            2、与插值语法的区别：
                (1)v-html会替换掉节点中所有的内容，{{xx}}则不会
                (2)v-html可以识别html结构
            3、严重注意：v-html有安全性问题：
                (1)在网站上动态渲染任意HTML，是非常危险的，容易导致XSS攻击
                (2)一定要在可靠可信的内容上使用v-html，用不要用在用户提交的内容上
        v-cloak指令(没有值):
            1、本质是一个特殊属性，Vue实例创建完毕并接管容器后，会删除v-cloak属性
            2、使用css配合v-cloak可以解决网速慢时页面展示出{{xxx}}的问题
        v-once指令：
            1、v-once所在节点在初次动态渲染后，就视为静态内容了
            2、以后数据的改变不会引起v-once所在结构的更新，可用于优化性能
        v-pre指令：
            1、跳过其所在节点的编译过程
            2、可利用它跳过：没有使用指令语法、没有使用插值语法的节点，会加快编译
     -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <!-- v-text指令 -->
        <div v-text="name">你好，</div>
        <div v-text="str"></div>
        <!-- v-html指令 -->
        <div v-html="str"></div>
        <div v-html="address"></div>
        <!-- v-cloak指令 -->
        <div v-cloak>{{str}}</div>
        <!-- v-once指令 -->
        <h2 v-once>初始化的n的值是：{{n}}</h2>
        <button @click="n++">点我n++</button>
        <!-- v-pre指令 -->
        <h2 v-pre>Vue其实很简单</h2>
        <h2 v-pre>初始化的n的值是：{{m}}</h2>
        <button @click="m++" a="1">点我m++</button>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                str: '你好啊！',
                address: '<h1>欢迎光临</h3>',
                n: 0,
                m: 0,
            }
        })
    </script>

</body>

</html>
```

### 自定义指令

需求1：定义一个v-big指令，和v-text功能类似，但会把绑定的数值放大10倍
需求2：定义一个v-fbind指令，和v-bind功能类似，但可以让其所绑定的input元素默认获取焦点
         自定义指令总结：
         一、定义语法：
             (1)局部指令：new Vue({directives{指令名:配置对象}}) 或 new Vue({directives(){}})
             (2)全局指令：Vue.directive(指令名，配置对象) 或 Vue.directive(指令名，回调函数)
         二、配置对象中常用的三个回调：
             (1)bind：指令与元素成功绑定时调用。
             (2)inserted：指令所在元素被插入页面时调用。
             (3)update：指令所在模板结构被重新解析时调用。
         三、备注：
              1、指令定义时不加v-，但使用时要加v-;
              2、指令名如果是多个单词，要使用kebab-case命名方式，不要用camelCase命名。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 需求1：定义一个v-big指令，和v-text功能类似，但会把绑定的数值放大10倍
         需求2：定义一个v-fbind指令，和v-bind功能类似，但可以让其所绑定的input元素默认获取焦点
         自定义指令总结：
         一、定义语法：
             (1)局部指令：new Vue({directives{指令名:配置对象}}) 或 new Vue({directives(){}})
             (2)全局指令：Vue.directive(指令名，配置对象) 或 Vue.directive(指令名，回调函数)
         二、配置对象中常用的三个回调：
             (1)bind：指令与元素成功绑定时调用。
             (2)inserted：指令所在元素被插入页面时调用。
             (3)update：指令所在模板结构被重新解析时调用。
         三、备注：
              1、指令定义时不加v-，但使用时要加v-;
              2、指令名如果是多个单词，要使用kebab-case命名方式，不要用camelCase命名。
    -->
    <div id="root">
        <h1>Hello {{name}}</h1>
        <h2>当前的n的值是：<span v-text="n"></span></h2>
        <h2>放大10倍后n的值是：<span v-big="n"></span></h2>
        <button @click="n++">点我n加1</button><br />
        <input type="text" v-fbind:value="n">
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        new Vue({
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
                n: 1
            },
            //局部指令
            directives: {
                //big函数何时会被调用？1、指令与元素成功绑定时（一上来）；2、指令所在的模板被重新解析时。
                big(element, binding) {
                    console.log('big', this) //注意此处的this是window
                    element.innerText = binding.value * 10
                },
                fbind(element, binding) {
                    element.value = binding.value
                    element.focus()
                },
                // fbind: {
                //     //指令与元素成功绑定时（一上来）
                //     bind(element, binding) {
                //         element.value = binding.value
                //     },
                //     //指令所在元素被插入页面时
                //     inserted(element, binding) {
                //         element.focus()
                //     },
                //     //指令所在的模板被重新解析时
                //     update(element, binding) {
                //         element.value = binding.value
                //     }
                // }
            }
        })
        //写法二(全局指令)
        Vue.directive('fbind', {
            //指令与元素成功绑定时（一上来）
            bind(element, binding) {
                element.value = binding.value
            },
            //指令所在元素被插入页面时
            inserted(element, binding) {
                element.focus()
            },
            //指令所在的模板被重新解析时
            update(element, binding) {
                element.value = binding.value
            }
        })
    </script>

</body>

</html>
```

### 生命周期

生命周期：
            1、又名：生命周期回调函数、生命周期函数。生命周期钩子
            2、是什么：Vue在关键时刻帮我们调用的一些特殊名称的函数
            3、生命周期函数的名字不可更改，但函数的具体内容是程序员根据需求编写的
            4、生命周期函数中的this指向的是vm 或 组件实例对象
         常用的生命周期钩子：
            1、mounted：发送ajax请求、启动定时器、绑定自定义事件、订阅信息等【初始化操作】
            2、beforeDestroy：清除定时器、解绑自定义事件、取消订阅信息等【收尾工作】
         关于销毁Vue实例
            1、销毁后借助Vue开发者工具看不到任何信息。
            2、销毁后自定义事件会失效，但原生DOM事件依然有效。
            3、一般不会再beforeDestroy操作数据。因为即便操作数据，也不会再触发更新流程了。

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\生命周期1.png)

![生命周期2](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\生命周期2.png)

![生命周期3](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\生命周期3.png)

![生命周期4](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\生命周期4.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 生命周期：
            1、又名：生命周期回调函数、生命周期函数。生命周期钩子
            2、是什么：Vue在关键时刻帮我们调用的一些特殊名称的函数
            3、生命周期函数的名字不可更改，但函数的具体内容是程序员根据需求编写的
            4、生命周期函数中的this指向的是vm 或 组件实例对象
         常用的生命周期钩子：
            1、mounted：发送ajax请求、启动定时器、绑定自定义事件、订阅信息等【初始化操作】
            2、beforeDestroy：清除定时器、解绑自定义事件、取消订阅信息等【收尾工作】
         关于销毁Vue实例
            1、销毁后借助Vue开发者工具看不到任何信息。
            2、销毁后自定义事件会失效，但原生DOM事件依然有效。
            3、一般不会再beforeDestroy操作数据。因为即便操作数据，也不会再触发更新流程了。
         -->
    <div id="root">
        <h1 :style="{opacity}">Hello {{name}}</h1>
        <button @click="stop">停止定时器</button>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //创建Vue实例
        const vm =
            new Vue({
                el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
                data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                    name: 'World',
                    opacity: 1,
                },
                methods: {
                    stop() {
                        this.$destroy()
                    }
                },
                // beforeCreate() {
                //     console.log('beforeCreate')
                // },
                // created() {
                //     console.log('created')
                // },
                // beforeMount() {
                //     console.log('beforeMount')
                // },
                // Vue完成模板的解析并把初始化的真实DOM元素放入页面后（挂载完毕）调用mounted
                mounted() {
                    console.log('开起了一个定时器')
                    this.timer = setInterval(() => {
                        this.opacity -= 0.01
                        if (this.opacity <= 0) this.opacity = 1
                    }, 16)
                },
                // beforeUpdate() {
                //     console.log('beforeUpdate')
                // },
                // updated() {
                //     console.log('updated')
                // },
                beforeDestroy() {
                    console.log('beforeDestroy')
                    clearInterval(this.timer)
                },
                destroyed() {
                    console.log('destroyed')
                }
            })
        //通过外部的定时器实现（不推荐）
        // setInterval(() => {
        //     vm.opacity -= 0.01
        //     if (vm.opacity <= 0) {
        //         vm.opacity = 1
        //     }
        // }, 16)
    </script>

</body>

</html>
```



# 第二章       Vue 组件化编程



## 模块与组件、模块化与组件化



### 模块

1、理解：向外提供特定功能的js程序、一般就是一个 js 文件

2、为什么：js 文件很多很复杂

3、作用：复用 js ，简化 js 的编写，提离 js 运行效率

### 组件

1、理解：用来实现局部（特定）功能效果的代码集合（html/css/js/image...）

2、为什么：一个界面的功能很复杂

3、作用：复用编码，简化项目编码，提高运行效率

### 模块化

当应用中的 js 都以模块来编写的，那这个应用就是一个模块化应用。

### 组件化

当应用中的功能都是多组件的方式来编写的，那这个应用就是一个组件化的应用。



![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\组件的定义.png)

![传统方式编写应用](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\传统方式编写应用.png)

![简单组件之间传参](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\组件化编程.png)

![组件的定义](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\Vue与VueComponent的关系.png)

![组件化编程](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\简单组件之间传参.png)



## 非单文件组件

### 非单文件组件

Vue中使用组件的三大步骤：
            一、定义组件（创建组件）
            二、注册组件
            三、使用组件（写组件标签）
         一、如何定义一个组件？
                使用Vue.extend(options)创建，其中options和new Vue(options)时传入的那个options几乎一样，但也有点区别：
                区别如下：
                    1、el不要写，为什么？——最终所有的组件都要经过一个vm的管理，由vm中的el决定服务那个容器。
                    2、data必须写成函数，为什么？——避免组件被服用时，数据存在引用关系。
                备注：使用template可以配置组件结构。
         二、如何注册组件？
                1、局部注册：靠new Vue的时候传入components选项
                2、全局注册：靠Vue.component('组件名',组件)
         三、编写组件标签：
                <school></school>
         几个注意点：
            1、关于组件名：
                一个单词组成：
                    第一种写法（首字母小写）：school
                    第二种写法（首字母大写）：School
                多个单词组成：
                    第一种写法（kebab-case命名）：my-school
                    第二种写法（CamelCase命名）：MySchool（需要Vue脚手架支持）
                备注：
                    (1)组件名尽可能回避HTML中已有的元素名称，例如：h2、H2都不行。
                    (2)可以使用name配置项指定组件在开发者工具中呈现的名字。
            2、关于组件标签：
                第一种写法：<school></school>
                第二种写法：<school/>
                备注：不用使用脚手架时，<school/>会导致后续组件不能渲染。
            3、一个简写方式：
                const school = Vue.extend(options) 可简化为： const school = options

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- Vue中使用组件的三大步骤：
            一、定义组件（创建组件）
            二、注册组件
            三、使用组件（写组件标签）
         一、如何定义一个组件？
                使用Vue.extend(options)创建，其中options和new Vue(options)时传入的那个options几乎一样，但也有点区别：
                区别如下：
                    1、el不要写，为什么？——最终所有的组件都要经过一个vm的管理，由vm中的el决定服务那个容器。
                    2、data必须写成函数，为什么？——避免组件被服用时，数据存在引用关系。
                备注：使用template可以配置组件结构。
         二、如何注册组件？
                1、局部注册：靠new Vue的时候传入components选项
                2、全局注册：靠Vue.component('组件名',组件)
         三、编写组件标签：
                <school></school>
         几个注意点：
            1、关于组件名：
                一个单词组成：
                    第一种写法（首字母小写）：school
                    第二种写法（首字母大写）：School
                多个单词组成：
                    第一种写法（kebab-case命名）：my-school
                    第二种写法（CamelCase命名）：MySchool（需要Vue脚手架支持）
                备注：
                    (1)组件名尽可能回避HTML中已有的元素名称，例如：h2、H2都不行。
                    (2)可以使用name配置项指定组件在开发者工具中呈现的名字。
            2、关于组件标签：
                第一种写法：<school></school>
                第二种写法：<school/>
                备注：不用使用脚手架时，<school/>会导致后续组件不能渲染。
            3、一个简写方式：
                const school = Vue.extend(options) 可简化为： const school = options
                -->
    <div id="root1">
        <h1>Hello {{name}}</h1>
        <!-- 第三步：编写组件标签 -->
        <school></school>
        <student></student>
        <hello></hello>
    </div>
    <div id="root2">
        <!-- 第三步：编写组件标签 -->
        <hello></hello>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //第一步：创建组件
        //创建student组件
        const student = Vue.extend({
            template: `<div><h2>你好啊！{{studentName}}</h2></div>`,
            data() {
                return {
                    studentName: '张三',
                    age: 18,
                }
            }
        })
        // 简化定义组件
        // const student = {
        //     template: `<div><h2>你好啊！{{studentName}}</h2></div>`,
        //     data() {
        //         return {
        //             studentName: '张三',
        //             age: 18,
        //         }
        //     }
        // }
        //创建school组件
        const school = Vue.extend({
            template: `<div><h2>你好啊！{{schoolName}}</h2></div>`,
            data() {
                return {
                    schoolName: '西大',
                    address: '西方路'
                }
            }
        })
        //创建hello组件
        const hello = Vue.extend({
            template: `<div><h2>你好啊！{{name}}</h2></div>`,
            data() {
                return {
                    name: 'Tom'
                }
            }
        })
        // 第二步：注册组件（全局注册）
        Vue.component('hello', hello)

        //创建Vue实例
        new Vue({
            el: '#root1',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
            },
            //第二步：注册组件（局部注册）
            components: {
                school,
                student,
            }
        })
        new Vue({
            el: '#root2'
        })
    </script>

</body>

</html>
```

### 组件的嵌套

关于VueComponent：
            1、school组件本质是一个名为VueComponent的构造函数，且不是程序员定义的，是Vue.extend生成的.
            2、我们只需要写<school></school>，Vue解析时会帮我们创建school组件的实例对象。
               即Vue帮我们执行的：new VueComponent(options)。
            3、特别注意：每次调用Vue.extend，返回的都是一个全新的vueComponent!!!
            4、关于this指向：
                (1)组件配置中：
                        data函数、methods中的函数、watch中的函数、computed中的函数，它们的this均是【VueComponent实例对象】
                (2)new Vue()配置中：
                        data函数、methods中的函数、watch中的函数、computed中的函数，它们的this均是【Vue实例对象】
            5、VueComponent的实例对象，以后简称vc（也可称之为：组件实例对象）。
                Vue的实例对象，以后简称vm。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- Vue中使用组件的三大步骤：
            一、定义组件（创建组件）
            二、注册组件
            三、使用组件（写组件标签）
         一、如何定义一个组件？
                使用Vue.extend(options)创建，其中options和new Vue(options)时传入的那个options几乎一样，但也有点区别：
                区别如下：
                    1、el不要写，为什么？——最终所有的组件都要经过一个vm的管理，由vm中的el决定服务那个容器。
                    2、data必须写成函数，为什么？——避免组件被服用时，数据存在引用关系。
                备注：使用template可以配置组件结构。
         二、如何注册组件？
                1、局部注册：靠new Vue的时候传入components选项
                2、全局注册：靠Vue.component('组件名',组件)
         三、编写组件标签：
                <school></school>
         几个注意点：
            1、关于组件名：
                一个单词组成：
                    第一种写法（首字母小写）：school
                    第二种写法（首字母大写）：School
                多个单词组成：
                    第一种写法（kebab-case命名）：my-school
                    第二种写法（CamelCase命名）：MySchool（需要Vue脚手架支持）
                备注：
                    (1)组件名尽可能回避HTML中已有的元素名称，例如：h2、H2都不行。
                    (2)可以使用name配置项指定组件在开发者工具中呈现的名字。
            2、关于组件标签：
                第一种写法：<school></school>
                第二种写法：<school/>
                备注：不用使用脚手架时，<school/>会导致后续组件不能渲染。
            3、一个简写方式：
                const school = Vue.extend(options) 可简化为： const school = options
         关于VueComponent：
            1、school组件本质是一个名为VueComponent的构造函数，且不是程序员定义的，是Vue.extend生成的.
            2、我们只需要写<school></school>，Vue解析时会帮我们创建school组件的实例对象。
               即Vue帮我们执行的：new VueComponent(options)。
            3、特别注意：每次调用Vue.extend，返回的都是一个全新的vueComponent!!!
            4、关于this指向：
                (1)组件配置中：
                        data函数、methods中的函数、watch中的函数、computed中的函数，它们的this均是【VueComponent实例对象】
                (2)new Vue()配置中：
                        data函数、methods中的函数、watch中的函数、computed中的函数，它们的this均是【Vue实例对象】
            5、VueComponent的实例对象，以后简称vc（也可称之为：组件实例对象）。
                Vue的实例对象，以后简称vm。
                -->
    <div id="root">
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //第一步：创建组件
        //创建student组件
        const student = Vue.extend({
            template: `<div><h2>你好啊！{{studentName}}</h2></div>`,
            data() {
                return {
                    studentName: '张三',
                    age: 18,
                }
            }
        })
        //创建school组件
        const school = Vue.extend({
            //编写嵌套student标签
            template: `<div>
                <h2>你好啊！{{schoolName}}</h2>
                <student></student>
                </div>`,
            data() {
                return {
                    schoolName: '西大',
                    address: '西方路'
                }
            },
            //组件嵌套
            components: {
                student,
            }
        })
        const app = Vue.extend({
            template: `<div><school></school></div>`,
            components: {
                school,
            }
        })

        //创建Vue实例
        new Vue({
            template: '<app></app>',
            el: '#root',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            //第二步：注册组件（局部注册）
            components: {
                app
            }
        })
    </script>

</body>

</html>
```

### 一个重要的内置关系

​        1、一个重要的内置关系;VueComponent.prototype.__proto__===Vue.propotype。
​        2、为什么要有这个关系：让组件实例对象 vc 可以访问到 Vue 原型上的属性、方法。

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue@2/dist/vue.js"></script>
</head>

<body>
    <!-- 
        1、一个重要的内置关系;VueComponent.prototype.__proto__===Vue.propotype。
        2、为什么要有这个关系：让组件实例对象 vc 可以访问到 Vue 原型上的属性、方法。
     -->
    <div id="root1">
        <h1>Hello {{name}}</h1>
        <!-- 第三步：编写组件标签 -->
        <school></school>
        <student></student>
        <hello></hello>
    </div>
    <div id="root2">
        <!-- 第三步：编写组件标签 -->
        <hello></hello>
    </div>
    <script type="text/javascript">
        Vue.config.productionTip = false //阻止 vue 在启动时生成生产提示
        //第一步：创建组件
        //创建student组件
        const student = Vue.extend({
            template: `<div><h2>你好啊！{{studentName}}</h2></div>`,
            data() {
                return {
                    studentName: '张三',
                    age: 18,
                }
            }
        })
        const school = Vue.extend({
            template: `<div><h2>你好啊！{{schoolName}}</h2>
                <h2>你好啊！{{address}}</h2>
                <button @click="showInfo">点击我提示信息</button>
                </div>`,
            data() {
                return {
                    schoolName: '西大',
                    address: '西方路'
                }
            },
            methods: {
                showInfo() {
                    alert('你好！')
                    console.log(this)
                }
            }
        })
        //创建hello组件
        const hello = Vue.extend({
            template: `<div><h2>你好啊！{{name}}</h2></div>`,
            data() {
                return {
                    name: 'Tom'
                }
            }
        })
        //创建Vue实例
        new Vue({
            el: '#root1',//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串。
            data: { //data 中用于存储数据，数据供el所指定的容器去使用，值我们暂时先写成一个对象。
                name: 'World',
            },
            //第二步：注册组件（局部注册）
            components: {
                school,
                student,
                hello,
            }
        })
    </script>

</body>

</html>
```



# 第三章       使用 Vue 脚手架



## 初始化脚手架

### 说明

Vue 脚手架是 Vue 官方提供的标准化开发工具（开发平台）。

### 具体步骤

第一步（仅第一次执行）：全局安装@vue/cli.

```vue
npm install -g @vue/cli
```

第二步：切换到你要创建项目的目录，然后使用命令创建项目。

```vue
vue create xxxx
```

第三步：启动项目

```vue
npm run serve
```

备注：

1、如果出现下载缓慢请配置 npm 淘宝镜像：npm config set registry

https://registy.npm.taobao.org

2、Vue脚手架隐藏了所有 webpack 相关的配置，若想查看具体的 webpack 配置，请执行：

vue inspect > output.js



###  关于不同版本的Vue

\> 1、vue.js 与 vue.runtime.xxx.js 的区别：

​    (1)vue.js是完整版的Vue，包含：核心功能+模板解析器。

​    (2)vue.runtime.xxx.js是运行版的Vue，只包含：核心功能：没有模板解析器。

\> 2、因为vue.runtime.xxx.js没有模板解析器，所以不能使用  template配置项，需要使用

​     render函数接收到的createElement函数去指定具体内容。



## Vue 脚手架的使用

### vue.config.js 配置文件

\> 使用vue inspect > output.js 可以查看到Vue脚手架的默认配置

\> 使用vue.config.js 可以对脚手架进行个性化定制，详情见：https//cli.vue.js.org/zh



### ref 属性

\> 被用来给元素或子组件注册引用信息（id的替代者）

\> 应用在html标签上获取的是真实DOM元素，应用在组件标签上是组件实例对象（vc）

\> 使用方式：

   打标识：<h1 ref="xxx">......</h1> 或 <School ref="xxx"></School>

   获取：this.$refs.xxx



### 配置项props

\> 功能：让组件接受外部传过来的数据

​    (1)传递数据：

​        <Demo name="xxx"/>

​    (2)接收数据：

​        第一种方式（只接收）：

​            props['name']

​        第二种方式（限制类型）：

​            props:{

​                name:Number

​            }

​        第三种方式（限制类型、限制必要性、指定默认值）：

​            props:{

​                name:{

​                    type:String,//类型

​                    required:true,//必要性

​                    default:'Mike' //默认值

​                }

​            }

  备注：props是只读的，vue底层会监测你对props的修改，如果进行了修改，就会发出警告，若业务需求确实需要修改，那么请复制props的内容到data中一份，然后去修改data中的数据。



### mixin(混入)

\> 功能：可以把多个组件共用的配置提取成一个混入对象

 使用方式：

​    第一步定义混合，例如：

​      {

​          data(){....},

​          methods:{....},

​          ....

​      }

​    第二步使用混入，例如：

​      (1)全局混入：Vue.mixin(xxx)

​      (2)局部混入：mixins:['xxx']



### 综上练习证明如下代码：

main.js、App.vue、school.vue、student.vue、mixin.js

**main.js**

```javascript
/*
该文件是整个项目的入口文件
*/
// 引入Vue
import Vue from 'vue'
// 引入APP组件，它是所有组件的父组件
import App from './App.vue'
//mixin
import { h } from './mixin'
// 关闭vue的生产提示
Vue.config.productionTip = false

Vue.mixin(h)
// 创建Vue实例对象 --- vm
new Vue({
  //简化
  render: h => h(App),
}).$mount('#app')   //相当于 el:'#root',

```

**App.vue**

```vue
<template>
  <div>
    <h1 v-text="msg" ref="title"></h1>
    <button @click="showDOM" ref="btn">点我输出上方的DOM元素</button>
    <School ref="sch" />
    <Student name="李四" sex="女" :age="18" />
  </div>
</template>

<script>
//引入School组件
import Student from "./components/Student";
import School from "./components/School";

export default {
  name: "App",
  components: { School, Student },
  data() {
    return {
      msg: "欢迎光临",
    };
  },
  methods: {
    showDOM() {
      console.log(this.$refs.title);
      console.log(this.$refs.btn);
      console.log(this.$refs.sch);
    },
  },
};
</script>
```

**School.vue**

```vue
<template>
  <div>
    <h2 @click="showName">{{ msg }}</h2>
  </div>
</template>
<script>
import { h } from "../mixin";
export default {
  name: "School",
  data() {
    return {
      msg: "你好！",
    };
  },
  mixins: [h],
  mounted() {
    console.log("你好啊！");
  },
};
</script>
```

**student.vue**

```vue
<template>
  <div>
    <h2 @click="showName">{{ msg }}</h2>
    <h2>学生姓名：{{ name }}</h2>
    <h2>学生性别：{{ sex }}</h2>
    <h2>学生年龄：{{ myAge + 1 }}</h2>
    <button @click="updateAge">尝试修改收到的年龄</button>
  </div>
</template>

<script>
export default {
  name: "Student",
  data() {
    return {
      msg: "我是一名学生",
      myAge: this.age,
    };
  },
  methods: {
    updateAge() {
      this.age++;
    },
  },
  // 1、简单声明接收
  // props:['name','sex','age'] //简单接收

  // 2、接收的同时对数据进行类型的限制
  //   props: {
  //     name: String,
  //     age: Number,
  //     sex: String,
  //   },

  // 3、接受的同时对数据进行类型限制+默认值的指定+必要性的限制
  props: {
    name: {
      type: String, //name的类型为字符串
      required: true, //name是否是必要的
    },
    age: {
      type: Number,
      default: 22, //默认值
    },
    sex: {
      type: String,
      required: true,
    },
  },
};
</script>
```

**mixin.js**

```javascript
export const h = {
    methods: {
        showName() {
            alert(this.msg)
        }
    }
}
```



### 插件

\> 功能：用于增强Vue

\> 本质：包含install方法的一个对象，install的第一个参数是Vue，第二个以后的参数是插件使用者传递的数据

\> 定义插件：

   对象：install = function(Vue,options){

​       //1、添加全局过滤器

​       Vue.filter(....)

​       //2、添加全局指令

​       Vue.directive(....)

​       //3、配置全局混入（合）

​       Vue.mixin(....)

​       //4、添加实例方法

​       Vue.prototype.$myMethod = function(){...}

​       Vue.prototype.$myProperty = xxxx

   }

   使用插件：Vue.use()



### 样式挑选(css/less)

使用 less 需安装

```vue
//查看 webpack
npm view webpack versions
//查看 less 的版本
npm view less-loader versions
//安装 less
npm i less-loader@7
```



### Todo-list 案例

**组件化编码流程（通用）**

1、实现静态组件：抽取组件，使用组件实现静态页面效果

2、展示动态数据：

（1）数据的类型、名称是什么？

（2）数据保存在那个组件？

3、交互——从绑定事件监听开始



**代码略**



**总结TodoList案例**

1、组件化编码流程：

​     (1)拆分静态组件：组件要按照功能点拆分，命名不要与html元素冲突

​     (2)实现动态组件：考虑数据的存放位置，数据是一个组件在用，还是一些组件在用：

​        1）一个组件在用：放在组件自身即可。

​        2）一些组件在用：放在他们共同的父组件上（< span style="color:red" >状态提升< /span >)

​     (3)实现交互：从绑定事件开始。

2、props适用于：

​     (1)父组件==>子组件通信

​     (2)子组件==>父组件通信（要求父先给子一个函数）

3、使用v-model时要切记：v-model绑定的值不能是props传过来的值。因为prop是不可以修改的！

4、props传过来的若是对象类型的值，修改对象中的属性时Vue不会报错，但不推荐这样做。



### 浏览器本地存储

**webStorage**

1、存储内容大小一般支持5MB左右（不同浏览器可能不一样）

2、浏览器端通过 WIndow.seesionStorage 和 Window.localStorage 属性来实现本地存储机制。

3、相关API：

   (1)xxxxStorage.setItem('key','value');

   该方法接收一个键和值作为参数，会把键值对添加到存储中，如果键名存在，则更新其对应的值。

   (2)xxxxStorage.getItem('key');

   该方法接收一个键名作为参数，返回键名对应的值。

   (3)xxxxStorage.removeItem('key');

   该方法接收一个键名作为参数，并把该键名从存储中删除。

   (4)xxxxStorage.clear();

   该方法会清空存储中的所有数据

4、备注：

   (1)SessionStorage存储的内容会随着浏览器窗口关闭而消失。

   (2)LocalStorage存储的内容，需要手动清楚才会消失。

   (3)xxxx.Storage.getItem(xxx)如果xxx对应的value获取不到，那么getItem的返回值是null。

   (4)JSON.parse(null)的结果依然时null。



### 组建的自定义事件

1、一种组件间通信的方式，适用于：子组件===>父组件

2、使用场景：A是父组件，B是子组件，B想给A传数据，那么就要在A中给B绑定自定义事件（事件的回调在A中）。

3、绑定自定义事件：

​    （1）第一种方式，在父组件中：<Demo @atguigu="texs"/>或<Demo v-on:atguigu="test"/>

​    （2）第二种方式，在父组件中：

```vue
<Demo ref="demo"/>
...
mounted(){
this.$ref.xxx.$on('atguigu',this.test)
}
```

​     （3）若想让自定义事件只能触发一次，可以使用 once 修饰符，或 $once 方法。

4、绑定自定义事件：this.$emit('atguigu',数据)

5、解绑自定义事件：this.$off('atguigu')

6、组件上也可以绑定原生DOM事件，需要使用 active 修饰符。

7、注意：通过 this.$ref.xxx.$on('atguigu',回调) 绑定自定义事件时，回调要配置在 methods 中，要么用箭头函数，否则 this 指向会出问题！



### 全局事件总线（GlobalEventBus）

1、一种组件间通信的方式，适用于任意组件间通信。

2、安装全局事件总线：

```vue
new Vue({
...
beforeCreate(){
       Vue。prototype.$bus = this //安装全局事件总线，$bus就是当前应用的vm
}
...
})
```

3、使用事件总线：

（1）接收数据：A组件想接收数据，则在A组件中给$bus绑定自定义事件，事件的回调留在A组件自身。

```vue
methods(){
demo(data){...}
}
...
mounted(){
this.$bus.$on('xxx',this.demo)
}
```

（2）提供数据：this.$bus.$emit('xxx',数据)

4、最好在 beforeDestroy钩子中，用$off去解绑当前组件所用到的事件。



### 消息订阅与发布（pubsub）

1、一种组件间通信的方式，适用于任意组件间通信。

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\订阅和发布.png)

2、使用步骤：

（1）安装pubsub：npm i pubsub-js

（2）引入：import pubsub from 'pubsub-js'

（3）接收数据：A组件想接收数据，则在A组件中订阅消息，订阅的回调留在A组件自身。

```vue
methods(){
demo(data){...}
}
...
mounted(){
this.pid = pubsub.subscribe('xxx',this.demo)//订阅消息
}
```

（4）提供数据：pubsub.publish('xxx',数据)

（5）最好在 beforeDestory 钩子中，用 Pubsub.unsubscribe(pid) 去< span style="color:red" >取消订阅。< /span >  



### nextTick

1、语法：this.$nextTick(回调函数)

2、作用：在下一次 DOM 更新结束后执行其指定的回调。

3、什么时候用：当改变数据后，要基于更新后的新 DOM 进行某些操作时，要在 nextTick 所指定的回调函数中执行。



### Vue 封装的过度与画面

1、作用：在插入、更新或移除 DOM 元素时，在合适的时候元素添加样式类名。

2、图示：

![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\Vue封装的过度与动画.png)

3、写法：

（1）准备好样式：

元素进入的样式：

​                  （1）v-enter：进入的起点

​                  （2）v-enter-actice：进入过程中

​                  （3）v-enter-to：进入的终点

元素离开的样式：

​                  （1）v-leave：离开的起点

​                  （2）v-leave-actice：离开过程中

​                  （3）v-leave-to：离开的终点

（2）使用 <transition>包裹要过度的元素，并配置name属性：

```vue
<transition name="hello">
    <h1 v-show="isShow">你好啊！</h1>
</transition>
```

（3）备注：若有多个元素需要过度，则需要使用：<transotion-group>，且每个元素都要指定 key 值。



# 第四章       Vue中的Ajax



## vue 脚手架配置代理

**方法一**

在 vue.config.js 中添加如下配置：

```vue
devServer:{
proxy:'http://localhost:5000'
}
```

说明：

1、优点：配置简单，请求资源时直接发给前端（8080）即可。

2、缺点：不能配置多个代理，不能灵活的控制请求是否走代理。

3、工作方式：若按照上述配置代理，当请求了前端不存在的资源时，那么该请求会转发服务器（优先匹配前端资源）

**方法二**

编写 vue.config.js 配置具体代理规则：

```vue
module.exports = {
devServer:{
proxy:{
'api1':{//匹配所有以'api1'开头的请求路径
target:'http://localhost:5000',//代理目标的基础路径
changeOrigin:true,
pathRewrite:{'^api1':''}
},
'api2':{//匹配所有以'api2'开头的请求路径
target:'http://localhost:5001',//代理目标的基础路径
changeOrigin:true,
pathRewrite:{'^api2':''}
},
}
}
}
/*
欺骗浏览器进行访问
changeOrigin设置为 true 时，服务器收到的请求中的 host 为 localhost:5000
changeOrigin设置为 false 时，服务器收到的请求中的 host 为 localhost:8080
changeOrigin默认值为true
*/
```

说明：

1、优点：可以配置多个代理，且可以灵活地控制请求是否走代理。

2、缺点：配置略微繁琐，请求资源时必须加前缀。



## vue 项目中常见的 2 个 Ajax 库

1、**axios：**通用的 Ajax 请求库，官方推荐，使用广泛。

2、**vue-resource：**vue 插件库，vue1.x使用广泛，官方已不维护。



## 插槽

1、作用：让父组件可以向子组件指定的位置插入 html 结构，也是一种组件间通信的方式，适用于 **父组件===>子组件**。

2、分类：默认插槽、具名插槽、作用域插槽

3、使用方式：

（1）默认插槽：

```vue
<!--父组件中-->
<Category>
    <div>html结构1</div>
</Category>
<!--子组件中-->
<template>
<div>
    <!--定义插槽-->
    <slot>插槽默认内容...</slot>
</div>
</template>
```

（2）具名插槽：

```vue
<!--父组件中-->
<Category>
  <template slot="center">
    <div>html结构1</div>
  </template>
  <template slot="footer">
    <div>html结构1</div>
  </template>
</Category>
<!--子组件中-->
<template>
<div>
    <!--定义插槽-->
    <slot name="center">插槽默认内容...</slot>
    <slot name="footer">插槽默认内容...</slot>
</div>
</template>
```

（3）作用域插槽：

1、理解：数据在组件的自身，但根据数据生成的结构需要组件的使用者来决定。（games数据在Category组件中，但使用数据所遍历出来的结构由App组件决定）

2、具体编码：

```vue
<!--父组件中-->
<Category>
  <template scope="scopeData">
    <!--生成的是ul列表--> 
    <ul>
        <li v-for="g in scopeData.games" :key="g">{{g}}</li>
    </ul>
  </template>
</Category>
<!--子组件中-->
<template>
<div>
    <!--定义插槽-->
    <slot :games="games">我是一些默认值，当使用者没有传递具体结构时，我会出现</slot>
</div>
</template>
<script>
    export default{
        name:'Category',
        props:['title'],
        data(){
            return{
                games:['红色警戒','穿越火线','超级玛丽']
            }
        }
    }
</script>
```



# 第五章       vuex



## 理解 vuex

### vuex 是什么

概念：专门在 Vue 中实现集中式状态（数据）管理的一个Vue插件，对 vue 应用中多个组件的共享状态进行集中式的管理（读/写），也是一种组件间通信的方式，且适用于任意组件间通信。

2、Github 地址：https://github.com/vuejs/vuex



### 什么时候使用 Vuex

1、多个组件依赖于同一状态。

2、来自不同组件的行为需要变更同一状态。



![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\vuex-store.png)

![vuex不走actions](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\vuex不走actions.png)

![vuex操作步骤](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\vuex操作步骤.png)

![vuex流程图](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\vuex流程图.png)

![vuex三步走](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\vuex三步走.png)

![vuex原图](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\vuex原图.png)

![多组件共享数据-vuex实现](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\多组件共享数据-vuex实现.png)

![多组件共享数据-总线](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\多组件共享数据-总线.png)



## Vuex

### 概念

在 Vue 中实现集中式状态（数据）管理的一个 Vue 插件，对 vue 应用中多个组件的共享状态进行集中式的管理（读/写），也是一种组件间通信的方式，且适用于任意组件间通信。

### 何时使用

多个组件需要共享数据时

### 搭建 vuex 环境

1、创建文件：src/store/index.js

```javascript
//引入Vue核心库
import Vue from 'vue'
//引入Vuex
import Vuex, { Store } from 'vuex'
//应用Vuex插件
Vue.use(Vuex)
//暴露Vuex
export default new Vuex.Store({
  //准备state--用于存储数据
  state: {
  },
  //准备mutations--用于操作数据（state）
  mutations: {
  },
  //准备actions--用于响应组件中的动作
  actions: {
  },
  modules: {
  }
})
//暴露store
// export default Store

```

2、在 main.js 中创建 vm 时传入 store 配置项

```javascript
//引入 store
import store from './store'
//创建 vm
new Vue({
    el:'#app',
    render:h=>h(App)
    store
})
```



### 基本使用

1、初始化数据，配置 actions、配置 mutations、操作文件 store.js

```javascript
import Vue from 'vue'
import Vuex, { Store } from 'vuex'

Vue.use(Vuex)

export default new Vuex.Store({
  //准备state--用于存储数据
  state: {
    sum: 0,//当前的和
  },
  //准备mutations--用于操作数据（state）
  mutations: {
    JIA(state, value) {
      state.sum += value
    },
    JIAN(state, value) {
      state.sum -= value
    }
  },
  //准备actions--用于响应组件中的动作
  actions: {
    jia(context, value) {
      console.log('actions中的jia被调用了')
      context.commit('JIA', value)
    },
    jian(context, value) {
      console.log('actions中的jian被调用了')
      context.commit('JIAN', value)
    },
    jiaOdd(context, value) {
      if (context.state.sum % 2) {
        console.log('actions中的jiaOdd被调用了')
        context.commit('JIA', value)
      }
    },
    jiaWait(context, value) {
      setTimeout(() => {
        console.log('actions中的jiaWait被调用了')
        context.commit('JIA', value)
      }, 500)
    }
  },
  modules: {
  }
})
//暴露store
// export default Store
```

2、组件中读取 vuex 中的数据：$store.state.sum

3、组件中修改 vuex 中的数据：$store.dispatch('actions中的方法名',数据)或 $store.commit('mutations中的方法名',数据)

备注：若没有网络请求或其他业务逻辑，组件中也可以越过 actions，即不写 dispatch，直接编写 commit。



### 四个 map 方法的使用

1、**mapState 方法：**用于帮助我们映射 state 中的数据为计算属性

```vue
computed:{
//借助 mapState 生成计算属性，sum、school、student（对象属性）
//对象写法
    ...mapState({sum:'sum',school:'school',student:'student'})
//数组写法
    ...mapState(["sum", "school", "student"]),
  },
}
```

2、**mapGetters 方法：**用于帮助我们映射 getters 中的数据为计算属性

```vue
computed:{
//借助 mapGetters 生成计算属性，bigSum（对象属性）
// 对象写法
    // ...mapGetters({bigSum:'bigSum'})
// 数组写法
    ...mapGetters(["bigSum"]),
  },
}
```

3、**mapActions 方法：**用于帮助我们生成与 actions 对话的方法，即：包括 $store.dispatch(xxx)的函数

```vue
methods:{
//靠 mapActions 生成：incrementOdd、incrementWait（对象形式）
...mapActions({incrementOdd:'jiaOdd',incrementWait:'jiaWait'})
//靠 mapActions 生成：incrementOdd、incrementWait（数组形式）
...mapActions(['jiaOdd','jiaWait'])
}
```

4、**mapMutations 方法：**用于帮助我们生成与 mutations 对话的方法，即：包括 $store.commit(xxx)的函数

```vue
methods:{
//靠 mapMutations 生成：increment、decrement（对象形式）
...mapMutations({increment:'JIA',decrement:'JIAN'})
//靠 mapMutations 生成：increment、decrement（数组形式）
...mapMutations(['JIA','JIAN'])
}
```



### 模块化+命名空间

1、目的：让代码更好维护，让多种数据分类更加明确。

2、修改 store.js

```javascript
const countAbout = {
    namespaced:true,//开启命名空间
    state:{x:1},
    mutations:{...},
    actions:{...},
    getters:{
        bigSum(state){
            return state.sum*10
        }
    }
}
const personAbout = {
    namespaced:true,//开启命名空间
    state:{person:[{'...'},{'...'}]},
    mutations:{...},
    actions:{...},
}
const store = new Vuex.Store({
    modules:{
        countAbout,
        personAbout,
    }
})
```

3、开启命名空间后，组件中读取 state 数据：

```vue
//方式一：自己直接读取
this.$store.state.personAbout.list
//方式二：借助 mapState 读取：
...mapState('countAbout',['sum','school','student'])
```

4、开启命名空间后，组件中读取 getters 数据：

```vue
//方式一：自己直接读取
this.$store.getters['personAbout/firstPersonName']
//方式二：借助 mapGetters 读取：
...mapGetters('countAbout',['bigSum'])
```

5、开启命名空间后，组件中调用 dispatch：

```vue
//方式一：自己直接dispatch
this.$store.dispatch('personAbout/addPersonWang',person)
//方式二：借助 mapActions：
...mapActions('countAbout',{incrementOdd:'jiaOdd',incrementWait:'jiaWait'})
```

6、开启命名空间后，组件中调用 commit：

```vue
//方式一：自己直接commit
this.$store.commit('personAbout/ADD_PERSON',person)
//方式二：借助 mapMutations：
...mapMutations('countAbout',{increment:'JIA',decrement:'JIAN'})
```



# 第六章       vue-route



## 相关理解

### vue-router 的理解

vue 的一个插件库，专门用来实现SPA应用

对 SPA 应用的理解

1、单页 Web 应用（single page web application，SPA）。

2、整个应用只有一个完整的页面。

3、点击页面中的导航链接不会刷新也米娜，只会做页面的局部刷新。

4、数据需要通过 ajax 请求获取。

### 路由的理解

**1、什么是路由？**

1、一个路由就是一组映射关系（key-value）

2、key 为路径，value 可能是 function 或 component

**2、路由分类**

1、后端路由：

（1）理解：value 是 function，用于处理客户端提交的请求

（2）工作过程：服务器接收到一个请求时，根据请求路径找到匹配的函数来处理请求，返回响应数据。

2、前端路由：

（1）理解：value 是 component，用于展示页面内容。

（2）工作过程：当浏览器的路径改变时，对应的组件就会显示。



![](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\路由器.png)

![SPA(single page web application)应用](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\SPA(single page web application)应用.png)

![路由器](C:\Users\FY\Desktop\笔记\学习笔记\Vue_image\route流程.png)



## 路由

1、理解：一个路由（route）就是一组映射关系（key-value），多个路由需要路由器（router）进行管理。

2、前端路由：key 是路径，value 是组件。

### 基本使用

1.安装 vue-router，命令：npm i vue-router

2、应用插件：vue.use(VueRouter)

3、编写router配置项：

```javascript
import Vue from 'vue'
import VueRouter from 'vue-router'
//引入插件
import Home from './components/Home'
import About from './components/About'

Vue.use(VueRouter)

const routes = [
  {
    path: '/home',
    name: 'Home',
    component: Home
  },
  {
    path: '/about',
    name: 'About',
    componnet: About
  }
]
//创建路由router的实例对象，去管理一组一组的路由规则
const router = new VueRouter({
  mode: 'history',
  base: process.env.BASE_URL,
  routes
})
//暴露路由
export default router
```

4、实现切换（active-class可配置高亮样式）

```html
<router-link active-class="active" to="/about">About</router-link>
```

5、指定展示位置

```html
<router-view></router-view>
```

### 几个注意点

1、路由组件通常存放在 pages 文件夹，一般组件通常存放在 components 文件夹。

2、通常切换，“隐藏”了的路由组件，默认是被销毁的，需要的时候再去挂载。

3、每个组件都有自己的 $route 属性，里面存储着自己的路由信息。

4、整个应用只有一个 router，可以通过组建的 $router 属性获取到。



### 多级路由

1、配置路由规则，使用 children 配置项：

```javascript
const routes = [
  {
    path: '/home',
    name: 'Home',
    component: Home,
    children: [{
      path: 'news',
      component: News,
    }, {
      path: 'message',
      component: Message,
    }
    ]
  },
  {
    path: '/about',
    name: 'About',
    component: About,
  }
]
```

2、跳转（要完整路径）：

```vue
<router-link to="/home/news">News</router-link>
```



### 路由的 query 参数

1、传递参数

```vue
<!-- 跳转路由并携带 query 参数，to的字符串写法 -->
<router-link :to="`/home/message/detail?id=${m.id}&title=${m.title}`">{{m.title}}</router-link
>&nbsp;&nbsp;
<!-- 跳转路由并携带参数query参数，to的对象写法 -->
<router-link:to="{
            path: '/home/message/detail',
            query: {
              id: m.id,
              title: m.title,
            },
          }"
>{{ m.title }}</router-link>
```

2、接收参数

```vue
$route.query.id
$route.query.title
```



### 命名路由

1、作用：可以简化路由的跳转

2、如何使用：

（1）给路由命名：

```javascript
const routes = [
  {
    path: '/home',
    name: 'Home',
    component: Home,
    children: [{
      path: 'news',
      component: News,
    }, {
      path: 'message',
      component: Message,
      children: [{
        name:'hello',//给组件命名
        path: 'detail',
        component: Detail,
      }]
    }
    ]
  },
  {
    path: '/about',
    name: 'About',
    component: About,
  }
]
```

2、简化跳转：

```vue
<!-- 简化前，需要写完整的路径 -->
<router-link to="/demo/test/welcome">跳转</router-link>
<!-- 简化后，直接通过名字跳转 -->
<router-link :to="{name:hello}">跳转</router-link>
<!-- 简化写法配合传参 -->
<router-link :to="{
                  name:'hello',
                  query:{
                  id:id,
                  title:title,
                  }
                  }">
跳转</router-link>
```



### 路由的 params 参数

1、配置路由，声明接收 params 参数

```javascript
const routes = [
  {
    path: '/home',
    name: 'Home',
    component: Home,
    children: [{
      path: 'news',
      component: News,
    }, {
      path: 'message',
      component: Message,
      children: [{
        path: 'detail/:id/:title',//使用占位符声明接收 params 参数
        component: Detail,
        name: message,
      }]
    }
    ]
  },
  {
    path: '/about',
    name: 'About',
    component: About,
  }
]
```

2、传递参数

```vue
<!-- 跳转并携带 params 参数，to的字符串写法 -->
<router-link :to="`/home/message/detail/${m.id}/${m.title}`">跳转</router-link>
<!-- 跳转并携带 params 参数，to的对象写法 -->
<router-link
          :to="{
            name: 'message',
            params: {
              id: m.id,
              title: m.title,
            },
          }">
跳转</router-link>
```

特别注意：路由并携带 params 参数时，若使用 to 的对象写法，则不能使用 path 配置项，必须使用 name 配置！

3、接收参数

```vue
$route.params.id
$route.params.title
```



### 路由的 props 配置

作用：让路由组件更加方便的收到参数

```javascipt
{
      path: 'message',
      component: Message,
      children: [{
        // path: 'detail/:id/:title',//配params参数
        path: 'detail',  //配query参数
        component: Detail,
        name: message,
        //props的第一种写法，值为对象，该对象中的所有key-value都会以props的形式传给Detail组件
        //props:{a:1,b:'hello'}
        //props的第二种写法，值为布尔值，若布尔值为真，就会把该路由组件收到的所有params参数，以props的形式传给Detail组件。
        // props:true
        //props的第三种写法，值为函数
        // props($route) {
        //   return { id: $route.query.id, title: $route.query.title }
        // }
        //简写
        props({ query: { id, title } }) {
          return { id, title }
        }
      }]
    }
    ]
  },
```

<router-link> 的 replace 属性

1、作用：控制路由跳转时操作浏览器历史记录的模式

2、浏览器的历史记录有两种写入方式，分别为 push 和 replace，push是追加历史记录，replace 是替换当前记录。路由跳转时候默认为 push

3、如何开启 replace 模式； < router-link replace ......> News< /router-link >



### 编程式路由导航

1、作用：不借助 <router-link> 实现路由跳转，让路由跳转更加灵活

2、具体编码：

```vue
//$router的两个API
      this.$router.push({
        name: "detail",
        query: {
          id: m.id,
          title: m.title,
        },
      });
      this.$router.replace({
        name: "detail",
        query: {
          id: m.id,
          title: m.title,
        },
      });
```



### 缓存路由组件

1、作用：让不展示的路由组件保持挂载，不被销毁。

2、具体编码：

```vue
<keep-alive include="News">
    <router-view></router-view>
</keep-alive>
```



### 两个新的生命周期钩子

1、作用：路由组件所独有的两个钩子，用于捕获路由组件的激活状态。

2、具体名字：

（1）activated 路由组件被激活时触发。

（2）deactivated 路由组件失活时触发。



### 路由守卫

1、作用：对路由进行权限控制

2、分类：全局守卫、独享守卫、组件内守卫

3、全局守卫：

```javascript
//全局前置路由守卫——初始化的时候被调用、每次路由切换之前被调用
router.beforeEach((to, from, next) => {
  console.log(to, from)
  if (to.meta.isAuth) {//判断是否需要鉴权
    if (localStorage.getItem('school') === '一中') {
      next()
    }
    else {
      alert('学校名不对，无权限查看')
    }
  }
  else {
    next()
  }
})
//全局后置路由守卫——初始化的时候被调用、每次路由切换之后被调用
router.afterEach((to, from) => {
  console.log('后置路由守卫', to, from)
  document.title = to.meta.title || '系统'
})
```

4、独享守卫

```javascript
beforeEnter:(to, from, next) => {
  console.log(to, from)
  if (to.meta.isAuth) {//判断是否需要鉴权
    if (localStorage.getItem('school') === '一中') {
      next()
    }
    else {
      alert('学校名不对，无权限查看')
    }
  }
  else {
    next()
  }
}
```

5、组件内守卫：

```vue
//进入守卫：通过路由规则，进入该组件时被调用
beforeRouterEnter(to,from,next){}
//离开守卫：通过路由规则，离开该组件时被调用
beforeRouterLeave(to,from,next){}
```



### 路由器的两种工作模式

1、对于一个 url 来说，什么是 hash 值？—— #及其后面的内容就是 hash 值。

2、hash 值不会包含在 HTTP 请求中，即：hash 值不会带给服务器。

3、hash 模式：

（1）地址中永远带着#号，不美观。

（2）若以后将地址通过第三方手机 app 分享，若 app 校验严格，则地址会被标记为不合法。

（3）兼容性较好。

4、history 模式：

1、地址干净，美观。

2、兼容性和 hash 模式相比略差。

3、应用部署上线时需要后端人员支持，解决刷新页面服务器 404 的问题。

