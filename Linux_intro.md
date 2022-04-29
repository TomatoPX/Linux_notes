<div align='center' ><font size='70'>Linux</font></div>

# Linux的目录结构

- Linux采用级层式树状目录，此结构中最上层是根目录：/

- Linux的世界里<font color="#ff0000">一切皆文件</font><br />

- / 下面有 root | home | bin | dev | etc 等基本组件

## 常用的目录结构

- /bin <font color="#ff0000">[常用]</font> (usr/bin、/usr/local/bin) <br /> 是Binary的缩写，这个目录存放着最经常使用的命令

- /sbin (/usr/sbin、/usr/local/sbin)<br />s就是Super User的意思，这里存放的是系统管理员使用的系统管理程序。

- /home <font color="#ff0000">[常用]</font><br />存放普通用户的主目录，在Linux中每个用户都有一个自己的目录，一般该目录名是以用户的账号命名

- /root <font color="#ff0000">[常用]</font> 该目录为系统管理员，也称作超级权限者的用户主目录

- /lib 系统开机所需要最基本的动态连接共享库，其作用类似于Windows里的DLL文件。几乎所有的应用程序都需要用到这些共享库

- /lost+found 这个目录一般情况下是空的，当系统非法关机后，这里就存放了一些文件

- /etc <font color="#ff0000">[常用]</font> 所有的系统管理所需要的配置文件和子目录my.conf 

- /usr <font color="#ff0000">[常用]</font> 这是一个非常重要的目录， 用户的很多应用程序和文件都放在这个目录下， 类似与windows下的program files目录。

- /boot <font color="#ff0000">[常用]</font> 存放的是启动Linux时使用的一些核心文件，包括一些连接文件以及镜像文件

- /proc <font color="#ff0000">[别动]</font> 这个目录是一个虚拟的目录，它是系统内存的映射，访问这个目录来获取系统信息

- /srv <font color="#ff0000">[别动]</font> service缩写， 该目录存放一些服务启动之后需要提取的数据

- /sys <font color="#ff0000">[别动]</font> 这是linux 2.6内核的一个很大的变化。该目录下安装了2.6内核中新出现的一个文件系统sysfs 

- /tmp这个目录是用来存放一些临时文件的

- /dev 类似于windows的设备管理器，把所有的硬件用文件的形式存储

- /media<font color="#ff0000">[常用]</font>linux系统会自动识别一些设备，例如U盘、光驱等等，当识别后，linux会把识别的设备挂载到这个目录下。

- /mnt<font color="#ff0000">[常用]</font><br />系统提供该目录是为了让用户临时挂载别的文件系统的，我们可以将外部的存储挂载在/mnt/上，然后进入该目录就可以查看里的内容了。

- /opt 这是给主机额外<font color="#ff0000">安装软件</font>所存放的目录。如安装ORACLE数据库就可放到该目录下。默认为空

- /usr/local<font color="#ff0000">[常用]</font> <br/>这是另一个给主机额外安装软件所安装的目录。一般是通过编译源码方式安装的程序

- /var<font color=red>[常用]</font> <br/>这个目录中存放着在不断扩充着的东西，习惯将经常被修改的目录放在这个目录下。包括各种日志文件

- /selinux [security-enhanced linux]<br/>SELinux是一种安全子系统，它能控制程序只能访问特定文件，有三种工作模式，可以自行设置.

******

# 远程登录到Linux

- 远程登录客户端有Xshell6, Xftp6,我们学习使用Xshell 和 Xftp6,其它的远程工具大同小异

- Xshell Xftp 都使用端口22进行登录Linux系统

******

# Vi和Vim编辑器

## vi和vim常用的三种模式

- 正常模式<br/> 以vim 打开一个档案就直接进入一般模式了（这是默认的模式）。在这个模式中，你可以使用『上下左右』按键来移动光标，你可以使用『删除字符』或『删除整行』来处理档案内容，也可以使用『复制、粘贴』来处理你的文件数据。

- 插入模式<br/> 按下`i，I，o，O，a，A，r，R`等任何一个字母之后才会进入编辑模式，一般来说按`i`即可，可以输入<kbd>Esc</kbd>离开插入模式进入正常模式

- 命令行模式<br/> 从正常模式输入 `:` 或`/`。 在这个模式当中，可以提供你相关指令，完成读取、存盘、替换、离开 vim、显示行号等的动作则是在此模式中达成的！

## vi和vim快捷键

- 拷贝当前行`yy`,拷贝当前行向下的5行`5yy`，粘贴`p`

- 删除当前行`dd`,删除当前行向下的5行`5dd` 

- 在文件中查找某个单词：命令行下用 `/关键字`+<kbd>Enter</kbd>查找，输入`n`就是查找下一个

- 设置文件的行号，取消文件的行号：命令行下用`:setnu`和`:set nonu`

- 使用快捷键到该文档的最末行 `G`(即<kbd>Shift</kbd>+`g`) 和最首行 `gg`

- 撤销动作，在一般模式下：`u`

- 将光标移动到20行，在一般模式下输入 `20`，再输入<kbd>Shift</kbd>+`g`

- 退出文件： `:wq`（保存退出）`:q`（退出） `:q!`（强制退出，不保存）

- [cheatsheet](https://www.runoob.com/w3cnote/all-vim-cheatsheat.html)

******

# 开机，重启和用户登录注销

## 关机&重启命令

- 基本介绍<br/>`shutdown -h now` 立该进行关机<br/>`shudown -h 1`"hello,1分钟后会关机了"<br/>`shutdown -r now` 现在重新启动计算机<br/>`halt` 关机，作用和上面一样<br/>`reboot` 现在重新启动计算机<br/>`sync` 把内存的数据同步到磁盘

- 注意细节<br/>不管是重启系统还是关闭系统，首先要运行`sync`命令，把内存中的数据写到磁盘中<br/>目前的`shutdown`/`reboot`/`halt`等命令均已经在关机前进行了`sync`, 老韩提醒：小心驶得万年船

## 用户登录和注销

- 登录时尽量少用root帐号登录，因为它是系统管理员，最大的权限，避免操作失误。可以利用普通用户登录，登录后再用”su-用户名’命令来切换成系统管理员身份。

- 在提示符下输入logout 即可注销用户

- 使用细节

    1. logout 注销指令在图形运行级别无效，在运行级别3下有效.

    2. 运行级别这个概念，在后面给大家介绍

******

# 用户管理

## 添加用户

- `adduser`和`useradd`的区别<br> `adduser`和`useradd`在Ubuntu中都可以用来创建用户，不存在一个可以一个不可以的概念；Linux中通常会使用`useradd`，而Ubuntu中通常使用`adduser`<br> `adduser`命令倾向于一种人际对话的过程，它会提示操作者按照步骤设置，前两步当然就是输入密码和再次确认密码，而`useradd`是没有人机对话过程的<br> `adduser`命令可以不带任何参数使用，并在完成后自动创建主目录，而`useradd`却不行，网上有一种说法是`useradd`创建出来的用户没有密码和主目录，这种说法是不准确的，因为`useradd`不带参数的使用才会这样，这属于使用`useradd`创建用户没有做完。<br> 

- `useradd`创建用户的过程，用户名，密码和主目录三个过程是分开进行的，它们分别对应：<br>创建一个用户newuser（默认家目录在`/home/newuser`）<br>
    ```Shell 
    useradd newuser
    ```
    为newuser设置密码
    ```Shell
    passwd newuser
    ```
    创建newuser时为newuser指定主目录
    ```Shell
    useradd -d /home/newuser newuser
    ```

- 上面三个过程，如果用adduser创建的话，就只需要：<br>创建一个用户newuser，并交互式的设置密码
    ```Shell
    adduser newuser
    ```

## 删除用户

- 基本语法<br> `userdel用户名`

- 删除用户是否保留家目录的讨论？<br>`userdel -r 用户名`<br>不一定，如果有他人的work在里面就不删除。一般情况下建议保留。

## 查询用户信息指令

- 基本语法<br> `id 用户名`

- 细节说明 <br> 用户不存在时，返回无此用户。

## 切换用户

- 在操作Linux中，如果当前用户的权限不够，可以通过`su-指令`，切换到高权限用户，比如root。

- 基本语法`su-切换用户名` 

- 细节说明

    1.从权限高的用户切换到权限低的用户,不需要输入密码,反之需要。

    2.当需要返回到原来用户时,使用exit/logout指令

## 查看当前用户/登录用户

- 基本语法 `whoami/whoamI`

## 用户组

### 用户组介绍

- 类似于角色，系统可以对有共性的多个用户进行统一的管理

- 新增组指令：`groupadd 组名`

- 删除组指令（基本语法）：`groupdel 组名`

- 增加用户时直接加上组指令（基本语法） ：`useradd -g 用户组 用户名`

- 修改用户的组指令(基本语法) ：`usermod -g 用户组 用户名`

### 用户和组相关文件

- /etc/passwd 文件
    用户（user）的配置文件，记录用户的各种信息
    每行的含义：<font color = blue>用户名：口令：用户标识号：组标识号：注释性描述：主目录：登录Shell</font> 

- /etc/shadow 文件
    口令的配置文件
    每行的含义：<font color = blue>登录名：加密口令：最后一次修改时间：最小时间间隔：最大时间间隔：警告时间：不活动时间：失效时间：标志</font>

- /etc/group 文件
    组（group）的配置文件，记录Linux包含的组的信息
    每行含义：<font color = blue>组名：口令：组标识号：组内用户列表</font>

******

# 实用指令

## 指定运行级别

### 基本介绍
- 运行级别说明:
    0: 关机
    1: 单用户【找回丢失密码】
    2: 多用户状态没有网络服务
    3: 多用户状态有网络服务
    4: 系统未使用保留给用户
    5: 图形界面
    6: 系统重启
    常用运行级别是3和5 ，也可以指定默认运行级别，后面演示

### 应用实例
- 命令:`init [0123456]`应用案例:通过init来切换不同的运行级别，比如动5-3，然后关机。

### CentOS7后运行级别说明
- 在CentOS7以前，在/etc/inittab文件中查看.
    现在进行了简化，如下:
    ```Shell
    multi-user.target: analogous to runlevel 3
    graphical.target: analogous to runlevel 5
    ```
    所以可以用以下指令进行查看和更改默认运行级别
    ```Shell
    #To view current default target, run:
    systemctl get-default
    #To set a default target, run:
    systemctl set-default TARGET.target
    ```

## 如何找回root密码（面试题）

- 不同版本有小区别。以下以CentOS7.6（及后的）为例

1. 首先，启动系统，进入开机界面，在界面中按`e`进入编辑界面。

2. 进入编辑界面，使用键盘上的上下键把光标往下移动，找到以““Linux16”开头内容所在的行数"，在行的最后面输入:`init=/bin/sh`。
    例： ```
        Linux16 /vmlinuz-3.10.0-957.e17.x86_64_root=UUID=12ae1cc1-09e0-42ce-b6\59-063df3e7c941 ro rhgb quiet LANG=zh_CN.UTF-8
        ```

3. 接着，输入完成后，直接按快捷键:<kbd>Ctrl</kbd>+`x` 进入单用户模式。

4. 接着，在光标闪烁的位置中输入: `mount -o remount,rw /`(注意:各个单词间有空格)，完成后按键盘的回车键（<kbd>Enter</kbd>)。

5. 在新的一行最后面输入: `passwd`，完成后按键盘的回车键(<kbd>Enter</kbd>)。输入密码，然后再次确认密码即可(韩顺平提示:密码长度最好8位以上,但不是必须的); 密码修改成功后，会显示`passw.....`的样式，说明密码修改成功

6. 接着，在鼠标闪烁的位置中（最后一行中）输入:`touch /.autorelabel`(注意: touch与 /后面有一个空格)，完成后按键盘的回车键(<kbd>Enter</kbd>)

7. 继续在光标闪烁的位置中，输入: `exec /sbin/init`(注意:exec与/后面有一个空格)完成后等待系统自动修改密码(韩顺平提示:这个过程时间可能有点长，耐心等待)，完成后，系统会自动重启，<b>新的密码生效了</b>

## 帮助指令

- man获得帮助信息
    基本语法:`man [命令或配置文件]`(功能描述∶获得帮助信息)
    在linux下，隐藏文件是以`.`开头，选项可以组合使用比如`ls -al`,比如 `ls -al /root`

- help指令
    基本语法:`help 命令`（功能描述:获得shell内置命令的帮助信息)

- 百度帮助更直接
    如果英语不太好的，也可以直接百度靠谱。

## 文件目录指令

### pwd指令基本语法: `pwd`

- (功能描述:显示当前工作目录的绝对路径)

### ls指令

- 基本语法:
    `ls [选项] [目录或是文件]`

- 常用选项：
    `-a `:显示当前目录所有的文件和目录，包括隐藏的。
    `-l `:以列表的方式显示信息

### cd指令

- 基本语法:
    `cd [参数]`(功能描述:切换到指定目录)
    理解:绝对路径和相对路径

- 常用选项：
    `cd ~` 或者`cd :`回到自己的家目录
    `cd ..`回到当前目录的上一级目录

### mkdir指令

- mkdir指令用于创建目录

- 基本语法:
    `mkdir [选项]`要创建的目录·

- 常用选项：
    `-p`:创建多级目录
        ```Shell
        mkdir -p /home/animal/tiger
        ```

### rmdir指令

- rmdir指令删除空目录

- 基本语法: 
    `rmdir [选项] 要删除的空目录`

- 使用细节：
    rmdir 删除的是空目录，如果目录下有内容时无法删除的。
    提示∶如果需要删除非空目录，需要使用rm -rf 要删除的目录

### touch指令

- touch指令创建空文件

- 基本语法：
    `touch 文件名称`

### cp指令

- cp指令拷贝文件到指定目录

- 基本语法: 
    `cp [选项] source dest`

- 常用选项:
    `-r`:递归复制整个文件夹

- 使用细节:
    强制覆盖不提示的方法:使用`\cp`替换`cp`

### rm指令

- 说明:rm指令移除文件或目录

- 基本语法:
    `rm [选项] 要删除的文件或目录`

- 常用选项:
    `-r`:递归删除整个文件夹
    `-f`:强制删除不提示

- 特别提醒：
    `-rf`操作非常危险，一定要弄清楚再操作

### mv指令

- mv移动文件与目录或重命名

- 基本语法：
    `mv oldNameFile newNameFile`(功能描述:重命名)
    `mv /temp/movefile /targetFolder` (功能描述∶移动文件)

### cat指令

- cat查看文件内容

- 基本语法:
    `cat [选项] 要查看的文件`
- 常用选项:
    `-n`:显示行号
- 使用细节:
    cat只能浏览而不能修改文件，为了浏览方便，一般会带上管道命令`| more`

