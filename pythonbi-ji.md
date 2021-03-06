

## from urllib import parse

- parse.urlencode(dict)将字典转化为key=value&key=value的url编码形式

- parse.quote(str)将字符串转化为url编码




## any() 函数用于判断给定的可迭代参数 iterable 是否全部为 False，则返回 False，如果有一个为 True，则返回 True。


## all() 函数用于判断给定的可迭代参数 iterable 中的所有元素是否都为 TRUE，如果是返回 True，否则返回 False。


## in 操作符用于判断键是否存在于字典中

```py
chain = {
	'a': 123,
	'b': 456,
	'c': 789
}
require = ['a', 'b', 'c']
a = (k in chain for k in require)
print(a)
```



默认情况下，dict迭代的是key。如果要迭代value，可以用for value in d.values()，如果要同时迭代key和value，可以用for k, v in d.items()。

如何判断一个对象是可迭代对象呢？方法是通过collections模块的Iterable类型判断
from collections import Iterable


在Python中，这种一边循环一边计算的机制，称为生成器：generator。
可以被next()函数调用并不断返回下一个值的对象称为迭代器：Iterator。
可以使用isinstance()判断一个对象是否是Iterator对象：
Iterator的计算是惰性的，只有在需要返回下一个数据时它才会计算。
集合数据类型如list、dict、str等是Iterable但不是Iterator，不过可以通过iter()函数获得一个Iterator对象。



xpath last()



from lxml import html
html = html.fromstring(r.text)



成员运算符‘in’和‘not in’



split()能让我们用指定字符分割字符串



join()能让我们将指定字符添加至字符串中



`from random import shuffle`    shuffle(list)打乱一个列表的元素


random.choice    随机选取



`s = a[a.find('p_skey=') + 7: a.find(';', a.find('p_skey='))]`




用正则表达式切分字符串比用固定的字符更灵活 `re.split(r'[\s\,\;]+', 'a,b;; c  d')`



`[x for x in os.listdir('.') if os.path.isfile(x) and os.path.splitext(x)[1]=='.py']`



`[x for x in os.listdir('.') if os.path.isdir(x)]`




幸运的是shutil模块提供了copyfile()的函数，你还可以在shutil模块中找到很多实用函数，它们可以看做是os模块的补充。




在操作系统中定义的环境变量，全部保存在os.environ这个变量中，要获取某个环境变量的值，可以调用os.environ.get('key')。



StringIO和BytesIO是在内存中操作str和bytes的方法，使得和读写文件具有一致的接口。



with语句来自动帮我们调用f.close()方法



动态语言的 “鸭子类型”，它并不要求严格的继承体系，一个对象只要 “看起来像鸭子，走起路来像鸭子”，那它就可以被看做是鸭子。




如果要获得一个对象的所有属性和方法，可以使用dir()函数，它返回一个包含字符串的list。调用len()函数试图获取一个对象的长度，实际上，在len()函数内部，它自动去调用该对象的__len__()方法



判断一个对象是否是函数,使用types模块中定义的常量



sys.path    所有已安装的内置模块和第三方模块，搜索路径存放在sys模块的path变量中



isinstance(object, classinfo)判断一个对象是否是一个已知的类型，类似 type()判断对象类型。还可以判断一个变量是否是某些类型中的一种isinstance([1, 2, 3], (list, tuple))




sys模块有一个argv变量，用list存储了命令行的所有参数。argv至少有一个元素，因为第一个参数永远是该.py文件的名称



sorted()函数也是一个高阶函数，它还可以接收一个key函数来实现自定义的排序，要进行反向排序，不必改动key函数，可以传入第三个参数reverse=True



filter()把传入的函数依次作用于每个元素，然后根据返回值是True还是False决定保留还是丢弃该元素。



reduce函数接收两个参数，一个是函数，函数必须接收两个参数，把结果继续和序列的下一个元素做累积计算。



map()函数接收两个参数，一个是函数，一个是Iterable，map将传入的函数依次作用到序列的每个元素，并把结果作为新的Iterator返回。



## for循环的对象统称为可迭代对象：Iterable。可以被next()函数调用并不断返回下一个值的对象称为迭代器：Iterator。

- 把list、dict、str等Iterable变成Iterator可以使用iter()函数

- Python的Iterator对象表示的是一个数据流，Iterator对象可以被next()函数调用并不断返回下一个数据。可以把这个数据流看做是一个有序序列，但我们却不能提前知道序列的长度，只能不断通过next()函数实现按需计算下一个数据，所以Iterator的计算是惰性的，只有在需要返回下一个数据时它才会计算。

- for循环本质上就是通过不断调用next()函数实现的



isinstance(object, classinfo)判断一个对象是否是一个已知的类型，类似 type()。



如果要对list实现类似Java那样的下标循环怎么办？Python内置的enumerate函数可以把一个list变成索引-元素对，这样就可以在for循环中同时迭代索引和元素本身



## 如何判断一个对象是可迭代对象

- `isinstance(123, Iterable) # 整数是否可迭代`




