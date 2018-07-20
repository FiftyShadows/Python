![](/assets/360截图17940622107137107.png)

![](/assets/360截图184702017878114.png)

![](/assets/360截图16720407100111136.png)

![](/assets/360截图17860603494875.png)


## shell

* shell是一个命令行解释器，为用户提供了一个向linux内核发送请求以便运行程序的界面系统级程序，用户可以用shell来启动、挂起、停止甚至是编写一些程序。

* shell还是功能强大的编程语言。shell是解释执行的脚本语言，在shell中可以直接调用Linux系统命语言。

## echo

echo $SHELL

-e    支持反斜线控制的字符转换

![](/assets/360截图176808038110297.png)

`echo -e "\e[1;31m 你好 \e[0m"`

![](/assets/360截图16821217658050.png)



## 别名

alias vi='vim'    临时生效

vim /root/.bashrc    保存了命令别名

source .bashrc

unalias vi



## 历史命令

/root/.bash_history    保存了历史命令,默认1000条

history -w    把缓存中的历史命令写入历史命令保存文件

history -c    清空历史命令

ls -alh

vim /etc/profile

两次tab键

    - 命令补全依赖于 $PATH

    - 文件目录依赖于操作路径

date



## 输出重定向

ifconfig > test.log

ls &>/dev/null

![](/assets/360截图17860603494875.png)

![](/assets/360截图16720404573679.png)


## 输入重定向

- wc 统计    -l行数    -w单词数    -c字符数    ctrl+d

- wc < test.log

- wc << ddy



## 管道符

- 命令1 | 命令2    命令1的正确输出结果作为命令2的操作对象

ls -l /etc | more

netstat -an

netstat -an | grep ESTABLISHED

netstat -an | grep ESTABLISHED | wc -l



date; tar -zcvf etc.tar.gz /etc; date

ls && echo yes || echo no

![](/assets/360截图17040515627772.png)



## 通配符

ls dzp*

ls dzp?

`ls dzp[0-9]`

`ls dzp[0-9][0-9]`

`ls dzp[^0-9]`

`ls dzp[^0-9]*`

![](/assets/360截图18720123123432.png)



![](/assets/360截图184307109611595.png)





## 基本命令

```
pwd (Print Working Directory) 查看当前目录
cd (Change Directory) 切换目录，如 cd /etc
ls (List) 查看当前目录下内容，如 ls -al
mkdir (Make Directory) 创建目录，如 mkdir blog
touch 创建文件，如 touch index.html
cat 查看文件全部内容，如 cat index.html
more/less 查看文件，如more /etc/passwd、less /etc/passwd
rm (remove) 删除文件，如 rm index.html、rm -rf  blog
rmdir (Remove Directory) 删除文件夹，只能删除空文件夹，不常用
mv (move) 移动文件或重命名，如 mv index.html ./demo/index.html
cp (copy) 复制文件，cp index.html ./demo/index.html
head 查看文件前几行，如 head -5 index.html
tail 查看文件后几行 –n –f，如 tail index.html、tail -f -n 5 index.html 
tab 自动补全，连按两次会将所有匹配内容显示出来
history 查看操作历史
> 和 >>重定向，如echo hello world! > README.md，>覆盖 >>追加
wget 下载，如wget https://nodejs.org/dist/v4.4.0/node-v4.4.0.tar.gz
tar 解压缩，如tar zxvf node-v4.4.0.tar.gz
curl 网络请求，如curl http://www.baidu.com
whoami 查看当前用户
| 管道符可以将多个命令连接使用，上一次（命令）的执行结果当成下一次（命令）的参数。
grep 匹配内容，一般结合管道符使用
more命令    查看某个命令的帮助
w命令    显示登录用户的详细信息
who命令    显示登录用户
last命令    查看最近那些用户登录系统
clock命令    时钟设置
uname命令    查看系统版本
su命令    切换用户    su - 切换到root用户    - ，他很关键，使用-，将使用用户的环境变量 
top命令    查看系统cpu、内存等使用情况
free命令    查看内存和swap分区使用情况
ps命令    显示进程信息
ps ux 显示当前用户的进程
ps uxwww 显示当前用户的进程的详细信息
ps aux 显示所有用户的进程
ps ef 显示系统所有进程信息
kill命令    干掉某个进程，进程号可以通过ps命令得到
kill -9 1001　将进程编号为1001的程序干掉
kill all -9 apache　将所有名字为apapche的程序杀死，kill不是万能的，对僵死的程序则无效。
```