### more指令

- more指令是一个基于VI编辑器的文本过滤器，它以全屏幕的方式按页显示文本文件的内容。more指令中内置了若干快捷键，详见操作说明

- 基本语法:
    `more 要查看的文件`
- 操作:
    | 操作 | 功能说明|
    |-|-|
    |空白键(<kbd>Space</kbd>)|代表向下翻一页;|
    |<kbd>Enter</kbd>|代表向下翻『一行』;|
    |`q`|代表立刻离开more ，不再显示该文件内容。|
    |<kbd>Ctrl</kbd>+`F`|向下滚动一屏|
    |<kbd>Ctrl</kbd>+`B`|返回上一屏|
    |`=`|输出当前行的行号|
    |`:f`|输出文件名和当前行的行号|

### less指令

- less指令用来分屏查看文件内容，它的功能与more指令类似，但是比more指令更加强大，支持各种显示终端。less指令在显示文件内容时，并不是一次将整个文件加载之后才显示，而是根据显示需要加载内容，对于显示大型文件具有较高的效率。

- 基本语法:
    `less 要查看的文件`

- 操作
    | 操作 | 功能说明|
    |-|-|
    |空白键(<kbd>Space</kbd>)|向下翻一页;|
    |<kbd>PageDown</kbd>|向下翻一页;|
    |<kbd>PageUp</kbd>|向上翻一页;|
    |`/字串`|向下搜寻『字串』的功能; `n`:向下查找;`N`:向上查找;|
    |`?字串`|向上搜寻『字串』的功能; `n`:向上查找;`N`:向下查找;|
    |`q`|离开less这个程序;|

### echo指令

- echo输出内容到控制台

- 基本语法:
    `echo [选项] [输出内容]`

- 应用实例:
    使用echo指令输出环境变量, `echo $HOSTNAME` `echo $PATH`
    使用echo指令输入某文件：
    - `echo "Hello" > h.txt`(覆盖输入"Hello"到h.txt) 
    - `echo "Hello" >> h.txt`(在原文件尾部追加输入"Hello"到h.txt) 
    - 详见后面 [>指令和>>指令]

### head指令

- head用于显示文件的开头部分内容，默认情况下head指令显示文件的前10行内容

- 基本语法：
    `head 文件`(功能描述:查看文件头10行内容)
    `head -n 5 文件`(功能描述:查看文件头5行内容，5可以是任意行数)

###  tail指令

- tail用于输出文件中尾部的内容，默认情况下tail指令显示文件的前10行内容。

- 基本语法：
    1) `tail 文件`(功能描述:查看文件尾10行内容)
    2) `tail -n 5 文件`(功能描述∶查看文件尾5行内容，5可以是任意行数)
    3) `tail -f 文件`（功能描述:<b>实时追踪</b>该文档的所有更新）

### \>指令和>>指令

- \>输出重定向和>>追加

- 基本语法:
    1)` ls -l > 文件` (功能描述:列表的内容写入文件(覆盖写)，如没有文件会创建)
    2)` ls -al >> 文件`(功能描述:列表的内容追加到文件的末尾)
    3) `cat 文件1 > 文件2`(功能描述:将文件1的内容覆盖到文件2)
    4) `echo "内容" >> 文件`

### ln指令

- 软链接也称为符号链接，类似于windows里的快捷方式，主要存放了链接其他文件的路径

- 基本语法:
    `ln -s [原文件或目录] [软链接名]`(功能描述:给原文件创建一个软链接)

- 细节说明:
    当我们使用pwd指令查看目录时，仍然看到的是软链接所在目录。
    可以用`rm`删除软连接

### history指令

- 查看已经执行过历史命令,也可以执行历史指令

- 基本语法：
    `history`(功能描述:查看已经执行过历史命令)
    `history 10` (显示最近使用过的10个指令)
    `!5`(执行历史编号为5的指令)

## 时间日期指令

### date指令

- 显示当前日期

- 基本语法
    1) `date` (功能描述:显示当前时间)
    2) `date +%Y`(功能描述:显示当前年份)
    3) `date +%m`(功能描述:显示当前月份)
    4) `date +%d`(功能描述:显示当前是哪一天)
    5) `date "+%Y-%m-%d %H:%M:%S"`（功能描述:显示年月日时分秒)

###  date指令-设置日期

- 基本语法
    `date -s 字符串时间`

- 应用实例
    设置系统当前时间，比如设置成2021-11-11 11:22:22
    `date -s 2021-11-11 11:22:22`

### cal指令

- 查看日历指令

- 基本语法`cal [选项]`
    (功能描述:不加选项，显示本月日历)

- 应用实例
    案例1:显示当前日历 `cal`
    案例2:显示2020年日历:`cal 2020`

## 搜索查找类

### find指令

- find指令将从指定目录向下递归地遍历其各个子目录，将满足条件的文件或者目录显示在终端。

- 基本语法
    `find [搜索范围] [选项]`

- 选项说明
    | 选项 | 功能 |
    |-|-|
    | `-name <查询方式>` | 按照指定的文件名查找模式查找文件 |
    | `-user <用户名>` | 查找属于指定用户名所有文件 |
    | `-size <文件大小>` | 按照指定的文件大小查找文件。<br>+n大于-n小于n等于<br>单位有k,M,G|

### locate指令

- locate指令可以快速定位文件路径。locate指令利用事先建立的系统中所有文件名称及路径的locate数据库实现快速定位给定的文件。Locate指令无需遍历整个文件系统，查询速度较快。为了保证查询结果的准确度，管理员必须定期更新locate时刻

- 基本语法
    `locate 搜索文件`

- 特别说明
   由于locate指令基于数据库进行查询，所以第一次运行前，必须使用`updatedb`指令创建locate数据库。

### which指令

- 可以查看某个指令在哪个目录下，比如ls指令在哪个目录`which ls`

### grep指令和管道符号|

- grep过滤查找，管道符`|`，表示将前一个命令的处理结果输出传递给后面的命令处理。

- 基本语法
    `grep [选项] 查找内容 源文件`

- 常用选项
    |  选项 | 功能  |
    |-|-|
    |`-n`| 显示匹配行及行号。 |
    |`-i`| 忽略字母大小写 |

- 应用实例
    案例1:请在hello.txt文件中，查找“yes”所在行，并且显示行号
    写法1: `cat /home/hello.txt | grep "yes"`
    写法2: `grep -n "yes" /home/hello.txt`

## 压缩和解压类

### gzip/gunzip指令

- gzip 用于压缩文件，gunzip 用于解压

- 基本语法
    `gzip 文件`      (功能描述:压缩文件,只能将文件压缩为*.gz文件)
    `gunzip 文件.gz`（功能描述:解压缩文件命令)

### zip/unzip指令

- zip 用于压缩文件，unzip 用于解压。这个在项目打包发布中很有用

- 基本语法
    `zip [选项] XXX.zip`将要压缩的内容(功能描述:压缩文件和目录的命令)
    `unzip [选项] XXX.zip`(功能描述:解压缩文件)

- zip常用选项
    `-r` :递归压缩，即压缩目录

- unzip的常用选项
    `-d <目录>`︰指定解压后文件的存放目录

### tar 指令

- tar指令是打包指令,最后打包后的文件是.tar.gz的文件。

- 基本语法
    `tar [选项] XXX.tar.gz 打包的内容`(功能描述:打包目录，压缩后的文件格式.tar.gz)

- 选项说明
    | 选项 | 功能 |
    | - |-  |
    | `-c` | 产生.tar打包文件 |
    | `-v` | 显示详细信息 |
    | `-f` | 指定压缩后的文件名打包同时压缩 |
    | `-z` | 打包同时压缩 |
    | `-x` | 解包.tar文件 |

- 应用实例
    案例1:压缩多个文件，将/home/pig.txt和/home/cat.txt压缩成 pc.tar.gz
    `tar -zcvf pc.tar.gz /home/pig.txt /home/cat.txt`
    案例2:将/home的文件夹压缩成myhome.tar.gz
    `tar -zcvf myhome.tar.gz /home/`
    案例3:将pc.tar.gz解压到当前目录
    `tar -zxvf pc.tar.gz`
    案例4:将myhome.tar.gz解压到/opt/tmp2目录下
    (1) `mkdir /opt/tmp2`
    (2) `tar -zxvf /home/myhome.tar.gz-C /opt/tmp2`(`-C`转到指定的目录)

******

# 组管理和权限管理

- 在linux中的每个用户必须属于一个组，不能独立于组外。在linux中每个文件有所有者、所在组、其它组的概念。

- Linux文件 F 的创建者 U 是 F 的默认所有者，这个 U 所属的组 G 就是 F 的默认所在组，此机器上所有不是 G 的组就是其他组。

## 所有者

- 一般为文件的创建者,谁创建了该文件，就自然的成为该文件的所有者。

- 查看文件的所有者
    指令:`ls -ahl`

- 修改文件所有者
    指令:`chown 用户名 文件名`

## 组的创建

- 基本指令
    `groupadd 组名`

- 应用实例
    创建一个组monster:`groupadd monster`
    创建一个用户fox，并放入到monster组中:`useradd -g monster fox`

## (文件/目录)所在组

- 当某个用户创建了一个文件后，这个文件的所在组就是该用户所在的组。

- 查看文件/目录所在组
    `ls -ahl`

- 修改文件所在的组√基本指令
    `chgrp 组名 文件名`

## 其它组

- 除文件的所有者和所在组的用户外，系统的其它用户都是文件的其它组

## 改变用户所在组

- 在添加用户时，可以指定将该用户添加到哪个组中，同样的用root的管理权限可以改变某个用户所在的组。

- 改变用户所在组

    1.`usermod -g 组名 用户名`

    2.`usermod -d 目录名 用户名`改变该用户登陆的初始目录。==特别说明==∶用户需有进入到新目录的权限。

## 权限的基本介绍

- ls -l中显示的内容如下:
    `-rwxrw-r-- 1 root root 1213 Feb 2 09:39 abc`

### 权限0-9位说明

1. 第0位确定文件类型(d,- ,l,c,b) 
    l是链接,相当于windows的快捷方式
    d是目录,相当于windows的文件夹
    c是字符设备文件,鼠标,键盘
    b是块设备，比如硬盘
    -是文件

2. 第1-3位确定所有者（该文件的所有者)拥有该文件的权限。---User

3. 第4-6位确定所属组(同用户组的)拥有该文件的权限，---Group

4. 第7-9位确定其他用户拥有该文件的权限---Other

### rwx权限详解

#### rwx作用到文件

1. [`r`] 代表可读(read):可以读取,查看

2. [`w`]代表可写(write):可以修改,但是不代表可以删除该文件,删除一个文件的前提条件是对该文件所在的自录有写权限，才能删除该文件.

3. [`x`]代表可执行(execute):可以被执行

#### rwx作用到目录

1. [`r`]代表可读(read):可以读取，ls查看目录内容

2. [`w`]代表可写(write):可以修改,对目录内创建+删除+重命名目录

3. [`x`]代表可执行(execute):可以进入该目录

#### 数字表示rwx

- 可用数字表示为: r=4,w=2,x=1 因此rwx=4+2+1=7

- 不同的权限可以用0-7这8个数字来表达

### ls的其他内容

- 例子： 
    `-rwxrw-r-- 1 root root 1213 Feb 2 09:39 abc`
    |字符 | 意思|
    |-|-|
    |`1`| 文件:硬连接数 或 目录:子目录数 |
    |`root`| 用户  |
    |`root`| 组 |
    |`1213`| 文件大小(字节)，如果是文件夹，显示4096字节 |
    |`Feb 2 09:39`| 最后修改日期 |
    |`abc`| 文件名 |

## 修改权限-chmod

- 基本说明:
    通过chmod指令，可以修改文件或者目录的权限。

- 第一种方式: `+`、`-`、`=`变更权限
    `u`:所有者`g`:所有组`o`:其他人`a`:所有人(u、g、o的总和)
    1) `chmod u=rwx,g=rx,o=x 文件/自录名`
    2) `chmod o+w 文件/目录名`
    3) `chmod a-x 文件/目录名`

- 第二种方式:通过数字变更权限
    r=4 w=2 x=1 rwx=4+2+1=7
    `chmod u=rwx,g=rx,o=x 文件目录名`相当于`chmod 751 文件/目录名`
    <table>
        <tr>
            <td> 数字 </td>
            <td> 0 </td>
            <td> 1 </td>
            <td> 2 </td>
            <td> 3 </td>
            <td> 4 </td>
            <td> 5 </td>
            <td> 6 </td>
            <td> 7 </td>
        </tr>
        <tr>
            <td> 权限 </td>
            <td> --- </td>
            <td> --x </td>
            <td> -w- </td>
            <td> -wx </td>
            <td> r-- </td>
            <td> r-x </td>
            <td> rw- </td>
            <td> rwx </td>
        </tr>
    </table>

## 修改文件所有者-chown

- 基本介绍
    `chown newowner 文件/目录` 改变所有者
    `chown newowner:newgroup 文件/自录`改变所有者和所在组
    `-R` 如果是目录则使其下所有子文件或目录递归生效

## 修改文件所在组-chgrp

- 基本介绍
    `chgrp newgroup 文件/目录` 改变所有组
    `-R` 如果是目录则使其下所有子文件或目录递归生效 

******

# 定时任务调度

## crond任务调度

### crond概述

- 进行定时任务的调度

- 任务调度:是指系统在某个时间执行的特定的命令或程序。

- 任务调度分类: 系统工作:有些重要的工作必须周而复始地执行。如病毒扫描等

- 个别用户工作:个别用户可能希望执行某些程序，比如对mysql数据库的备份。

### 基本语法

- `crontab [选项]`

### 常用选项

- 如下表
    |选项| 功能 |
    | -|- |
    | `-e `|编辑crontab定时任务 |
    | `-l `| 查询crontab任务|
    | `-r `|删除当前用户所有的crontab任务 |

### 快速入门

- 设置任务调度文件: /etc/crontab

- 设置个人任务调度:

    1. 执行crontab -e命令。

    2. 接着输入任务到调度文件

    3. 如:`*/1 * * * * ls -l /etc    / > /tmp/to.txt` 意思说每小时的每分钟执行`ls -l /etc/ > /tmp/to.txt`命令

### 参数细节说明

- 5个占位符的说明
    | 项目| 含义|范围 |
    |- |- | -|
    |第一个“`*`" | 一小时当中的第几分钟|0-59 |
    |第二个“`*`" | 一天当中的第几小时 | 0-23 |
    |第三个“`*`" | 一个月当中的第几天 | 1-31 |
    |第四个“`*`" | 一年当中的第几月 | 1-12 |
    |第五个“`*`" | 一周当中的星期几 | 0-7(0和7都代表星期日) |

