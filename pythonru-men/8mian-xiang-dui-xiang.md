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
student.__init_
print(student.name, student.age)
```




##区别模块变量与类中的变量

- 类变量：和类相关的变量

- 实例变量：和对象相关联的

- 类变量和具体的对象无关，在类中应该定义抽象的变量，定义具体的变量并没有意义

- 实例方法：和对象实例相关联

```py
class Student():
    #类变量
    sum = 88
    def __init__(self, name, age):
        #实例变量
        self.name = name
        self.age = age
    def do_homeword(self):
        print('I am doing homework.')

student = Student('zhangsan','18')
student.__init__('s', 22)
print(student.name, student.age, student.sum)
```



##self

- `student1.__dict__`dict是一个字典，保存着当前对象下所有的变量，但不包含类变量

- 如果访问一个实例变量，首先会在实例变量列表里面去查找，如果没有并不会返回空，而是到类变量列表里面寻找，如果没找到会到父类里去寻找


- self在定义实例方法时必须显式指定，调用实例变量时用self传参，self可以替换成其他参数

```
class Student():
    name = 'qiyue'
    age = 22
    def __init__(self, name, age):
        self.name = name
        self.age = age
        print(self)
    def do_homework():
        pass

student1 = Student('石敢当', 18)
print(student1.__dict__)
print(Student.__dict__)
```



##在实例方法中访问类变量

- 第一种方式：用类来访问，Student.sum

- 第二种方式：用self来访问，`self.__class__`









