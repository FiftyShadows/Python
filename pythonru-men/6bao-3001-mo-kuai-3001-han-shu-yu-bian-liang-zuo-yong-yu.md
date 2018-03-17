##while循环与使用场景

- 条件循环执行

- 递归

```
couter = 1
while couter <= 10:
    print(couter)
    couter += 1
else:
    print('EOF')
```



##for与for-else循环

- 主要是用来遍历/循环 序列或者集合、字典

- 循环执行完会执行else，但else并不常用

- if break跳出循环；**else也不会被执行**

- if continue 跳过当前循环，继续后边的循环

```
a = [['apple','orange','grape','banana'],(3,2,1,4)]

for x in a:
    for y in x:
        if y == 'orange':
            break
        print(y,end=' ')
else:
    print('over')
    
#会跳出内循环，但并不会影响外循环
```

- 通过range()遍历指定长度;三个参数为开始，结束，元素之间的步进制

```
for x in range(0,10,2):
    print(x,end=' | ')
    
a = [0,1,2,3,4,5,6,7,8,9,10]
b = a[0:len(a):2]
print(b)
```




##高性能、封装性(可复用)、抽象




##Python工程的组织结构：包、模块儿、类

- 包 -- 模块 -- 类 -- 函数、变量

- 命名空间：区分相同的模块，但是模块里的内容不相同

- 包可以包含子包

- 包内会包含__init__.py




##导入模块的两种方式

- 使用import导入模块，不能导入模块的变量`import t.c7 as m`

- `from t.c7 import a`导入的是具体的变量，也可以导入变量`from t import c7`，也可使用*导入所有的变量和函数，但是引入不明确

- 在模块中可以定义其他模块通过*引入的变量`__all__ = ['a','c']`

- 在一行的末尾加\将代码换行，或者加()




##__init__.py

- 当导入一个包或者一个包下的某一个模块时，__init__文件首先会被自动执行

- 通过`__all__ = ['c7']`定义哪些模块会被导出`from t import *`

- 批量导入，在__int__文件中导入系统类库，其他模块可通过导入包的形式导入系统类库

```
#t包的__init__.py
import sys
import datetime
import io

#c7.py
import t
print(t.sys.path)
```





##包与模块的几个常见错误

- 包和模块是不会被重复导入的

- 避免循环导入

- 导入模块时会执行模块内的代码



