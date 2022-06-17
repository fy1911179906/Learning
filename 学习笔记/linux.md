# Linux 入门

## Linux 的介绍

### **概述**

linux 是一个开源、免费的操作系统，其稳定性、安全性、处理多并发已经得到业界的认可，目前很多企业级的项目都会部署到 Linux/Unix 系统上。

Linux 创始人：Linux Torvalds

**Linux 主要的发行版：**

Ubuntu（乌班图）、RedHat（红帽）、CentOS、Debain（蝶变）、Fedora、SuSE、OpenSUSE；

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\linux发行版.png)

**Linux 和 Unix的关系**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux和Unix的关系.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux和Unix的关系1.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux和Unix的关系2.png)

**Linux 和 Windows 比较**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux和Windows比较.png)



# Linux 的安装



## Windows 和 VM 和 CentOS的关系说明

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Windows和VM 和CentOS的关系说明.png)



## 虚拟机的网络连接三种形式的说明

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\虚拟机的网络连接三种形式的说明.png)

### 配置网络，可以上网

点击上面右侧的，两个计算机图片，选择启用 eh0，即可成功连接到网络，就可以上网。



## 安装 vmtools

### 介绍

vmtools 安装后，可以让我们在 Windows 下更好的管理 vm 虚拟机

1）可以直接粘贴命令在 windows 和 centos 系统之间

2）可以设置 Windows 和 centos 的共享文件夹

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\共享文件夹.png)

### 安装 vmtools 的步骤：

1、进入 centos

2、点击 vm 菜单的 ->install vmware tools

3、centos 会出现一个 vm 的安装包

4、点击右键解压，得到一个安装文件

5、进入该 vm 解压的目录，该文件在 /root/桌面/vmware-tools-distrib/下

6、安装 ./vmware-install.pl

7、全部使用默认设置即可

8、需要 reboot 重新启动即可生效



### 设置共享文件夹

**基本介绍**

1、为了方便，可以设置一个共享文件夹，比如 d:/myshare

**具体步骤**

1、菜单 -> vm -> setting，如图设置即可注意，设置选项为 always enable，这样可以读写了

2、Windows 和 centos 可以共享 d:/myshare 目录可以读写文件了

3、共享文件夹在 centos 的 /mnt/hgfs/ 下

**注意事项和细节说明**

 1、Windows 和 centos 就可以共享文件了，但是在实际开发中，文件的上传下载是需要使用远程方式完成的

2、远程方式登录，我们后面会具体讲解

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\设置共享文件夹.png)



## 虚拟机克隆

如果你已经安装了一台 Linux 操作系统，你还想再要更多的，没必要再重新安装，你只需要克隆就可以了

**步骤：**

方式一：直接拷贝一份安装好的虚拟机文件

方式二：使用 VMware 的克隆操作

注意，克隆，需要先关闭 Linux 系统



## 虚拟机快照

如果你在使用虚拟机系统的时候（比如Linux），你想回到原来的某一个状态，也就是说你担心可能有些误操作造成系统异常，需要回到原先某个正常运行的状态，VMware 也提供了这样的功能，就叫快照管理。

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\虚拟机快照.png)



## 虚拟机迁移和删除

我在前面讲过，虚拟系统安装好了，它的本质就是文件（放在文件夹的）。因此虚拟系统的迁移很方便，你可以把安装好的虚拟系统这个文件夹整体拷贝或者到另外位置使用。删除也很简单，用 VMware 进行移除，再点击菜单 -> 从磁盘删除即可，或者直接手动删除即可，或者直接手动删除虚拟系统对应的文件夹即可。



# Linux 的目录结构



## 基本介绍

Linux 的文件系统是采用级层式的树状目录结构，在此结构中的最上层是根目录 “/”，然后在此目录下再创建其他的目录。**在 Linux 世界里，一切皆文件。**

### 具体目录

**/bin【常用】**（/usr/bin、/usr/local/bin）

是 Binary 的缩写，这个目录放着最经常使用的命令。

**/sbin** （/usr/sbin、/usr/local/sbin）

s就是Super User 的意思，这里存放的是系统管理员使用的系统管理程序。

/**home 【常用】**

存放普通用户的主目录，在 Linux 中每个用户都有一个自己的目录，一般该目录名是以用户的账号命名

**/root 【常用】**

该目录为系统系统管理员，也称作超级权限者的用户主目录

**/lib** 

系统开机所需要最基本的动态连接共享库，算作用类似于 Windows 里的 DLL 文件。几乎所有的应用程序都需要用到这些共享库

**/lost + found** 

这个目录一般情况下是空的，当系统非法关机后，这里就存放一些文件

**/etc 【常用】**

所有的系统管理所需要的配置文件和子目录 my.conf

**/usr 【常用】**

这是一个非常重要的目录，用户的很多应用程序文件都放在这个目录下，类似与 Windows 下的 program files 目录

**/boot 【常用】**

存放的是启动 Linux 时使用的一些核心文件，包括一些连接文件以及镜像文件

**/proc 【不能动】**

这个目录是一个虚拟的目录，它是系统内存的映射，访问这个目录来获取系统信息

**/srv 【不能动】**  

service 缩写，该目录存放一些服务启动之后需要提取的数据

**/sys 【不能动】**

这是 Linux2.6 内核的一个很大的变化。该目录下安装了 2.6 内核中新出现的一个文件系统sysfs

/**tmp**

这个目录是用来存放一些临时文件的

/**dev**

类似于 Windows 的设备管理器，把所有的的硬件用文件的形式存储

/**media 【常用】**

Linux 系统会自动识别一些设备，例如 U盘、光驱等等，当识别后，Linux 会把识别的设备挂载到这个目录下

/**mnt 【常用】**

系统提供该目录是为了让用户临时挂载的文件系统的，我们可以将外部的存储挂载在 /mnt/ 上，然后进入该目录就可以查看里的内容了。d:/myshare

/**opt**

这是给主机额外安装软件所摆放的目录。如安装 ORACLE 数据库就可放到该目录下。默认为空。

**/usr/local 【常用】**

这是另一个给主机额外安装软件所安装的目录。一般是通过编译源代码方式安装的程序

**/var 【常用】**

这个目录中存放着在不断扩充的东西，习惯将经常被修改的目录放在这个目录下。包括各种日志文件

**/selinux 【security-enhanced linux】**

SELinux 是一种安全子系统，它能控制程序只能访问特定文件，有三种工作模式，可以自行设置



# Linux 远程登录到 Linux 服务器



## 远程连接

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\远程连接.png)

### 远程登录工具Xshell6

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\远程登陆Xshell.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\远程登陆Xshell6下载.png)



## 远程上传下载文件

### 远程上传下载文件Xftp6

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\远程上传下载文件Xftp6.png)



## Linux ifconfig 命令查询 IP 连接



# Linux Vi 和 Vim 编辑器



### Vi和Vim的基本介绍

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Vi和Vim的基本介绍.png)

### Vi和Vim的常用的三种模式

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Vi和Vim的常用的三种模式.png)

