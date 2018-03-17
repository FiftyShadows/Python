##类

- 最基本的作用：封装

- 类里的def为方法

- 模块里的def为函数

- 类的定义和类的实例化最好在不同的模块

- 类里的变量，称作数据成员



##方法和函数的区别

- 方法是设计层面，面向对象里的概念

- 函数：程序运行、过程式的一种称谓



##类与对象

- 类是现实世界或思维世界中的实体在计算机中的反应，它将数据以及这些数据上的操作封装在一起

- 行为与特征




##构造函数

- 可以显式的调用构造函数

- 构造函数只能返回None，不能返回其他

```
class Student():
    name = ''
    age = 0
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def do_homeword(self):
        print('I am doing homework.')

student = Student('zhangsan','18')

print(student.name, student.age)
```




##区别模块变量与类中的变量













