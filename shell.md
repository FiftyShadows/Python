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

alias vi='vim'    临时生效

vim /root/.bashrc    保存了命令别名

source .bashrc

unalias vi

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



## 输入重定向

- wc 统级    -l行数    -w单词数    -c字符数 









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