### Vi和Vim基本使用

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Vi和Vim基本使用.png)

### 各种模式的相互切换

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\各种模式的相互切换.png)

### vi 和 vim 快捷键

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\vi和vim快捷键.png)

1、拷贝当前行 yy，拷贝当前行向下的5行 5yy，并粘贴。

2、删除当前行 dd，删除当前行向下的5行 5dd

3、在文件中查找某个单词【命令行下/关键字，回车查找，输入 n 就是查找下一个】

4、设置文件的行号，取消文件的行号【命令行下 :set nu 和 :set nonu】

5、编辑 /etc/profile 文件，使用快捷键到该文档的最末行【G】和最前行【gg】

6、在一个文件中输入“hello”，然后有撤销这个动作 u

7、编辑 /etc/profile 文件，并将光标移动到 20行 shift + g

8、更多的查整理的文档 

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\vi和vim快捷键-1.png)



# Linux 开机、重启和用户登陆注销



## 关机&重启命令

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\关机&重启命令.png)

### 基本介绍

shutdown -h now --------- 立刻进行关机

shutdown -h 1 ------------ 一分钟后关机

shutdown -r now---------- 现在重启计算机

halt -------------------------- 关机，作用和上面一样

reboot ---------------------- 现在重新启动计算机

sync ------------------------ 把内存的数据同步到磁盘

### 注意细节

1、不管是重启系统还是关闭系统，首先要运行 sync 命令，把内存中的数据写到磁盘中

2、目前的 shutdown/reboot/halt 等命令均已经在关机前运行了 sync。



## 用户登录和注销

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\用户登录和注销.png)

### 基本介绍

1、登录时尽量少用 root 账号登录，因为它是系统管理员，最大的权限，避免操作失误。可利用普通用户登录，登录后再用 “su - 用户名” 命令来切换成系统管理员身份。

2、在提示符下输入 logout 即可注销用户。

### 注意细节

1、logout 注销指令在图形运行级别无效，在运行级别3下有效。

2、运行级别这个概念，后面给大家介绍。



# Linux 用户管理



## 用户管理

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\用户管理.png" style="zoom:150%;" />

### 基本介绍

Linux 系统是一个多用户多任务的操作系统，任何一个要使用系统资源的用户，都必须首先向系统管理员申请一个账号，然后以这个账号的身份进入系统

### 添加用户

**基本语法**

useradd 用户名

**应用案例**

案例1：添加一个用户 milan

```linux
useradd milan
```

**细节说明**

1、当创建用户成功后，会自动的创建和用户同名的家目录

2、也可以通过 useradd -d 指定目录 新的用户名，给新创建的用户指定家目录

```linux
useradd -d 指定目录组名 用户名
useradd -d /home/salegroup milan
```



## 指定/修改密码

**基本语法**

passwd 用户名

**应用案例**

给 milan 指定密码

```linux
passwd milan
```

补充，显示当前用户所在的目录的命令 **pwd**



## 删除用户

**基本语法**

userdel 用户名

**应用案例**

1、删除用户 milan，但是要保留家目录

```linux
userdel milan
```

2、删除用户以及用户主目录，比如 tom

```linux
userdel -r tom
```

**细节说明**

是否保留家目录讨论？

一般情况下，我们建议保留



## 查询用户信息

**基本语法**

id 用户名

**应用案例**

案例：请查询 root 信息

```linux
id root
```

**细节说明**

当用户不存在时，返回无此用户



## 切换用户

**介绍**

在操作 Linux 中，如果当前用户的权限不够，可以通过 su - 指令，切换到高权限用户，比如 root

**基本语法**

su - 切换用户名

**应用案例**

创建一个用户 jack，指定密码，然后切换到 jack

**细节说明**

1、从权限高的用户切换到权限低的用户，不需要输入密码，反之需要。

2、当需要返回到原来用户时，使用 exit/logout 指令



## 查看当前用户/登录用户

**基本语法**

whoami / who am i



## 用户组

### **介绍**

类似于角色，系统可对有共性的多个用户进行统一的管理

### **新增组**

指令：groupadd 组名

案例演示

```linux
groupadd salegroup
```

### **删除组**

指令（基本语法）：groupdel 组名

案例演示

```linux
groupdel salegroup
```

### **增加用户时直接加上组**

指令（基本语法）：useradd -g 用户组 用户名

增加一个用户 zwj，直接将他指定到 wudang

```linux
useradd -g wudang zwj
```

### **修改用户的组**

指令（基本语法）：usermod -g 用户组 用户名

案例演示

创建一个组 mojiao

把 zwj 放入到 mojiao

```linux
groupadd mojiao
usermod -g mojiao zwj
```



## 用户和组相关文件

**/etc/passwd 文件**

用户（user）的配置文件，记录用户的各种信息

每行的含义：用户名：口令：用户标识符：组标识符：注释行描述：主目录：登录Shell

**/etc/shadow 文件**

口令的配置文件

每行的含义：登录名：加密口令：最后一次修改时间：最小时间间隔：最大时间间隔：警告时间：不活动时间：失效时间：标志

**/etc/group 文件**

组（group）配置文件，记录 Linux 包含的组的信息

每行的含义：组名：口令：组标识号：组内用户列表

### shell 解释器

**shell 解析器（bash、fcsh、csh等）**



# Linux 实用指令



## 指定运行级别

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\指定运行级别.png" style="zoom:150%;" />

### CentOS7后运行级别说明

在 centos 7 以前，/etc/initab 文件中

进行简化，如下

multi-user.target:analogous to runlevel 3

graphical.target:analogous to runlevel 5

##To view current default target,run:

systemctl get-default

##To set a default target,run:

systemctl set-default TARGET.target

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\指定级别.png" style="zoom:150%;" />



## 找回 root 密码

**面试题**

如何找回 root 密码

设置运行级别，Linux运行后，直接进入到命令行终端，设置单用户模式

### 具体步骤

1、首先，启动系统，进入开机界面，在界面中按 “e” 进入编辑界面，如图

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\开机界面.png)

2、进入编辑界面，使用键盘上的上下键把光标往下移动，找到以 ““Linux16” 开头内容所在的行数”，在行的最后面输入：init=/bin/sh。

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\编辑界面.png)

3、接着，输入完成后，直接按快捷键：Ctrl + x 进入单用户模式。

4、接着，在光标闪烁的位置中输入：mount -o remount,rw/（注意各个单词间有空格），完成后按键盘的回车。

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\注意空格.png" style="zoom:150%;" />

5、在新的一行最后面输入：passwd，完成后按键盘的回车键（Enter）。输入密码，然后再次确认密码即可（密码最好8位以上，但不是必须的），密码修改成功后，会显示 passwd......的格式，说明密码修改成功

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\修改密码.png" style="zoom:150%;" />

6、接着，在鼠标闪烁的位置中（最后一行中）输入：touch/ .autorelabel（注意：touch与 / 后面有一个空格），完成后按回车键（Enter）