- 特殊符号的说明
    |  特殊符号 | 含义  |
    |-|-|
    | ` * `|   代表任何时间。比如第一个“`*`”就代表一小时中每分钟都执行一次的意思。 |
    | ` , `| 代表不连续的时间。比如“`0 8,12,16 * * * 命令`”，就代表在每天的8点0分，12点0分，16点0分都执行一次命令   |
    | ` - `|  代表连续的时间范围。比如“`0 5 * * 1-6 命令`”，代表在周一到周六的凌晨5点0分执行命令  |
    | ` */n `|  代表每隔多久执行一次。比如“`*/10 * * * * 命令`”，代表每隔10分钟就执行一遍命令  |

### 应用实例

1. 每隔1分钟，就将当前的日期信息，追加到/tmp/mydate文件中:
    `*/1 * * * * date >> /tmp/mydate`

2. 每隔1分钟,将当前日期和日历都追加到/home/mycal文件中
    1. `vim/home/my.sh` 写入内容 `date >> /home/mycal` 和 `cal >> /home/mycal`
    2. 给my.sh增加执行权限，`chmod u+x /home/my.sh`
    3. `crontab -e` 增加 `*/1 * * * * /home/my.sh`

3. 每天凌晨2:00将mysql数据库testdb，备份到文件中。
    提示: 指令为`mysqldump -u root -p密码 数据库 > /home/db.bak`
    1. `crontab -e`
    2. `0 2 * * * mysqldump -u root -proot testdb > /home/db.bak`

### 相关指令

- service crond restart[重启任务调度]

## at任务调度

### at基本介绍

1. at命令是一次性定时计划任务，at的守护进程atd会以后台模式运行，检查作业队列来运行。

2. 默认情况下，atd守护进程每60秒检查作业队列，有作业时，会检查作业运行时间，如果时间与当前时间匹配，则运行此作业。

3. at命令是一次性定时计划任务，执行完一个任务后不再执行此任务了

4. 在使用at命令的时候，一定要保证atd进程的启动，可以使用相关指令来查看:
    `ps -ef | grep atd` //可以检测atd是否在运行

### at命令格式

- 常用命令
    `at [选项] [时间]`
    <kbd>Ctrl</kbd> + `D`结束at命令的输入

### at命令选项

- 如下表
    |选项 | 选项|
    | -| -|
    |` -m`| 当指定的任务被完成后，将给用户发送邮件，即使没有标准输出  |
    |`-I `|  atq的别名 （查看当前存在任务及任务号） |
    |`-d `|  atrm的别名 （通过任务号删除任务）|
    |`-v `|  显示任务将被执行的时间 |
    |`-c `| 打印任务的内容到标准输出  |
    |`-v `|  显示版本信息 |
    |`-q <队列> `| 使用指定的队列  |
    |`-f <文件> `|  从指定文件读入任务而不是从标准输入读入 |
    |`-t  <时间参数>`| 以时间参数的形式提交要运行的任务  |

### at时间定义at指定时间的方法:

