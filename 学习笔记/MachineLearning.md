# 第二部分       matplotlib

1、什么是 matplotlib

2、matplotlib 基本要点

3、matplotlib 的散点图、直方图、柱状图

4、更多的画图工具



## 什么是 matplotlib



### 为什么要学习 matplotlib 

1、能将数据进行可视化，更直观地呈现

2、是数据更加客观、更具说服力

什么是 matplotlib

matplotlib：最流行的 Python 底层绘图库，只要做数据可视化图表，名字取材于 MATLAB，模仿 MATLAB 构建



## matplotlib 基本要点



### 简单画图

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\matplotlib基本要点.png)

每个红色的点是坐标，把5个点的坐标连接成一条线，组成了一个折线图，那么到底如何把它通过代码画出来呢？通过下面的小例子我们来看一下 matplotlib 该如何该如何简单的使用

假设一天中每隔两个小时（range(2,26,2)）的气温（℃）分别是[15,13,14,5,17,20,25,26,26,27,22,18,15]

```python
from matplotlib import pyplot as plt #导入pyplot
# 数据在x轴的位置，是一个可迭代对象
x = range(2,28,2)
# 数据在y轴的位置，是一个可迭代对象
y = [15,13,14,5,17,20,25,26,26,27,22,18,15]
# x轴和y轴的数据一起组成了所有要绘制出的坐标，分别是(2,15),(4,13),(6,14),......
# 传入x和y，通过plot绘制出折线图
plt.plot(x,y)
#展示图形
plt.show()
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\气温折线图.png)

### 完善图像信息

但是目前存在以下几个问题：

1、设置图片大小（想要一个高清无码大图）

2、保存到本地

3、描述信息，比如x轴和y轴表示什么，这个图表表示什么

4、调整x或者y的刻度的间距

5、线条的样式（比如颜色，透明度等）

6、标记出特殊的点（比如告诉别人最高点和最低点在哪里）

7、给图片添加一个水印(防伪，防止盗用)

```python
from matplotlib import pyplot as plt #导入pyplot

# figure 图形图标的意思，在这里指的就是我们画的图，通过实例化一个 figure 并且传递参数，能够在后台自动使用该 figure 实例，在图像模糊的时候可以传入 dpi 参数，让图片更加清晰
fig = plt.figure(figsize=(20,8),dpi=80)

# 数据在x轴的位置，是一个可迭代对象
x = range(2,28,2)
# 数据在y轴的位置，是一个可迭代对象
y = [15,13,14,5,17,20,25,26,26,27,22,18,15]

# x轴和y轴的数据一起组成了所有要绘制出的坐标，分别是(2,15),(4,13),(6,14),......
# 传入x和y，通过plot绘制出折线图
plt.plot(x,y)

# 设置x轴的刻度
plt.xticks(x)
# plt.xticks(x[::2]) # 当刻度太密集时候使用列表的步长（间隔取值）来解决，matplotlib 会自动帮我们对应
# _xtick_labels = [i/2 for i in range(4,49)]
# plt.xticks(_xtick_labels)
# plt.yticks(range(min(y),max(y)+1))

# 保存图片
plt.savefig("./page_01.png")

#展示图形
plt.show()
```



**练习案例**

如果列表a 表示10点到12点的每一分钟的气温，如何绘制折线图观察每分钟气温的变化情况？

a = [random.randint(20,35) for i in range(120)]

```python
from matplotlib import pyplot as plt
import random

x = range(0,120)
# 设置随机种子，让不同时候随机的得到的结果都一样
y = [random.randint(20,35) for i in range(120)]

plt.figure(figsize=(20,8),dpi=80)

plt.plot(x,y)

_x = list(x)
_xtick_labels = ["10点{}分".format(i) for i in range(60)]
_xtick_labels += ["11点{}分".format(i) for i in range(60)]

# 让列表x中的数据和_xticklabels上的数据都传入，最终会在x轴上一一对应的显示出来
# 两组数据的长度必须一样，否则不能完全覆盖整个轴
# 使用列表的切片，每隔3个选一个数据进行展示
# 为了让字符串不会覆盖，使用 rotation 选项，让字符串旋转45°显示
plt.xticks(_x[::3],_xtick_labels[::3],rotation=45)

plt.show()
```

### 添加显示中文

为什么无法显示中文：

matplotlib 默认不支持字符，因为默认的英文字体无法显示汉字

查看 Linux/mac 下面支持的字体

fc-list 查看支持的字体

fc-list：lang=zh 查看支持的中文（冒号前面有空格）

如何修改 matplotlib 的默认字体

通过 matplotlib.rc 可以修改，具体方法参见源码（windows/Linx）

通过 matplotlib.rc 下面 font_manager可以解决（windows/Linx/mac）

```python
from matplotlib import font_manager

# window 和 Linux 设置字体的方法
# font = {'family':'MicroSoft YaHei','weight':'bold','size':'larger'}
# matplotlib.rc("font",**font)
# matplotlib.rc("font",family="MicroSoft YaHei",weight="bold")
my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")
# 设置中文字体（指定具体的字体文件路径，然后在需要显示中文的地方添加fontproperties参数）
plt.xticks(_x[::3],_xtick_labels[::3],rotation=45,fontproperties=my_font)
```

### 给图像添加描述信息

```python
# 设置中文字体
my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")
# 设置中文字体（指定具体的字体文件路径，然后在需要显示中文的地方添加fontproperties参数）
plt.xticks(_x[::3],_xtick_labels[::3],rotation=45,fontproperties=my_font)
plt.xlabel("时间(s)",fontproperties=my_font,size=15)#设置x轴的label，size可以设置字体大小
plt.ylabel("温度(℃)",fontproperties=my_font,size=15)#设置y轴的label
plt.title("10点到12点每分钟的时间变化情况",fontproperties=my_font,size=30)#设置图像标题title
```

### Anaconda

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\anaconda.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\Anaconda镜像.png)



**练习案例**

假设大家在30岁的时候，根据自己的实际情况，统计出来了从11岁到30岁每年交的女(男)朋友的数量如列表a，请绘制出该数据的折线图，以便分析自己每年交女(男)朋友的数量走势

a = [1,0,1,1,2,4,3,2,3,4,4,5,6,5,4,3,3,1,1,1] 要求：1、y轴表示个数；2、x轴表示岁数，比如11岁，12岁等。

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")

x = range(11,31)
y = [1,0,1,1,2,4,3,2,3,4,4,5,6,5,4,3,3,1,1,1]

# 设置图形大小
plt.figure(figsize=(20,8),dpi=80)

plt.plot(x,y)
# 设置x轴刻度
_xtick_labels = ["{}岁".format(i) for i in x]
plt.xticks(x,_xtick_labels,fontproperties=my_font)
plt.yticks(range(0,9))
#绘制网格
plt.grid()
#展示
plt.show()
```

假设大家在30岁的时候，根据自己的实际情况，统计出来了你和你同桌各自从11岁到30岁每年交的女(男)朋友的数量如列表a和b，请在一张图中绘制出该数据的折线图，以便分析自己和同桌20年间的差异，同时分析每年交女(男)朋友的数量走势

a = [1,0,1,1,2,4,3,2,3,4,4,5,6,5,4,3,3,1,1,1]；b = [1,0,3,1,2,2,3,3,2,1,2,1,1,1,1,1,1,1,1,1]；要求：1、y轴表示个数；2、x轴表示岁数，比如11岁，12岁等。

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")

x = range(11,31)
y_1 = [1,0,1,1,2,4,3,2,3,4,4,5,6,5,4,3,3,1,1,1]
y_2 = [1,0,3,1,2,2,3,3,2,1,2,1,1,1,1,1,1,1,1,1]
# 设置图形大小
plt.figure(figsize=(20,8),dpi=80)

plt.plot(x,y_1,label="自己")
plt.plot(x,y_2，label="同桌")
# 设置x轴刻度
_xtick_labels = ["{}岁".format(i) for i in x]
plt.xticks(x,_xtick_labels,fontproperties=my_font)
plt.yticks(range(0,9))
#绘制网格
plt.grid(alpha=.4)
#添加图例
plt.legend(prop=my_font,loc="upper left")
#展示
plt.show()
```

图例参数

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\图例loc参数.png)

在上一个案例中如果大家希望自定义绘制图形的风格怎么办？

```python
plt.plot(x,# x
         y,# y
         #在绘制的时候指定即可
         color = "r", # 线条颜色
         linestyle = "--", # 线条风格
         linewidth = 5, # 线条粗细
         alpha = 0.5, # 透明度
        )
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\自定义绘制.png)

完整案例代码

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")

x = range(11,31)
y_1 = [1,0,1,1,2,4,3,2,3,4,4,5,6,5,4,3,3,1,1,1]
y_2 = [1,0,3,1,2,2,3,3,2,1,2,1,1,1,1,1,1,1,1,1]
# 设置图形大小
plt.figure(figsize=(20,8),dpi=80)