7、继续在光标闪烁的位置中，输入：exec /sbin/init （注意：exec 与 / 后面有一个空格），完成后按键盘的回车键（Enter），等待系统启动修改密码（这个过程时间可能有点长，耐心等待）。完成后，系统会自动重启，新的密码生效了。

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\新的密码生效.png" style="zoom:150%;" />



## 帮助指令

### man 获得帮助信息

**基本语法：**man [命令或配置文件] （功能描述：获得帮助信息）

**在 Linux 下，隐藏文件是以 . 开头，选项可以组合使用 比如 ls -al，比如 ls -al /root**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\隐藏文件.png)

案例：查看 ls 命令的帮助信息

```linux
man ls
```

### help 指令

**基本语法：**help 命令（功能描述：获得 shell 内置命令的帮助信息）

**应用实例**

案例：查看 cd 命令的帮助信息

```linux
help cd
```



## 文件目录类



### pwd 指令（当前工作目录）

**基本语法：**pwd （功能描述：显示当前工作目录的绝对路径）

**应用实例：**

案例：显示当前工作目录的绝对路径

### ls 指令

**基本语法：**ls [选项] [目录或是文件]

**常用选项**

-a：显示当前目录所有的文件和目录，包括隐藏的。

-l：以列表的方式显示信息

**应用实例**

案例：查看当前目录的所有内容信息



### cd 指令

**基本语法：**cd [参数] （功能描述：切换到指定目录）

理解：绝对路径和相对路径

cd ~ 或者 cd: 回到自己的家目录

cd.. 回到当前目录的上一级目录

**应用实例**

案例1：使用绝对路径切换到 root 目录

```linux
cd /root
```

案例2：使用相对路径到 /root 目录,比如在 /home/tom 里

```linux
cd ../../root
```

案例3：表示会到当前目录的上一级目录

```linux
cd ..
```

案例4：回到家目录

```linux
cd ~
```



### mkdir 指令（创建目录）

**mkdir 指令用于创建目录**

**基本语法：**mkdir [选项] 要创建的目录

**常用选项**

-p：创建多级目录

**应用实例**

案例1：创建一个目录 /home/dog

```linux
mkdir /home/dog
```

案例2：创建多级目录 /home/animal/tiger

```linux
mkdir -p /home/animal/tiger
```



### rmdir 指令（删除空目录）

**rmdir 指令删除空目录**

**基本语法：**rmdir [选项] 要删除的空目录

**应用实例：**案例：删除一个目录 /home/dog

**使用细节**

rmdir 删除的是空目录，如果目录下有内容时无法删除的。

提示“如果需要删除非空目录，需要使用 rm -rf 要删除的目录

比如：rm -rf /home/animal



### touch 指令（创建空文件）

**touch 指令创建空文件**

**基本语法：**touch 文件名称

**应用实例：**案例：创建一个空文件 hello.txt



### cp 指令（拷贝文件到指定目录）

**cp 指令拷贝文件到指定目录**

**基本语法：**cp [选项] source dest

**常用选项**

-r：递归复制整个文件夹

**应用实例**

案例1：将 /home/hello.txt 拷贝到 /home/bbb 目录下

```linux
cp hello.txt bbb/
```

案例2：递归复制整个文件夹

```linux
cp -r /home/bbb/ /opt/
```

**使用细节**

强制覆盖不提示的方法：\cp



### rm 指令（指令移除文件或目录）

**rm 指令移除文件或目录**

**基本语法：**rm [选项] 要删除的文件或目录

**常用选项**

-r：递归删除整个文件夹

-f：强制删除不提示

**应用实例**

案例1：将 /home/hello.txt 删除

```linux
rm /home/hello.txt
```

案例2：递归删除整个文件夹 /home/bbb

```linux
rm -r /home/bbb
```

**使用细节**

强制删除不提示的方法：带上 -f 参数即可



### mv 指令（移动文件与目录或重命名）

**mv 移动文件与目录或重命名**

**基本语法**

mv oldNameFile newNameFile （功能描述：重命名）

mv /temp/movefile /targetFolder （功能描述：移动文件）

**应用实例**

案例1：将 /home/cat.txt 文件 重新名为 pig.txt

```linux
mv cat.txt pig.txt
```

案例2：/home/pig.txt 文件 移动到 /root 目录下

```linux
mv /home/pig.txt /root/
```

案例1和2操作来连起来使用

```linux
mv cat.txt /root/pig.txt
```

案例3：移动整个目录，比如将 /opt/bbb 移动到 /home 下

```linux
mv /opt/bbb /home/
```



### cat 指令（查看文件内容）

**cat 指令查看文件内容**

**基本语法：**cat [选项] 要查看的文件

**常用选项**

-n：显示行号

**应用实例：**案例：/etc/profile 文件内容，并且显示行号

```linux
cat -n /etc/profile
cat -n /etc/profile | more
```

**使用细节：**cat 只能浏览文件，而不能修改文件，为了浏览方便，一般会带上管道命令 | more



### more 指令（查看文件内容）

more 指令是一个基于 VI 编辑器的文本过滤器，它以全屏幕的方式按页显示文本文件的内容，more 指令中内置了若干快捷键，详见操作说明

**基本语法：**more 要查看的文件

操作说明，如图

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\more操作说明.png" style="zoom:150%;" />

**应用实例：**案例：采用 more 查看文件 /etc/profile

```linux
more /etc/profile
```



### less 指令（分屏查看文件内容）

less 指令用来分屏查看文件内容，它的功能与 more 指令类似，但是比 more 指令更加强大，支持各种显示终端。less 指令在显示文件内容时，并不是一次将整个文件加载之后才显示，而是根据显示需要加载内容，对于显示大型文件具有较高的效率。

**基本语法：**less 要查看的文件

操作说明，如图

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\less操作说明.png" style="zoom:150%;" />

**应用实例：**案例：采用 less 查看一个大文件文件 /opt/杂文.txt

```linux
less /opt/杂文.txt
```



### echo 指令

**echo 输出内容到控制台**

**基本语法：**echo [选项] [输出内容]

**应用案例**

案例1：使用 echo 指令输出环境变量，比如输出$PATH、$HOSTNAME等

```linux
echo $PATH
```

案例2：使用 echo 指令输出 Hello World！

```linux
echo "Hello，World"
```



### head 指令

**head 指令用于显示文件的开头部分内容，默认情况下 head 指令显示文件的前10行内容**

**基本语法**

head 文件 （功能描述：查看文件头10行内容）

head -n 5 文件 （功能描述：查看文件头5行内容，5可以是任意行数）

**应用实例：**案例：查看 /etc/profile 的前面5行代码

```linux
head -n 5 /etc/profile
```



### tail 指令

**tail 指令用于显示文件的开头部分内容，默认情况下 head 指令显示文件的前10行内容**

**基本语法**

tail文件 （功能描述：查看文件尾10行内容）

tail -n 5 文件 （功能描述：查看文件尾5行内容，5可以是任意行数）

tail -f 文件（功能描述：实时追踪该文档的所有更新）