1. 接受在当天的hh:mm (小时:分钟）式的时间指定。假如该时间已过去，那么就放在第二天执行。例如: `04:00`

2. 使用midnight（深夜）,noon(中午)，teatime(饮茶时间，一般是下午4点）等比较模糊的词语来指定时间。

3. 采用12小时计时制，即在时间后面加上AM(上午）或PM(下午)来说明是上午还是下午。例如:`12pm`

4. 指定命令执行的具体日期，指定格式为month day(月日）或mm/dd/yy (月/日/年）或dd.mm.yy(日.月.年），指定的日期必须跟在指定时间的后面。
    例如:`04:00 2021-03-1`

5. 使用相对计时法。指定格式为:`now + count time-units`, now就是当前时间，time-units是时间单位，这里能够是minutes(分钟)、hours (小时)、days(天)、weeks（星期)。count是时间的数量，几天，几小时。例如:`now + 5 minutes`

6. 直接使用today (今天)、tomorrow(明天）来指定完成命令的时间。
    例如:`5pm tomorrow  `

******

# Linux磁盘分区、挂载

## Linux磁盘原理介绍

1. Linux来说无论有几个分区，分给哪一目录使用，它归根结底就只有一个根目录，一个独立且唯一的文件结构，Linux中每个分区都是用来组成整个文件系统的一部分。

2. Linux采用了一种叫“载入”的处理方法，它的整个文件系统中包含了一整套的文件和目录，且将一个分区和一个目录联系起来。这时要载入的一个分区将使它的存储空间在一个目录下获得。

## 查看所有设备挂载情况

- 命令: `lsblk`或者`lsblk -f`

- 可以看到各硬盘分区的UUID和挂载点等信息 

## 硬盘说明

1. Linux硬盘分IDE硬盘和SCSI硬盘，目前基本上是SCSI硬盘

2. 对于IDE硬盘，驱动器标识符为“`hdx~`”,其中“hd”表明分区所在设备的类型，这里是指IDE硬盘了。“`x`”为盘号(a为基本盘，b为基本从属盘，c为辅助主盘，d为辅助从属盘)，"`~`”代表分区，前四个分区用数字1到4表示，它们是主分区或扩展分区，从5开始就是逻辑分区。例，hda3表示为第一个IDE硬盘上的第三个主分区或扩展分区,hdb2表示为第二个IDE硬盘上的第二个主分区或扩展分区。

3. 对于SCSI硬盘则标识为“`sdx~`" ，SCSI硬盘是用“`sd`”来表示分区所在设备的类型的，其余则和IDE硬盘的表示方法一样。

## 挂载的经典案例
- 说明:
    下面我们以增加一块硬盘为例来熟悉下磁盘的相关指令和深入理解磁盘分区、挂载、卸载的概念。如何增加一块硬盘

### 虚拟机添加硬盘

- 在【虚拟机】菜单中，选择【设置】,然后设备列表里添加硬盘，然后一路【下一步】，中间只有选择磁盘大小的地方需要修改，至到完成。然后重启系统(才能识别)!

### 分区

- 命令`fdisk /dev/sdb`

- 开始对/sdb分区
    m 显示命令列表
    p 显示磁盘分区同fdisk -l
    n 新增分区
    d 删除分区
    w 写入并退出
    说明:开始分区后输入n,新增分区，然后选择p，分区类型为主分区。两次回车默认剩余全部空间。最后输入w写入分区并退出，若不保存退出输入q

### 格式化

- 格式化磁盘

- 分区命令:`mkfs -t ext4 /dev/sdb1`其中ext4是分区类型

### 挂载

- 将一个分区与一个目录联系起来
    `mount 设备名称 挂载目录`
    例如: `mount /dev/sdb1/newdisk`

- 卸载
    `umount 设备名称或者挂载目录`
    例如:`umount /dev/sdb1` 或者 `umount /newdisk`

- <font color = red>注意:用命令行挂载重启后会失效</font>

### 设置可以自动挂载

- 永久挂载:通过修改/etc/fstab实现挂载
    添加：
    `/dev/sdb1    /newdisk   ext4   defaults 0 0 `
    添加完成后执行`mount -a`(重新加载fstab文件中的内容)即刻生效

## 磁盘情况查询

### 查询系统整体磁盘使用情况

- 基本语法
    `df -h` 

### 查询指定目录的磁盘占用情况

- 基本语法
    `du -h`
    查询指定目录的磁盘占用情况，默认为当前目录

- 选项    
    `-s` 指定目录占用大小汇总
    `-h` 带计量单位
    `-a` 含文件
    `--max-depth=n ` 子目录深度
    `-c` 列出明细的同时，增加汇总值

- 应用实例
    查询/opt目录的磁盘占用情况，深度为1
    ` du -hac --max-depth=1 /opt `

### 磁磁情况-工作买用指令

1. 统计/opt文件夹下文件的个数
    `ls -l /opt | grep "^-" | wc -l`(wc->word count)
2. 统计/opt文件夹下目录的个数
    `ls -l /opt | grep "^d" | wc -l`
3. 统计/opt文件夹下文件的个数，包括子文件夹里的
    `ls -lR /opt | grep "^-" | wc -l`
4. 统计/opt文件夹下目录的个数，包括子文件夹里的.    
    `ls -lR /opt | grep "^d" | wc -l`
5. 以树状显示自录结构 `tree 目录` ,注意，如果没有tree ,则使用`yum install tree`安装(或者apt-get install...)

******

# 网络配置

## 查看网络IP和网关

- 查看windows环境的中的网络配置：`ipconfig`

- 查看linux的网络配置:`ifconfig`

- ping测试主机之间网络连通性
    `ping 目的主机`（功能描述:测试当前服务器是否可以连接目的主机)●
    - 应用实例
    测试当前服务器是否可以连接百度`ping www.baidu.com`

## linux网络环境配置

### 第一种方法(自动获取):

- 说明:登陆后，通过界面的来设置自动获取ip，特点:linux启动后会自动获取IP缺点是每次自动获取的ip地址可能不一样。

### 第二种方法(指定ip)

- 说明:直接修改配置文件来指定IP并可以连接到外网(程序员推荐)
    编辑vi/etc/sysconfig/network-scripts/ifcfg-ens33
    要求:将ip地址配置的静态的，比如: ip地址为192.168.200.130

- ifcfg-ens33文件说明
    ```Shell
    DEVICE=etho #接口名(设备,网卡)
    HWADDR=00:0C:2x:6x:Ox:xx #MAC地址
    TYPE=Ethernet    #网络类型（通常是Ethemet)
    UUID=926a57ba-92c6-4231-bacb-f27e5e6a9f44 #随机id
    ONBOOT=yes   #系统启动的时候网络接口是否有效(yes/no)
    #IP的配置方法[none|static|bootp|dhcp]
    #（引导时不使用协议|静态分配IP[BOOTP协议|DHCP协议)
    BOOTPROTO=static #<===========改这个
    #IP地址
    IPADDR=192.168.200.130 #<===========加这个
    #网关
    GATEWAY=192.168.200.2 #<===========加这个
    #域名解折器
    DNS1=192.168.200.2 #<===========加这个
    ```

### 重启网络服务或者重启系统生效

`service network restart` . `reboot`

## 设置主机名和hosts映射

### 设置全机名
1. 为了方便记忆，可以给linux系统设置主机名,也可以根据需要修改主机名
2. 指令`hostname` :查看主机名
3. 修改文件在/etc/hostname指定
4. 修改后，重启生效

### 设置hosts映射

- 思考:如何通过主机名能够找到(比如ping)某个linux系统?

#### windows设置hosts映射

- 在C:\Windows\System32\drivers\etc\hosts文件指定即可

- 案例:`192.168.200.130 hspedu100`

#### linux设置hosts映射

- 在/etc/hosts文件指定

- 案例:`192.168.200.1 ThinkPad-PC`

## 主机名解析机制分析(Hosts、DNS)

### Hosts是什么

- 一个文本文件，用来记录IP和Hostname(主机名)的映射关系

### DNS

1. DNS，就是Domain Name System 的缩写，翻译过来就是域名系统

2. 是互联网上作为域名和IP地址相互映射的一个分布式数据库

### 解析机制应用分析

- 用户在浏览器输入了 `www.baidu.com`

1. 浏览器先检查浏览器缓存中有没有该域名解析IP地址，有就先调用这个IP完成解析;如果没有检查操作系统DNS解析器缓存，如果有直接返回IP完成解析。这两个缓存，可以理解为本地解析器缓存

2. 一般来说，当电脑第一次成功访问某一网站后，在一定时间内，浏览器或操作系统会缓存他的IP地址（DNS解析记录).
    如在cmd窗口中输入 
    `ipconfig /displaydns`//DNS域名解析缓存
    `ipconfig /flushdns`  //手动清理dns缓存

3. 如果本地解析器缓存没有找到对应映射,检查系统中hosts文件中有没有配置对应的域名IP映射，如果有，则完成解析并返回。

4. 如果本地DNS解析器缓存和hosts文件中均没有找到对应的IP, 则到域名服务DNS进行解析域

5. 域名服务DNS进行解析会先向==本地域名服务器==发出请求
    如果没有结果，本地域名服务器会向==根域名服务器==发出请求
    如果没有结果，本地域名服务器会向==顶级（二级，三级...）域名服务器==发出请求
    如果没有结果，本地域名服务器会向==权威域名服务器==发出请求
    如果有本地域名服务器会把结果返回客户电脑

******

# 进程管理(重点)

## 基本介绍

1. 在LINUX中，每个<font color = red>执行的程序</font>都称为一个进程。每一个进程都分配一个ID号(pid,进程号)。程序是静态的，跑起来就变成了动态的进程。

2. 每个进程都可能以两种方式存在的。<font color = red>前台</font>与<font color = red>后台</font>，所谓前台进程就是用户目前的屏幕上可以进行操作的。后台进程则是实际在操作，但由于屏幕上无法看到的进程，通常使用后台方式执行。

3. 一般系统的服务都是以后台进程的方式存在，而且都会常驻在系统中。直到关机才才结束。

## 显示系统执行的进程

### 显示执行的进程基本介绍

- `ps [选项]`命令是用来查看目前系统中，有哪些正在执行，以及它们执行的状况。可以不加任何参数.
    `-a`:显示当前终端的所有进程信息
    `-u`:以用户的格式显示进程信息
    `-x`:显示后台进程运行的参数
    一般连在一起用：`ps -aux`
    指令:`ps -aux | grep xxx `, 比如我看看有没有sshd服务

### ps显示的信息选项:
- 
    System V展示风格
    USER: 进程执行用户名称
    PID: 进程号
    %CPU: 进程占用CPU的百分比
    %MEM: 进程占物理内存的百分比
    VSZ: 占用的虚拟内存大小(单位:KB )
    RSS: 占用的物理内存大小(单位:KB)
    TTY: 终端信息, （TT是缩写）
    STAT: 运行状态，其中`S`-睡眠，`s`-表示该进程是会话的先导进程，`N`-表示进程拥有比普通优先级更低的优先级，`R`-正在运行，`D`-短期等待，`Z`-僵死进程，`T`-被跟踪或者被停止等等
    STARTED: 进程的启动时间
    TIME: CPU时间，即进程使用CPU的总时间
    COMMAND: 启动进程所用的命令和参数，如果过长会被截断显示

### ps应用实例

- 要求:以全格式显示当前所有的进程,查看进程的父进程。`ps -ef`是以全格式显示当前所有的进程, `-e`显示所有进程, `-f`全格式
    `ps -ef | grep XXX`

- 细节
    是BSD风格
    UID: 用户ID
    PID: 进程ID
    PPID: 父进程ID
    C: CPU用于计算执行优先级的因子。数值越大，表明进程是CPU密集型运算，执行优先级会降低; 数值越小，表明进程是I/O密集型运算，执行优先级会提高
    STIME: 进程启动的时间
    TTY: 完整的终端名称
    TIME: CPU时间
    CMD: 启动进程所用的命令和参数

- 查询`sshd`的父进程
    输入`ps -ef | grep sshd `
    得到：`root  7690 1 0 10:02 ? 00:00:00 /usr/sbin/sshd -D` 发现父进程PID为1号
    输入`ps -aux | more `
    得到：`root 1 0.1 0.3 128424 7052 ? Ss 10:01 0:05 /usr/lib/svstemd/svstemd --switched-root --system --deserialize 22`
    这个1号进程就是System系统进程

## 终止进程kill和killall

- 介绍: 若是某个进程执行一半需要停止时，或是已消了很大的系统资源时，此时可以考虑停止该进程。使用kill命令来完成此项任务。

### kill和killall基本语法
- `kill [选项] 进程号`(功能描述:通过进程号杀死进程)
    `killall 进程名称`（功能描述:通过进程名称杀死进程，也支持通配符，这在系统因负载过大而变得很慢时很有用)

- 常用选项
    -9:表示强迫进程立即停止

### kill和killall实践

1. 踢掉某个非法登录用户
    输入`ps -ef | grep sshd `，查询非法登录用户的相关pid为"n"
    `kill n`即可把非法用户踢掉

2. 终止远程登录服务sshd,在适当时候再次重启sshd服务
    输入`ps -ef | grep sshd `，查询sshd相关服务pid为"n"
    `kill n`即终止远程登录服务sshd
    使用以下命令重启sshd：
    `/bin/systemctl start sshd.service`

3. 终止多个gedit
    `killall gedit`

4. 强制杀掉一个终端
    输入`ps -ef | grep bash `，查询相关终端的PID为"n"
    `kill n`并不能杀掉终端，因为系统认为你可能是误操作
    使用`kill -9 n`强制杀掉终端

## 查看进程树pstree

- 基本语法
    `pstree [选项]`，可以更加直观的来看进程信息

- 常用选项
    `-p`: 显示进程的PID
    `-u`: 显示进程的所属用户

## 服务(service)管理

- 介绍:
    服务(service)本质就是进程，但是是运行在后台的，通常都会监听某个端口，等待其它程序的请求，比如(mysql , sshd 防火墙等)，因此我们又称为守护进程，是Linux中非常重要的知识点。

### service管理指令
1. service服务名[start | stop | restart | reload | status]
2. 在CentOS7.0后<font color = red>很多服务不再使用service</font>, 而是<font color = red>systemctl</font>(后面专门讲)
3. service指令管理的服务在/etc/init.d查看 `ls -l /etc/init.d/`

### service管理指令案例

- 请使用service 指令，查看，关闭，启动network [注意:在虚拟系统演示，因为网络连接会关闭]
    `service network status`查看 network
    `service network stop`关闭 network
    `service network start`启动 network

### 查看服务名:

- 方式1:使用setup ->系统服务就可以看到全部。`setup`

- 方式2:/etc/init.d看到service指令管理的服务``ls -l /etc/init.d``


### 服务的运行级别(runlevel):

- Linux系统有7种运行级别(runlevel):<font color = red>常用的是级别3和5</font>
    运行级别0∶系统停机状态，系统默认运行级别不能设为0，否则不能正常启动
    运行级别1∶单用户工作状态，root权限，用于系统维护，禁止远程登陆
    运行级别2∶多用户状态(没有NFS)，不支持网络
    运行级别<font color = red>3</font>∶完全的多用户状态(有NFS)，登陆后进入控制台命令行模式
    运行级别4∶系统未使用，保留
    运行级别<font color = red>5</font>:X11控制台，登陆后进入图形GUI模式
    运行级别6:系统正常关闭并重启，默认运行级别不能设为6，否则不能正常启动

- 开机的流程说明:
    开机->BIOS->/boot->systemd进程1->运行级别->运行级对应的服务

### chkconfig指令

- 介绍
    1. 通过chkconfig命令可以给服务的各个运行级别设置自启动/关闭
    2. chkconfig指令管理的服务在/etc/init.d查看
    3. 注意:Centos7.0后，很多服务使用<font color = red>systemctl</font>管理(后面马上讲) 

- chkconfig基本语法
    查看服务` chkconfig --list [| grep xxx]`
    `chkconfig 服务名 --list`
    设定某服务在某运行级别的开关`chkconfig --level 5 服务名 on/off`

- 案例演示:对network服务进行各种操作,把network在3运行级别,关闭自启动
    `chkconfig --level 3 network off`

- 使用细节:
    `chkconfig`重新设置服务后自启动或关闭，需要重启机器`reboot`生效.

### systemctl管理指令

- 基本语法:`systemctl [start | stop | restart | status] 服务名`

- systemctl指令管理的服务在/usr/lib/systemd/system查看: 
    `ls -l /usr/lib/systemd/system`

- systemctl设置服务的自启动状态
    1.` systemctl list-unit-files [| grep 服务名]`(查看服务开机启动状态, grep可以进行过滤)
    2. `systemctl enable 服务名`(设置服务开机启动)（默认同时在3，5级别起效）
    3. `systemctl disable 服务名`(关闭服务开机启动)（默认同时在3，5级别起效）
    4. `systemctl is-enabled 服务名`(查询某个服务是否是自启动的)

- 应用案例:
    查看当前防火墙的状况，关闭防火墙和重启防火墙。
    1. 查`ls -l /usr/lib/systemd/system | grep fire`查到防火墙相关服务叫：firewalled.service
    2. ` systemctl list-unit-files [| grep firewalled.service]` 或`systemctl status firewalled`得到目前防火墙状态
    3. `systemctl stop firewalled`关闭防火墙
    4. `systemctl start firewalled`开启防火墙

- 细节讨论:
    1.关闭或者启用防火墙后，立即生效。[telnet测试某个端口即可]`telnet 地址 端口`
    2.这种方式只是临时生效，当重启系统后，还是回归以前对服务的设置。
    3.如果希望设置某个服务自启动或关闭永久生效，要使用systemctl [enable|disable]服务名.

### 打开或者关闭指定端口

- 在真正的生产环境，往往需要将防火墙打开，但问题来了，如果我们把防火墙打开，那么外部请求数据包就不能跟服务器监听端口通讯。这时，需要打开指定的端口。比如80、22、8080等

- firewall指令(Ubuntu用的是ufw)
    打开端口:`firewall-cmd --permanent --add-port=端口号/协议`
    关闭端口:`firewall-cmd --permanent --remove-port=端口号/协议`
    重新载入,才能生效:`firewalli-cmd --reload`
    查询端口是否开放: `firewall-cmd --query-port=端口/协议`
    注意：`端口/协议`都要写。例子：`22/tcp`

## 动态监控系统

### top命令介绍:

- top与ps命令很相似。它们都用来显示正在执行的进程。Top与ps最大的不同之处，在于top在执行一段时间可以更新正在运行的的进程。

- 基本语法
   ` top [选项]`
    选项说明:
    |选项|功能|
    |-|-|
    | `-d 秒数` | 指定top命令每隔几秒更新。默认是3秒 |
    | `-i` | 使top不显示任何闲置或者僵死进程。 |
    | `-p` | 通过指定监控进程ID来仅仅监控某个进程的状态。 |

### top命令界面解读：
- 
    ``` 
    top - 23:55:37 up 8:20，2 users, load average: 0.01，0.00，0.00
    Tasks: 263 total, 1 running，262 sleeping, 0 stopped, 0 zombie
    %Cpu(s):0.0 us,0.0 sy,0.0 ni,99.9 id,0.0 wa，0.0 hi,0.0 si,0.0 st
    MiB Mem : 15913.6 total，13465.3 free, 916.3 used,1532.0 buff/cache
    MiB Swap:2048.0 total, 2048.0 free, 0.0 used.14542.4 avail Mem
    ```
23:55:37 -> 系统时间
8:20 -> 系统运行时间
2 users -> 使用系统的用户数
load average -> 系统平均负载，三个数平均值在70%以下较好
Tasks -> 任务
%Cpu(s)->cup占比，us用户，sy系统，id空闲
MiB Mem -> 内存占用情况
MiB Swap -> 交换区占用情况
avail Mem -> 可获取的内存

### 交互操作说明
- 
    | 操作 | 功能 |
    | - | - |
    |  P | 以CPU使用率排序，默认就是此项  |
    |  M |  以内存的使用率排序 |
    | N  | 以PID排序 |
    | q  | 退出top  |

### 应用实例

1. 监视特定用户
    `top`: 输入此命令，按回车键，查看执行的进程。
    `u`∶ 然后输入“u”回车，再输入用户名，即可

2. 终止指定的进程。
    `top`: 输入此命令，按回车键，查看执行的进程。
    `k`: 然后输入“k”回车，再输入要结束的进程ID号

3. 指定系统状态更新的时间(每隔10秒自动更新)∶
    `top -d 10`

## 监控网络状态

### 查看系统网络情况netstat

- 基本语法
    `netstat [选项]`
    选项说明
    `-an` 按一定顺序排列输出
    `-p` 显示哪个进程在调用应用案例

### 检测主机连接命令ping :

- 是一种网络检测检测工具，它主要是用检测远程主机是否正常，或是两部主机间的网线或网卡故障。如: ping对方ip地址

******

# RPM与YUM

## RPM包的管理

### RPM简介
- rpm用于互联网下载包的打包及安装工具，它包含在某些Linux分发版中。它生成具有.RPM扩展名的文件。RPM是RedHat Package Manager (RedHat软件包管理工具）的缩写，类似windows的setup.exe，这一文件格式名称虽然打上了RedHat的标志，但理念是通用的。Linux的分发版本都有采用(suse,redhat, centos等等），可以算是公认的行业标准了。

### RPM简单查询指令

- rpm包的简单查询指令
    查询已安装的rpm列表 `rpm -qa | grep xx`
    举例:看看当前系统，是否安装了firefoxrpm包名基本格式
    `rpm -qa | grep firefox`

- 一个rpm包名:firefox-60.2.2-1.el7.centos.x86_64
    名称:firefox
    版本号:60.2.2-1
    适用操作系统: el7.centos.x86_64表示centos7.x的64位系统
    如果是i686、i386表示32位系统，noarch表示通用。

### RPM其它查询指令

- `rpm -qa `:查询所安装的所有rpm软件包
    1. `rpm -qa | more`
    2. `rpm -qa | grep`
- `rpm -q 软件包名`: 查询软件包是否安装
- `rpm -qi 软件包名`: 查询软件包信息
- `rpm -ql 软件包名`: 查询软件包中的文件
- `rpm -qf 文件全路径名`: 查询文件所属的软件包
    案例：
    1. `rpm -qf /etc/passwd`
    2. `rpm -qf /root/install.log`

### 卸载RPM包

- 基本语法
    `rpm -e RPM包的名称`//erase
    案例: 删除firefox软件包 `rpm -e firefox`

- 细节讨论
    1. 如果其它软件包依赖于您要卸载的软件包，卸载时则会产生错误信息。如: `rpm -e foo`
    `removing these packages would break dependencies:foo is needed by bar-1.0-1`
    2. 如果我们就是要删除foo这个rpm包，可以增加参数`--nodeps` ,就可以强制删除，但是一般不推荐这样做，因为依赖于该软件包的程序可能无法运行。如: `rpm -e --nodeps foo`

### 安装rpm包

- 基本语法
    `rpm -ivh RPM包全路径名称`

- 参数说明
    `i`=install安装
    `v`=verbose提示
    `h`=hash进度条

## yum

### 介绍yum

- Yum是一个Shell前端软件包管理器。基于RPM包管理，能够从指定的服务器自动下载RPM包并且安装，可以自动处理依赖性关系，并且一次安装所有依赖的软件包。

### yum的基本指令
- 查询yum服务器是否有需要安装的软件`yum list | grep xx软件列表`

- 安装指定的yum包 `yum install xxx`

### yum应用实例

- 案例:请使用yum的方式来安装firefox
    `rpm -e firefox`
    `yum list | grep firefox`
    `yum install firefox`

******

# JAVA定制篇-搭建JavaEE环境

## 概述

- 如果需要奋Linux下进行JavaEE的开发，我们需要安装如下软件
    | 名称|
    |-|
    | ideal |
    | tomcat |
    | mysql |
    | jdk|
## 安装JDK

- 安装步骤
    1. `mkdir /opt/jdk`
    2. 通过xftp6上传到/opt/jdk 下
    3. `cd /opt/jdk`
    4. 解压`tar -zxvf jdk-8u261-linux-x64.tar.gz`
    5. `mkdir /usr/local/java`
    6. `mv /opt/jdk/jdki.8.0_261 /usr/local/java`
    7. 配置环境变量的配置文件`vim /etc/profile`
    8. `export JAVA_HOME=/usr/local/java/jdk1.8.0_261`
    9. `export PATH =$JAVA_HOME/bin:$PATH`
    10. `source /etc/profile`[让文件生效]s

- 测试是否安装成功
    编写一个简单的Hello.java输出"hello,world!"

## tomcat的安装

- 步骤:

    1. 上传安装文件，并解压缩到/opt/tomcat

    2. 进入解压目录/bin，启动tomcat `./startup.sh`

    3. 开放端口8080

- 测试是否安装成功:
    在windows、Linux下访问 `http://linuxip:8080`

## idea的安装

- 步骤:

    1. 上传安装文件，并解压缩到/opt/idea

    2. 进入解压目录/bin，启动IDEA `./idea.sh`

## mySQL的安装

- 网上找教程，直接apt装也可以

- 安装完成后用`sudo systemctl start mysql.service`（ubuntu）`systemctl start mysqld.service`（centos）来启动mysql

- 然后开始设置root用户密码
    Mysql自动给root用户设置随机密码，运行`grep "password" /var/log/mysqld.log`可看到当前密码(centos). Ubuntu 用`sudo mysql_secure_installation`

******

# 大数据定制篇-Shell编程

## 为什么要学习Shell编程

1. Linux运维工程师在进行服务器集群管理时，需要编写Shell程序来进行服务器管理。

2. 对于JavaEE和Python程序员来说，工作的需要，你的老大会要求你编写一些Shell脚本进行程序或者是服务器的维护，比如编写一个定时备份数据库的脚本

3. 对于大数据程序员来说，需要编写Shell程序来管理集群。

## Shell是什么

- Shell是一个命令行解释器，它为用户提供了一个向Linux内核发送请求以便运行程序的界面系统级程序，用户可以用Shell来启动、挂起、停止甚至是编写一些程序。

## Shell脚本的执行方式

### 脚本格式要求

1. 脚本以#!/bin/bash开头

2. 脚本需要有可执行权限

### 编写第一个Shell脚本

- 需求说明:创建一个shell脚本，输出hello world!

- 操作：
    `vim hello.sh`
    ```Shell
    #!/bin/bash
    echo "HelloWorld!"
    ```
    保存退出，运行：`./hello.sh`

### 脚本的常用执行方式
- 方式1(输入脚本的绝对路径或相对路径)
    说明:首先要赋予helloworld.sh脚本的+x权限,再执行脚本方式
        `./hello.sh`

- 方式2(sh+脚本)
    说明:不用赋予脚本+x权限，直接执行即可。
        `sh hello.sh`(注，sh用的是dash而不是bash，会有一定区别)

## Shell的变量

### Shell变量介绍

1. Linux Shell中的变量分为,系统变量和用户自定义变量

2. 系统变量:`$HOME`、`$PWD`、`$SHELL`、`$USER`等等，比如:`echo $HOME` 等等..

3. 显示当前shell中所有变量:set

### shell变量的定义

- 基本语法
    1. 定义变量:变量名=值(==不要打空格==)
    2. 撤销变量:`unset 变量`
    3. 声明静态变量:`readonly 变量`，注意:不能unset

### shell变量快速入门

- 案例1:定义变量A    
- 案例2∶撤销变量A    
- 案例3:声明静态的变量B=2，不能unset
    ```Shell
    #!/bin/bash
    #案例1:定义变量A
    A=100
    #输出变量需要加上$
    echo A=$A    #A=100
    echo "A=$A"    #A=100
    #案例2:撤销变量A
    unset A
    echo "A=$A"    #A=
    #案例3:声明静态的变量B=2，不能unset
    readonly B=2
    echo "B=$B"    #B=2
    unset B  #./var.sh:第13行:unset: B:无法反设定:只读variable
    ```

### shell变量的规则

1. 变量名称可以由字母、数字和下划线组成，但是不能以数字开头。5A=200(×)

2. 等号两侧不能有空格

3. 变量名称一般习惯为大写,这是一个规范，我们遵守即可

### 将命令的返回值赋给变量

1. A= \`date\` 反引号（`~`那个键），运行里面的命令，并把结果返回给变量A

2. A=`$(date)`等价于反引号 `$()`
    ```Shell
    A=`date`
    echo "A=$A"  #会显示当前时间
    ```

## 设置环境变量

- 基本语法

    1. `export 变量名=变量值`（功能描述:将shell变量输出为环境变量)

    2. `source 配置文件`(功能描述:让修改后的配置信息立即生效)

    3. `echo $变量名`(功能描述:查询环境变量的值)

- 快速入门

    1. 在/etc/profile文件中定义TOMCAT_HOME环境变量

    2. 查看环境变量TOMCAT_HOME的值

    3. 在另外一个shell程序中使用TOMCAT_HOME
    注意:在输出TOMCAT_HOME 环境变量前,需要让其生效`source /etc/profile`

    4. 生效后再其他shell程序中可以用`$TOMCAT_HOME`来使用环境变量

## Shell的注释

- 单行：`#`

- 多行：
    ```Shell
    :<<! 
    ...
    ...
    ...
    !
    ```

## 位置参数变量

### 位置参数介绍

- 当我们执行一个shell脚本时，如果希望获取到命令行的参数信息，就可以使用到位置参数变量

- 比如:`./myshell.sh 100 200`，这个就是一个执行shell的命令行，可以在myshell 脚本中获取到参数信息

### 位置参数基本语法

- `$n` (功能描述:n为数字，`$0`代表命令本身，`$1`-`$9`代表第一到第九个参数，十以上的参数，十以上的参数需要用大括号包含，如`${10}`)

- `$*`（功能描述:这个变量代表命令行中所有的参数，`$*`把所有的参数看成一个整体)

- `$@`（功能描述:这个变量也代表命令行中所有的参数，不过`$@`把每个参数区分对待)

- `$#`(功能描述:这个变量代表命令行中所有参数的个数)

### 位置参数案例

-   ```Shell
    #!/bin/bash
    echo "0=$0 1=$1 2=$2"
    echo "所有的参数=$*"
    echo "$@"
    echo “参数的个数=$#"
    ```

- 执行`./myshell.sh 100 200`：
    ```
    0=./myshell.sh 1=100 2=200
    所有的参数=100 200
    100 200
    参数的个数=2
    ```

## 预定义变量

- 基本介绍
    就是shell设计者事先已经定义好的变量，可以直接在shell脚本中使用

### 预定义变量基本语法

- `$$`(功能描述:当前进程的进程号(PID))

- `$!`(功能描述:后台运行的最后一个进程的进程号(PID))

- `$?`(功能描述:最后一次执行的命令的返回状态。如果这个变量的值为0，证明上一个命令正确执行;如果这个变量的值为非0(具体是哪个数，由命令自己来决定)，则证明上一个命令执行不正确了。)

### 预定义变量实例

- 在一个shell脚本中简单使用一下预定义变量
    ```Shell
    #!/bin/ bash
    echo "当前执行的进程id=$$"
    #以后台的方式运行一个脚本，并获取他的进程号
    /root/shcode/myshell.sh & #后台的方式运行用&号
    echo "最后一个后台方式运行的进程id=$!"
    echo "执行的结果是=$?"
    ```

## 运算符

### shell运算符基本语法

1. “`$((运算式))`”或“`$[运算式]`”或者`expr m + n`//expression表达式

2. 注意expr运算符间要有空格,如果希望将expr的结果赋给某个变量,使用: \`\`反引号

3. `expr m - n`

4. `expr` `\*`.`/`.`%` 乘，除，取余

### 运算符应用实例

- 案例1:计算(2+3)X4的值

- 案例2∶请求出命令行的两个参数[整数]的和

-   ```Shell
    #!/bin/bash
    #案例1:计算(2+3)X4的值
    #使用第一种方式
    RES1=$(((2+3)*4))
    echo "res1=$RES1"
    #使用第二种方式，推荐使用
    RES2=$[(2+3)*4] # 用sh，即用dash这里是错的
    echo " res2=$RES2"
    #使用第三种方式expr
    TEMP=`expr 2 + 3`         #注意运算符旁有空格
    RES4=`expr $TEMP \* 4`#    注意乘号旁有转义符
    echo "res4=$RES4"
    #案例2:请求出命令行的两个参数[整数]的和20 50
    SUM=$[$1+$2]
    echo "sum=$SUM"
    ```

## 条件判断

### 判断语句基本语法
- `[ condition ]`(注意condition前后要有空格)
    空返回true，可使用`$?`验证(0为true,>1为false )

- 应用实例
    `[ hspEdu ]`    返回true
    `[ ] `          返回false(==中间要有空格，不然不合语法==)
    `[ condition ] && echo OK || echo notok`    条件满足，执行后面的语句

### 常用判断条件

#### 字符串比较

- `=`字符串比较

#### 两个整数的比较
- 
    `-lt`小于
    `-le`小于等于
    `-eq`等于
    `-gt`大于
    `-ge`大于等于
    `-ne`不等于

#### 按照文件权限进行判断
- 
    `-r`有读的权限
    `-W`有写的权限
    `-x`有执行的权限

#### 按照文件类型进行判断
- 
    `-f` 文件存在并且是一个常规的文件
    `-e` 文件存在
    `-d` 文件存在并是一个目录

### 应用实例
- 
    案例1: "ok"是否等于"ok"
    判断语句: 使用 `=`
    案例2:23是否大于等于22
    判断语句: 使用 `-ge`
    案例3 :/root/shcode/aaa.txt目录中的文
    件是否存在
    判断语句: 使用 `-f`

-   ```Shell
    #!/bin/bash
    #案例1:"ok"是否等于"ok"#判断语句:使用=
    if [ "ok" = "ok" ]
    then
        echo " equal"
    fi
    #案例2:23是否大于等于22#判断语句:使用-ge
    if [ 23 -ge 22 ]
    then
        echo "大于"
    fi
    #案例3:/root/shcode/aaa.txt目录中的文件是否存在
    #判断语句:使用-f
    if [ -f /root/shcode/aaa.txt ]
    then
        echo "存在"
    fi
    ```

## 流程控制

### if 判断

- 基本语法
    ```Shell
    if [ 条件判断式 ]
    then
    代码
    fi
    ```
    或者，多分支
    ```Shell
    if [ 条件判断式 ]
    then
    代码
    elif [ 条件判断式 ]
    then
    代码
    fi
    ```

- 注意事项:` [ 条件判断式 ] `，中括号和条件判断式之间必须有空格，中括号前后也应该有空格。

### case 语句

- 基本语法
    ```Shell
    case $变量名 in
    "值1")
    如果变量的值等于值1，则执行程序1
    ;;
    "值2")
    如果变量的值等于值2，则执行程序2
    ;;
    …省略其他分支.….
    *)
    如果变量的值都不是以上的值，则执行此程序
    ;;
    esac
    ```

- 案例：当命令行参数是1时，输出"周一"，是2时，就输出"周二"，其它情况输出"other"
    ```Shell
    case $变量名 in
    "值1")
    如果变量的值等于值1，则执行程序1
    ;;
    "值2")
    如果变量的值等于值2，则执行程序2
    ;;
    …省略其他分支.….
    *)
    如果变量的值都不是以上的值，则执行此程序
    ;;
    esac
    ```

### for循环

- 基本语法1
    ```Shell
    for 变量 in 值1 值2 值3…
    do
    程序
    done
    ```
    应用实例1:打印命令行输入的参数[这里可以看出`$*`和`$@`的区别]
    ```Shell
    #!/bin/bash
    #注意$*是把输入的参数，当做一个整体，所以，只会输出一句
    for i in "$*"
    do
        echo " num is $i"    
    done
    #使用$@来获取输入的参数，注意，这时是分别对待，所以有几个参数，就输出几句
    echo "=========================="
    for j in "$@"
    do
        echo " num is $j"   
    done
    ```
    结果：
    ```Shell
    num is 100 200 300
    ==========================
    num is 100
    num is 200
    num is 300
    ```

- 基本语法2
    ```Shell
    for ((初始值;循环控制条件;变量变化))
    do
    程序
    done
    ```
    应用实例2:从1加到100的值输出显示
    ```Shell
    #!/bin/bash
    SUM=0
    for (( i=1; i<=100; i++)) #()是数学运算式，所以可以用<>=号
    do
    #写上你的业务代码
        SUM=$[$SUM+$i]
    done
    echo "SUM=$SUM"
    ```

### while循环

- 基本语法
    ```Shell
    while [ 条件判断式 ]
    do
    程序
    done
    ```
    注意:while和`[`有空格，条件判断式和`[`也有空格
    案例1 :从命令行输入一个数n，统计从1+..+n的值是多少?
    ```Shell
    #!/bin/bash
    SUM=0
    i=0
    while [ $i -le $1 ]
    do
        SUM=$[$SUM+$i]
        #i自增
        i=$[$i+1]
    done
    echo “执行结果=$SUM"
    ```

## read读取控制台输入

- 基本语法
    `read (选项) (参数)`

- 选项:
    `-p`:指定读取值时的提示符;
    `-t`:指定读取值时等待的时间(秒)，如果没有在指定的时间内输入，就不再等待了。

- 参数
    变量:指定读取值的变量名

- 应用实例
    ```Shell
    #!/bin/bash
    #案例1:读取控制台输入一个NUM1值
    read -p "请输入一个数NUM1=" NUM1
    echo "你输入的NUM1=$NUM1"
    #案例2:读取控制台输入一个NUM2值，在10秒内输入。
    read -t 10 -p "请输入一个数NUM2" NUM2
    echo "你输入的NUM2=$NUM2"
    ```
    结果：
    ```Shell
    请输入一个数NUM1=20
    你输入的NUM1=20
    请输入一个数NUM255
    你输入的NUM2=55 #10秒内不输入，因为没回车，就只在上一排有：你输入的NUM2=
    ```

## 函数

- 函数介绍
    shell编程和其它编程语言一样，有系统函数，也可以自定义函数。系统函数中，我们这里就介绍两个。

### 系统函数

#### basename

- 基本语法
    功能:返回完整路径最后`/`的部分，常用于获取文件名
    `basename [pathname] [suffix]`
    `basename [string] [suffix]`(功能描述:basename命令会删掉所有的前缀包括最后一个(`/`)字符，然后将字符串显示出来。
    选项:
    suffix为后缀，如果suffix被指定了，basename会将pathname或string中的suffix去掉。

- 应用实例
    案例1∶请返回/home/aaa/test.txt的"test.txt"部分
    ```Shell
    basename /home/aaa/test.txt
    basename /home/aaa/test.txt .txt
    ```
    返回
    ```Shell
    test.txt
    test
    ```

#### dirname

- 功能:返回完整路径最后`/`的前面的部分，常用于返回路径部分
    `dirname 文件绝对路径`（功能描述:从给定的包含绝对路径的文件名中去除文件名(非目录的部分），然后返回剩下的路径(目录的部分）)

- 应用实例
    案例1:请返回/home/aaa/test.txt的/home/aaa
    ```Shell
    dirname /home/aaa/test.txt
    ```
    返回
    ```Shell
    /home/aaa
    ```

### 自定义函数

- 基本语法
    ```Shell
    [ function ] funname[()]
    {
        Action;
        [return int;]
    }
    or
    funname() {
        action;
        #echo "输出";
        [return int;]
    }
    ```

    调用直接写函数名: `funname [值]`

- 应用实例
    案例1:计算输入两个参数的和，getSum
    ```Shell
    # !/bin/bash
    #案例1:计算输入两个参数的和(动态的获取)，getSum
    #定义函数getSum
    function getSum() {
        SUM=$[$n1+$n2]
        echo "和是=$SUM"
    }

    #输入两个值
    read -p "请输入一个数n1=" n1
    read -p "请输入一个数n2=" n2
    #调用自定义函数
    getSum $n1 $n2
    ```

- 运用了return的shell函数可以用`$?`来获取它的返回值

- 在Shell中，调用函数时可以向其传递参数。在函数体内部，通过 `$n` 的形式来获取参数的值，例如，`$1`表示第一个参数，`$2`表示第二个参数...以此类推

## Shell编程综合案例

- 需求分析

    1. 每天凌晨2:30备份数据库hspEduDB到 /data/backup/db

    2. 备份开始和备份结束能够给出相应的提示信息

    3. 备份后的文件要求以备份时间为文件名，并打包成.tar.gz的形式，比如2021-03-12_230201.tar.gz

    4. 在备份的同时，检查是否有10天前备份的数据库文件，如果有就将其删除。

- 思路：
    1. 用crond定时在凌晨2:30调用备份的shell script

    2. shell script要能备份同时检查10天前备份的数据库文件

- 写：放在 `use/sbin` 下，因为这目录下是root的权限
    ```Shell
    #备份目录
    BACKUP=/data/backup/db 
    #当前时间
    DATETIME=$(date +%Y-%m-%d_%H%M%S)
    echo $DATETIME
    #数据库的地址
    HOST=localhost
    #数据库用户名
    DB_USER=root
    #数据库密码
    DB_PW=hspedu100
    #备份的数据库名
    DATABASE=hspedu
    #创建备份目录，如果不存在，就创建
    [ ! -d "${BACKUP}/${DATETIME}" ] && mkdir -p "${BACKUP}/${DATETIME}"
    #备份数据库
    mysqldump -u${DB_USER} -p${DB_PW} --host=${HOST} -q -R --databases ${DATABASE} | gzip > ${BACKUP}/${DATETIME}/$DATETIME.sql.gz
    #将文件处理成tar.gz
    cd ${BACKUP}
    tar -zcvf $DATETIME.tar.gz ${DATETIME}
    #删除对应的备份目录
    rm -rf ${BACKUP}/${DATETIME}
    #删除10天前的备份文件
    find ${BACKUP} -atime +10 -name "*.tar.gz" -exec rm -rf {} \;
    echo "备份数据库${DATABASE}成功-"
    ````
    使用 ` crontab -e `自动执行：`30 2 * * * /usr/sbin/mysql_db_backup.sh`
    注：上一段话记得在输完`...backup.sh`后把光标从sh后面移动到前面有字符的地方再按<kbd>Esc</kbd>退出编辑模式，不然会一直重复输入上一句话。

******

# Python定制篇-Python开发平台Ubuntu

- Ubuntu（友帮拓、优般图、乌班图)是一个以==桌面==应用为主的开源GNU/Linux操作系统，Ubuntu是基于GNU/Linux，支持x86、amd64 (即x64）和==ppc==架构，由全球化的专业开发团队（Canonical Ltd)打造的。

- 专业的Python开发者一般会选择Ubuntu这款Linux系统作为生产平台.温馨提示:Ubuntu 和Centos都是基于GNU/Linux内核的，因此基本使用和Centos是几乎一样的,它们的各种指令可以通用，同学们在学习和使用Ubuntu的过程中，会发现各种操作指令在前面学习CentOS都使用过。只是界面和预安装的软件有所差别

## 安装

- 直接装

## Ubuntu的root 用户

- 安装ubuhtu成功后，都是普通用户权限，并没有最高root权限，如果需要使用root权限的时候，通常都会在命令前面加上sudo。有的时候感觉很麻烦。(演示)

- 我们一般使用su命令来直接切换到root用户的，但是如果没有给root设置初始密码，就会抛出su :Authentication failure这样的问题。所以，我们只要给root用户设置一个初始密码就好了。

### 给root用户设置密码并使用
1. 输入sudo passwd命令，输入一般用户密码并设定root用户密码。
2. 设定root密码成功后，输入su命令，并输入刚才设定的root密码，就可以切换成root了。提示符$代表一般用户，提示符#代表root用户。
3. 以后就可以使用root用户了
4. 输入exit命令，退出root并返回一般用户

## Ubuntu下开发Python
- 说明
    安装好Ubuntu后，默认就已经安装好Python的开发环境。

- 在Ubuntu下开发一个Python程序
    1) `vi hello.py` 编写 `hello.py`
    2) `python3 hello.py` 运行 `hello.py`