plt.plot(x,y_1,label="自己",color="orange",linestyle=":")
plt.plot(x,y_2，label="同桌",color="cyan",linestyle="-.")
# 设置x轴刻度
_xtick_labels = ["{}岁".format(i) for i in x]
plt.xticks(x,_xtick_labels,fontproperties=my_font)
plt.yticks(range(0,9))
#绘制网格
plt.grid(alpha=.4)
#添加图例,loc参数默认在右上角
plt.legend(prop=my_font,loc="upper left")
#展示
plt.show()
```

**总结：前面我们都做了什么**

1、绘制了折线图（plt.plot）

2、设置了图片的大小和分辨率（plt.figure）

3、实现了图片的保存（plt.savefig）

4、设置了xy轴上的刻度和字符串（xticks）

5、解决了刻度稀疏和密集的问题（xticks）

6、设置了标题，xy轴的label（title，xlabel，ylabel）

7、设置了字体（font_manager.fontProperties.matplotlib.rc）

8、在一张图上绘制多个图形（plt 多次 plot 即可）

9、为不同的图形添加图例



## matplotlib 的散点图、直方图、柱状图

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\对比常用统计图.png)

## ![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\matplotlib思维导图.png)



### 散点图

**绘制散点图**

假设通过爬虫你获取到了北京2016年3，10月份每天白天的最高气温（分别位于列表a，b），那么此时如何寻找出气温和随时间（天）变化的某种规律？

a = [11,17,16,11,12,11,12,6,6,7,8,9,12,15,14,17,18,21,16,17,20,14,15,15,15,19,,21,22,22,22,23]

b = [26,26,28,19,21,17,16,19,18,20,,20,19,22,23,17,20,21,20,22,15,11,15,5,13,17,10,11,13,12,13,6]

技术要点：plt.scatter(x,y)

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")
y_3 = [11,17,16,11,12,11,12,6,6,7,8,9,12,15,14,17,18,21,16,17,20,14,15,15,15,19,21,22,22,22,23]
y_10 =  [26,26,28,19,21,17,16,19,18,20,20,19,22,23,17,20,21,20,22,15,11,15,5,13,17,10,11,13,12,13,6]
x_3 = range(1,32)
x_10 = range(51,82)
# 设置图形大小
plt.figure(figsize=(20,8),dpi=80)
#使用scatter方法绘制散点图，
plt.scatter(x_3,y_3,label="3月份")
plt.scatter(x_10,y_10,label="10月份")
# 设置x轴刻度
_x = list(x_3)+list(x_10)
_xtick_labels = ["3月{}日".format(i) for i in x_3]
_xtick_labels += ["10月{}日".format(i) for i in x_10]
plt.xticks(_x[::3],_xtick_labels[::3],fontproperties=my_font,rotation=45)
#添加图例,loc参数默认在右上角
plt.legend(prop=my_font,loc="upper left")
#添加描述信息
plt.xlabel("时间",fontproperties=my_font,size=15)
plt.ylabel("温度(℃)",fontproperties=my_font,size=15)
plt.title("标题",fontproperties=my_font,size=30)
#展示
plt.show()
```

**散点图的更多应用场景**

1、不同条件（维度）之间的内在关联关系；2、观察数据的离散聚合程度。



### 条形图

**绘制条形图**

假设你获取到了2017年内地电影票房前20的电影（列表a）和电影票房数据（列表b），那么如何更加直观的展示该数据？

a = ["战狼","速度与激情8","功夫瑜伽","西游伏妖篇","变形金刚5：最后的骑士","摔跤吧！爸爸","加勒比海盗5：死无对证","金刚：骷髅岛","极限特工：终极回归","生化危机6：终章","乘风破浪","神偷奶爸3","智取威虎山","大闹天竺","金刚狼3：殊死一战","蜘蛛侠：英雄归来","悟空传","银河护卫队2","情圣","新木乃伊"]

b = [56.01,26.94,17.53,16.49,15.45,12.96,11.8,11.61,11.28,11.12,10.49,10.3,8.75,7.55,7.32,6.99,6.88,6.86,6.58,6.23]单位：亿

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")
a = ["战狼","速度与激情8","功夫瑜伽","西游伏妖篇","变形金刚5：最后的骑士","摔跤吧！爸爸","加勒比海盗5：死无对证","金刚：骷髅岛","极限特工：终极回归","生化危机6：终章","乘风破浪","神偷奶爸3","智取威虎山","大闹天竺","金刚狼3：殊死一战","蜘蛛侠：英雄归来","悟空传","银河护卫队2","情圣","新木乃伊"]

b = [56.01,26.94,17.53,16.49,15.45,12.96,11.8,11.61,11.28,11.12,10.49,10.3,8.75,7.55,7.32,6.99,6.88,6.86,6.58,6.23]

#设置图形大小
plt.figure(figsize=(20,15),dpi=80)
#绘制条形图
plt.bar(range(len(a)),b,width=0.3)
#设置字符串到x轴
plt.xticks(range(len(a)),a,fontproperties=my_font,rotation=45)
plt.show()
```

绘制纵向直方图

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")
a = ["战狼","速度与激情8","功夫瑜伽","西游伏妖篇","变形金刚5：最后的骑士","摔跤吧！爸爸","加勒比海盗5：死无对证","金刚：骷髅岛","极限特工：终极回归","生化危机6：终章","乘风破浪","神偷奶爸3","智取威虎山","大闹天竺","金刚狼3：殊死一战","蜘蛛侠：英雄归来","悟空传","银河护卫队2","情圣","新木乃伊"]

b = [56.01,26.94,17.53,16.49,15.45,12.96,11.8,11.61,11.28,11.12,10.49,10.3,8.75,7.55,7.32,6.99,6.88,6.86,6.58,6.23]

#设置图形大小
plt.figure(figsize=(20,15),dpi=80)
#绘制条形图，barh绘制纵向直方图
plt.barh(range(len(a)),b,height=0.3,color="orange")
#设置字符串到y轴
plt.yticks(range(len(a)),a,fontproperties=my_font)
plt.grid(alpha=.3)
plt.show()
```

假设你知道了列表a中电影分别在2017-09-14（b_14），2017-09-15（b_15），2017-09-16（b_16）三天的票房，为了展示列表中的电影本身的票房以及同其他电影的数据对比情况，应该如何更加直观的呈现该数据？

a = ["猩球崛起3：终极之战","敦克尔克","蜘蛛侠;英雄归来","战狼2"]

b_16 = [15746,312,4497,319]；b_15 = [12357,156,2045,168]；b_14 = [2358,399,2358,362]

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")
a = ["猩球崛起3：终极之战","敦克尔克","蜘蛛侠;英雄归来","战狼2"]
b_16 = [15746,312,4497,319]
b_15 = [12357,156,2045,168]
b_14 = [2358,399,2358,362]
bar_width = 0.2
x_14 = list(range(len(a)))
x_15 = [i+bar_width for i in x_14]
x_16 = [i+bar_width*2 for i in x_14]
# 设置图形大小
plt.figure(figsize=(20,8),dpi=80)
plt.bar(range(len(a)),b_14,width=bar_width,label="9月14日")
plt.bar(x_15,b_15,width=bar_width,label="9月15日")
plt.bar(x_16,b_16,width=bar_width,label="9月16日")
#设置图例
plt.legend(prop=my_font)
#设置x轴的刻度
plt.xticks(x_15,a,fontproperties=my_font)
plt.show()
```



### 直方图

**绘制直方图**

假设你获取了249部电影的时长（列表a），希望统计出这些电影时长的分布状态（比如时长为100分钟到120分钟电影的数量，出现的频率）等信息，你应该如何呈现这些数据？

a = [103, 82, 88, 119, 95, 122, 110, 90, 129, 125, 102, 102, 99, 82, 113, 122, 132, 130, 82, 124, 131, 139, 126, 134, 133, 102, 95, 80, 115, 92, 92, 97, 94, 123, 114, 99, 98, 107, 134, 85, 114, 128, 140, 115, 81, 84, 120, 114, 110, 87, 140, 80, 93, 89, 94, 93, 82, 119, 116, 108, 97, 84, 113, 139, 86, 84, 135, 116, 103, 127, 95, 87, 110, 134, 130, 128, 104, 113, 117, 90, 134, 91, 103, 108, 129, 82, 138, 137, 129, 88, 129, 87, 140, 95, 124, 99, 104, 110, 88, 140, 120, 116, 110, 82, 106, 111, 104, 86, 102, 126, 89, 117, 117, 128, 114, 89, 121, 80, 101, 130, 88, 95, 105, 117, 105, 116, 107, 87, 136, 102, 109, 105, 140, 101, 112, 101, 99, 89, 93, 91, 126, 113, 109, 121, 123, 115, 87, 86, 89, 91, 100, 132, 110, 94, 82, 103, 119, 126, 101, 125, 94, 82, 113, 107, 89, 89, 117, 127, 105, 124, 136, 101, 128, 127, 118, 135, 91, 81, 130, 116, 139, 98, 102, 105, 129, 88, 119, 111, 81, 131, 90, 101, 111, 121, 126, 139, 97, 131, 80, 93, 81, 124, 110, 90, 110, 114, 139, 116, 112, 91, 136, 95, 97, 104, 136, 98, 120, 121, 134, 110, 110, 129, 108, 113, 112, 111, 123, 90, 96, 123, 137, 136, 86, 113, 137, 91, 114, 83, 96, 120, 126, 115, 132, 137, 97, 94, 90, 91, 115, 82]

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")

a = [103, 82, 88, 119, 95, 122, 110, 90, 129, 125, 102, 102, 99, 82, 113, 122, 132, 130, 82, 124, 131, 139, 126, 134, 133, 102, 95, 80, 115, 92, 92, 97, 94, 123, 114, 99, 98, 107, 134, 85, 114, 128, 140, 115, 81, 84, 120, 114, 110, 87, 140, 80, 93, 89, 94, 93, 82, 119, 116, 108, 97, 84, 113, 139, 86, 84, 135, 116, 103, 127, 95, 87, 110, 134, 130, 128, 104, 113, 117, 90, 134, 91, 103, 108, 129, 82, 138, 137, 129, 88, 129, 87, 140, 95, 124, 99, 104, 110, 88, 140, 120, 116, 110, 82, 106, 111, 104, 86, 102, 126, 89, 117, 117, 128, 114, 89, 121, 80, 101, 130, 88, 95, 105, 117, 105, 116, 107, 87, 136, 102, 109, 105, 140, 101, 112, 101, 99, 89, 93, 91, 126, 113, 109, 121, 123, 115, 87, 86, 89, 91, 100, 132, 110, 94, 82, 103, 119, 126, 101, 125, 94, 82, 113, 107, 89, 89, 117, 127, 105, 124, 136, 101, 128, 127, 118, 135, 91, 81, 130, 116, 139, 98, 102, 105, 129, 88, 119, 111, 81, 131, 90, 101, 111, 121, 126, 139, 97, 131, 80, 93, 81, 124, 110, 90, 110, 114, 139, 116, 112, 91, 136, 95, 97, 104, 136, 98, 120, 121, 134, 110, 110, 129, 108, 113, 112, 111, 123, 90, 96, 123, 137, 136, 86, 113, 137, 91, 114, 83, 96, 120, 126, 115, 132, 137, 97, 94, 90, 91, 115, 82]

#计算组数
d = 3 #组距
num_bins = (max(a)-min(a))//d + 1

# 设置图形大小
plt.figure(figsize=(20,8),dpi=80)
plt.hist(a,num_bins)
#设置图例
plt.legend(prop=my_font)
#设置x轴的刻度
plt.xticks(range(min(a),max(a)+d,d),fontproperties=my_font)

plt.grid(alpha=.3)
plt.show()
```