函数调用是通过栈（stack）这种数据结构实现的，每当进入一个函数调用，栈就会加一层栈帧，每当函数返回，栈就会减一层栈帧。由于栈的大小不是无限的，所以，递归调用的次数过多，会导致栈溢出。



`定义可变参数和定义一个list或tuple参数相比，仅仅在参数前面加了一个*号。在函数内部，参数numbers接收到的是一个tuple。Python允许你在list或tuple前面加一个*号，把list或tuple的元素变成可变参数传进去。`



Python的函数返回多值其实就是返回一个tuple，但写起来更方便。



数据类型检查可以用内置函数isinstance(),raise TypeError('bad operand type')



hex()函数把一个整数转换成十六进制表示的字符串



## Python中，数值类型（int和float）、字符串str、元组tuple都是不可变类型。而列表list、字典dict、集合set是可变类型。



## set集合

- set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。

- 通过add(key)方法可以添加元素到set中，可以重复添加，但不会有效果

- 通过remove(key)方法可以删除元素

- set可以看成数学意义上的无序和无重复元素的集合，因此，两个set可以做数学意义上的交集、并集等操作

- set和dict的唯一区别仅在于没有存储对应的value，但是，set的原理和dict一样，所以，同样不可以放入可变对象，因为无法判断两个可变对象是否相等，也就无法保证set内部“不会有重复元素”。试试把list放入set，看看是否会报错。

- 对于不变对象来说，调用对象自身的任意方法，也不会改变该对象自身的内容。相反，这些方法会创建新的对象并返回，这样，就保证了不可变对象本身永远是不可变的。



## Python的可变类型与不可变类型

- Python的每个对象都分为可变和不可变，主要的核心类型中，数字、字符串、元组是不可变的，列表、字典是可变的。

- 对不可变类型的变量重新赋值，实际上是重新创建一个不可变类型的对象，并将原来的变量重新指向新创建的对象（如果没有其他变量引用原有对象的话（即引用计数为0），原有对象就会被回收）。

- 对于不可变类型 int，无论创建多少个不可变类型，只要值相同，都指向同个内存地址。同样情况的还有比较短的字符串。

- 修改代码声明两个相同值的浮点型变量，查看它们的 id，发现它们并不是指向同个内存地址，这点和 int 类型不同（这方面涉及 Python 内存管理机制，Python 对 int 类型和较短的字符串进行了缓存，无论声明多少个值相同的变量，实际上都指向同个内存地址。）。



## list比较，dict有以下几个特点,dict是用空间来换取时间的一种方法

- 查找和插入的速度极快，不会随着key的增加而变慢；

- 需要占用大量的内存，内存浪费多



## dict避免key不存在的错误

- 通过in判断key是否存在

- 通过dict提供的get()方法，如果key不存在，可以返回None，或者自己指定的value    `d.get('Thomas', -1)`

- 要删除一个key，用pop(key)方法，对应的value也会从dict中删除



## range()函数，可以生成一个整数序列，再通过list()函数可以转换为list


## input输入的是str，int()把str转换成整数


## 非零数值、非空字符串、非空list等，就判断为True，否则为False


## tuple元祖

- tuple 和 list 非常类似，但是 tuple 一旦初始化就不能修改

- 没有 append()，insert() 这样的方法。其他获取元素的方法和 list 是一样的，你可以正常地使用classmates[0]，classmates[-1]，但不能赋值成另外的元素

- 不可变的 tuple 有什么意义？因为 tuple 不可变，所以代码更安全。如果可能，能用 tuple 代替 list 就尽量用 tuple。

- 只有 1 个元素的 tuple 定义时必须加一个逗号    括号()既可以表示 tuple，又可以表示数学公式中的小括号，这就产生了歧义，因此，Python 规定，这种情况下，按小括号进行计算，计算结果自然是1。

- tuple 的陷阱：当你定义一个 tuple 时，在定义的时候，tuple 的元素就必须被确定下来

- tuple 所谓的 “不变” 是说，tuple 的每个元素，指向永远不变。




## list列表

- 可以用-1做索引，直接获取最后一个元素

- append追加元素到末尾

- insert插入到指定的位置

- pop删除list末尾的元素

- 要把某个元素替换成别的元素，可以直接赋值给对应的索引位置



## format()

- 另一种格式化字符串的方法是使用字符串的format()方法，它会用传入的参数依次替换字符串内的占位符{0}、{1}……，不过这种方式写起来比%要麻烦得多

- ` 'Hello, {0}, 成绩提升了 {1:.1f}%'.format('小明', 17.125)`



## 输出格式化的字符串

- %运算符就是用来格式化字符串的。在字符串内部，%s表示用字符串替换，%d表示用整数替换，有几个%?占位符，后面就跟几个变量或者值，顺序要对应好。如果只有一个%?，括号可以省略。

- %s会把任何数据类型转换为字符串    `'Age: %s. Gender: %s' % (25, True)`

- 转义，用%%来表示一个%



```
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，Windows系统会忽略这个注释；
第二行注释是为了告诉Python解释器，按照UTF-8编码读取源代码，否则，你在源代码中写的中文输出可能会有乱码。
```


len()函数计算的是str的字符数