**应用实例**

案例1：查看 /etc/profile 的最后5行代码

```linux
tail -n 5 /etc/profile
```

案例2：实时监控 mydate.txt，看看到文件有变化时，是否看到，实施的追加日期

```linux
tail -f /home/mydate.txt
```



### > 指令 和 >> 指令（> 输出重定向和 >> 追加）

**> 输出重定向和 >> 追加**

**基本语法**

1）ls -l > 文件 （功能描述：列表的内容写入文件 a.txt 中（覆盖写））

2）ls -al >> 文件 （功能描述：列表的内容追加到文件 aa.txt 的末尾）

3）cat 文件1 > 文件2 （功能描述：将文件1的内容覆盖到文件2）

4）echo "内容" >> 文件（追加）

**应用实例**

案例1：将 /home 目录下的文件列表写入到 /home/info.txt 中，覆盖写入

```linux
ls -l /home/info.txt #[如果 info.txt 没有创建，则会自动创建]
```

案例2：将当前日历信息追加到 /home/mycal 文件中

```linux
cal >> /home/mycal
```



### ln 指令（软链接）

ln 指令软链接也称为符号链接，类似于 Windows 里的快捷方式，主要存放了链接其他文件的路径

**基本语法：**ln -s [源文件或目录] [软链接名] （功能描述：给原文件创建一个软链接）

**应用实例**

案例1：在 /home 目录下创建一个软链接 myroot，连接到 /root 目录

```linux
ln -s /root /home/myroot
```

案例2：删除软链接 myroot

```linux
rm /home/myroot
```

**细节说明**

当我们使用 pwd 指令查看目录时，仍然看到的是软链接所在的目录。

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\软链接.png" style="zoom:150%;" />



### history 指令（查看历史命令）

**history 指令用于查看已经执行过历史命令，也可以执行历史命令**

**基本语法：**history （功能描述：查看已经执行过历史命令）

**应用实例**

案例1：显示所有的历史命令

```linux
history
```

案例2：显示最近使用过的10个命令

```linux
history 10
```

案例3：执行历史编号为5的指令

```linux
!5
```



## 时间日期类



### **date 指令 - 显示当前日期**

**基本语法**

1）date （功能描述：显示当前时间）

2）date + %Y （功能描述：显示当前年份）

3）date + %m （功能描述：显示当前月份）

4）date +%d （功能描述：显示当前是哪一天）

5）date "+%Y-%m-%d %H:%M:%S" （功能描述：显示年月日时分秒）

**应用实例**

案例1：显示当前时间信息

```linux
date
```

案例2：显示当前时间年月日

```linux
date  "+%Y-%m-%d"
```

案例3：显示当前时间年月日时分秒

````linux
date "+%Y-%m-%d %H:%M:%S"
````



### date 指令 - 设置日期

**基本语法：**date -s 字符串时间

**应用实例：**案例：设置系统当前时间，比如设置成 2021-11-11 11:22:22

```linux
date -s 2021-11-11 11:22:22
```



### cal 指令

**cal 指令用于查看日历**

**基本语法：**cal [选项] （功能描述：不加选项，显示本月日历）

**应用实例**

案例1：显示当前日历

```linux
cal
```

案例2：显示2020年日历

```linux
cal 2020
```



## 搜索查找类



### find 指令

**find 指令将从指定目录向下递归遍历其各个子目录，将满足条件的文件或目录显示在终端**

**基本语法：**find [搜索范围] [选项]

**选项说明**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\find选项说明.png" style="zoom:150%;" />

**应用实例**

案例1：按文件名：根据名称查找 /home 目录下的 hello.txt 文件

```linux
find /home -name hello.txt
```

案例2：按拥有者：查找 /opt 目录下，用户名称为 nobody 的文件

```linux
find /opt -user nobody
```

案例3：查找整个 Linux 系统下大于200M的文件（+n 大于，-n小于，n等于）

```linux
find / -size +200M
```



### locate 指令（创建数据库查询）

locate 指令可以快速定位文件路径。locate 指令利用事先建立的系统中所有文件名称及路径的locate数据实现快速定位给定的文件。locate 指令无需遍历整个文件系统，查询速度较快。为了保证查询结果的准确度，管理员必须定期更新 locate 时刻

**基本语法：**locate 搜索文件

**特殊说明：**由于 locate 指令基于数据库进行查询，所以第一次运行前，必须使用 updatedb 指令创建 locate数据库。

**应用实例：**案例：请使用 locate 指令快速定位 hello.txt 文件所在目录

```linux
updatedb        #创建数据库
locate hello.txt
```



### which 指令

which 指令可以查看某个指令在哪个目录下，比如 ls 指令在哪个目录下

```linux
which ls
```



### grep 指令（过滤查找） 和 管道符号  |

**grep 过滤查找，管道符，“|”，表示将前一个命令的处理结果输出传送给后面的命令处理。**

**基本语法：**grep [选项] 查找内容 源文件

**常用选项**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\grep常用选项.png" style="zoom:200%;" />

**应用实例：**案例：请在 hello.txt 文件中，查找 “yes” 所在行，并且显示行号

```linux
写法1：cat /home/hello.txt | grep "yes"
写法2：grep -n "yes" /home/hello.txt
```



## 压缩和解压类



### gzip/gunzip 指令（压缩/解压文件）

**gzip 用于压缩文件，gunzip 用于解压的**

**基本语法**

**gzip 文件 （功能描述：压缩文件，只能将文件压缩为 *.gz 文件）**

**gunzip 文件.gz （功能描述：解压缩文件命令）**

**应用实例**

案例1：gzip 压缩，将 /home 下的 hello.txt 文件进行压缩

```linux
gzip /home/hello.txt
```

案例2：gunzip 解压，将 /home 下的 hello.txt.gz 文件进行解压

```linux
gunzip /home/hello.txt.gz
```



### zip/unzip 指令（压缩/解压文件）

**zip 用于压缩文件，unzip 用于解压的，这个在项目打包发布中很有用的**

**基本语法**

**zip [选项] XXX.zip 将要压缩的内容（功能描述：压缩文件和目录的命令）**

**unzip [选项] XXX.zip（功能描述：解压缩文件命令）**

**zip 常用选项**

-r：递归压缩，即压缩目录

**unzip 常用选项**

-d<目录>：指定解压后文件的存放目录

**应用实例**

案例1：gzip 压缩，将 /home 下的所有文件进行压缩成 myhome.zip

```linux
#将 home 目录及其包含的文件和子文件夹都压缩
zip -r myhome.zip /home/
```

案例2：unzip 解压，将 myhome.zip 解压到 /opt/tmp 目录下

```linux
unzip -d /opt/tmp /home/myhome.zip
```



### tar 指令（打包指令）

**tar 指令是打包指令，最后打包后的文件是 .tar.gz 的文件。**

**基本语法：**tar [选项] XXX.tar.gz 打包的内容 （功能描述：打包目录，压缩后的文件格式 .tar.gz）

**选项说明**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\tar选项说明.png)