**那么问题来了**

在美国2004年人口普查发现有124 million 的人在离家相对较远的地方工作，根据他们从家到上班地点所需要的时间，通过抽样统计（最后一列）出了下表的数据，这些数据能够绘制成直方图么？

interval = [0,5,10,15,20,25,30,35,40,45,60,90]

width = [5,5,5,5,5,5,5,5,5,15,30,60]

quantity = [836,2737,3723,3926,3596,1438,3273,642,824,613,215,47]

**一般来说能够使用 plt.hist 方法的是那些没有统计过的数据，所以这题为了达到直方图的效果，需要绘制条形图**

```python
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")

interval = [0,5,10,15,20,25,30,35,40,45,60,90]
width = [5,5,5,5,5,5,5,5,5,15,30,60]
quantity = [836,2737,3723,3926,3596,1438,3273,642,824,613,215,47]

#设置图形大小
plt.figure(figsize=(20,8),dpi=80)
plt.bar(range(12),quantity,width=1)
#设置x轴的刻度
_x = [i-0.5 for i in range(13)]
_xtick_labels = interval+[150]
plt.xticks(_x,_xtick_labels)
plt.grid()
plt.show()
```

**直方图更多应用场景**

1、用户的年龄分布状态

2、一段时间内用户点击次数的分布状态

3、用户活跃时间的分布状态



### matplotlib 常见问题总结

1、应该选择那种图形来呈现数据

2、matplotlib.plot(x,y)

3、matplotlib.bar(x,y)

4、matplotlib.scatter(x,y)

5、matplotlib.hist(data,bins,normed)

6、xticks 和 yticks 的设置

7、label 和 title，grid 的设置

8、绘图的大小和保存图片

### matplotlib 使用的流程总结

1、明确问题

2、选择图形的呈现方式

3、准备数据

4、绘图和图形完善

### matplotlib 更多的图形样式

matplotlib 支持的图形是非常多的，如果有其他需求，我们查看一下 url 地址：http://matplotlib.org/gallery/index.html

## 更多的绘图工具

plotly：可视化工具中的 github，相比于 matplotlib 更加简单，图形更加漂亮，同时兼容 matplotlib 和 pandas，地址：https://plotly/python/



# 第二部分       numpy



## 数组的形状

### a.shape 查看数组的形状

### a.reshape((3,4)) 修改数组的形状,但并不会改变a本身

### np.arange(12) 创建数组（仅仅是一维数组）

### a.flatten() 转化为一维数组的方法

```python
import numpy as np
a = np.array([[3,4,5,6,7,8],[4,5,6,7,8,9]])
# 查看数组的形状
a.shape
# 修改数组的形状,但并不会改变a本身
a.reshape((3,4))
# 创建数组（仅仅是一维数组）
t4 = np.arange(12) #array([0,1,2,3,4,5,6,7,8,9,10,11,12])
# 转化为一维数组的方法
a.reshape((a.shape[0]*a.shape[1],))
a.flatten()
# 三维数组a.shape(2，2，3)的值，第一个是块，第二个是行，第三个是列
b = a.reshape((2,2,3))
```



## 数组和数的计算

```python
import numpy as np
a = np.array([[3,4,5,6,7,8],[4,5,6,7,8,9]])
# a + 1 的值是a数组里所有元素都加上1
a + 1
# a - 1 的值是a数组里所有元素都减去1
a - 1
# a * 3 的值是a数组里所有元素都乘上1
a * 3
```



## 数组和数组的计算

```python
import numpy as np
a = np.array([[3,4,5,6,7,8],[4,5,6,7,8,9]])
b = np.array([[31,41,51,61,71,81],[41,51,61,71,81,91]])
# 同行同列数组，对应数组元素相加减，相乘除
# 只同行一列数组，则该数组可以和同行的数组每列计算
# 只同列一行数组，则该数组可以和同列的数组每行计算
a + b
a * b
# 不同维度的数组计算无法计算
```



## 广播原则

如果两个数组的后缘维度（trailing dimension，即从末尾开始算起的维度）的轴长度相符或其中一方的长度位1，则认为它们是广播兼容的。广播会在缺失和（或）长度为1的维度上进行。

怎么理解呢？可以把维度指的是 shape 所对应的数字个数

那么问题来了：

shape 为(3,3,3)的数组能够和(3,2)的数组进行计算么？

shape 为(3,3,2)的数组能够和(3,2)的数组进行计算么？

有什么好处呢？

举个例子：每列的数据减去列的平均值的结果



## 为什么要学习 numpy

快速；方便；科学计算的基础库

## 什么是 numpy

一个在 Python 中做科学计算的基础库，重在数值计算，也是大部分PYTHON 科学计算库的基础库，多用于在大型、多维数组上执行数值运算。

### numpy 创建数组（矩阵）



### arange([start,] stop[,step,],dtype=None) 生成数组

### type(a) 获取数组的类名

### a.dtype 获取数据的类型

```python
import numpy as np
a = np.array([1,2,3,4,5])
b = np.array(range(1,6))
c = np.arange(1,6)
# -->上面a，b，c内容相同，注意 arange和range的区别
# np.arange 的用法：arange([start,] stop[,step,],dtype=None)
# 获取数组的类名
type(a) #numpy.ndaaray
# 获取数据的类型
a.dtype # dtype('int64')
```

**numpy 中常见的更多数据类型**

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\numpy中常见的更多数据类型.png)



## 数据类型的操作

### a.astype('i1/int8') 修改数组的数据类型

### np.round(array[],int) 修改浮点型的小数位数

```python
#指定创建的数组的数据类型：
a = np.array([1,0,1,0],dtype=np.bool) #或者使用 dtype = '?'
# array([True,False,True,False],dtype=bool)

# 修改数组的数据类型：
a.astype('i1') #或者使用 a.astype(np.int8) array([1,0,1,0],dtype=int8)

# 随机小数生成
h = np.array([random.random() for i in range(10)])
# 修改浮点型的小数位数
b = np.array([0.8447799300684048, 0.9867804858512462, 0.8372703456403361, 0.31481079214245133, 0.2898897741265748, 0.465906766281052, 0.8084171038174494, 0.6343465377794216])
c = np.round(b,2) #[0.52 0.57 0.84 0.16 0.44 0.89 0.28 0.52]
# python 里的随机小数生成和修改浮点型的小数位数
random.random()
round(random.random(),3)
```



## 轴（axis）

在 numpy 中可以理解为方向，使用0，1，2...数字表示，对于一个一维数组，只有一个0轴，对于2维数组（shape(2,2)），有0轴和1轴，对于三维数组（shape(2,2,3)），有0，1，2轴

有了轴的概念之后，我们计算会更加方便，比如计算一个2维数组的平均值，必须指定是计算哪个方向上面的数字的平均值

那么问题来了：在前面的知识，轴在那里？回顾 np.arange(0,10).reshape((2,5))，reshape 中2表示0轴长度（包含数据的条数）为2，1轴长度为5，2*5一共10个数据。

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\二维数组的轴.png)

![三维数组的轴](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\三维数组的轴.png)

## numpy 读取数据

CSV：Comma-Separated Value，逗号分隔值文件

显示：表格状态

源文件：换行和逗号分割行列的格式化文本，每一行的数据表示一条记录

由于 csv 便于展示，读取和写入，所以很多地方也是用 csv 的格式存储和传输中小型的数据，为了方便教学，我们会经常操作 csv 格式的文件，但是操作数据库中的数据也是很容易的实现的

### np.loadtxt() 读取数据

```python
np.loadtxt(frame.dtype=np.float,delimiter=None,skiprows=0,usecols=None,unpack=False)
```

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\numpy读取数据.png)

