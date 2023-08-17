Xshell常用命令
----------

### cd-更改目录

```shell
# 切换到主目录 
cd 
# 切换到主目录 
cd ~ 
# 切换到目录/tmp 
cd /tmp
# 切换到当前目录下的dir目录 
cd dir
# 切换到根目录 
cd /
# 切换到到上一级目录 
cd ..
# 切换到上二级目录 
cd ../..
# 切换到用户目录，比如是root用户，则切换到/root下
cd ~

```

### cp-复制文件

```shell
# 把文件复制为新文件afile.bak 
cp afile afile.bak 
# 把文件afile从当前目录复制到/home/bible/目录下 
cp afile /home/bible/ 
# 把当前目录下的所有未隐藏文件复制到/tmp/目录下 
cp * /tmp 
# 递归性地把当前目录下的docs目录复制为新目录docs.bak,保持文件属性，并复制所有的文件，包括以句点开头的隐藏文件。为了方便起见，-a选项包含-R选项 
cp -a docs docs.bak 
# 在覆盖前询问用户 
cp -i 
# 告诉用户正在做什么 
cp -v 
# 若给出的源文件是一个目录文件，此时将复制该目录下所有的子目录和文件
cp -r 

```

### cat-显示文件内容

```shell
# 显示文件内容
cat file

```

### diff-比较文件内容

```shell
# 比较目录1与目录2的文件列表是否相同，但不比较文件的实际内容，不同则列出
diff dir1 dir2
# 比较文件1与文件2的内容是否相同，如果是文本格式的文件，则将不相同的内容显示，如果是二进制代码则只表示两个文件是不同的
diff file1 file2
# 比较文件，显示两个文件不相同的内容
comm file1 file2

```

### find-查找文件

```shell
# 在当前目录中查找rpm包
find .-name *.rpm
# 在当前目录及其子目录中查找文件名包含page的文件
find .|grep page
# 在系统的任何地方查找文件名包含traceroute的文件
locate traceroute

```

### grep-搜索文件内容

```shell
# 在文件exports中查找包含bible的所有行 
grep bible /etc/exports
# 在WEB服务器日志文件access.log的后100行中查找包含“404”的行 
tail -100 /var/log/apache/access.log|grep 404 
# 在WEB服务器日志文件access.log的后100行中，查找没有被google访问的行 
tail -100 /var/log/apache/access.log|grep -v googlebot
# 在主apache配置文件中，查找所有非注释行 
grep -v ^# /etc/apache2/httpd.conf

```

### head-查看文件的名字和后缀

```shell
# x:开始几行aaa.log：要查看的文件的名字和后缀 
head -n x aaa.log

```

### kill-杀掉进程

```shell
kill -signal %jobnumber   

kill -l   

# 参数：   

    -l  ：这个是 L 的小写，列出目前 kill 能够使用的讯号 (signal) 有哪些？共有62个信号。 

    signal ：代表给予后面接的那个工作什么样的指示啰！用 man 7 signal 可知：   

    -1 ：重新读取一次参数的设定档 (类似 reload)；   

    -2 ：代表与由键盘输入 [ctrl]-c 同样的动作；   

    -9 ：立刻强制删除一个工作； 

    -15：以正常的程序方式终止一项工作。与 -9 是不一样的。  

# 范例一：找出目前的 bash 环境下的背景工作，并将该工作删除。   

jobs 
[1]+  Stopped					vim bashrc   
kill -9 %1 
[1]+  已砍掉						vim bashrc 

```

### ln-建立连接

```shell
# 硬连接
ln source_path target_path
# 软连接
ln -s source_path target_path

```

### ls-列出文件

```shell
# 显示当前目录文件 
ls
# 给出当前目录下所有文件的一个长列表，包括以句点开头的“隐藏”文件 
ls -la
# 列出当前目录下以字母a开头的所有文件 
ls a*
# 给出当前目录下以.doc结尾的所有文件 
ls -l *.doc

```

### mv-移动和重命名文件

```shell
# 将afile重命名为bfile
mv aflie bfile 
# 把当前目录下的afile移动到/tmp/目录下
mv afile /tmp 

```

### mkdir-建立目录

```shell
# 在当前目录中建立名为photos的目录
mkdir photos 
# 在当前目录下建立指定的嵌套子目录
mkdir -p this/that/theother

```

### more,less-查看文件内容

```shell
# 查看/etc/passwd的内容 
more /etc/passwd

# 功能：分页显示命令   

    more file 

    more命令也可以通过管道符(|)与其他的命令一起使用,例如：   ps ux|more   ls|more 

# 查看/etc/passwd的内容 
less /etc/passwd 

```

### ps-查看进程

```shell
ps [options]
# DESCRIPTION（描述）：ps命令显示运行程序选项的一些信息。如果你想显示选项的一些重复信息，请使用top命令替代。 

用标准语法查看系统上的每一个进程。    

   ps -e

   ps -ef

   ps -eF

   ps -ely 

```

### pwd-查看当前路径

```shell
# 查看当前路径
pwd

```

### rm-删除文件和目录

```shell
# 删除文件afile
rm afile 
# 删除当前目录下的所有文件（未隐藏文件）。rm命令不删除目录，除非也指定了-r(递归)参数。
rm *  
# 删除domed目录以及它所包含的所有内容 
rm -rf domed 
# 删除当前目录下所有以字母a开头的文件，并且在每次删除时，提示用户进行确认 
rm -i a* 

```