******

# Python定制篇-APT软件管理和远程登录

## APT软件管理

### apt介绍

- apt是Advanced Packaging Tool的简称，是一款安装包管理工具。在Ubuntu下，我们可以使用apt命令进行软件包的安装、删除、清理等，类似于Windows中的软件管理工具。

- apt用的是美国服务器，国内有镜像站，我们要重定位过去下载更快

### Ubuntu软件操作的相关命令
- 
    ```
    sudo apt-get update 更新源<----
    sudo apt-get install package 安装包<----
    sudo apt-get remove package 删除包<----
    sudo apt-cache search package 搜索软件包
    sudo apt-cache show package 获取包的相关信息，如说明、大小、版本等<----
    sudo apt-get install package --reinstall 重新安装包
    sudo apt-get -f install 修复安装
    sudo apt-get remove package --purge 删除包，包括配置文件等
    sudo apt-get build-dep package 安装相关的编译环境
    sudo apt-get upgrade 更新已安装的包
    sudo apt-get dist-upgrade 升级系统
    sudo apt-cache depends package 了解使用该包依赖那些包
    sudo apt-cache rdepends package 查看该包被哪些包依赖
    sudo apt-get source package 下载该包的源代码<----
    ```

### 更新Ubuntu软件下载地址

- 寻找国内镜像源
    https://mirrors.tuna.tsinghua.edu.cn/ 所谓的镜像源:可以理解为提供下载软件的地方，比如Android手机上可以下载软件的安卓市场;iOS手机上可以下载软件的AppStore