## numpy 存储数据

现在这里有一个英国和美国各自 youtube 1000多个视频的点击，喜欢，不喜欢，评论数量（"views","likes","dislikes","comment_total")]的csv，运用刚刚所学习的只是，我们尝试来对其进行操作

```python
import numpy as np
file_path = "./numpy.csv"
# unpack默认值为False，是否转置
data1 = np.loadtxt(file_path,delimiter=",",dtype="int",unpack=True)
data2 = np.loadtxt(file_path,delimiter=",",dtype="int")
```

注意其中添加 delimiter 和 dtype 以及 unpack 的效果

delimiter：指定边界符号是什么，不指定会导致每行数据为一个整体的字符串而报错

dtype：默认情况下对于较大的数据会将其变为科学计数的方式

unpack：默认是 False(0)，默认情况下，有多少条数据，就会有多少行。为True(1)的情况下，每一列的数据会组成一行，原始数据有多少列，加载出来的数据就会有多少行，相当于转置的效果

## numpy 中的转置

转置是一种变换，对于numpy 中的数组来说，就是在对角线方向交换数据，目的也是为了更方便的去处理数据。下面介绍三种方法可以转置。

### data.transpose()

### data.swapaxes(1,0)

### data.T

```python
data = np.arange(0,18).reshape((3,6))
# 第一种方法，就译为转置
data.transpose()
# 第二种方法，是交换两轴
data.swapaxes(1,0)
# 第三种方法，是数学意义上的转置T
data.T
```

那么，结合之前的所学的 matplotlib 把英国和美国的数据呈现出来？

看到这个问题，我们应该考虑什么？

1、我们想要反映出什么样的结果，解决什么问题？

2、选择什么样的呈现方式？

3、数据还需要做什么样的处理？

4、学代码



## numpy 索引和切片

对于刚刚加载出来的数据，我如果只想选择其中的某一列（行）我们应该怎么做呢?

其实操作很简单，和 Python 中的列表的操作一样

```python
data = np.arange(12).reshape((3,4))
# 取一行
data [1]
# 取一列
data[:,2]
# 取多行
data[1:3] #取二三行
# 取多列
data[:,2:] # 取三四列
# 取不连续的多行
data[[1,3]] #取一三行
# 取不连续的多列
data[:,[2,4]]# 取二四列
# 取多行和多列，取第三行，第四列的值
data[2,3]
# 取得是行和列交叉点的位置
data[2:5,1:4]
# 取多个不相邻的点
data[[0,2],[0,1]]
```



## numpy 中数值的修改

```python
a = np.arange(24).reshape((4,6))
a[:2:4] = 0 #将三四列的值修改为0
a<10 #返回的是boolean类型数组
a[a<10] = 3 #将数组a小于10的元素修改为3
```



## numpy 中布尔索引

```python
a = np.arange(24).reshape((4,6))
a[:2:4] = 0 #将三四列的值修改为0
a<10 #返回的是boolean类型数组
a[a<10] = 3 #将数组a小于10的元素修改为3
```



## numpy 中三元运算符

### np.where(a<10,0,10) numpy的三元运算符

```python
a = np.arange(24).reshape((4,6))
np.where(a<10,0,10)  #把a中小于10的数字替换为0，把大于20的替换为20
```



## numpy 中的 clip（裁剪）

### a.clip(10,18) numpy 中的 clip（裁剪）

```python
a.clip(10,18) # 小于10替换为10，大于18的替换为18，但是nan不会被替换
```



## numpy 中的 nan 和 inf

### nan(NAN,Nan):not a number 表示不是一个数字

什么时间 numpy 中会出现 nan：当我们读取本地文件为 float 的时候，如果有缺失，就会出现 nan 当做了一个不合适的计算的时候（比如无穷大（inf）减去无穷大）

### inf(-inf,inf):infinity,inf 表示正无穷大，inf 表示负无穷

什么时候会出现 inf 包括（-inf，+inf），比如一个数字除以0，（python 中直接会报错，numpy 中的是一个 inf 或者 -inf）

**那么如何指定一个 nan 或者 inf 呢？注意他们的 type 类型**

```python
np.inf #float
np.nan #float
```



## numpy 中的 nan 的注意点

### np.count_nonzero(a!=a) 统计a与自己对应位置的值是否相等，判断数组里 nan 的个数

### a[np.isnan(a)]=0 , np.isnan(a) 判断是否为 nan，是则替换为0

### np.sum(a,axis=0) 

```python
# 1、两个 nan 是不相等的
np.nan == np.nan # False
# 2、np.nan !=np.nan
np.nan !=np.nan # True
# 3、利用以上的特性，判断数组中 nan 的个数
a = np.array([1.,2.,nan])
np.count_nonzero(a!=a) #统计a与自己对应位置的值是否相等，判断数组里 nan 的个数
# 4、由于2，那么如何判断一个数字是否为 nan 呢？通过 np.isnan(a) 来判断，返回 bool 类型比如希望把 nan 替换为0
a[np.isnan(a)] = 0
# 5、nan 和任何值计算都为 nan
np.sum(a) # 和的值为 nan 
a = np.arange(24).reshape((4,6)) #[[ 0  1  2  3  4  5]
                                  #[ 6  7  8  9 10 11]
                                  #[12 13 14 15 16 17]
                                  #[18 19 20 21 22 23]]
np.sum(a,axis=0) # [36 40 44 48 52 56]
np.sum(a,axis=1) # [ 15  51  87 123]
```

那么问题来了，在一组数据中单纯的把 nan 替换为0，合适么？会带来什么样的影响？

比如，全部替换为0后，替换之前的平均值如果大于0，替换之后的均值肯定会变小，所以更一般的方式是把缺失的数值替换为均值（中值）或者是直接删除有缺失值的一行

那么问题来了：如何计算一组数据的中值或者是均值，如何删除有缺失数据的那一行（列）[pandas中介绍]

```python
def fill_ndarray(data):
   for i in range(data.shape[1]): # 遍历每一列
        temp_col = data[:,i] #当前的一列
        nan_num= np.count_nonzero(temp_col==temp_col)
        if nan_num != 0: # 不为0，说明当前这一列中有nan
            temp_not_nan_col = temp_col[temp_col==temp_col] # 当前一列不为 nan 的 array
            # 选中当前为 nan 的位置，把值赋值为不为 nan 的均值
            temp_col[np.isnan(temp_col)] = temp_not_nan_col.mean()
   return data

if __name__ == '__main__':
    data = np.arange(12).reshape((3,4)).astype("float")
    data[1,2:] = np.nan
    print(data)
    data = fill_ndarray(data)
    print(data)
```



## numpy 中常用统计函数

### 求和：data.sum(axis=None) 或者 np.sum(data,axis=None)

### 均值：data.mean(a,axis=None) 受离群点的影响较大

### 中值：np.median(data,axis=None)

### 最大值：data.max(axis=None)

### 最小值：data.min(axis=None)

### 极值：np.ptp(data,axis=None) 即最大值和最小值极差

### 标准差：data.std(axis=None)

标准差是一组数据平均值分散程度的一种度量。一个较大的标准差，代表大部分数值和其平均值之间差异较大；一个较小的标准差，代表这些数值较近平均值反映出数据的波动稳定情况，越大表示波动越大，越不稳定。

**默认返回多维数组的全部的统计结果，如果指定 axis，则返回一个当前轴上的结果**



## 数组的拼接

现在我希望把之前案例中两个国家的数据方法一起来研究分析，那么应该怎么做？

### np.vstack((data1,data2)) 竖直拼接

### np.hstack((data1,data2)) 水平拼接

```python
data1 = np.arange(12).reshape((2,6))
data2 = np.arange(12).reshape((2,6))
np.vstack((data1,data2)) #[[ 0  1  2  3  4  5]
                          #[ 6  7  8  9 10 11]
                          #[ 0  1  2  3  4  5]
                          #[ 6  7  8  9 10 11]]
np.hstack((data1,data2)) #[[ 0  1  2  3  4  5  0  1  2  3  4  5]
                         #[ 6  7  8  9 10 11  6  7  8  9 10 11]]
```



## 数组的行列交换

```python
data = np.arange(12,24).reshape((3,4))
data[[1,2],:] = data[[2,1],:] # 行交换
data[:,[0,2]] = data[:,[2,0]] # 列交换
```

### 动手

现在我希望把之前案例中两个国家的数据方法一起来研究分析，同时保留国家的信息（每条数据的国家来源），那么应该怎么做？

```python
import numpy as np
us_data = "./US_video_data_numbers.csv"
uk_data = "./GB_video_data)numbers.csv"

# 加载国家数据
us_data = np.loadtxt(us_data,delimiter=",",dtype=int)
uk_data = np.loadtxt(us_data,delimiter=",",dtype=int)
# 添加国家信息
# 构造全为0的数据
zeros_data = np.zeros((us_data.shape[0],1))
ones_data = np.ones((uk_data.shape[0],1))
# 分别添加一列全为0，1的数组
us_data = np.hstack((us_data,zeros_data))
uk_data = np.hstack((uk_data,ones_data))
# 拼接两组数据
final_data = np.vstack(uk_data,uk_data)
print(final_data)
```



## numpy 更多好用的方法

### 1、获取最大值最小值的位置： np.argmax 和 np.argmin

（1）np.argmax(data,axis=0)

（2）np.argmin(data,axis=1)