**应用实例**

案例1：压缩多个文件，将 /home/pig.txt 和 /home/cat.txt 压缩成 pc.tar.gz

```linux
tar -zcvf pc.tar.gz /home/pig.txt /home/cat.txt
```

案例2：将 /home 的文件夹 压缩成 myhome.tar.gz

```linux
tar -zcvf myhome.tar.gz /home/
```

案例3：将 pc.tar.gz 解压到当前目录，切换到 /opt/

```linux
tar -zcvf pc.tar.gz
```

案例4：将 myhome.tar.gz 解压 到 /opt/tmp2 目录下

```linux
mkdir /opt/tmp2
tar -zcvf /home/myhome.tar.gz -C /opt/tmp2
```



# Linux 组管理和权限管理



## Linux 组基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux组基本介绍.png" style="zoom:150%;" />



## 文件/目录 所有者

**一般为文件的创建者，谁创建了该文件，就自然的成为该文件的所有者**

**查看文件的所有者：**指令：ls -ahl

**应用实例**

![](D:\第一学期学习\Python SDK\查看文件所有者.png)

**修改文件所有者：**指令：chown 用户名 文件名

**应用实例：**案例：使用 root 创建一个文件 apple.txt，然后将其所有者修改成 tom

```linux
chown tom apple.txt
```



## 组的创建

**基本指令：**groupadd 组名

**应用实例**

案例1：创建一个组，monster

```linux
groupadd monster
```

案例2：创建一个用户 fox，并放入到 monster 组中

```linux
useradd -g monster fox
```



## 文件/目录 所在组

**当某个用户创建了一个文件后，这个文件在所在组就是该用户所在的组**

**查看文件的所有者：**指令：ls -ahl

**应用实例**

![](D:\第一学期学习\Python SDK\查看文件所有者.png)

**修改文件所在的组：**指令：chgrp 组名 文件名

**应用实例：**案例：使用 root 用户创建文件 orange.txt，看看当前这个文件属于哪个组，然后将其所在组修改成 fruit 组

```linux
chgrp fruit orange.txt
```



## 其它组

**除了文件的所有者和所在组的用户外，系统的其它用户都是文件的其它组**



## 改变用户所在组

在添加用户时，可以指定特定将该用户添加到那个组中，同样的用 root 的管理权限可以改变某个用户所在的组。

**改变用户所在组**

1、usermod -g 组名 用户名

2、usermod -d 目录名 用户名 改变该用户登陆的初始目录。特**别说明：用户需要有进入到新目录的权限。**

**应用实例：**将 zwj 这个用户从原来所在组，修改到 wudang 组。

```linux
usermod -g wudang zwj
```



## 权限的基本介绍

**ls -l 中显示的内容如下**

-rwxrw-r-- 1 root root 1213 Feb 2 09:39 abc

**0-9 位说明**

**1、第0位确定文件类型（d，-，l，c，b）**

l 是链接，相当于 windows 的快捷方式

d 是目录，相当于 windows 的文件夹

c 是字符设备文件，鼠标，键盘

b 是块设备，比如硬盘

**2、第1-3位确定所有者（该文件的所有者）拥有该文件的权限。 ---User**

**3、第4-6位确定所属组（同用户组的）拥有该文件的权。 ---Group**

**4、第7-9位确定其他用户拥有该文件的权限。 ---Other**



### rwx 权限详解

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\rwx权限详解.png" style="zoom:150%;" />

### 文件及目录权限实际案例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\文件及目录权限实际案例.png" style="zoom:150%;" />



### 修改权限 - chmod

**基本说明：通过 chmod 指令，可以修改文件或者目录的权限。**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\修改权限.png" style="zoom:150%;" />

**第一种方式：+，-，= 变更权限**

u：所有者；g：所在组；o：其他人；a所有人（u、g、o的总和）

1）chmod u=rwx，g=rx，o=x 文件/目录名

2）chmod o+w 文件/目录名

3）chmod a-x 文件/目录名

**案例演示**

1）给 abc 文件的所有者读写执行的权限，给所在组读执行权限，给其它组读执行权限。

```linux
chmod u=rwx,g=rx,o=rx abc
```

2）给 abc 文件的所有者除去执行的权限，增加组写的权限。

```linux
chmod u-x,g+w abc
```

3）给 abc 文件的所有用户添加读的权限。

```linux
chmod a+r abc
```

**第二种方式：通过数字变更权限**

r=4 w=2 x=1 rwx=4+2+1

chmod u=rwx,g=rx,o=x 文件目录名

相当于 chmod 751 文件目录名

**案例演示：**案例：将 /home/abc.txt 文件的权限修改成 rwxr-xr-x，使用给数字的方式实现。

```linux
chmod 755 /home/abc.txt
```



### 修改文件所有者 - chown

**基本介绍**

chown newowner 文件/目录 改变所有者

chown newowner:newgroup 文件/目录 改变所有者和所在组

-R 如果是目录，则使其下所有子文件或目录递归生效

**案例演示**

案例1：请将 /home/abc.txt 文件的所有者修改成 tom

```linux
chown tom /home/abc.txt
```

案例2：请将 /home/kkk 目录下所有的文件和目录的所有者都修改成 tom

```linux
chown -R tom /home/kkk
```



### 修改文件所在组 - chgrp

**基本介绍**

chgrp newgroup 文件/目录 改变所在组

**案例演示**

案例1：请将 /home/abc.txt 文件的所在组修改成 shaolin （少林）

```linux
chgrp shaolin /home/abc.txt
```

案例2：请将 /home/kkk 目录下所有的文件和目录的所在组都修改成 shaolin（少林）

```linux
chgrp -R shaolin /home/kkk
```



### 警匪游戏

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\警匪游戏.png" style="zoom:150%;" />



# Linux 定时任务调度



## crond 任务调度

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\crond任务调度.png" style="zoom:150%;" />

### crond任务调度细节说明

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\crond任务调度之细节说明.png" style="zoom:150%;" />

### crond任务调度特殊符号说明

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\crond任务调度特殊符号说明.png" style="zoom:150%;" />

### crond任务调度特定时间任务案例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\crond任务调度特定时间任务案例.png" style="zoom:150%;" />

### crond任务调度应用实例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\crond任务调度应用实例.png" style="zoom:150%;" />

案例1：每隔一分钟，就将当前的日期信息，追加到 /tmp/mydate 文件中（要写一个脚本.sh 文件）

```linux
*/1 * * * * date >> /tmp/mydate
```

案例2：每隔一分钟，将当前日期和日历都追加到 /home/mycal 文件中

```sh
date >> /home/mycal
cal >> /home/cal
```

```linux
vim /home/my.sh #写入内容 date >> /home/mycal 和 cal >> /home/cal
#给 my.sh 增加执行权限
chmod u+x /home/my.sh
#打开列表
crontab -e 
#增加 
*/1 * * * * /home/my.sh
```

案例3：每天凌晨2:00将当 mysql 数据库 testdb，备份文件中。提示：指令为 mysqldump -u root -p密码 数据库 >> /home/db.bak

