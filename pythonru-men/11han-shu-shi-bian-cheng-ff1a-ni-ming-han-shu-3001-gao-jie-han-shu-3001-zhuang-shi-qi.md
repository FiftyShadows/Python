## 匿名函数

* 匿名函数\(lambada表达式\)

* 冒号后边只能是表达式，不能是代码块

```
f = lambda x,y: x+y
```

## 三元表达式

* 条件为真时返回的结果 if 条件判断 else 条件为假时返回的结果

* 三元表达式适合与lambda表达式搭配使用

## map    推荐使用

* map可与lambada搭配使用

* map\(func, \*iterables\)    星号代表可变参数

* 列表传入个数必须和lambada表达式参数个数相同；结果列表的长度取决于传入的列表最小的长度

* map和lambada并不能提升运行效率，只是代码更加简洁

```
list_x = [1,2,3,4,5,6,7,8,9]
def square(x):
    return x*x
r = map(square, list_x)
print(list(r))

r1 = map(lambda x: x*x, list_x)
```

## reduce

* reduce的第三个参数表示x的初始值；不同于sum求和函数

* lambada必须传入两个参数

* map/reduce    大数据 编程模型    映射    规约    并行计算

```
list_x = [1,2,3,4,5,6,7,8]
r = reduce(lambda x,y: x+y, list_x)
(((1+2)+3)+4)+5
```

## filter

* 判断字母大小写：数据处理时，依靠大写字母判断是不是句子的开头。

```
list_x = [1,0,0,1,0,0,1,0,0,0]
filter(lambda x: x == 1, list_x)
```

## 命令式编程vs函数式编程

* 命令式编程；def, if else, for

* 函数式编程：map,reduce,filter,lambda算子

## 装饰器

* 更改函数的功能，要遵循开闭原则

* 新增加的需求属于函数本身的，现在把实现放在了函数外；并没有体现函数本身的特性

```
import time
def f1():
    print('This is a func.')
def f2():
    print('This is anothre func.')

def print_current_time(func):
    print(time.time())
    func()

 print_current_time(f1) 
 print_current_time(f2)
```

* 装饰器是一种模式

* 可以接受定义时候的复杂，但不能接受调用时候的复杂

* python的装饰器体现了AOP的编程思想

```
import time
def decorator(func):
    def wrapper(func):
        print(time.time())
        func()
    return wrapper

@decorator
def f1():
    print('This is a func.')

f1()

#f = decorator(f1)
#f()
```



## 装饰器传参

* 可变参数\*args

```py
import time

def decorator(fnc):
    def wrapper(*args):
        print(time.time())
        fnc(*args)
    return wrapper

@decorator
def f1(username, id):
    print('This is' + username + id)

f1('zhangsan', '666');
```




##装饰器完整形态

- 关键字可变参数；传入多个关键字参数

```
import time

def decorator(fnc):
    def wrapper(*args, **kw):
        print(time.time())
        fnc(*args, **kw)
    return wrapper

@decorator
def f1(username, id):
    print('This is' + username + id)
```




##装饰器应用

- 代码稳定性：不去改变函数的具体实现，通过装饰器改变函数行为

- 代码复用性