## 纯英文的str可以用ASCII编码为bytes，内容是一样的，含有中文的str可以用UTF-8编码为bytes。含有中文的str无法用ASCII编码，因为中文编码的范围超过了ASCII编码的范围，Python会报错

```py
>>> 'ABC'.encode('ascii')
b'ABC'
>>> '中文'.encode('utf-8')
b'\xe4\xb8\xad\xe6\x96\x87'
>>> '中文'.encode('ascii')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
UnicodeEncodeError: 'ascii' codec can't encode characters in position 0-1: ordinal not in range(128)



#从网络或磁盘上读取了字节流，那么读到的数据就是bytes。要把bytes变为str，就需要用decode()方法
>>> b'ABC'.decode('ascii')
'ABC'
>>> b'\xe4\xb8\xad\xe6\x96\x87'.decode('utf-8')
'中文
```



ord()函数获取字符的整数表示，chr()函数把编码转换为对应的字符。


采用8个比特（bit）作为一个字节（byte），所以，一个字节能表示的最大的整数就是255，这个编码表被称为ASCII编码

Unicode标准也在不断发展，但最常用的是用两个字节表示一个字符（如果要用到非常偏僻的字符，就需要4个字节）。代操作系统和大多数编程语言都直接支持Unicode。

本着节约的精神，又出现了把Unicode编码转化为“可变长编码”的UTF-8编码。UTF-8编码把一个Unicode字符根据不同的数字大小编码成1-6个字节，常用的英文字母被编码成1个字节，汉字通常是3个字节，只有很生僻的字符才会被编码成4-6个字节。

在计算机内存中，统一使用Unicode编码，当需要保存到硬盘或者需要传输的时候，就转换为UTF-8编码。用记事本编辑的时候，从文件读取的UTF-8字符被转换为Unicode字符到内存里，编辑完成后，保存的时候再把Unicode转换为UTF-8保存到文件



##Strip()

- 去掉字符串前后空格和`\n`




##map()

- 需要通过list()方法把map对象转化为列表




##文件读写操作

- 使用open('<文件路径>'， '<操作方式>')磁盘上读写文件的功能都是由操作系统提供的，现代操作系统不允许普通的程序直接操作磁盘，所以，读写文件就是请求操作系统打开一个文件对象（通常称为文件描述符），然后，通过操作系统提供的接口从这个文件对象中读取数据（读文件），或者把数据写入这个文件对象（写文件）。

- read()会一次性读取文件的全部内容，如果文件有10G，内存就爆了，所以，要保险起见，可以反复调用read(size)方法，每次最多读取size个字节的内容。另外，调用readline()可以每次读取一行内容，调用readlines()一次读取所有内容并按行返回list。因此，要根据需要决定怎么调用。

- 如果文件很小，read()一次性读取最方便；如果不能确定文件大小，反复调用read(size)比较保险；如果是配置文件，调用readlines()最方便

- 像open()函数返回的这种有个read()方法的对象，在Python中统称为file-like Object。除了file外，还可以是内存的字节流，网络流，自定义流等等。file-like Object不要求从特定类继承，只要写个read()方法就行。StringIO就是在内存中创建的file-like Object，常用作临时缓冲。

- close()方法关闭文件。文件使用完毕后必须关闭，因为文件对象会占用操作系统的资源，并且操作系统同一时间能打开的文件数量也是有限的

- 使用with...as...语句可以省去关闭文件f.close()这个步骤

- 可以反复调用write()来写入文件，但是务必要调用f.close()来关闭文件。当我们写文件时，操作系统往往不会立刻把数据写入磁盘，而是放到内存缓存起来，空闲的时候再慢慢写入。只有调用close()方法时，操作系统才保证把没有写入的数据全部写入磁盘。忘记调用close()的后果是数据可能只写了一部分到磁盘，剩下的丢失了。所以，还是用with语句来得保险

- 要写入特定编码的文本文件，请效仿codecs的示例，写入unicode，由codecs自动转换成指定编码。

- read读取全部文件

- readlines读取全部文件，并把每一行存在列表中

- readline读取文件的一行

- 指针模式：读取文件会记录指针，下次读取时从指针位置开始读取(只能读取未读取部分的内容)。写入也包含指针模式，如果写入时没有该文件，则会自动帮我们创建一个。

- write()写入文件，需要`\n`换行

- f.writelines(['First\n', 'Second\n', 'Third\n'])

- 追加和写入基本一样，区别在于：

    1. 写入是直接覆盖原文件，追加是在原文件基础上在后面追加内容
    
    2. 追加模式是小写字母a，写入是w
    
- 二进制模式:在模式后加上b可以进入二进制读取模式。就能对exe文件或者图像文件进行处理。而文件中的读取模式将以字节（bytes）的模式来读取。

```
f = open('workfile', 'rb')
f = open('workfile', 'wb')
f = open('workfile', 'ab')
f = open('workfile', 'rb+')
```

- 由于读取文件会存在很多不确定性，比如文件不存在、目录不存在等错误，我们可以用前一章节的异常处理来进行甄别

```
try:
    with open('workfile') as f:
        print(f.readlines())
except FileNotFoundError:
    print('File does not exist!')
```










