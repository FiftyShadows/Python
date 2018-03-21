##枚举其实是一个类

- 枚举用来表示不同的类型；可读性更高

- 枚举的意义重在标签而非数值；标签大写

- 不能定义两个相同的标签

- 可以有两个枚举类型的值相等，第二个标签相当于第一个的别名;第二个并非是一个独立的枚举，所以遍历时不会遍历到它。要想遍历到含别名的枚举类型，需要遍历`VIP.__members__.items()`或者`VIP.__members__`

```
from enum import Enum
class VIP(Enum):
    YELLOW = 1
    GREEN = 1
    RED = 2
print(VIP.GREEN)    #VIP.YELLOW
```





##枚举和普通类相比有什么优势

- 不可变性

- 没有防止相同标签的功能

- 枚举是单例模式，不能够实例化

```
from enum import Enum

class VIP(Enum):
    YELLOW = 1
    GREEN = 1
    RED = 3
    BLACK = 4

print(type(VIP.YELLOW))
print(type(VIP.YELLOW.name))
print(VIP['YELLOW'])
```




##枚举类型、枚举名称与枚举值

- VIP.YELLOW.name    获取标签的名称

- VIP.YELLOW.value    获取标签的值

- 枚举的名称和枚举本身不同    VIP.YELLOW是枚举类型

- 枚举可遍历

```
for v in VIP:
    print(v)
```





##枚举的比较运算

- result = VIP.GREEN == 2    不会报错，但并没有意义

- result = VIP.GREEN == VIP.GREEN

- result = VIP.GREEN > VIP.BLACK   报错，枚举类型不可以比较 

- result = VIP.GREEN is VIP.GREEN    可以做身份比较

- result = VIP.GREEN == VIP1.GREEN    不会报错；但并没有意义





##枚举注意事项

- 相同标签名和相同标签值





##枚举转换

- 数据库中可以用数字存储枚举类型；简洁，占用数据库空间小

- 代码中不建议用数字代表类型

- 把数据库中的数字转换成枚举类型：VIP(a);使用数值访问具体的枚举类型

```
#1.可读性 2.性能
if a == VIP.YELLOW:
    print()
if a == VIP.BLACK:
    print()
    
    
a = 1
print(VIP(a))    #VIP.YELLOW
```




##枚举小结

- `from enum import IntEnum`强制要求枚举类型值为数字

- 加unique装饰器，让不同枚举类型不能取相同的值

- 枚举是单例模式，不能够实例化

- 扩展是开放的，修改是关闭的

```
from enum import IntEnum,unique
@unique
class VIP(IntEnum):
    YELLOW = 1
    GREEN = 2
```



##基础知识与高阶知识关系

- 基础知识可以写出代码，而高阶知识可以写出优质可维护的代码

- 业务逻辑开发者，不考虑太多的封装性，高阶知识用处并不大

- 包、类库的开发者；非常有用





##闭包

- 闭包：由函数和它在定义时外部的环境变量所构成的一个整体

- 调用闭包函数时，不仅仅返回了函数，实际上返回的是闭包，把函数和环境变量都返回回来了；保存在`callback.__closure__`内置对象里；`callback.__closure__[0].cell_contents`可以取到变量

- 闭包 = 函数 + 环境变量（函数定义时候）

```
def f1():
    a = 10
    def f2():
        a = 20
        print(a)
    print(a)
    f2()
    print(a)

f1()
```




##闭包误区

- 只有内部函数引用了环境变量，才能成为闭包

```py
def f1():
    a = 10
    #没有引用这里的环境变量，不能成为闭包
    def f2():
        #a被python认为是一个局部变量
        a = 20
        print(a)
    print(a)
    f2()
    print(a)

f1()
```



##闭包的应用




