```linux
crontab -e
0 2 * * * mysqldump -u root -proot testdb > /home/db.bak
```

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\crond图解.png" style="zoom:150%;" />



## at 定时任务

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\at定时任务.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\at图解.png)

### at 命令选项

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\at命令选项.png" style="zoom:150%;" />

### at 时间定义

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\at时间定义.png" style="zoom:150%;" />

### at 应用实例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\at应用实例.png" style="zoom:150%;" />

**ctrl + D 退出 at**

案例1：2天后的下午5点执行 /bin/ls/home

```linux
at 5pm + 2 days
```

案例2：atq 命令来查看系统中没有执行的工作任务

```linux
atp
```

案例3：明天17点钟，输出时间到指定文件内，比如 /root/date100.log

```linux
at 5pm tomorrow
```

案例4：2分钟后，输出时间到指定文件内，比如 /root/date200.log

```linux
at now + 2 minutes
```

案例5：删除已经设置的任务，atrm 编号

```linux
atrm 5
```



# Linux 磁盘分区、挂载



## Linux分区

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux分区.png" style="zoom:150%;" />

### Linux硬盘说明

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux硬盘说明.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux分区图解.png" style="zoom:150%;" />



### 分区查看方法

**查看所有设备挂载情况：命令：lsblk 或者 lsblk -f**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\分区查看方法.png" style="zoom:150%;" />



## 挂载的经典案例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\挂载的经典案例.png" style="zoom:150%;" />

### 虚拟机增加硬盘步骤

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\虚拟机增加硬盘步骤1.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\虚拟机增加硬盘步骤2.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\挂载案例命令界面.png)

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\虚拟机增加硬盘步骤3.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\虚拟机增加硬盘步骤4.png" style="zoom:150%;" />



## 磁盘情况查询



### 查看系统整体磁盘使用情况

**基本语法：** df -h

**应用实例：**查看系统整体磁盘使用情况

```linux
df -h
```

### 查看指定目录的磁盘占用情况

**基本语法：**du -h /目录

**查看指定目录的磁盘占用情况，默认为当前目录**

-s：指定目录占用大小汇总

-h：带计量单位

-a：含文件

--max-depth=1：子目录深度

-c：列出明细的同时，增加汇总值

**应用实例：**查询 /opt 目录的磁盘占用情况，深度为1

```linux
du -hac --max-depth=1 /opt
```

### 磁盘情况工作实用指令

**可以统计文件夹数量的指令：wc -l**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\磁盘情况工作实用指令.png" style="zoom:150%;" />

```linux
tree /opt #以树状显示目录
```



# Linux 网络配置



<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux网络配置.png" style="zoom:150%;" />

## 查看网络IP和网关

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看网络IP和网关.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看网关.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\网络配置.png" style="zoom:150%;" />



## ping 测试主机之间网络连通性

**基本语法：**ping 目的主机 （功能描述：测试当前服务器是否可以连接目的主机）

**应用案例：**测试当前服务器是否连接百度

```linux
ping www.baidu.com
```



## Linux网络环境配置

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux网络环境配置.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux网络环境配置2.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\网络配置文件.png)

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\网络配置文件修改.png" style="zoom:150%;" />

### 网络配置文件修改后静态IP

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\网络配置文件修改后静态IP.png" style="zoom:150%;" />



### 网络配置重启生效

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\网络配置重启生效.png" style="zoom:150%;" />



## 设置主机名和host映射



### 设置主机名

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\设置主机名和host映射.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\设置主机名和host映射演示.png)

### 设置hosts映射

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\设置主机名和host映射步骤.png" style="zoom:150%;" />

**Windows**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\windows里的host文件.png)

**Linux**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux里的host文件.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\设置hosts映射.png)



## 主机名解析过程分析(Hosts、DNS)



<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\主机名解析过程分析(Hosts、DNS).png" style="zoom:150%;" />

### 主机名解析过程分析(Hosts、DNS)应用实例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\主机名解析过程分析(Hosts、DNS)应用实例.png" style="zoom:150%;" />



# Linux 进程管理



## 基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux进程管理基本介绍.png" style="zoom:150%;" />



## 显示系统执行的进程

### ps 命令查看进程目前执行状况

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\显示系统执行的进程.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看进程列表介绍.png" style="zoom:150%;" />



### 查看进程列表详解介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看进程列表详解介绍.png" style="zoom:150%;" />



### 应用实例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\显示系统执行的进程应用实例.png" style="zoom:150%;" />



## 终止进程 kill 和 killall

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\终止进程kill和killall.png" style="zoom:150%;" />

### 应用实例

案例1：踢掉某个非法登录用户

```linux
kill 进程号 #比如 kill 11421
```

案例2：终止远程登陆服务 sshd，在适当时候再次重启 sshd 服务

```linux
kill sshd 对应的进程号 #终止远程登陆服务 sshd
/bin/systemctl start sshd.service #再次重启 sshd 服务
```

案例3：终止多个 gedit

```linux
killall gedit
```

案例4：强制杀掉一个终端

```linux
kill -9 bash 对应的进程号
```



## 查看进程树 ptree

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看进程树 ptree.png" style="zoom:150%;" />



## 服务管理

### 服务管理介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\服务管理介绍.png" style="zoom:150%;" />

**service 管理指令案例：**请使用 service 指令，查看，关闭，启动 network [注意：在虚拟机系统演示，因为网络连接会关闭]

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\服务管理查看状态.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\服务管理关闭网络服务.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\服务管理重启网络服务.png)



### 查看服务名

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看服务名.png" style="zoom:150%;" />



### 服务的运行级别

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\服务的运行级别.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\服务的运行级别切换.png" style="zoom:150%;" />



### chkconfig 指令

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\chkconfig指令.png" style="zoom:150%;" />



### systemctl 管理指令

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\systemctl管理指令.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\端口防火墙图解.png" style="zoom:150%;" />



### 打开或者关闭指定端口

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\打开或者关闭指定端口.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\打开或者关闭指定端口案例.png)

**应用实例**

案例1：启用防火墙，测试111端口是否能 telnet（Windows下）

```linux
telnet IP号 端口号
```

案例2：开放111端口

```linux
firewall-cmd --permanent --add-port=111/tcp
firewall-cmd --reload
```

案例3：再次关闭111端口

```linux
firewall-cmd --permanent --remove-port=111/tcp
firewall-cmd --reload
```



## 动态监控进程

### 动态监控进程介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\动态监控进程.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\动态监控进程图解介绍.png" style="zoom:150%;" />



### 交互操作说明

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\动态监控进程交互操作说明.png" style="zoom:150%;" />

**应用实例**

案例3：指定系统状态更新的时间（每隔10秒自动更新）

```linux
top -d 10
```



## 监控网络状态

### 查看系统网络情况 netstat

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\监控网络状态.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\监控网络状态图解.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\监控网络状态图解.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\监控网络状态图解3.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\监控网络状态图解4.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\监控网络状态图解.png" style="zoom:150%;" />



