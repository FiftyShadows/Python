?代表非贪婪，放在要匹配的字符之前


##正则表达式

- import re

- re.findall('python', a)返回一个列表

```
import re
a = 'c|c++|java|c#|python|js'
r = re.findall('python', a)
print(r)    #['python']
if len(r) > 0:
    print('ok')
```




##元字符和普通字符

- \d等

- 普通字符用于定界





##字符集

- 取反操作`[^cf]`

- 利用字符顺序省略`[c-f]`





##概括字符集

- `\w`和`[a-zA-Z0-9_]`等价

- `\s`匹配空白字符

- `\d`数字

- .除换行符外任意字符




##量词

- `{3,6}`贪婪匹配





##贪婪和非贪婪

- 默认贪婪匹配

- 非贪婪的表示`{3,6}?`；这里的?是关键字，非量词





##0次、1次、无限多次

- *：0到无限次

- +：1到无限次

- ?：0或1次；字符串去重




##边界匹配符

- ^和$




##组

- ()




##匹配模式参数

- `r = re.findall('c#.{1}', s, re.I | re.S)`I表示忽略大小写，S表示可以匹配`\n`





##re.sub正则替换

- re.sub(reg, '', str, 0)，第四个参数0表示无限替换，或者替换n个

- str.replace()**由于字符串不可变性，原字符串不会被替换，只会返回**

```py
import re
s = 'javaC#alsjdC#akshdkaC#hakndaC#adnajdC#'
def convert(value):
    matched = value.group()
    return '!!' + matched + '!!'
s = re.sub('C#', convert, s)
print(s)
```




##把函数作为参数传递

- 注意获得的是字符串，返回的也必须是字符串

- 灵活的设计方式：接收一个函数作为参数的方式





##search与match函数

- match从一个开始匹配，匹配不到则返回None，匹配到则返回对象

- search返回匹配到的第一个的对象




##group分组

```
import re
s = 'Life is short, I use python.I love python.'
r1 = re.search('Life(.*)python(.*)python', s)
print(r1.group(0, 1, 2))
print(r1.groups())
r2 = re.findall('Life(.*)python(.*)python', s)
print(r2)
```




##常用正则表达式






##JSON

- JavaScript Object Notation；JS对象标记

- 是一种轻量级的数据交换格式

- 字符串是JSON的表现形式

- 符合JSON格式的字符串叫做JSON字符串

- 易于阅读、易于解析、网络传输效率高、跨语言交换数据




##反序列化

- JSON有JSON对象和JSON数组

- JSON中数字和布尔值不需要加引号，布尔值为false/true，解析成python后为False/True

- 发序列化：由字符串到语言下的某种数据结构的过程

```py
import json
s = json.loads(xx)
```





##序列化

- json数据类型和python的转化关系

- 序列化方法；json.dumps()

```
JSON    PYTHON    
object    dict
array    list
string    str
number    int
number    float
true    True
false    False
null    None
```



##存储对象到数据库

- 序列化和反序列化的方式效率太低

- 拆成二维表结构在mysql中存储；或者在nosql(mongodb)





##JSON总结

- ECMAScript标准的实现：JavaScript,ActionScript,JSON

- REST服务的标准格式

- 传输数据的一种格式























