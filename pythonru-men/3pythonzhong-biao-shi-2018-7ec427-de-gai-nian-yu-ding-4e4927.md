##现实世界总是存在一组一组的事物




##列表

- type([1,2,3,4,5,6])

- 嵌套列表

- ['a','b','c','d'][2]单一数字索引访问得到的将是字符串

- ['a','b','c','d'][-1:]冒号形式得到的还是一个列表

- ['a','b','c','d']+['e','f','g']

- ['a','b']*3 == ['a', 'b', 'a', 'b', 'a', 'b']





##元组

- (1,2,3,4,5,6)    (1,2,3,4,5,6)[0]    (1,2,3,4,5,6)[0:3]

- (1,2,3)+(4,5,6)    (1,2,3)*3

```
type((1))    //int
type(('hello'))    //str
```

- ()既可以表示元组，又可以表示数学运算符号    (1)会优先解析为数学运算符

- 表示只有一个元素的元组(1,)

- 表示没有元素的元组type(())

- int,float,bool,str,list,tuple

- str list tuple序列

    - 共有的操作,每个元素都会被分配一个序号
    
    - 切片，[0:3]
    
    - "hello world"[0:8:2]    2表示元素之间的步进制
    
- 3 in [1,2,3,4]    返回布尔值

- 3 not in [1,2,3,4,5]

- len([1,2,3,4,5])

- max([1,2,3,4,5,6])

- min()

- ord()将参数转换成ascll码




##集合set

- 无序

- type({1,2,3,4,5,6})

- 不重复



- len()长度判断

- 1 in {1,2,3,4}判断集合是否包含某个元素

- 1 not in {1,2,3,4}

- {1,2,3,4,5,6} - {3,4}    求两个集合的差集

- {1,2,3,4,5,6} & {3,4}    求两个集合共有元素    交集

- {1,2,3,4,5,6} | {3,4，7}    合集，并集

- 定义一个空的集合    type(set())





##字典dict

- 通过key关键字，找到value值

- 很多个key和value，集合类型(set)，无序的，不是序列

- {key1:value1,key2:value2}


- 通过key访问

- 字典不能有相同的key

    - {'Q':'abc','Q':'efg'}
    
- {1:'新月打击','1':'苍白之瀑'}    字典的键不一定非得是字符串

- value: str int float list set dict

- key: 必须是不可变的类型    int,str都是不可变类型

- 空的字典表示方法{}，type({})




##总结

![](/assets/360截图20180315000133125.jpg)





