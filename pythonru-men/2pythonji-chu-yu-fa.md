##什么是代码？

- 代码是现实世界事物在计算机世界中的映射




##什么是写代码？

- 写代码是将现实世界中的事物用计算机语言来描述





##Python的基本数据类型

##Number： 数字

    - 整数：int；浮点数：float


```
type(1)    //int
type(1.0)    //float

type(1+1.0)    //float
type(1*1.0)    //float
type(2/2)    //float
type(2//2)    //int
//单斜杠是除法，会自动转换成float；双斜杠是整除，返回的是int类型
```




##各进制的表示与转换

- 0b进制表示符

    - 0b10
    
    - python自动转化成十进制
    
- 0o表示八进制

- 0x表示十六进制


- type()方法查看变量类型

- bin()方法把其他进制的数向二进制转换

- int()方法把其他进制的数向十进制转换

- hex()方法把其他进制的数向十六进制转换

- oct()方法把其他进制的数向八进制转换





##bool布尔类型：表示真、假

- 布尔类型是属于数字分类下的一种

- bool(0),bool(1)

- 非零的数字都是表示布尔真

- bool('abc')    bool('')字符串

- bool([1,2,3])    bool([])列表

- bool({1,1,1})    bool({})元组

- bool(None)




##complex复数

- 36j





##str字符串

- 单引号，双引号，三引号

```
'let"s go'
"let's go"
'let\'s go'
```

- 转义字符

- 多行字符串表示

```
"""
hello world
hello world
hello world
"""
//'\nhello world\nhello world\nhello world\n'
//也可以用单引号表示
```

- '''hello world\nhello world\nhello world'''

- print('''\nhello world\nhello world\nhello world\n''')

```
//字符串换行的两种方式之二：
'hello\
world'
//'helloworld'
```



##转义字符

- 特殊的字符

    - 无法"看见"的字符
    
    - 与语言本身语法有冲突的字符
    
- \n换行\r回车，这两个不是一回事

- 字符串的前面加r之后，不是一个普通字符串，而是一个原始字符串

```
print('c:\\north\\sourth')
print(r'c:\north\sourth')
```



##字符串的操作，字符串的运算

- 'hello'+'world'

- 'hello'*3

- 'hello'[0]    'hello'[-1]

- 'hello'[0:5]    5是要截取的下一位

- 负数表示步长

- "hello world"[6:11]等价"hello world"[6:20]

- "hello world"[6:]    截取到末尾

- [:-4]    [-4:]

- r'c:\windows'等价于R'c:\windows'














