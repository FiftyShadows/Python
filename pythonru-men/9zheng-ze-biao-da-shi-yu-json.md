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



























