采用8个比特（bit）作为一个字节（byte），所以，一个字节能表示的最大的整数就是255，这个编码表被称为ASCII编码

Unicode标准也在不断发展，但最常用的是用两个字节表示一个字符（如果要用到非常偏僻的字符，就需要4个字节）。代操作系统和大多数编程语言都直接支持Unicode。

本着节约的精神，又出现了把Unicode编码转化为“可变长编码”的UTF-8编码。UTF-8编码把一个Unicode字符根据不同的数字大小编码成1-6个字节，常用的英文字母被编码成1个字节，汉字通常是3个字节，只有很生僻的字符才会被编码成4-6个字节。





**python八荣八耻**

以动手实践为荣 , 以只看不练为耻;

以打印日志为荣 , 以单步跟踪为耻;

以空格缩进为荣 , 以制表缩进为耻;

以单元测试为荣 , 以人工测试为耻;

以模块复用为荣 , 以复制粘贴为耻;

以多态应用为荣 , 以分支判断为耻;

以Pythonic为荣 , 以冗余拖沓为耻;

以总结分享为荣 , 以跪求其解为耻。

##将本地gitbook同步到github，并创建线上gitbook

1. 在github上创建仓库，不要初始化

2. 把本地公钥设置到github上

3. 设置gitbook仓库地址，即github上的https地址

4. 本地Sync

5. 打开gitbook网站，新建gitbook，选择仓库

## 23种设计模式、代码大全2