# Linux RPM 与 YUM



## RPM 包的管理

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\RPM包的管理.png" style="zoom:150%;" />

### RPM 包简单查询指令

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\RPM包简单查询指令.png" style="zoom:150%;" />

### RPM 包其它查询指令

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\RPM包其它查询指令.png" style="zoom:150%;" />

### RPM 包卸载指令

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\RPM包卸载指令.png" style="zoom:150%;" />

### RPM 包安装指令

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\RPM包安装指令.png" style="zoom:150%;" />



## yum

### yum 介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\yum介绍.png" style="zoom:150%;" />



# Linux 搭建 JavaEE 环境



## 概述 - JDK

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\概述-JDK.png" style="zoom:150%;" />



## tomcat 的安装

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\tomcat的安装.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\为tomcat开放端口.png)



## idea 2020的安装

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\idea2020的安装.png" style="zoom:150%;" />



MySQL 的安装

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\mysql的安装.png" style="zoom:150%;" />

安装 mysql 5.7（CentOS7.6）

1、新建文件夹 /opt/mysql，并 cd 进去

2、运行 wget http://dev.mysql.com/get/mysql-5.7.26-1.el7.x86_64.rpm-bundle.tar，下载 mysql 安装包

PS：centos7.6 自带的类 mysql 数据库是 mariadb，会跟 mysql 冲突，要先删除。

3、运行 tar -xvf mysql-5.7.26-1.el7.x86_64.rpm-bundle.tar

4、运行 rpm -qa | grep mari，查询 mariadb 相关安装包

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\marriadb卸载.png)

5、运行 rpm -e --nodeps mariadb-libs，卸载

6、然后开始真正安装 mysql，依次运行以下指令

rpm -ivh mysql-community-common-5.7.26-1.el7.x86_64.rpm

rpm -ivh mysql-community-libs-5.7.26-1.el7.x86_64.rpm

rpm -ivh mysql-community-client-5.7.26-1.el7.x86_64.rpm

rpm -ivh mysql-community-server-5.7.26-1.el7.x86_64.rpm

7、运行 systemctl start mysqld.service，启动 mysql

8、然后开始设置 root 用户密码

MySQL 自动给 root 用户设置随机密码，运行 grep "password" /var/log/mysqld.log 可看到当前密码

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\mysql当前密码.png)

9、运行 mysql -u root -p密码，用 root 用户登录，提示输入密码可以用上述的，可以成功登录进去 mysql 命令行

10、设置 root 密码，对于个人开发环境，如果要设比较简单的密码（生产环境服务器设置复杂密码），可以运行 set global validate_password_policy=0；提示密码设置策略（validate_password_policy 默认值 1）

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\密码设置策略.png)

11、set password for 'root'@'localhost'=password('123456')

12、运行 flush pricileges；使密码设置生效



# Linux 大数据之Shell 编程



## 为什么要学习Shell编程

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\为什么要学习Shell编程.png" style="zoom:150%;" />



## Shell 脚本的执行方式

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Shell脚本的执行方式.png" style="zoom:150%;" />



## Shell的变量

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Shell的变量.png" style="zoom:150%;" />



### Shell变量的定义

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Shell变量的定义.png" style="zoom:150%;" />

### 应用实例代码

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Shell变量应用实例.png" style="zoom:150%;" />



## 设置环境变量

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\设置环境变量.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\设置环境变量的使用.png)

### Shell 脚本的多行注释

```shell
:<<!
内容
!
```



## 位置参数变量

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\位置参数变量.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\位置参数使用.png)

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\位置参数变量使用.png)



## 预定义变量

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\预定义变量.png" style="zoom:150%;" />

### 预定义变量使用

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\预定义变量使用1.png" style="zoom: 150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\预定义变量使用2.png" style="zoom: 200%;" />



## 运算符

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\运算符.png" style="zoom:150%;" />

### 运算符使用

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\运算符使用.png)



## 条件判断

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\条件判断.png" style="zoom:150%;" />

### 常用条件判断语句

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\条件判断语句.png)

### 条件判断语句使用

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\条件判断语句使用.png)





## 流程控制

### 流程控制 if

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\流程控制.png" style="zoom:150%;" />



### 流程控制 if 使用

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\流程控制使用.png)



### 流程控制 case

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\流程控制case.png" style="zoom:150%;" />

### 流程控制 case 使用

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\流程控制case使用.png)



### 流程控制 for

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\流程控制for.png" style="zoom:150%;" />

### 流程控制 for 使用

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\流程控制for使用.png)



### 流程控制 while

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\流程控制while.png" style="zoom:150%;" />

### 流程控制 while 使用

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\流程控制while使用.png)



## read读取控制台输入

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\read读取控制台输入.png" style="zoom:150%;" />

### read读取控制台输入使用

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\read读取控制台输入使用.png" style="zoom:150%;" />



## 函数



### 函数 basename

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\函数basename.png" style="zoom:150%;" />

**函数 basename 使用**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\函数basename使用.png" style="zoom:150%;" />



### 函数 dirname

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\函数dirname.png" style="zoom:150%;" />

**函数 dirname 使用**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\函数dirname使用.png)



### 自定义函数 

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\自定义函数.png" style="zoom:150%;" />

**自定义函数使用**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\自定义函数使用.png)



## Shell 编程综合案例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Shell编程综合案例.png" style="zoom:150%;" />

### 数据库备份步骤

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\数据库备份步骤.png)

### 数据库备份步骤代码

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\数据库备份步骤代码.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\数据库备份步骤代码加入crontab.png)



# Linux Python 开发平台 Ubuntu



## Ubuntu 介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Ubuntu介绍.png" style="zoom:150%;" />



## Ubuntu 安装

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Ubuntu安装.png" style="zoom:150%;" />



## Ubuntu 的 root 用户

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Ubuntu的root用户.png" style="zoom:150%;" />



## Ubuntu 下的开发 Python

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Ubuntu下的开发Python.png" style="zoom:150%;" />



# Linux APT 软件管理和远程连接



## apt 介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\apt介绍.png" style="zoom:150%;" />

### APT软件管理原理示意图

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\APT软件管理原理示意图.png" style="zoom:150%;" />



## Ubuntu 软件操作的相关命令

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Ubuntu软件操作的相关命令.png" style="zoom:150%;" />



## 更新 Ubuntu 软件下载地址

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\更新Ubuntu软件下载地址.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\更新Ubuntu软件下载地址-1.png" style="zoom:150%;" />



### 寻找国内镜像

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\寻找国内镜像.png" style="zoom:150%;" />

### 备份Ubuntu默认的源地址

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\备份Ubuntu默认的源地址.png" style="zoom:150%;" />

### 更新源服务器列表

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\更新源服务器列表.png" style="zoom:150%;" />

### 更新源

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\更新源.png" style="zoom:150%;" />



## Ubuntu 软件安装和卸载的最佳实践

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Ubuntu软件安装和卸载的最佳实践.png" style="zoom:150%;" />