### 2、创建一个全0的数组：np.zeros((3,4))

### 3、创建一个全1的数组：np.ones((3,4))

### 4、创建一个对角线为1的正方形数组（方阵）：np.eye(3)

```python
# 创建一个全0的数组
np.zeros((2,3)) #[[1. 1. 1. 1.]
                #[1. 1. 1. 1.]
                #[1. 1. 1. 1.]]
# 创建一个全1的数组
np.ones((3,4)) #[[0. 0. 0.]
               #[0. 0. 0.]]
# 创建一个对角线为1的正方形数组（方阵）
np.eye(3) #[[1. 0. 0.]
          #[0. 1. 0.]
          #[0. 0. 1.]]
# 获取最大值最小值的位置
np.argmax(data,axis=0) #[0 1 2]
np.argmin(data,axis=1) #[1 0 0]
```



## numpy 生成随机数

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\numpy生成随机数.png)

```python
np.random.randint(10,20,(4,5))# 生成10到20之间的随机数，形状为4*5的二位数组
```

### 分布的补充

**1、均匀分布：**在相同的大小范围的出现概率等可能的

**2、正态分布：**呈钟型，两头低，中间高，左右对称

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\分布的补充.png)



## numpy 的注意点 copy 和 view

1、a=b 完全不复制，a 和 b 相互影响

2、a = b[:]，视图的操作，一种切片，会创建新的对象a，但是a的数据完全由b保管，他们两个的数据变化是一致的，

3、a = b.copy()，复制，a 和 b互不影响

### 动手

英国和美国各自youtube1000的数据结合之前的 matplotlib 绘制出各自的评论数量的直方图。希望了解英国的youtube中视频的评论数和喜欢数的关系，应该如何绘制改图

```python
import numpy as np
us_data = "./US_video_data_numbers.csv"
uk_data = "./GB_video_data)numbers.csv"

# 加载国家数据
us_data = np.loadtxt(us_data,delimiter=",",dtype=int)
# 取评论的数据
us_data_comments = us_data[:,-1]
us_data_comments[us_data_comments<=5000]
d = 50
bin_nums = (us_data_comments.max()-us_data_comments.min())//d
# 绘图
plt.figrue(figsize=(20,8),dpi=80)
plt.hist(us_data_comments,bin_nums)
```



## 小结

1、如何选择一行或者多行的数据（列）？

2、如何给选取的行或列赋值？

3、如何把大于10的值替换为10？

4、np.where 如何使用？

5、np.chip 如何使用？

6、如何转置（交换轴）？

7、读取和保存数据为 csv

8、np.nan 和 np.inf 是什么？

9、常用的统计函数你记得几个？

10、标准差反映出数据的什么信息？

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\numpy思维导图.png)



# 第三部分       pandas



## 为什么要学习 pandas

那么问题来了：numpy 已经能够帮助我们处理数据，能够结合 matplotlib 解决我们数据分析的问题，那么 pandas 学习的目的在什么地方呢？

numpy 能够帮助我们处理处理数值型数据，但是这还不够。很多时候，我们的数据除了数值之外，还有字符，还有时间序列等。

比如：我们通过爬虫获取到了存储在数据库中的数据

比如：之前youtube的例子中除了数值之外还有国家的信息，视频的分类（tag）信息，标题信息等。

所以，numpy 能够帮助我们处理数值，但是 pandas 除了处理数值之外（基于numpy），还能够帮助我们处理其他类型数据



## pandas 的常用数据类型

1、Series 一维，代表签数组

2、DATa Frame 二维，Series容器



## pandas 之 Series 创建



###  创建 Series

data = pd.Series(np.arange(10),index=list(string.ascii_uppercase[:10]))

a = {string.ascii_uppercase[i]:i for i in range(10)}；pd.Series(a)

### 修改Series数据类型

data2.astype(float)

### 查看 Series数据类型

type(data)

```python
import string
#创建 Series
data = pd.Series(np.arange(10),index=list(string.ascii_uppercase[:10]))#A    0
                                                                       #B    1
                                                                       #C    2
                                                                       #D    3
                                                                       #E    4
                                                                       #F    5
                                                                       #G    6
                                                                       #H    7
                                                                       #I    8
                                                                       #J    9
                                                                       #dtype: int32
#查看 eries数据类型
type(data)
# <class 'pandas.core.series.Series'>
data1 = pd.Series([1,2,3,4,5],index=list("abcde"))#a    1
                                                  #b    2
                                                  #c    3
                                                  #d    4
                                                  #e    5
                                                  #dtype: int64
a = {string.ascii_uppercase[i]:i for i in range(10)}
#{'A': 0, 'B': 1, 'C': 2, 'D': 3, 'E': 4, 'F': 5, 'G': 6, 'H': 7, 'I': 8, 'J': 9}
pd.Series(a)  #A    0
              #B    1
              #C    2
              #D    3
              #E    4
              #F    5
              #G    6
              #H    7
              #I    8
              #J    9
              #dtype: int64
pd.Series(a,index=list(string.ascii_uppercase[5:15]))  #F    5.0
                                                       #G    6.0
                                                       #H    7.0
                                                       #I    8.0
  #为什么类型为float呢?                                 #J    9.0
  #numpy中nan为float，pandas会自动                      #K    NaN    
  #根据数据类型更改Series的dtype类型                     #L    NaN                                                                            #M    NaN
                                                       #N    NaN
                                                       #O    NaN
                                                       #dtype: float64
data2 = pd.Series(a)                   
#修改Series数据类型
data2.astype(float)   #A    0.0
                      #B    1.0
                      #C    2.0
                      #D    3.0
                      #E    4.0
                      #F    5.0
                      #G    6.0
                      #H    7.0
                      #I    8.0
                      #J    9.0
                      #dtype: float64
```



## pandas 之 Series 切片和索引

```python
data[2:10:2] #C    2
             #E    4
             #G    6
             #I    8
             #dtype: int32
data[1]   #1
data[[2,3,5]]  #C    2
               #D    3
               #F    5
               #dtype: int32
data[data>4]          #F    5
                      #G    6
                      #H    7
                      #I    8
                      #J    9
                      #dtype: int32
data["F"]   #5
data[["A","D","J"]]   #A    0
                      #D    3
                      #J    9
                      #dtype: int32
```

切片：直接传入 start end 或者步长即可

索引：一个的时候直接传入序号或者 index，多个的时候传入序号或者 index 的列表



## pandas 之 Series 的索引和值

### data.index   获取索引列表

### data.values 获取值的列表

对于一个陌生的 Series 类型，我们如何知道他的索引和具体的值呢？

```python
data.index
#Index(['A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J'], dtype='object')
data.values
#array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
type(data.index)
#<class 'pandas.core.indexes.base.Index'>
type(data.values)
#<class 'numpy.ndarray'>
data.where(data>4,10)
#A    10
#B    10
#C    10
#D    10
#E    10
#F     5
#G     6
#H     7
#I     8
#J     9
#dtype: int32
```

Series 对象本质上有两个数组构成，一个数组构成对象的键（index，索引），一个数组构成对象的值（values），键->值

ndarray 的很多方法都可以运用于 Series 类型，比如 argmax，clip

Series 具有 where 方法，但是结果和 ndarray 不同



## pandas 之读取外部数据

现在假设我们有一组关于狗的名字的统计数据，那么为了观察这组数据的情况，我们应该怎么做呢？

数据来源：https://www.kaggle.com/new-york-city/nyc-dog-names/data

我们的这组数据存在 csv 中，我们直接使用pd.read_csv即可。和我们想象的有些差别，我们以为它会是一个 Series 类型，但是它是一个 DataFrame，那么接下来我们就来了解这个数据类型

但是还有一个问题：对于数据库比如mysql或者mongodb中的数据我们如何使用呢？

pd.read_sql(sql_sentence,connection)。那么，mongodb呢？

```python
import pandas as pd
df = pd.read_csv("./dogNames2.csv")
print(df)
```



## pandas 之 DataFrame

```python
data = pd.DataFrame(np.arange(12).reshape((3,4)))
#   0  1   2   3
#0  0  1   2   3
#1  4  5   6   7
#2  8  9  10  11 
```

DataFrame 对象既有行索引，又有列索引

行索引，表名不同行，横向索引，叫index，0轴，axis=0

列索引，表名不同列，纵向索引，叫columns，1轴，axis=1

```python
data = pd.DataFrame(np.arange(12).reshape((3,4)),index=list(string.ascii_uppercase[:3]),columns=list(string.ascii_uppercase[-4:]))
#   W  X   Y   Z
#A  0  1   2   3
#B  4  5   6   7
#C  8  9  10  11
```

那么问题来了：

1、DataFrame 和 Series 有什么关系呢？

2、Series 能够传入字典，那么 DataFrame 能够传入字典作为数据么？

3、对于一个dataframe 类型，既有行索引，又有列索引，我们能够对他做什么操作呢？



## DataFrame 的属性和方法

和一个ndarray一样，我们通过 shape，nidm，dtype了解这个ndarray的基本信息，那么对于DataFrame我们有什么方法了解呢

### DataFrame 的基本属性

df.shape # 行数、列数

df.dtypes # 列数据类型

df.ndim # 数据维度

df.index # 行索引

df.columns # 列索引

df.values # 对象值，二维ndarray数组

### DataFrame 整体情况查询

df.head(3) # 显示头部几行，默认5行

df.tail(3) # 显示末尾几行，默认5行