- 备份Ubuntu默认的源地址
    `sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup`

- 更新源服务器列表
    先清空sources.list 文件复制镜像网站的地址
    `su`
    `echo '' >sources.list`

- 复制镜像网站的地址，拷贝到sources.list文件
    复制粘贴

- 更新源
    更新源地址: sudo apt-get update

### Ubuntu软件安装,卸载的最佳实践

- 案例说明:使用apt完成安装和卸载vim软件，并查询vim 软件的信息:(因为使用了镜像网站，速度很快)
    `sudo apt-get remove vim//卸载`
    `sudo apt-get install vim//安装`
    `sudo apt-cache show vim//查询软件的信息`

## 远程登录Ubuntu

### ssh介绍

- SSH为Secure Shell的缩写，由IETF的网络工作小组(Network Working Group)所制定;SSH为建立在应用层和传输层基础上的安全协议。

- SSH是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。常用于远程登录。几乎所有UNIX/LInux平台都可运行SSH。

- 使用SSH服务，需要安装相应的服务器和客户端。客户端和服务器的关系:如果，A机器想被B机器远程控制，那么，A机器需要安装SSH服务器，B机器需要安装SSH客户端。

- 和CentOS不一样，Ubuntu默认没有安装SSHD服务(使用netstat 指令查看 `netstat -anp | more`: `sudo apt install net-tools`)，因此，我们不能进行远程登录。

### 安装SSH和启用

`sudo apt-get install openssh-server`
- 执行上面指令后，在当前这台Linux上就安装了SSH服务端和客户端。

`service sshd restart`
- 执行上面的指令，就启动了sshd服务。会监听端口22

### 在Windows使用XShell6/XFTP6登录Ubuntu

- 前面我们已经安装了XShell6，直接使用即可。

- 注意:使用hspEdu 用户登录，需要的时候再su-切换成root用户

### 从一台linux系统远程登陆另外一台linux系统

- 在创建服务器集群时，会使用到该技术

- 基本语法:
    `ssh 用户名@IP`
    例如:`ssh hspedu@192.168.200.222`

- 使用ssh访问，如访问出现错误。可查看是否有该文件 `~/.ssh/known_ssh`尝试删除该文件解决，一般不会有问题登出

- 登出
    命令:`exit`或者`logout`

******

# CentOS8.1的使用

- 下载，安装

******

# 日志管理

## 日志介绍和实例

### 日志基本介绍

1. 日志文件是重要的系统信息文件，其中记录了许多重要的系统事件，包括用户的登录信息、系统的启动信息、系统的安全信息、邮件相关信息、各种服务相关信息等。

2. 日志对于安全来说也很重要，它记录了系统每天发生的各种事情，通过日志来检查错误发生的原因, 或者受到攻击时攻击者留下的痕迹。

3. 可以这样理解日志是用来记录重大事件的工具

### 系统常用的日志

- /var/log/目录就是系统日志文件的保存位置
    |  日志文件  |  说明  |
    |-|-|
    |  <font color = red>/var/log/boot.log  |  系统启动日志  |
    |  <font color = red>/var/log/cron  |  记录与系统定时任务相关的曰志  |
    |  /var/log/cups/  |   记录打印信息的曰志 |
    |  /var/log/dmesg  |  记录了系统在开机时内核自检的信总。也可以使用dmesg命令直接查看内核自检信息 |
    | /var/log/btmp   |  记录错误登陆的日志。这个文件是二进制文件，不能直接用Vi查看，而要使用lastb命令查看。  |
    |  <font color = red>/var/log/lastlog  |  记录系统中所有用户最后一次的登录时间的日志。这个文件也是二进制文件.要使用lastlog命令查看  |
    |  <font color = red>/var/log/mailog  |  记录邮件信息的曰志  |
    |  <font color = red>/var/log/message  |  记录系统重要消息的日志.这个日志文件中会记录Linux系统的绝大多数<br>重要信息。如果系统出现问题，首先要检查的应该就是这个日志文件  |
    |  <font color = red>/var/log/secure  |  记录验证和授权方面的倍息，只要涉及账户和密码的程序都会记录，比如系统<br>的登录、ssh的登录、su切换用户，sudo授权，<br>甚至添加用户和修改用户密码都会记录在这个<br>日志文件中 |
    |  /var/log/wtmp  |  永久记录所有用户的登陆、注销信息，同时记录系统的后动、重启、关机事件。是二进制文件.而要使用last命令查看  |
    |  <font color = red>/var/tun/ulmp  |  记录当前已经登录的用户的信息。这个文件会随着用户的登录和注销而不断变化，只记录当前登录用户的信息。这个文件不能用Vi查看，而要使用w、who、users等命令查看  |

### 应用案例

- 使用root用户通过xshell6登陆，第一次使用错误的密码，第二次使用正确的密码登录成功看看在日志文件/var/log/secure里有没有记录相关信息  yes

## 日志管理服务rsyslogd

- CentOS7.6日志服务是rsyslogd ,CentOS6.x日志服务是syslogd 。rsyslogd 功能更强大。rsyslogd的使用、日志文件的格式，和syslogd 服务兼容的。

## 日志服务配置文件

- 查询Linux 中的rsyslogd 服务是否启动
    `ps -aux | grep "rsyslog" | grep -v "grep"`

- 查询rsyslogd服务的自启动状态
    `systemctl list-unit-files | grep rsyslog`

- √配置文件:/etc/rsyslog.conf
    编辑文件时的格式为:`*.*  存放日志文件`
    其中第一个`*`代表日志类型，第二个`*`代表日志级别

1. 日志类型分为:
    | 类型 | 注释|
    |-|-|
    | auth    |            ##pam产生的日志|
    |authpriv  |  ##ssh、ftp等登录信息的验证信息|
    |corn|    ##时间任务相关|
    |kern|    ##内核|
    |lpr|    ##打印|
    |mail|    ##邮件|
    |mark(syslog)-rsyslog|    ##服务内部的信息，时间标识|
    |news|##新闻组|    
    |user|    ##用户程序产生的相关信息|
    |uucp|    ##unix to unix copy主机之间相关的通信|
    |local 1-7|    ##自定义的日志设备|

2. 日志级别分为:
    | 类型 | 注释|
    |-|-|
    |debug|##有调试信息的，日志通信最多|
    |info|##—般信息日志，最常用|
    |notice|##最具有重要性的普通条件的信息|
    |warning|##警告级别|
    |err|##错误级别，阻止某个功能或者模块不能正常工作的信息|
    |crit|##严重级别，阻止整个系统或者整个软件不能正常工作的信息|
    |alert|##需要立刻修改的信息|
    |emerg|##内核崩溃等重要信息|
    |none|##什么都不记录|
    注意:从上到下,级别从低到高，记录信息越来越少

- √由日志服务rsyslogd记录的日志文件，日志文件的格式包含以下4列:
    1. 事件产生的时间
    2. 产生事件的服务器的主机名
    3. 产生事件的服务名或程序名
    4. 事件的具体信息

- 日志如何查看实例
    查看一下/var/log/secure日志，这个日志中记录的是用户验证和授权方面的信息.来分析如何查看
    `Nov 12 12:18:26 hspEdu100 unix_chkpwd[10480]:password check failed for user (root)`

## 自定义日志服务

- 日志管理服务应用实例
    在/etc/rsyslog.conf中添加一个日志文件/var/log/hsp.log,当有事件发送时(比如sshd服务相关事件)，该文件会接收到信息并保存.给小伙伴演示重启，登录的情况，看看是否有日志保存
    `vim /etc/rsyslog.conf`
    ```Shell
    #l增加自定义的日志
    *.*    /var/log/hsp.log
    ```
    `> /var/log/hsp.log`
    `cat /var/log/hsp.log`
    重启
    `cat hsp.log | grep sshd`
    我们可以看到sshd的记录

## 日志轮替介绍

- 基本介绍

    日志轮替就是把旧的日志文件移动并改名，同时建立新的空日志文件，当旧日志文件超出保存的范围之后，就会进行删除

- 日志轮替文件命名
    1. centos7使用logrotate进行日志轮替管理，要想改变日志轮替文件名字，通过/etc/logrotate.conf配置文件中“dateext”参数:
    2. 如果配置文件中有“dateext”参数，那么日志会用<font color = red>日期</font>来作为日志文件的后缀，例如“secure-20201010”。这样日志文件名不会重叠，也就不需要日志文件的改名，只需要指定保存日志个数，删除多余的日志文件即可。
    3. 如果配置文件中没有“dateext”参数，日志文件就需要进行改名了。当第一次进行日志轮替时，<font color = red>当前的“secure”日志会自动改名为“secure.1”，然后新建“secure”日志，用来保存新的日志</font>。当第二次进行日志轮替时，“secure.1”会自动改名为“secure.2”，当前的“secure”日志会自动改名为“secure.1"，然后也会新建“secure”日志，用来保存新的日志，以此类推。

- logrotate配置文件
    letc/logrotate.conf 为logrotate的全局配置文件
    ```Shell
    # rotate log files weekly,每周对日志文件进行一次轮替
    weeklly
    # keep 4 weeks worth of backlogs,共保存4份日志文件，当建立新的日志文件时，旧的将会被删除
    rotate 4
    # create new (empty) log files after rotating old ones,创建新的空的日志文件，在日志轮替后
    create
    # use date as a suffix of the rotated file,使用日期作为日志轮替文件的后缀
    dateexct
    # uncomment this if you want your log files compressed,日志文件是否压缩。如果取消注释，则日志会在转储的同时进行压缩
    #compress
    # RPM packages drop log rotation information into this directory 
    include /etc/logrotate.d
    # 包含/etc/logrotate.d/目录中所有的子配置文件。也就,是说会把这个目录中所有子配置文件读取进来，
    #下面是单独设置，优先级更高。
    # no packages own wtmp and btmp -- we'll rotate them here
    /var/log/wtmp {
        monthly #每月对日志文件进行一次轮替
        create 0664 root utmp #建立的新日志文件，权限是0664，所有者是root，所属组是utmp组
        minsize 1M #日志文件最小轮替大小是1MB。也就是日志一定要超过1MB才会轮替，否则就算时间达到一个月，也不进行日志转储
        rotate 1 #仅保留一个日志备份。也就是只有wtmp和wtmp.1日志保留而已
    }
    /var/log/btmp {
        missingok #如果日志不存在，则忽略该日志的警告信息monthly
        create 0600 root utmp
        rotate 1
    }
    ```