### rmdir-删除空目录

```shell
# 将删除空目录
rmdir 

```

### rz,sz-文件上传下载

```shell
# 运行命令sudo rz，即是接收文件，xshell就会弹出文件选择对话框，选好文件之后关闭对话框，文件就会上传到linux里的当前目录 。
sudo rz
#运行命令sudo sz file 就是发文件到windows上（保存的目录是可以配置）
sudo sz file

比ftp命令方便多了，而且服务器不用再开FTP服务了。

```

### stop,start-重启tomcat

```shell
./catalina.sh stop

./catalina.sh start

```

### top-查看cpu，内存

```shell
# 查看cpu、内存
top

```

### tar-打包，rar-解包

```shell
# 将a和b打成**.rar
tar -cvf **.tar a.jsp b.java
# 将**.tar 解包
tar -xvf **.tar a.jsp b.java

```

详细介绍：[linux tar打包、解包命令](http://www.jianshu.com/p/b9a667d8cb1e)

### tail-查看文件详细信息

```shell
# 看aaa.txt文件的详细信息 
tail -f aaa.txt
# x:最后几行 
tail -n x aaa.log

```

### touch-创建一个空文件

```shell
# 创建一个空文件，文件名为aaa.txt
touch aaa.txt

```

### vi-编辑文件

```shell
# 用vi编辑文件/etc/bubby.txt 
vi /etc/bubby.txt
# 用vim编辑文件/etc/bubby.txt 
vim /etc/bubby.txt

# 快捷操作： 

    切换窗口：	alt+1,alt+2 

    全屏：		alt+回车 

# 将vim挂起（暂停）：ctrl+z，暂停后可进行其他shell操作，完了之后可通过 fg 命令切换回vim界面继续编辑 

:MR：查看历史文件记录（注意：MR大写） 

:sp 横向切换界面窗口   

:vsp 纵向切换界面窗口   方便多文件对照编码	emacs /etc/bubby.txt 用emacs编辑文件/etc/bubby.txt 

```

详细介绍：[linux 下vi与vim区别以及vim的使用](https://www.cnblogs.com/baichuanhuihai/p/7928404.html)

基本系统命令
------

### clear-清屏

```shell
# 清屏
clear

```

### chown-变更使用者

**变更文件或目录的拥有者或所属群组**

**`chown -R -h owner file`**

**R(recursive)** 选项意味着对所有子目录下的文件也都进行同样的操作。  
**h** 选项意味着在改变符号链接文件的属主时不影响该链接所指向的目标文件

**`chown -R xh test1`** (test1目录及子目录的所有文件属主变为xh)

### clock-时钟设置

```shell
# 对系统Bios中读取时间参数
clock –r
# 将系统时间(如由date设置的时间)写入Bios
clock –w

```

### date-系统日期设定

```shell
# 设置系统时期为2006年5月20日6点整。
date -s “060520 06:00:00″

```

### free-查看内存和swap分区使用情况

```shell
# 查看内存和swap分区使用情况
free -tm

```

### iostat-磁盘吞吐量

```shell
-c 	只显示CPU行
-d 	显示磁盘行
-k 	以千字节为单位显示磁盘输出
-t 	在输出中包括时间戳
-x 	在输出中包括扩展的磁盘指标

```

### last-查看最近哪些用户登录系统

```shell
# 查看最近哪些用户登录系统
last

```

### man-查看某个命令的帮助

```shell
# 显示ls命令的帮助内容
man ls

```

### reboot,shutdown-关闭和重启计算机

```shell
# 重新启动计算机
reboot
# 重新启动计算机，停止服务后重新启动计算机
shutdown -r now
# 关闭计算机，停止服务后再关闭系统
shutdown -h now
# 关闭计算机
halt

# 一般用shutdown -r now,在重启系统时，关闭相关服务，shutdown -h now也是如此。

```

### su-切换用户

```shell
# 切换到root用户
su -
# 切换到zhoulj用户
su – zhoulj

# 注意：-，他很关键，使用-，将使用用户的环境变量

```

### uname-查看系统版本

```shell
# 显示操作系统内核的version
uname -R

```

### uptime-现在的时间

```shell
# 系统开机运转到现在经过的时间，连线的使用者数量，最近一分钟，五分钟和十五分钟的系统负载
uptime

```

### vmstat-监视虚拟内存使用情况

```shell
# 监视虚拟内存使用情况
vmstat

```

### w-显示登录用户的详细信息

```shell
# 显示登录用户的详细信息
w

```

### who-显示登录用户

```shell
# 显示登录用户
who

```

### 重启tomcat

1.  查看要重启进程的进程号 `Ps –ef|grep xxxx`
2.  杀掉该项目的进程  
    先杀第二列，再杀第一列 `Sudo kill -9 x x`  
    (x为进程号，同时杀多个中间以空格分割)
3.  重启tomcat  
    首先找到tomcat的bin目录 `Cd tomcat/bin`;  
    然后运行 `sudo ./run.sh`即可启动tomcat。

常用实例
----

### 查看端口号占用情况并杀死进程

```shell
netstat -tunlp|grep pid

kill -9 pid

```

### 编辑

```shell
crontab -e

i 			进入编辑模式
esc 		退出编辑模式
:wq 		退出并保存
:q! 		退出不保存

```
