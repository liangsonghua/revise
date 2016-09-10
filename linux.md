**ls命令**

ls命令是linux下最常用的命令。ls命令就是list的缩写缺省下ls用来打印出当前目录的清单如果ls指定其他目录那么就会显示指定目录里的文件及文件夹清单。

**cat主要有三大功能**：

- 1.一次显示整个文件
```
。$ cat filename
```

- 2.从键盘创建一个文件。
```
$ cat > filename
```

-    只能创建新文件,不能编辑已有文件.
- 3.将几个文件合并为一个文件：
```
$cat file1 file2 > file
```



```
cat -n file1 file2 
输出file1和file2文件的内容
```


less [options] [file-list]
less与more类似，但比more更加完善, more以一页一页的显示方便使用者逐页阅读


**tar 主要命令：**

- -c 创建包
- -x 解包
- -t 列出包中的内容
- -r 增加文件到指定包中
- -u 更新包中的文件

**比如：**
在linux中用使用tar命令将文件aaa打包为bak.tar。

```
tar -cf bak.tar  aaa
```

**系统目录：**

（带链接树形目录结构）

- /bin  二进制执行文件，也就是命令文件
- /etc 下存放的是配置文件
- /dev 存放是时外部设备文件，硬盘，usb等
- /lib 存放的是库文件
- /var  可变化的目录
-  /home 用户的家目录
-  /root 用来存放用户信息




**s 命令来替换字符串**

全局替换命令为：:%s/源字符串/目的字符串/g

- /pattern: 从光标开始处向文件尾搜索pattern
- ?pattern: 从光标开始处向文件首搜索pattern
- n: 在同一方向重复上一次搜索命令
- N: 在反方向上重复上一次搜索命令
- :s/p1/p2/g: 将当前行中所有p1均用p2替代
- :n1,n2s/p1/p2/g: 将第n1至n2行中所有p1均用p2替代
- :g/p1/s//p2/g: 将文件中所有p1均用p2替换


hosts文件 是一个用于储存 计算机网络 中各节点信息的计算机文件。这个文件负责将 主机名称 映射到相应的 IP地址 。hosts文件通常用于补充或替换网络中 DNS 的功能。和DNS不同的是，计算机的用户可以直接对hosts文件进行控制





**gdb命令**

- backtrace bt 打印当前的函数调用栈的所有信息。
- info threads 显示当前可调试的所有线程，每个线程会有一个GDB为其分配的ID，后面操作线程的时候会用到这个ID。 前面有*的是当前调试的线程。
- set scheduler-locking 线程调试 显示线程状态,off 不锁定任何线程
- info break 可列出所有断点信息，info break 后也可设置要查看的break num


**文件权限**

Linux文件权限一共10位长度，分成四段，文件类型  用户 用户组 其他用户组

文件权限值：分为三种 读w 写r 执行x 各自的值为4、2、1



**rpm相应命令**


```
rpm -qf /etc/my.conf
```
 找出/etc/my.conf文件属于哪个包(package)

- －ivh：安装显示安装进度--install--verbose--hash 
- －Uvh：升级软件包--Update； 
- －qpl：列出RPM软件包内的文件信息[Query Package list]； 
- －qpi：列出RPM软件包的描述信息[Query Package install package(s)]； 
- －qf：查找指定文件属于哪个RPM软件包[Query File]； 
- －Va：校验所有的RPM软件包，查找丢失的文件[View Lost]； 
- －e：删除包
 
**spinlock**

spinlock在多处理器多线程环境的场景中有很广泛的使用，一般要求使用spinlock的临界区尽量简短，这样获取的锁可以尽快释放，以满足其他忙等的线程。<br/>
Spinlock和mutex不同，spinlock不会导致线程的状态切换(用户态->内核态)，但是spinlock使用不当(如临界区执行时间过长)会导致cpu busy飙高。<br/>

**硬连接**

硬连接实际上是为文件建一个别名，链接文件和源文件实际上同一个文件。使用ls -i就可以得到两个文件的inode号是同一个。


**bash配置**

- .bash_profile 类似于编程中的构造函数，当登录shell时，shell会寻找该文件做环境初始化。
- .bashrc 是在bash环境时.bash_profile的替补。
- .bash_logout 类似于编程中的析构函数，当登录shell退出时，shell会寻找该文件，并按其指示办事。
- /etc/profile是系统文件,对系统下全体用户起作用

**Redhat 9所支持的安装方式**

- 光盘安装 (常规情况) 硬盘安装 (无光驱情况)
- 网络安装-NFS方式 (适合于批量安装大量服务器，和kickstart自动安装一起使用)
- 网络安装-FTP方式 (适合于批量安装大量服务器，和kickstart自动安装一起使用)
- 网络安装-HTTP方式 (适合于批量安装大量服务器，和kickstart自动安装一起使用)


**定时脚本：**

*　　*　　*　　*　　*　　command
　
分　时　日　月　周　命令