- 说明:也可以把某个日志文件的轮替规则，写到/etc/logrotate.d目录,比如:
    logrotate.d里面有好多文件，其中一个：bootlog：
    ```Shell
    /var/log/boot.log
    {
        missingok
        daily
        copytruncate
        rotate 7
        notifempty
    }
    ```

## 自定义日志轮替

- logrotate配置文件
    |  参数|参数说明|
    |-|-|
    |daily|日志的轮替周期是每天|
    |weekly|日志的轮替周期是每周|
    |monthly|日志的轮替周期是每月|
    |rotate 数字|保留的日志文件的个数。0指没有备份|
    |compress|日志轮替时，旧的日志进行压缩|
    |create mode owner group |建立新日志，同时指定新日志的权限与所有者和所属组|
    |mail address|当日志轮替时，输出内容通过邮件发送到指定的邮件地址。|
    |missingok|如果日志不存在，则忽略该日志的警告信息|
    |notifempty|如果日志为空文件，则不进行日志轮替|
    |minsize 大小|日志轮替的最小值。也就是日志一定要达到这个最小值才会轮替，否则就算时间达到也不轮替|
    |size   大小|日志只有大于指定大小才进行日志轮替，而不是按照时间轮替。|
    |dateext|使用日期作为日志轮替文件的后缀。|
    |sharedscripts|在此关键字之后的脚本只执行一次。|
    |prerotate/endscript|在日志轮替之前执行脚本命令。|
    |postrotate/endscript|在日志轮替之后执行脚本命令。|

- 把自己的日志加入日志轮替

    - 第一种方法是直接在/etc/logrotate.conf配置文件中写入该日志的轮替策略

    - 第二种方法是在/etc/logrotate.d/目录中新建立该日志的轮替文件，在该轮替文件中写入正确的轮替策略，因为该目录中的文件都会被“include”到主配置文件中，所以也可以把日志加入轮替。
    
    - 推荐使用第二种方法，因为系统中需要轮替的日志非常多，如果全都直接写入/etc/logrotate.conf配置文件，那么这个文件的可管理性就会非常差，不利于此文件的维护。

    - 在/etc/logrotate.d/配置轮替文件一览

- 案例:在/etc/logrotate.conf进行配置,或者直接在/etc/logrotate.d/下创建文件 hsplog编写如下内容，具体轮替的效果可以参考/var/log下的boot.log情况.:
    ```Shell
    /var/log/hsp.log
    {
        missingok
        daily
        copytruncate
        rotate 7
        notifempty
    }
    ```

## 日志轮替机制

- 日志轮替机制原理
    日志轮替之所以可以在指定的时间备份日志，是依赖系统定时任务。在/etc/cron.daily/目录，就会发现这个目录中是有logrotate文件(可执行)，logrotate通过这个文件依赖定时任务执行的。

## 内存日志

- 查看内存日志
    journalctl 可以查看内存日志,这里我们看看常用的指令

    |  指令|参数说明|
    |-|-|
    |`journalctl`| ##查看全部|
    |`journalctl -n 3`| ##查看最新3条|
    |`journalctl --since 19:00 --until 19:10:10` |#查看起始时间到结束时间的日志可加日期|
    |`journalctl -p err `|##报错日志|
    |`journalctl -o verbose `|##日志详细内容|
    |`journalctl_PID=1245 _COMM=sshd`| ##查看包含这些参数的日志（在详细日志查看)或者journalctl [ grep sshd|
    注意: journalctl 查看的是==内存日志==,重启清空
    演示案例:
    使用journalctl | grep sshd来看看用户登录清空,==重启系统==，再次查询，看看日志有什么变化没有

******
# 定制自己的Linux

- 通过裁剪现有Linux系统(CentOS7.6)，创建属于自己的min Linux小系统，可以加深我们对linux的理解。老韩利用centos7.6，搭建一个小小linux系统很有趣。

## 基本原理

- 启动流程介绍:
    制作Linux小系统之前,再了解一下Linux的启动流程:
    1. 首先Linux要通过自检，检查硬件设备有没有故障
    2. 如果有多块启动盘的话，需要在BIOS中选择启动磁盘
    3. 启动MBR中的bootloader引导程序
    4. 加载内核文件
    5. 执行所有进程的父进程、老祖宗systemd
    6.欢迎界面

- 在Linux的启动流程中，加载内核文件时关键文件:
    1. kernel文件:vmlinuz-3.10.0-957.el7.x86_64
    2. initrd文件: initramfs-3.10.0-957.el7.x86_64.img

## 制作min linux思路分析

1. 在现有的Linux系统(centos7.6)上加一块硬盘/dev/sdb，在硬盘上分两个分区，一个是/boot ,一个是/，并将其格式化。需要明确的是，现在加的这个硬盘在现有的Linux系统中是/dev/sdb,但是，当我们把东西全部设置好时，要把这个硬盘拔除，放在新系统上，此时，就是/dev/sda

2. 在/dev/sdb硬盘上，将其打造成独立的Linux系统，里面的所有文件是需要拷贝进去的

3. 作为能独立运行的Linux系统，内核是一定不能少，要把内核文件和initramfs文件也一起拷到/dev/sdb上

4. 以上步骤完成，我们的自制Linux就完成了。创建一个新的linux虚拟机，将其硬盘指向我们创建的硬盘，启动即可

## 制作流程

- P127 https://www.bilibili.com/video/BV1Sv411r7vd?p=127

******

# Linux内核源码介绍&内核升级

## 为什么要阅读linux内核?

- 爱好，就是喜欢linux(黑客精神)

- 想深入理解linux底层运行机制，对操作系统有深入理解

- 阅读Linux内核，你会对整个计算机体系有一个更深刻的认识。作为开发者，不管你从事的是驱动开发，应用开发还是后台开发，你都需要了解操作系统内核的运行机制，这样才能写出更好的代码。

- 作为开发人员不应该只局限在自己的领域，你设计的模块看起来小，但是你不了解进程的调用机制，你不知道进程为什么会阻塞、就绪、执行几个状态。那么很难写出优质的代码。

- 找工作面试的需要

- 老韩忠告，作为有追求的程序员，还是应该深入的了解一个操作系统的底层机制,(比如linux/unix)最好是源码级别的，这样你写多线程高并发程序，包括架构，优化，算法等，高度不一样的，当然老韩也不是要求小伙伴儿把一个非常庞大的Linux内核每一行都读懂。我觉得。你至少能看几个核心的模块把。

## linux0.01内核源码

### Linux内核源码基本介绍

- Linux的内核源代码可以从网上下载,解压缩后文件一般也都位于linux目录下。内核源代码有很多版本，可以从linux0.01内核入手，总共的代码1w行左右，最新版本5.xx.xx 总共代码超过700w行，非常庞大.

- 内核地址: https://www.kernel.org/

- 很多人害怕读Linux内核，Linux内核这样大而复杂的系统代码，阅读起来确实有很多困难，但是也不象想象的那么高不可攀。老韩建议可以从linux0.01入手。

### linux0.01内核源码目录&阅读

- 阅读内核源码技巧

1. linux0.01的阅读需要懂c语言

2. 阅读源码前，应知道Linux内核源码的整体分布情况。现代的操作系统一般由进程管理、内存管理、文件系统、驱动程序和网络等组成。Linux内核源码的各个目录大致与此相对应.

3. 在阅读方法或顺序上，有纵向与横向之分。所谓纵向就是顺着程序的执行顺序逐步进行;所谓横向，就是按模块进行。它们经常结合在一起进行。

4. 对于Linux启动的代码可顺着Linux的启动顺序一步步来阅读;对于像内存管理部分，可以单独拿出来进行阅读分析。实际上这是一个反复的过程,不可能读—遍就理解

### 下载

- https://mirrors.edge.kernel.org/pub/linux/kernel/Historic/linux-0.01.tar.gz

## linux内核最新版和内核升级

- 内核地址: https://www.kernel.org/ 查看

- 下载&解压最新版

    `wget https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.8.16.tar.gz`
    `tar -zxvf linux-5.8.16.tar.gz`

### kernel升级操作

- uname -a //查看当前的内核版本

- yum info kernel -q //检测内核版本，显示可以升级的内核

- yum update kernel /升级内核

- yum list kernel-q //查看已经安装的内核

- 重启后选择新内核boot

-  升级内核要考虑兼容性问题

******

# linux系统备份与恢复

## 备份基本介绍

- 实体机无法做快照，如果系统出现异常或者数据损坏，后果严重，要重做系统，还会造成数据丢失。所以我们可以使用备份和恢复技术

- linux的备份和恢复很简单，有两种方式

    1. 把需要的文件(或者分区)用TAR打包就行，下次需要恢复的时候，再解压开覆盖即可

    2. 使用dump和restore命令

- 如果linux上没有dump和restore指令，需要先安装
    `yum -y install dump`
   ` yum -y install restore`

## 备份操作

### 使用dump完成备份

- dump支持分卷和增量备份（所谓增量备份是指备份上次备份后修改/增加过的文件，也称差异备份)。

- dump语法说明
    - 例子：
    `dump [-cu] [-0123456789] [-f<备份后文件名>] [-T<日期>] [目录或文件系统]`
    `dump []-wW`
    - 选项：
    `-c` :创建新的归档文件，并将由一个或多个文件参数所指定的内容写入归档文件的开头。
    `-0123456789`:备份的层级。0为最完整备份，会备份所有文件。若指定0以上的层级，则备份至上一次备份以来修改或新增的文件, 到9后，可以再次轮替.
    `-f<备份后文件名>`∶指定备份后文件名
    `-j`:<font color = red>调用bzlib库压缩备份文件</font>，也就是将备份后的文件压缩成bz2格式，让文件更小
    `-T<日期>`:指定开始备份的时间与日期
    `-u`︰备份完毕后，在/etc/dumpdares中记录备份的文件系统，层级，日期与时间等。`-t`:指定文件名，若该文件已存在备份文件中，则列出名称
    `-W`:显示需要备份的文件及其最后一次备份的层级，时间，日期。
    `-w`:与-W类似,但仅显示需要备份的文件。

### 应用案例

- dump应用案例1
    将/boot目录所有内容备份到/opt/boot.bak0.bz2文件中，备份层级为 “0”
    `dump -0uj -f /opt/boot.bak0.bz2 /boot`

- dump应用案例2
    在/boot目录下增加一个新文件，备份层级为“1”(只备份上次使用层次“O”备份后发生过改变的数据)，==注意比较看看这次生成的备份文件boot1.bak有多大==
    dump -1uj -f /opt/boot.bak1.bz2 /boot
    老韩提醒:通过dump命令再配合crontab可以实现无人值守备份

- `dump -W`
    显示需要备份的文件及其最后一次备份的层级，时间，日期
    ```Shell
    Last dump(s) done (Dump '>' file systems):
    > /dev/sda3    (    /) Last dump: never
      /dev/sda1    (/boot) Last dump: Level 1，Date Sat Oct 24 15:09:06 2020
    ```

- 查看备份时间文件
    `cat /etc/dumpdates`
    ```Linux
    [root@hspedu100 opt]# cat /etc/dumpdates
    /dev/sda1 0 Sat 0ct 24 15:08:09 2020 +0800
    /dev/sda1 1 Sat 0ct 24 15:09:06 2020 +0800
    ```

-  dump备份文件或者目录
    前面我们在备份分区时，是可以支持增量备份的，如果<font color = red>备份文件或者目录，不再支持增量备份</font>,即只能使用0级别备份
    - 案例，使用dump备份/etc 整个目录
        `dump -0j -f /opt/etc.bak.bz2 /etc/`
        #下面这条语句会报错，提示 : `DUMP: Only level 0 dumps are allowed on a subdirectory`
        `dump -1j -f /opt/etc.bak.bz2 /etc/`

- 老韩提醒
    如果是重要的备份文件，比如数据区，建议将文件上传到其它服务器保存，<font color = blue>不要将鸡蛋放在同一个篮子</font>.

## 使用备份

### 使用restore完成恢复

- 基本介绍
    restore命令用来恢复已备份的文件，可以从dump生成的备份文件中恢复原文件

- restore基本语法
    `restore [模式选项] [选项]`
    说明下面四个模式，不能混用，在一次命令中,只能指定一种。
    `-C`:使用对比模式，将备份的文件与已存在的文件相互对比。
    `-i`:使用交互模式，在进行还原操作时，restores指令将依序询问用户
    `-r`:进行还原模式
    `-t`:查看模式，看备份文件有哪些文件

- 选项
    `-f<备份设备>`:从指定的文件中读取备份数据，进行还原操作

### 应用案例

- 应用案例1
    restore命令比较模式，比较备份文件和原文件的区别
    测试
    `mv /boot/hello.java /boot/hello100.java`
    `restore -c -f boot.bak1.bz2//注意和最新的文件比较`
    结果：
    ```Shell
    Dump tape is compressed.
    Dump   date: Fri Nov 13 23:11:11 2020
    Dumped from: Fri Nov 13 22:08:18 2020
    Level 1 dump of /boot on hspEdu100:/dev/sda1
    Label: none
    filesys = /boot
    restore: unable to stat ./hello.java: No such file or directory
    Some files were modified! 1 compare errors
    ```
    再操作    
    `mv /boot/hello100.java /boot/hello.java`
    `restore -C -f boot.bak1.bz2`
    结果：
    ```Shell
    Dump tape is compressed.
    Dump   date: Fri Nov 13 23:11:11 2020
    Dumped from: Fri Nov 13 22:08:18 2020
    Level 1 dump of /boot on hspEdu100:/dev/sda1
    Label: none
    filesys= /boot
    ```

- 应用案例2
    restore命令查看模式，看备份文件有哪些数据/文件
    测试
    `restore -t -f boot.bak0.bz2`

- 应用案例3
    restore命令还原模式，<font color = red>注意细节</font>:如果你有增量备份，需要把增量备份文件也进行恢复，有几个增量备份文件，就要恢复几个，按顺序来恢复即可。
    测试
    `mkdir /opt/boottmp`
    `cd /opt/boottmp`
    `restore -r -f /opt/boot.bak0.bz2//恢复到第1次完全备份状态`
    `restore -r -f /opt/boot.bak1.bz2//恢复到第2次增量备份状态`

******

# Linux可视化管理webmin和bt运维工具

## webmin介绍