df.info() # 相关信息概览：行数，列数，列索引，列非空值个数，列类型，行类型，内存占用

df.describe() #快速综合统计结果：计数，均值，标准差，最大值，四分位数，最小值



### 动手

那么回到之前我们读取的狗名字统计的数据上，我们尝试一下刚刚的方法

那么问题来了：

很多同学肯定想知道使用次数最高的前几个名字是什么呢？

df.sort_values(by="Count_AnimalName",ascending=False)

那么问题又来了：

如果我们数据有10列，我想按照其中的第1，第3，第8列排序，怎么办？（看ipython的帮助文档）

```python
df = df.sort_values(by="列名",ascending=False) # ascending 如果为True,降序
```



## pandas 之取行或者列

刚刚我们知道了如何给数据按照某一行或者列排序，那么现在我们想单独研究使用次数前100的数据，应该如何做？

### df_sorted = df.sort_values(by="列名")

```python
df_sorted = df.sort_values(by="列名")
df_sorted[:100]
```

那么问题来了：

我们具体要选择某一列该怎么选择呢？ df["列名"]

我们要同时选择行和列该怎么办？  df[:100] ["列名"]



## pandas 之 loc

还有更多的经过 pandas 优化过的选择方式：

### 1、df.loc 通过标签索引行数据

### 2、df.iloc 通过位置获取行数据

```python
data = pd.DataFrame(np.arange(12).reshape((3,4)),index=list(string.ascii_uppercase[:3]),columns=list(string.ascii_uppercase[-4:]))
#   W  X   Y   Z
#A  0  1   2   3
#B  4  5   6   7
#C  8  9  10  11 
data.loc["A","W"]
#0
data.loc["A",["W","Z"]]
#W    0
#Z    3
#Name: A, dtype: int32
type( data.loc["A",["W","Z"]])
#<class 'pandas.core.series.Series'>
data.loc[["A","C"],["W","Z"]]
#   W   Z
#A  0   3
#C  8  11
data.loc["A":,["W","Z"]]
#   W   Z
#A  0   3
#B  4   7
#C  8  11
data.loc["A":"C",["W","Z"]]#冒号在loc里面是闭合的，即会选择到冒号后面的数据
#   W   Z
#A  0   3
#B  4   7
#C  8  11
data.iloc[1,:]
#W    4
#X    5
#Y    6
#Z    7
#Name: B, dtype: int32
data.iloc[:,1:2]
#   X
#A  1
#B  5
#C  9
data.iloc[:,1:]
#   X   Y   Z
#A  1   2   3
#B  5   6   7
#C  9  10  11
```



## pandas 之布尔索引

回到之前狗的名字的问题上，假如我们想找到所有的使用次数超过800的狗的名字，应该怎么选择？

### df[df["列名"]>800]

```python
df[df["Count_AnimalName"]>800]
```

回到之前狗的名字的问题上，假如我们想找到所有的使用次数超过700并且名字字符串的长度大于4的狗的名字，应该怎么选择？

```python
df[(df["Count_AnimalName"]>700)&(df["Row_Labels"].str.len()>4)]
```

两个问题：

1、&符号表示什么？哪有其他的连接符号可以使用么？& 且的意思；| 或的意思。

2、str 是什么方法？

注意点：不同的条件之间需要用括号括起来

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\pandas之字符串方法.png)

### df["info"].str.split("/").tolist() 

```python
df["info"].str.split("/").tolist()
```



## 缺失数据的处理

观察下面这组数据

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\缺失数据.png)

我们的数据缺失通常有两种情况：

一种就是空，None等，在 pandas 是NaN（和np.nan一样）

另一种是我们让其为0，蓝色框中

对于 NaN 的数据，在 numpy 中我们是如何处理的？在 pandas 中我们处理起来非常容易。

判断数据是否为NaN：pd.isnull(df)，pd.notnull(df)

处理方式1：删除NaN所在的行列dropna(axis=0,how="any",inplace=False)

处理方式2：填充数据，t.fillna(t.mean())，fiallna(t.median())，t.fillna(0)

处理为0的数据：t[t==0]=np.nan

当然并不是每次为0的数据都需要处理

计算平均值情况，nan 是不参与计算的，但是0会

### pd.isnull(data) 是否为空

### pd.notnull(data)  是否不为空

### data.dropna(axis=1,how="all") 删除NaN所在的行列

### data.dropna(axis=1,how="any",inplace=False) 

### data.fillna(data.mean()) 确实处理

```python
pd.isnull(data)
#       W      X      Y      Z
#A   True  False  False  False
#B  False   True  False  False
#C  False  False  False   True
pd.notnull(data)
#       W      X     Y      Z
#A  False   True  True   True
#B   True  False  True   True
#C   True   True  True  False
data.dropna(axis=1,how="all")
#     W    X   Y    Z
#A  NaN  1.0   2  3.0
#B  4.0  NaN   6  7.0
#C  8.0  9.0  10  NaN
data.dropna(axis=0,how="all")
#     W    X   Y    Z
#A  NaN  1.0   2  3.0
#B  4.0  NaN   6  7.0
#C  8.0  9.0  10  NaN
data.dropna(axis=1,how="any")
#    Y
#A   2
#B   6
#C  10
data.dropna(axis=0,how="any",inplace=True)#inplace参数，默认为False，表示是否替换
#Empty DataFrame
#Columns: [W, X, Y, Z]
#Index: []
data.fillna(data.mean())
#     W    X   Y    Z
#A  6.0  1.0   2  3.0
#B  4.0  5.0   6  7.0
#C  8.0  9.0  10  5.0
data["W"].fillna(data["W"].mean())
#A    6.0
#B    4.0
#C    8.0
#Name: W, dtype: float64
data["W"] = data["W"].fillna(data["W"].mean())
data
#     W    X   Y    Z
#A  6.0  1.0   2  3.0
#B  4.0  NaN   6  7.0
#C  8.0  9.0  10  NaN
```



## pandas 常用统计方法

```python
# 评分的平均分
rating_mean = df["Rating"].mean()
# 导演的人数
temp_list = df["Actors"].str.split(",").tolist()
nums = set([i for j in temp_list for i in j])
# 电影时长的最大最小值
max_runtime = df["Runtime(Minutes)"].max()
max_runtime_index = df["Runtime(Minutes)"].argmax()
min_runtime = df["Runtime(Minutes)"].min()
min_runtime_index = df["Runtime(Minutes)"].argmin()
runtime_median = df["Runtime(Minutes)"].median()
```



### 动手一

对于这一组电影数据，如果我们想 rating，runtime 的分布情况，应该如何呈现数据？

```python
import pandas as pd
file_path = "./"
df = pd。read_csv(file_path)
# 准备数据
runtime_data = df["Runtime(Minutes)"].values

max_runtime = runtime_data.max()
min_runtime = runtime_data.min()
# 计算组数
num_bin = (max_runtime-min_runtime)//0.5

# 设置图形的大小
plt.figrue(figsize=(20,8),dpi=80)
plt.hist(runtime_data,num_bins)
plt.xticks(range(min_runtime,max_runtime+0.5))
plt.show()

```

```python
import pandas as pd
file_path = "./"
df = pd。read_csv(file_path)
# 准备数据
runtime_data = df["Runtime(Minutes)"].values

max_runtime = runtime_data.max()
min_runtime = runtime_data.min()
# 设置不等宽的组距，hist 方法中取到的会是一个左闭右开的区间[1.9,3.5]
num_bin_list = [1.9,3.5]
i = 3.5
while i <= max_runtime:
    i += 0.5
    num_bin_list.append(i)

# 设置图形的大小
plt.figrue(figsize=(20,8),dpi=80)
plt.hist(runtime_data,num_bin_list)

# xticks 让之前的组距能够对应上
plt.xticks(num_bin_list)
plt.show()

```



### 动手二

假设现在我们有一组从2006年到2016年1000部最流行的电影数据，我们想知道这些电影数据中评分的平均分，导演的人数等信息，我们应该怎么获取?

数据来源：https://www.kaggle.com/damianpanek/sunday-eda/data

```python
df["Rating"].mean() #评分的平均分
director_len = len(set(df["Director"].tolist()))#导演的人数等信息
# 获取演员的人数
temp_actors_list = df["Actors"].str.split(",").tolist()
actors_list = [i for j in temp_actors_list for i in j]
```



### 思考

对于这一组电影数据，如果我们希望统计电影分类（genre）的情况，应该如何处理数据？

思路：重新构造一个全为0的数组，列名为分类，如果某一条数据中分类出现过，就让0变为1

```python
import pandas as pd
file_path = "./"
df = pd.read_csv(file_path)
df["Rating"].mean() #评分的平均分
director_len = len(set(df["Director"].tolist()))#导演的人数等信息   # [[],[],[]]
# 统计分类的列表
temp_genre_list = df["Genre"].str.split(",").tolist()
genre_list = list(set([i for j in temp_genre_list for i in j]))
# 构造全为0的数组
zeros_df = pd.DataFrame(np.zeros((df.shape[0],len(genre_list))),columns=genre_list)
# 给每一部电影出现分类的位置赋值1
for i in range(df.shape[0]):
    zeros_df.loc[i,temp_genre_list[i]] = 1

# 统计每个分类的电影的数量和
genre_count = zeros_df.sum(axis=0)
# 排序
genre_count = genre_count.sort_values()
_x = genre_count.index
_y = genre_count.values
# 画图
plt.figure(figsize=(20,8),dpi=80)
plt.bar(range(len(_x)),_y)
plt.xticks(range(len(_x)),_x)
plt.show()
```