- 第1列表示分钟1～59 每分钟用*或者 */1表示
- 第2列表示小时1～23（0表示0点）
- 第3列表示日期1～31
- 第4列表示月份1～12
- 第5列标识号星期0～6（0表示星期天）
- 第6列要运行的命令


**其他命令：**

dd命令用于复制文件并对原文件的内容进行转换和格式化处理。dd命令功能很强大的，对于一些比较底层的问题，使用dd命令往往可以得到出人意料的效果。用的比较多的还是用dd来备份裸设备。但是不推荐，如果需要备份oracle裸设备，可以使用rman备份，或使用第三方软件备份

df命令用于显示磁盘分区上的可使用的磁盘空间。默认显示单位为KB。可以利用该命令来获取硬盘被占用了多少空间，目前还剩下多少空间等信息

du ： disk usage 查看当前目录磁盘空间使用情况

nohup命令：如果你正在运行一个进程，而且你觉得在退出帐户时该进程还不会结束，那么可以使用nohup命令。该命令可以在你退出帐户/关闭终端之后继续运行相应的进程

csh:调用 C shell。

Tcsh是csh的增强版，并且完全兼容csh。它不但具有csh的全部功能，还具有命令行编辑、拼写校正、可编程字符集、历史纪录、 作业控制 等功能，以及C语言风格的语法结构。

AWK 是一种优良的文本处理工具， Linux 及 Unix 环境中现有的功能最强大的数据处理引擎之一, AWK 提供了极其强大的功能：可以进行样式装入、 流控制 、数学 运算符 、进程 控制语句 甚至于内置的变量和函数。

SED: Stream EDitor

shutdown -r now：在重新启动Linux系统的同时把内存中的信息写入硬盘

ifconfig eth0 up  激活网卡

dpkg是一个Debian的一个命令行工具，它可以用来安装、删除、构建和管理Debian的软件包。

**arp命令：**

(地址解析协议，即ARP（Address Resolution Protocol），是根据 IP地址 获取 物理地址 的一个 TCP/IP协议 。<br/>
 主机 发送信息时将包含目标IP地址的ARP请求广播到网络上的所有主机，并接收返回消息，以此确定目标的物理地址；<br/>
收到返回消息后将该IP地址和物理地址存入本机ARP缓存中并保留一定时间，下次请求时直接查询ARP缓存以节约资源。<br/>
arp协议发的都是广播包-broadcast
)

- arp -a 和你通信了的一些机器。IP和MAC .arp的中文意思就是通过IP而知道别人的MAC地址，也就是常说的地址解析。 
- ARP -d 就是清除缓存中的数据。也是删除IP和MAC绑定的项目。


**系统配置文件：**

- /sbin/init在核心完整的加载后，开始运行系统的第一支程序，主要的功能就是准备软件运行的环境，包括系统的主机名称、网络配置、语系处理、文件系统格式及其他服务的启动等。 
- /bin/sh解释脚本的shell命令，开机后运行
- /etc/sysvinit就是 system V 风格的 init 系统，顾名思义，它源于 System V 系列 UNIX。sysvinit 中运行模式描述了系统各种预订的运行模式。
- /etc/inittab定义了系统引导时的运行级别, 进入或者切换到一个运行级别时做什么。

- /etc/hosts 设定用户自已的IP与名字的对应表
- /etc/HOSTNAME   设定用户的节点名 
- /etc/resolv.conf    设置DNS  
- /etc/gateways 设定路由器 

- /proc/interrupts 显示使用的中断
- /proc/ioports 当前使用的I/O端口
- /proc/kcore 系统物理内存映像。与物理内存大小完全一样，但不实际占用这么多的内存。
- /proc/kmsg  内核输出的消息，也被送到syslog

**挂载和卸载设备**

挂载设备使用mount，卸载设备使用umount

有三种方式，通过设备名，挂载点或者设备名和挂载点

- umount /dev/hdc
- umount /mnt/cdrom
- umount /mnt/cdrom /dev/hdc

**netstat 命令**

netstat 命令用于显示各种网络相关信息，如网络连接，路由表，接口状态,连接等信息。

参数apn的作用如下：

- -a (all)显示所有选项，默认不显示LISTEN相关
- -p 显示建立相关链接的程序名
- -n 拒绝显示别名，能显示数字的全部转化成数字。

**Linux系统的负载（Load）**

- 通过就绪和运行的进程数来反映
- 可以通过TOP命令查看
- 可以通过uptime查看
- Load：2.5，1.3，1.1  表示距离现在最近的1分钟，5分钟和15分钟内的负载，1.1 -> 1.3 -> 2.5 可见负载有增加的趋势。


**多线程**

- pthread_create 创建一个线程
- pthread_join用来等待一个线程的结束
- pthread_mutex_init 初始化一个线程互斥锁
- pthread_exit结束一个线程


**Shell**

- $!表示shell最后运行进程中的PID，
- $0：当前进程的文件名，
- $n：代表第n个参数，
- $?：最后运行的命令的结束代码返回值，
- $$: shell本身的PID，