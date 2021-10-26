# 搭建开发环境



### 在虚拟机的 Ubuntu 中创建 python web 开发环境

安装 python 管理工具

```py
wy@ubuntu:~$sudo apt-get -y install python-pip
```

安装虚环境包

```py
wy@ubuntu:~$sudo pip install virtualenv
```

安装完毕后，可以创建虚环境并进入虚环境中安装 Django。具体步骤包括以下三步：

执行 virtualenv djangovenv 语句，在当前用户文件内，创建虚环境 djangovenv。wy@ubuntu:~$ virtualenv djangovenv

激活虚环境。wy@ubuntu:~$ source djangovenv/bin/activate

在虚环境中，执行 pip install django 语句安装 django 或 flask。（djangovenv) wy@ubuntu:~$ pip install django;（djangovenv) wy@ubuntu:~$ pip install flask;



### 在 Windows 中创建支持 python 开发的虚环境

（1）安装 python

（2）输入命令 pip install virtualenv 安装虚环境管理包。

（3）进入开发项目用文件夹，输入命令：virtualenv VENV，创建虚环境文件夹。

（4）输入cd VENV 命令进入虚环境所在目录，输入 Scripts\activate 激活虚环境。

（5）输入pip install django 命令在虚环境中安装 django 包。



# 创建和启动 flask 应用

