# Linux命令基础
在刚入门学习和使用linux总会为记不住各种各样的命令而苦恼，我总结一下以防自己遗忘。

## 命令组成
linux的命令由三部分组成：**命令 选项 参数**，三个组成部分由空格隔开

其中选项可分为长选项和短选项，如--all和-a

长选项和短选项的作用是一样的，但是短选项可以多个组合，如-al，但长选项不可以组合

## 命令分类
shell的命令分为6种：
- **builtin**：shell内建命令
- **file**：磁盘文件，外部命令
- **function**：shell函数
- **keywords**：shell关键字
- **alias**：别名
- **unfound**：没有找到

### 如何查看命令的类型----type
使用type COMMAND就可以查看命令的类型：

[simon@centos-linux ~]$ **type ls**

**ls is aliased to `ls --color=auto'**

[simon@centos-linux ~]$ **type cd**

**cd is a shell builtin**

## 目录相关知识
目录的作用是用于存放其他的文件和目录。

### 相对路径和绝对路径
linux采用的是树形结构，每一个文件或目录都可以从根开始查找，如/usr/local/src,这种从根目录开始查找出的路径称为**绝对路径**

**相对路径**指的是从当前工作目录到目标目录的路径

### 特殊目录
####（.）和（..）
在每个目录下都会存在两个特殊的目录，分别是点（.）和点点（..）,在linux中以.开头的文件都是隐藏文件。

- .代表当前目录
- ..代表当面目录的父目录（上层目录）

#### ~
代表用户的家目录，使用cd或cd ~可以到达家目录

## su----切换用户
su命令是switch user的缩写，用来切换linux系统中的用户，命令格式为：**su [-l] USERNAME**
### su选项-硬切换和软切换
使用选项-l为硬切换,相当于注销当前账户。登录新账户。

## ls----列出文件和目录
ls默认情况下会列出当前**工作目录**下的文件和目录
![image description](http://i2.piimg.com/4851/cbb0b2d1700fb9ef.png)


### ls选项
ls有众多选项，下面列举一些常用的选项
#### -l----使用长列表模式
此选项可以列出文件和目录的更多信息

![image description](http://i4.piimg.com/4851/04f83de5aec5d161.png)

与**-h合用**，以人类可读的方式打印文件大小
#### -a----显示隐藏文件
使用-a选项可以显示以.开头的文件即linux的隐藏文件

![image description](http://i4.piimg.com/4851/b4accc82275a9e08.png)

#### -A----显示隐藏文件除了.和..