### webmin基本介绍
- Webmin是功能强大的基于Web的Unix/linux系统管理工具。管理员通过浏览器访问Webmin的各种管理功能并完成相应的管理操作。除了各版本的linux以外还可用于:AIX、HPUX、Solaris、Unixware、lrix和FreeBSD等系统

### 安装webmin&配置
1. 下载地址:http://download.webmin.com/download/yum/ 用下载工具下载即可
    也可以使用`wget http://download.webmin.com/download/yum/webmin-1.700-1.noarch.rpm`
2. 安装:`rpm -ivh webmin-1.700-1.noarch.rpm`
3. 重置密码`/usr/libexec/webmin/changepass.pl /etc/webmin root test`
    root是webmin的用户名，不是OS的，这里就是把 webmin的root用户密码改成了test
4. 修改webmin服务的端口号（默认是10000出于安全目的)
`vim /etc/webmin/miniserv.conf`  #修改端口
    将port=10000 和 listen=10000 修改为其他端口号，如port=6666
5. 重启webmin
    `/etc/webmin/restart` #重启
    `/etc/webmin/start` #启动
    `/etc/webmin/stop` #停止
6. 防火墙放开6666端口
    `firewall-cmd --zone=public --add-port=6666/tcp --permanent `#配置防火墙开放6666端口
    `firewall-cmd --reload` #更新防火墙配置
    `firewall-cmd --zone=public --list-ports` #查看已经开放的端口号
7. 登录webmin
    http://ip:6666 可以访问了
    用root账号和重置的新密码test

### webmin使用

- 图形化界面，自己看

## bt(宝塔)

- 基本介绍

    bt宝塔Linux面板是提升运维效率的服务器管理软件，支持一键LAMP/LNMP/集群/监控/网站/FTP/数据库/JAVA等多项服务器管理功能。

- 安装

    1. 安装:`yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh`
    注：`&&`的意思是先执行`&&`前一个指令，再执行`&&`后一个指令。
    2. 安装成功后控制台会显示登录地址，账户密码，复制浏览器打开登录

- 使用介绍，比如可以登录终端,配置，快捷安装运行环境和系统工具，添加计划任务脚本

- 如果bt的用户名，密码忘记了，使用`bt default`可以查看

******

# Linux面试题-(腾讯,百度,美团,滴滴)

- 分析日志t.log(访问量)，将各个ip地址截取，并统计出现次数,并按从大到小排序(腾讯)
    ```
    http://192.168.200.10/index1.html
    http://192.168.200.10/index2.html
    http://192.168.200.20/index1.html
    http://192.168.200.30/index1.html
    http://192.168.200.40/index1.html
    http://192.168.200.30/order.html
    http://192.168.200.10/order.html
    ```
    ```Shell
    cat t.log | cut -d '/' -f 3 | sort | uniq -c | sort -nr 
    #cut启了split的作用
    # sort -nr 是反向sort
    # uniq -c ：uniq -c 是统计相邻行的重复情况，所以要先排序，将相同的IP排在一起才能统计
    ```

- 统计连接到服务器的各个ip情况，并按连接数从大到小排序(腾讯)
    `netstat -an` #显示连接到服务器的各个ip
    ```Shell
    netstat -an | grep ESTABLISHED | awk -F " " '{print $5}' | awk -F ":" '{print $1}' | sort |  uniq -c | sort
    # awk  -F " " '{print $5}  按空格截取到第五段
    # awk -F ":" '{print $1}' = cut -d ":" -f 1, 前面不用cut因为它不支持空格
    ```

- 问题:如忘记了mysql5.7数据库的ROOT用户的密码，如何找回?(滴滴)
    ` vim /etc/my.cnf`  之后，在文件最后加入语句：    `skip-grant-tables`
    再重启mysql：    `service mysqld restart`
    登录sql, 空密码就可以进入了： `mysql -u root -p`
    进入MySQL后：
    ```Shell
    show databases;#里面有一个mysql database
    use mysql;
    show tables; #里面有一个user表
    desc user; # 发现有一个：authentication_string
    update user set authentication_string=password("hsphello") where user='root'; #新密码：hsphello
    flush privileges;
    exit; #退出mysql
    ```    
    ` vim /etc/my.cnf`然后注销之前加的`skip-grant-tables`
    再重启mysql： `service mysqld restart`
    密码就改好了

- 写出指令:统计ip访问情况，要求分析nginx访问日志(access.log)，找出访问页面数量在前十位的ip(美团)
    和前几题相似：
    ```Shell
     cat access.log | awk -F " " '{print $1}' | sort | uniq -c | sort -nr | head 
     # head默认显示前十行，不然可以加-n显示前n行
     ```

- 使用tcpdump监听本机,将来自ip 192.168.200.1,tcp端口为22的数据，保存输出到tcpdump.log，用做将来数据分析(美团)
    `tcpdump -i ens33 host 192.168.200.1 and port 22`# 监听
    `tcpdump -i ens33 host 192.168.200.1 and port 22 >> tcpdump.log`保存
    使用<kbd>Ctrl</kbd>+`C`退出监听加保存

- 常用的Nginx模块，用来做什么(头条)
    rewrite模块，实现重写功能
    access模块:来源控制
    ssl模块:安全加密
    ngx_http_gzip_module :网络传输压缩模块
    ngx_http_proxy_module：模块实现代理
    ngx_http_upstream_ module：模块实现定义后端服务器列表
    ngx_cache_purge：实现缓存清除功能

- 如果你是系统管理员，在进行Linux系统权限划分时,应考虑哪些因素?（腾讯)
    1. 首先阐述Linux权限的主要对象
        1. 阐述rwx在文件上的权限含义
            1. r:文件内容查看权限（cat more less)
            2. w:文件内容编辑权限（vi echo)(但不能删除文件本身)
            3. x:文件的执行权限
        2. 阐述在目录上的权限含义
            1. r:目录内文件列表查看权限（ls）
            2. w:目录内文件的增删、复制、剪切权限( touch rm cp mv)
            3. x:能否进入目录的权限（cd)
        3. 修改权限
            1. chmod [augo][+-=][rwx] filename
            2. chmod 644 filename
            3. chmod -R 644 filename 权限递归选项
    2. 根据自己实际经验谈考虑因素
        - 注意权限分离，比如:工作中，Linux系统权限和数据库权限不要在同一个部门
        - 权限最小原则(即:在满足使用的情况下最少优先)
        - 减少使用root用户，尽量用普通用户+sudo提权进行日常操作。
        - 重要的系统文件，比如/etc/passwd， /etc/shadow etc/fstab , /etc/sudoers等,日常建议使用chattr(change attribute)锁定, 需要操作时再打开。【<font color = red>演示比如:锁定/etc/passwd让任何用户都不能随意useradd,除非解除锁定)</font>: `chattr +i /etc/passwd`】
            - 我们还可以把chattr藏起来：`which chattr`-->`/usr/bin/chattr`#chattr在这里-->`mv /usr/bin/chattr /opt`#把它藏起来，其他人就不能chattr了。 
            - 如果想用`find / -name chattr`来找chattr，我们还可以把chattr改名：`mv /opt/chattr /opt/h`
            - 解锁，把前面的改回去，然后：`chattr -i /etc/passwd`
        - 使用SUID, SGID, Sticky设置特殊权限。
        - 可以利用工具，比如chkrootkit/rootkit hunter检测rootkit脚本( rootkit是入侵者使用工具在不察觉的建立了入侵系统途径)[<font color = red>演示使用</font>`wget ftp://ftp.pangeia.com.br/pub/seg/pac/chkrootkit.tar.gz`]
            - 解压后，`./chkrootkit`进行扫描
        - 利用工具Tripwire检测文件系统完整性

- 权限操作思考题
    1. 用户tom对目录/home/test有执行和读写权限，/home/test/hello.java是只读文件，问tom对hello.java文件能读吗?能修改吗?能删除吗?
    - 能读，不能改，能删
    2. 用户tom对目录/home/test只有读写权限，/home/test/hello。java是只读文件，问tom对 hello.java文件能读吗?能修改吗?能删除吗?
    - ==进不去test folder， 所以啥都不能干==
    3. 用户tom对目录/home/test只有执行权限，/home/test/hello.java是只读文件，问tom对 hello.java文件能读吗?能修改吗?能删除吗?
    - 能读，不能改，不能删
    4. 用户tom对目录/home/test 只有执行和写权限，/home/test/hello.java是只读文件，问tom对 hello.java文件能读吗?能修改吗?能删除吗?
    - 能读，不能改，能删，只是不能ls

- 说明Centos7启动流程,并说明和CentOS6相同和不同的地方(腾讯)
    见附图Linux7，wordver
    主要是把下面四阶段描述出来，然后要提出它们的不同在==第二第四==阶段。
    - 第一步、硬件启动阶段
        - 这一步和CentOs6差不多，详细请看图
    - 第二步、GRUB2引导阶段
        - 从这一步开始, CentoS6和centOS7的启动流程区别开始展现出来了。CentOS7的主引导程序使用的是grub2:
        - 这一步的流程:显示加载两个镜像，再加载MOD模块文件，把grub2程序加载执行，接着解析配置文件/boot/grub2/grub.cfg，根据配置文件加载内核镜像到内存，之后构建虚拟根文件系统，最后转到内核。
        - 在这里grub.cfg配置文件已经比较复杂了，但并不用担心，到了centoS7中一般是使用命令进行配置，而不直接去修改配置文件了。不过我们可以看到grub.cfg配置文件开头注释部分说明了由/etc/grub.d/目录下文件和/etc/default/grub文件组成。
        - 一般修改好配置后都需要使用命令`grub2-mkconfig -o /boot/grub2/grub.cfg`，将配置文件重新生成。
    - 第三步、内核引导阶段
        - 这一步与CentoS6也差不多，加载驱动，切换到真正的根文件系统，唯一不同的是执行的初始化程序变成了/usr/lib/systemd/systemd
    - 第四步、systemed初始化阶段（又叫系统初始化阶段)
        - ==CentOS7中我们的初始化进程变为了systemd。执行默认target配置文件/etc/systemd/system/default.target(这是一个软链接，与默认运行级别有关)。然后执行sysinit.target来初始化系统和 basic.target 来准备操作系统。接着启动multi-user.target下的本机与服务器服务，并检查/etc/rc.d/rc.local文件是否有用户自定义脚本需要启动。最后执行 multi-user下的getty.target 及登录服务，检查default.target是否有其他的服务需要启动。==
        - 注意:/etc/systemd/system/default.target指向了/lib/systemd/system/目录下的 graphical.target或multiuser.target。而graphical.target依赖multiuser.target，multiuser.target依赖basic.target，basic.target依赖sysinit.target，所以倒过来执行。
        - System概述（了解): systemd即为system daemon，是Linux下的一种init 软件，开发目标是提供更优秀的框架以表示系统服务间的以来关系，并依此实现系统初始化时服务的并行启动，同时达到降低shell系统开销的效果，最终代替现在常用的System V 与 BSD风格的init程序。
        - 与多数发行版使用的System V风格的 init相比，systemd采用了以下的新技术:A.采用Socket激活式与总线激活式服务，以提高相互依赖的各服务的并行运行性能;B.用Cgroup 代替PID来追踪进程，即使是两次 fork之后生成的守护进程也不会脱离systemd 的控制。
        - unit对象: unit表示不同类型的systemd对象，通过配置文件进行标识和配置;文件中主要包含了系统服务、监听socket、保存的系统快照以及其他与init相关的信息。(也就是Centos6中的服务器启动脚本)    

- 问题:列举Linux高级命令，至少6个(百度)
    netstat//网络状态监控 top //系统运行状态 lsblk //查看硬盘分区 find//查找
    ps -aux//查看运行进程 chkconfig//查看服务启动状态 systemctl//管理系统服务器

- 问题:Linux查看内存、io读写、磁盘存储、端口占用、进程查看命令是什么?(瓜子)
    top//iotop//df -lh//netstat -tunlp//ps -aux | grep 关心的进程

- 使用Linux命令计算t2.txt第二列的和并输出(美团)
    张三 40
    李四 50
    王五 60
    `cat t2.txt | awk -F " " '{sum+=$2} END {print sum}'`

- Shell脚本里如何检查一个文件是否存在?并给出提示(百度)
    ```Shell
    if [ -f 文件名 ] then echo "存在" else echo "不存在" fi
    ```

- 用shell写一个脚本，对文本t3.txt 中无序的一列数字排序,并将总和输出(百度)
    ```Shell
    sort -n t3.txt | awk -F '{sum+=$0; print $0 } END {print "和="sum}'
    # $0不是打印所有列，awk是行处理，$0是指那一行所有的内容
    ```

- 请用指令写出查找当前文件夹(/home)下所有的文本文件内容中包含有字符“cat"的文件名称(金山)
    
    ```Shell
    # -r 为了递归
    grep -r "cat" /home | cut -d ":" -f 1
    ```

- 请写出统计/home目录下所有文件个数和所有文件总行数的指令(在金山面试题扩展)
    `find /home -name "*.*"| wc -l`
    `find /home -name "*.*"| xargs wc -l`

- 列出你了解的web服务器负载架构(滴滴)
    Nginx
    Haproxy
    Keepalived
    LVS

- 每天晚上10点30分，打包站点目录/var/spool/mail备份到/home目录下(每次备份按时间生成不同的备份包 比如按照年月日时分秒)(滴滴)
    ```Shell
    #!/bin/ bash
    cd /var/spool/ && /bin/tar zcf /home/mail-`date +%Y-%m-%d%H%M%S`.tar.gz mail/
    ```
    `chmod u+x mail.sh `
    `crontab -e`
    ```Shell
    30 22 * * * /root/mail.sh
    ```   

- 如何优化Linux系统,说出你的方法(瓜子)
    1. 对Linux的架构的优化，和原则分析
        - 网络
        - 磁盘Io
        - 文件连接数
        - 安全
        - 防火墙端口监听
        - 关掉不必要的服务
    2. 对linux系统本身的优化-规则
        (1)不用root ,使用sudo提示权限
        (2)定时的自动更新服务时间,使用`nptdate npt1.aliyun.com`,让croud定时更新
        (3)配置yum源，指向国内镜像(清华，163)
        (4)配置合理的防火墙策略,打开必要的端口，奖闭不必要的端口
        (5)打开最大文件数(调整文件的描述的数量) vim /etc/profile ulimit -SHn 65535
        (6)配置合理的监控策略
        (7)配置合理的系统重要文件的备份策略
        (8)对安装的软件进行优化，比如nginx ,apache
        9)内核参数进行优化/etc/sysctl.conf
        (10)锁定一些重要的系统文件 chattr /etc/passwd /ect/shadow /etc/inittab
        (11)禁用不必要的服务setup , ntsysv