### 动手三

对于这一组电影数据，如果我们希望统计电影分类（genre）的情况，应该如何处理数据？

思路：重新构造一个全为0的数组，列名为分类，如果某一条数据中分类出现过，就让0变为1

```python
temp_genre_list = df["Genre"].str.split(",").tolist()#tolist(),todict()等方法偶尔会用到
# 统计分类的列表
genre_list = [] #所有的分类放到 genre_list 中
for i in temp_genre_list:
    genre_list.extend(i)
genre_list = list(set(genre_list)) #去重
# 构造全为0的数组
zeros_genre = pd.DataFrame(np.zeros(shape=(df.shape[0],len(genre_list)),dtype=int),columns=genre_list)
# 给每一部电影出现分类的位置赋值1
for i in range(df.shape[0]):
    genres = df["Genre"][i]
    zeros_genre.loc[i,genres.split(",")] = 1 # 给出现分类的地方设置为1
df_with_genre = df.join(zero(zeros_genre))
```



## 数组合并之 join

### data.join(data1)

**join：默认情况下他是把行行索引相同的数据合并到一起**

```python
data = pd.DataFrame(np.arange(12).reshape((3,4)),index=list(string.ascii_uppercase[:3]),columns=list(string.ascii_uppercase[-4:]))
data
#   W  X   Y   Z
#A  0  1   2   3
#B  4  5   6   7
#C  8  9  10  11
data1 = pd.DataFrame(np.ones((2,5)),index=list(string.ascii_uppercase[:2]))
data1
#     0    1    2    3    4
#A  1.0  1.0  1.0  1.0  1.0
#B  1.0  1.0  1.0  1.0  1.0
data.join(data1)
#   W  X   Y   Z    0    1    2    3    4
#A  0  1   2   3  1.0  1.0  1.0  1.0  1.0
#B  4  5   6   7  1.0  1.0  1.0  1.0  1.0
#C  8  9  10  11  NaN  NaN  NaN  NaN  NaN
data1.join(data)
#     0    1    2    3    4  W  X  Y  Z
#A  1.0  1.0  1.0  1.0  1.0  0  1  2  3
#B  1.0  1.0  1.0  1.0  1.0  4  5  6  7
```



## 数据合并之 merge

### data.merge(data1,left_on="",right_on="",how="")

**merge：按照指定的列把数据按照一定的方式合并到一起**

默认的合并方式 inner，交集

merge outer，并集，NaN补全

merge left，左边为准，NaN补全

merge right，右边为准，NaN补全

```python
data
#     M    N  O    P
#A  1.0  1.0  a  1.0
#B  1.0  1.0  b  1.0
#C  1.0  1.0  c  1.0
data1
#     V    W  X    Y    Z
#A  0.0  0.0  c  0.0  0.0
#B  0.0  0.0  d  0.0  0.0
data.merge(data1,left_on="O",right_on="X")
#     M    N  O    P    V    W  X    Y    Z
#0  1.0  1.0  c  1.0  0.0  0.0  c  0.0  0.0
data.merge(data1,left_on="O",right_on="X",how='inner')
#     M    N  O    P    V    W  X    Y    Z
#0  1.0  1.0  c  1.0  0.0  0.0  c  0.0  0.0
data.merge(data1,left_on="O",right_on="X",how='outer')
#     M    N    O    P    V    W    X    Y    Z
#0  1.0  1.0    a  1.0  NaN  NaN  NaN  NaN  NaN
#1  1.0  1.0    b  1.0  NaN  NaN  NaN  NaN  NaN
#2  1.0  1.0    c  1.0  0.0  0.0    c  0.0  0.0
#3  NaN  NaN  NaN  NaN  0.0  0.0    d  0.0  0.0
data.merge(data1,left_on="O",right_on="X",how='left')
#     M    N  O    P    V    W    X    Y    Z
#0  1.0  1.0  a  1.0  NaN  NaN  NaN  NaN  NaN
#1  1.0  1.0  b  1.0  NaN  NaN  NaN  NaN  NaN
#2  1.0  1.0  c  1.0  0.0  0.0    c  0.0  0.0
data.merge(data1,left_on="O",right_on="X",how='right')
#     M    N    O    P    V    W  X    Y    Z
#0  1.0  1.0    c  1.0  0.0  0.0  c  0.0  0.0
#1  NaN  NaN  NaN  NaN  0.0  0.0  d  0.0  0.0
```



### 动手

刚刚我们学会了数据分合并，那么接下来，我们按照电影分类（genre）信息把数据呈现出来

**思考**

现在我们有一组关于全球星巴克店铺的统计数据，如果我们想知道美国的星巴克数量和中国的那个多，或者我们想知道中国每个省份星巴克的数量的情况，那么应该怎么办？

数据来源：https://www.kaggle.com/starbucks/store-locations/data



## 分组和聚合

在 pandas 中类似的分组的操作我们有很简单的方式来完成

### df.groupby(by="columns_name")

那么问题来了，调用 groupby 方法之后返回的是什么内容？

```python
import pandas as pd
import numpy as np
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")

df = pd.read_csv("./pizza.csv")
# print(df.info())
# print(df.head(1))
# 某省份个城市的店铺数量统计图
data_NY = df[df["province"]=="IL"]
grouped = data_NY.groupby(by="city")
grouped_count = grouped['province'].count()

#各省份的店铺数量统计图
# grouped = df.groupby(by="province")
# grouped_count = grouped["city"]

# 统计每个省份的商店数量和(横向)
grouped_count = grouped_count.sort_values()
_x = grouped_count.index
_y = grouped_count.values
# 画图
plt.figure(figsize=(20,8),dpi=80)
plt.barh(range(len(_x)),_y,color="orange")
plt.yticks(range(len(_x)),_x,fontproperties=my_font)
plt.show()
```

**语句连起来**

```python
grouped = data_NY.groupby(by="city")['province'].count() #或者
grouped = data_NY.groupby(by="city").count()['province']
```

grouped = df.groupby(by="columns_name")

grouped 是一个 DataFrameGroupBy 对象，是可迭代的

grouped 中的每一个元素是一个元组

元组里面是（索引（分组的值），分组之后的 DataFrame）

那么，回到之前的问题：要统计美国的披萨店铺的数量，我们应该怎么做？分组之后的每个 DataFrame 的长度？

长度是一个思路，但是我们有更多的方法（聚合方法）来解决这个问题。

DataFrameGroupBy 对象有很多经过优化的方法

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\DataFrameGroupBy.png)

如果我们需要对国家和省份进行分组统计，应该怎么操作呢？

grouped = df.groupby(by=[df["province"],df["city"]])

很多时候我们只希望对获取分组之后的某一部分数据，或者说我们只希望对某几列数据进行分组，这个时候我们应该怎么办呢？

获取分组之后的某一部分数据：

grouped = df.groupby(by=["province","city"])["city"].count()

对某几列数据进行分组：

grouped = df["province"].groupby(by=[df["province"],df["city"]]).count()

```python
grouped = df.groupby(by=["province","city"])["city"].count()  #数据类型pandas.core.series.Series
grouped1 = df["province"].groupby(by=[df["province"],df["city"]]).count()#数据类型pandas.core.series.Series
print(grouped)
print(grouped1)
print(type(grouped))
print(type(grouped1))
```

观察结果，由于只选择了一列数据，所以结果是一个 Series 类型，如果我们想返回一个 DataFrame类型呢？

```python
data = pd.DataFrame(np.ones((3,4)),index=list('abc'),columns=list('abcd'))
data
#     a    b    c    d
#a  1.0  1.0  1.0  1.0
#b  1.0  1.0  1.0  1.0
#c  1.0  1.0  1.0  1.0
data['a']
#a    1.0
#b    1.0
#c    1.0
#Name: a, dtype: float64
type(data['a'])
#<class 'pandas.core.series.Series'>
type(data[['a']])
#<class 'pandas.core.frame.DataFrame'>
```

以下的两条命令结果一样，和之前的结果的区别在于当前返回的是一个 DataFrame 类型

```python
grouped = df.groupby(by=["province","city"])["city"].count()  #数据类型pandas.core.series.Series
grouped1 = df["province"].groupby(by=[df["province"],df["city"]]).count()#数据类型pandas.core.series.Series

#以下的两条命令结果一样，和之前的结果的区别在于当前返回的是一个 DataFrame 类型

grouped2 = df.groupby(by=["province","city"])[["city"]].count() #数据类型class 'pandas.core.frame.DataFrame
grouped3 = df[["province"]].groupby(by=[df["province"],df["city"]]).count()#数据类型class 'pandas.core.frame.DataFrame
print(grouped)
print(grouped1)
print(grouped2)
print(grouped3)
print(type(grouped))
print(type(grouped1))
print(type(grouped2))
print(type(grouped3))
```



## 索引和复合索引



**简单的索引操作：**

### 获取 index：df.index

### 指定 index：df.index = ['x','y]

### 重新设置 index：df.reindex(list('abcdef'))

### 指定某一列作为 index ：df.set_index("Country",drop=False)

### 返回 index 的唯一值：df.set_index("Country").index.unique()