## 远程登陆 Ubuntu

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\远程登陆Ubuntu.png" style="zoom:150%;" />



### 安装SSH和启用

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\安装SSH和启用.png" style="zoom:150%;" />

### Windows 远程连接

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Windows远程连接.png" style="zoom:150%;" />

### Linux 远程连接

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux远程连接.png" style="zoom:150%;" />

### SSH 远程登陆示意图

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\SSH远程登陆示意图.png" style="zoom:150%;" />



# CentOS8.1 的使用



## 安装 CentOS8.1

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\安装CentOS8.1.png" style="zoom:150%;" />



## 安装 CentOS8.1 的步骤

**和安装CentOS7.4大同小异**



## CentOS8.0和CentOS7.0的比较

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\CentOS8.0和CentOS7.0的比较.png" style="zoom:150%;" />



# Linux 日志管理



## 基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志管理的基本介绍.png" style="zoom:150%;" />



## 系统常用的日志

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\系统常用的日志.png" style="zoom:150%;" />

### 系统常用的日志列表

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\系统常用的日志列表.png" style="zoom:150%;" />

### 系统常用日志应用案例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\系统常用日志应用案例.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\系统常用日志应用案例图片.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\系统常用日志应用案例图片2.png" style="zoom:150%;" />



## 日志管理服务 rsyslogd

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志管理服务rsyslogd.png" style="zoom:150%;" />

### 日志类型

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志管理服务rsyslogd日志类型.png" style="zoom:150%;" />

### 日志级别

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志管理服务rsyslogd日志级别.png" style="zoom:150%;" />

### 日志文件格式

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志文件格式.png" style="zoom:150%;" />

### 日志管理服务应用案例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志管理服务应用案例.png" style="zoom:150%;" />



## 日志轮替



### 基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志轮替.png" style="zoom:150%;" />



### logrotate配置文件

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\logrotate配置文件.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\logrotate配置文件演示.png" style="zoom:150%;" />

**logrotate配置文件参数说明**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\logrotate配置文件参数说明.png" style="zoom:150%;" />



### 把自己的日志加入到日志轮替

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\把自己的日志加入到日志轮替.png" style="zoom:150%;" />



### 应用实例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志轮替应用实例.png" style="zoom:150%;" />

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志轮替应用实例演示-1.png)



### 日志轮替机制原理

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\日志轮替机制原理.png" style="zoom:150%;" />



## 查看内存日志

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看内存日志.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看内存日志图解.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\查看内存日志演示.png" style="zoom:150%;" />



# Linux 定制自己的 Linux 系统



## 基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\定制自己的Linux基本介绍.png" style="zoom:150%;" />



## 基本原理

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\定制自己的Linux基本原理.png" style="zoom:150%;" />



## 制作 minlinux 思路分析

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\制作minlinux思路分析.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\制作minlinux思路分析图解.png" style="zoom:150%;" />



# Linux 内核源码介绍和内核升级



## 为什么要阅读 Linux 内核

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\为什么要阅读Linux内核.png" style="zoom:150%;" />



## Linux0.01 内核源码

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux0.01内核源码.png" style="zoom:150%;" />



### Linux0.01 内核源码目录及阅读

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux0.01内核源码目录及阅读.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux0.01内核源码目录.png" style="zoom:150%;" />



### Linux0.01 内核源码目录解析

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux0.01内核源码目录解析.png" style="zoom:150%;" />



### Linux0.01 内核源码主方法解析

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux0.01内核源码主方法解析.png" style="zoom:150%;" />



## Linux 内核最新版本和内核升级

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux0.01内核最新版本和内核升级.png" style="zoom:150%;" />



### Linux 内核升级应用实例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux内核升级应用实例.png" style="zoom:150%;" />



# Linux 系统备份与恢复



## 基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\Linux系统备份与恢复基本介绍.png" style="zoom:150%;" />



## 安装 dump 和 restore

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\安装dump和restore.png" style="zoom:150%;" />



## 使用 dump 完成备份



### 基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\使用dump完成备份.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\使用dump完成备份图解.png" style="zoom:150%;" />



### 应用案例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\使用dump完成备份应用案例.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\dump 的使用1.png" style="zoom:150%;" />

**dump 的使用**

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\dump的使用.png)



### dump备份文件或者目录

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\dump备份文件或者目录.png" style="zoom:150%;" />



## 使用restore完成恢复



### 基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\使用restore完成恢复基本介绍.png" style="zoom:150%;" />



### 应用案例

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\使用restore完成恢复应用案例.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\使用restore完成恢复应用案例1.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\使用restore完成恢复应用案例2.png" style="zoom:150%;" />



# Linux 可视化管理 webmin 和 bt 运维工具



## webmin

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\webmin.png" style="zoom:150%;" />



### 、安装webmin配置

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\安装webmin配置.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\安装webmin配置1.png" style="zoom:150%;" />



### webmin 简单演示

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\webmin简单演示.png" style="zoom:150%;" />



## bt（宝塔）



### 基本介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\bt（宝塔）.png" style="zoom:150%;" />



### 使用介绍

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\bt（宝塔）使用介绍.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\bt（宝塔）使用介绍1.png" style="zoom:150%;" />



# Linux 面试题（腾讯，百度，美团，滴滴）



## 面试题 - 2

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\分析日志访问量.png" style="zoom:150%;" />

### 分析日志访问量

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\分析日志访问量-1.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\分析日志访问量-2.png" style="zoom:150%;" />



## 面试题 - 2

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\找回mysqlroot密码.png" style="zoom:150%;" />



### 找回 mysql root用户密码

**修改 /etc/my.cnf 文件，在后面加上一句话 skip-grant-tables**

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\找回mysqlroot用户密码.png" style="zoom:150%;" />



### 访问 IP 的数量统计（美团）

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\ip统计.png" style="zoom:150%;" />



### tcpdump 统计

![](C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\tcpdump统计.png)



## 面试题 - 3

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\面试题-3.png" style="zoom:150%;" />



## 面试题 - 4

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\面试题-4.png" style="zoom:150%;" />



## 面试题 - 5

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\面试题-5.png" style="zoom:150%;" />



### chattr 权限隔离（防黑）

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\chattr防黑.png" style="zoom:150%;" />

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\chattr防黑图解.png" style="zoom:150%;" />



### chkrootkit 检测入侵

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\chkrootkit检测入侵.png" style="zoom:150%;" />



## 面试题 - 6

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\面试题-6.png" style="zoom:150%;" />



## 面试题 - 7

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\面试题-7.png" style="zoom:150%;" />



## 面试题 - 8

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\面试题-8.png" style="zoom:150%;" />



### 算总和

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\算总和.png" style="zoom:150%;" />



## 面试题 - 9

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\面试题-9.png" style="zoom:150%;" />



## 面试题 - 10

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\面试题-10.png" style="zoom:150%;" />



### Linux 优化图解

<img src="C:\Users\FY\Desktop\笔记\学习笔记\Linux_image\linux优化图解.png" style="zoom:150%;" />