假设 a 为一个 DataFrame，那么当 a.set_index(["c","d])即设置两个索引的时候是什么样子的结果呢？

a = pd.DataFrame({'a':range(7),'b':range(7,0,-1),'c':['one','one','one','two','two','two','two'],'d':list("hjklmno")})

```python
data = pd.DataFrame(np.ones((3,4)),index=list('abc'),columns=list('abcd'))
data
#     a    b    c    d
#a  100.0  1.0  1.0  1.0
#b  1.0  1.0  1.0  1.0
#c  1.0  1.0  1.0  1.0
data.index = ['A','B','C']
data
#     a    b    c    d
#A  100.0  1.0  1.0  1.0
#B  1.0  1.0  1.0  1.0
#C  1.0  1.0  1.0  1.0
data.index
I#Index(['A', 'B', 'C'], dtype='object')
data.set_index("a")
#       b    c    d
#a                 
#100.0  1.0  1.0  1.0
#1.0  1.0  1.0  1.0
#1.0  1.0  1.0  1.0
data.set_index("a",drop=True)
#         b    c    d
#a                   
#100.0  1.0  1.0  1.0
#1.0    1.0  1.0  1.0
#1.0    1.0  1.0  1.0
data["a"].unique()
#array([100.,   1.])
data["d"].unique()
#array([1.])
data.set_index("b").index
#Float64Index([1.0, 1.0, 1.0], dtype='float64', name='b')
data.set_index("b")
#         a    c    d
#b                   
#1.0  100.0  1.0  1.0
#1.0    1.0  1.0  1.0
#1.0    1.0  1.0  1.0
data.set_index("b").index.unique()
#Float64Index([1.0], dtype='float64', name='b')
len(data.set_index("b").index.unique())
#1
#
len(data.set_index("b").index)
#3
list(data.set_index("b").index)
#[1.0, 1.0, 1.0]
data.set_index(["a","b"])
#             c    d
#a     b            
#100.0 1.0  1.0  1.0
#1.0   1.0  1.0  1.0
#      1.0  1.0  1.0
data.set_index(["a","b"]).index
#MultiIndex([(100.0, 1.0),
#            (  1.0, 1.0),
#            (  1.0, 1.0)],
#           names=['a', 'b'])
a = pd.DataFrame({'a':range(7),'b':range(7,0,-1),'c':['one','one','one','two','two','two','two'],'d':list("hjklmno")})
a
#   a  b    c  d
#0  0  7  one  h
#1  1  6  one  j
#2  2  5  one  k
#3  3  4  two  l
#4  4  3  two  m
#5  5  2  two  n
#6  6  1  two  o
b = a.set_index(["c","d"])
b
#       a  b
#c   d      
#one h  0  7
#    j  1  6
#    k  2  5
#two l  3  4
#    m  4  3
#    n  5  2
#    o  6  1
c = b["a"]
c
#c    d
#one  h    0
#     j    1
#     k    2
#two  l    3
#     m    4
#     n    5
#     o    6
#Name: a, dtype: int64
type(c)
#<class 'pandas.core.series.Series'>
 c["one"]["j"]
#1
c["one"]
#d
#h    0
#j    1
#k    2
#Name: a, dtype: int64
c.swaplevel()
#d  c  
#h  one    0
#j  one    1
#k  one    2
#l  two    3
#m  two    4
#n  two    5
#o  two    6
#Name: a, dtype: int64
```



## Series 复合索引

### X.swaplevel() 里外交换

level 相当于就是复合索引的里外层，交换了 level 之后，里外交换，所以能够直接从 h 开始取值

```python
a
#   a  b    c  d
#0  0  7  one  h
#1  1  6  one  j
#2  2  5  one  k
#3  3  4  two  l
#4  4  3  two  m
#5  5  2  two  n
#6  6  1  two  o
X=a.set_index(["c","d"])["a"]
X
#c    d
#one  h    0
#     j    1
#     k    2
#two  l    3
#     m    4
#     n    5
#     o    6
#Name: a, dtype: int64
X["one","h"]
#0
X["one"]["j"]
#1
```



### 动手

现在我们有全球排名靠前的10000本书的数据，那么请统计一下下面几个问题：

1、不同年份书的数量

2、不同年份书的平均评分情况

数据来源：https://www.khttps://www.kaggle.com/zygmunt/goodbooks-10k

```python
import numpy as np
import pandas as pd
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")

data = pd.read_csv('./books.csv')
# print(data.info())
# print(data.head(1))
grouped_book_count = data.groupby(by="original_publication_year")["title"].count()
# print(grouped_book_count)
grouped_average_rating =data["average_rating"].groupby(by=data["original_publication_year"]).mean()
# print(grouped_average_rating)

_x = grouped_average_rating.index
_y = grouped_average_rating.values
# 画图
plt.figure(figsize=(20,8),dpi=80)
plt.plot(range(len(_x)),_y)
plt.xticks(list(range(len(_x)))[::10],_x[::10],rotation=45)
plt.show()
```



### 动手

现在我们有1965到2016年地震发生数据，请统计每年地震的发生次数。

```python
import numpy as np
import pandas as pd
from matplotlib import pyplot as plt
from matplotlib import font_manager

my_font = font_manager.FontProperties(fname="C:\Windows\Fonts\msyh.ttc")


data = pd.read_csv('./earthquake.csv')
# print(data.info())
# print(data.head(1))
# print(data["Date"])

years_data = data["Date"].str.split("/").tolist()
years_data = pd.DataFrame(years_data)
data["Date"]= years_data[2]

#1965到2016年的地震数量统计
grouped = data.groupby(by="Date")["Magnitude Type"].count()


#某年地震类型的数量统计
# data = data[data["Date"]=='2011']
# grouped =data.groupby(by="Magnitude Type")["Date"].count()
# print(grouped)

_x = grouped.index
_y = grouped.values
# 画图（横向）
# plt.figure(figsize=(20,8),dpi=80)
# plt.barh(range(len(_x)),_y,color="orange")
# plt.yticks(range(len(_x)),_x,fontproperties=my_font)
# plt.show()
# 画图（纵向）
plt.figure(figsize=(20,8),dpi=80)
plt.bar(range(len(_x)),_y)
plt.xticks(range(len(_x)),_x,rotation=45)
plt.show()
```



## 为什么要学习 pandas 中的时间序列

不管在什么行业，时间序列都是一种非常重要的数据形式，很多统计数据以及数据的规律也都和时间序列有着非常重要的联系，而且在 pandas 中处理时间序列是非常简单的

### 生成一段时间范围

### pd.date_range(start=None,end=None,periods=None,freq='D')

### pd.to_datetime(data["date"],format="")

start 和 end 以及 freq 配合能够生成 start 和 end 范围内以频率为 freq 的一组时间索引

start 和 periods 以及 freq 配合能够生成从 start 开始的频率为 freq 的 periods 个时间索引

![](C:\Users\FY\Desktop\笔记\学习笔记\MachineLearning_inage\时间序列频率缩写.png)

```python
pd.date_range(start="20170101",end="20170924")
#DatetimeIndex(['2017-01-01', '2017-01-02', '2017-01-03', '2017-01-04',
#               '2017-01-05', '2017-01-06', '2017-01-07', '2017-01-08',
#               '2017-01-09', '2017-01-10',
#               ...
#               '2017-09-15', '2017-09-16', '2017-09-17', '2017-09-18',
#               '2017-09-19', '2017-09-20', '2017-09-21', '2017-09-22',
#               '2017-09-23', '2017-09-24'],
#              dtype='datetime64[ns]', length=267, freq='D')
pd.date_range(start="20170101",end="20170924",freq="BM")
#DatetimeIndex(['2017-01-31', '2017-02-28', '2017-03-31', '2017-04-28',
#               '2017-05-31', '2017-06-30', '2017-07-31', '2017-08-31'],
#              dtype='datetime64[ns]', freq='BM')
pd.date_range(start="20170101",end="20170924",freq="WOM-3FRI")
#DatetimeIndex(['2017-01-20', '2017-02-17', '2017-03-17', '2017-04-21',
#               '2017-05-19', '2017-06-16', '2017-07-21', '2017-08-18',
#               '2017-09-15'],
#              dtype='datetime64[ns]', freq='WOM-3FRI')
pd.date_range(start="20170101",periods=10,freq="H")
#DatetimeIndex(['2017-01-01 00:00:00', '2017-01-01 01:00:00',
#               '2017-01-01 02:00:00', '2017-01-01 03:00:00',
#               '2017-01-01 04:00:00', '2017-01-01 05:00:00',
#               '2017-01-01 06:00:00', '2017-01-01 07:00:00',
#               '2017-01-01 08:00:00', '2017-01-01 09:00:00'],
#              dtype='datetime64[ns]', freq='H')
pd.date_range(start="2017/01/01",periods=10,freq="MS")
#DatetimeIndex(['2017-01-01', '2017-02-01', '2017-03-01', '2017-04-01',
#               '2017-05-01', '2017-06-01', '2017-07-01', '2017-08-01',
#               '2017-09-01', '2017-10-01'],
#              dtype='datetime64[ns]', freq='MS')
pd.date_range(start="2017-01-01 10:10:10",periods=10,freq="H")
#DatetimeIndex(['2017-01-01 10:10:10', '2017-01-01 11:10:10',
#               '2017-01-01 12:10:10', '2017-01-01 13:10:10',
#               '2017-01-01 14:10:10', '2017-01-01 15:10:10',
#               '2017-01-01 16:10:10', '2017-01-01 17:10:10',
#               '2017-01-01 18:10:10', '2017-01-01 19:10:10'],
#              dtype='datetime64[ns]', freq='H')
```
