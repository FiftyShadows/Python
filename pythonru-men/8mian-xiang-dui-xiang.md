![](/assets/Python类.png)

## 类

* 最基本的作用：封装

* 类里的def为方法

* 模块里的def为函数

* 类的定义和类的实例化最好在不同的模块

* 类里的变量，称作数据成员

## 方法和函数的区别

* 方法是设计层面，面向对象里的概念

* 函数：程序运行、过程式的一种称谓

## 类与对象

* 类是现实世界或思维世界中的实体在计算机中的反应，它将数据以及这些数据上的操作封装在一起

* 行为与特征

## 构造函数

* 可以显式的调用构造函数

* 构造函数只能返回None，不能返回其他

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

## 区别模块变量与类中的变量

* 类变量：和类相关的变量

* 实例变量：和对象相关联的

* 类变量和具体的对象无关，在类中应该定义抽象的变量，定义具体的变量并没有意义

* 实例方法：和对象实例相关联

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

## self

* `student1.__dict__`dict是一个字典，保存着当前对象下所有的变量，但不包含类变量

* 如果访问一个实例变量，首先会在实例变量列表里面去查找，如果没有并不会返回空，而是到类变量列表里面寻找，如果没找到会到父类里去寻找

* self在定义实例方法时必须显式指定，self可以替换成其他参数

* self可以代表当前对象

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

## 在实例方法中访问类变量

* 第一种方式：用类来访问，Student.sum

* 第二种方式：用self来访问，`self.__class__`

* 实例方法通常用来操作实例变量的

## 类方法

* 类方法操作和类相关的变量

* 操作与对象无关的变量，最正确的是使用类方法

* 允许对象调用类方法，并不建议

* @classmethod，cls代表当前的类，可替换成其他名字

```
class Student():
    sum = 0
    @classmethod
    def plus_sum(cls):
        cls.sum += 1
```

## 静态方法

* 静态方法可以被类或者对象调用

* 可以访问类变量，跟类方法区别是，类方法传入cls，静态方法没有cls，静态方法可以被类方法代替，类方法更方便通过cls访问类变量

* 不推荐使用，静态方法跟面向对象关联比较弱，类似普通方法

* 当静态方法和类或对象没有太大关系的时候，可以使用

* @staticmethod

```
class Student():
    sum = 0
    @staticmethod
    def add(x,y):
        print(Stident.sum)
        print(x + y)

Student.add(3,2)
```

## 类方法和静态方法都不可以访问实例变量

## 成员可见性：公开和私有

* 类内部访问和外部访问

* 不要直接对变量做外部的修改。对于类下面变量的更改，应该通过方法来完成；在方法中可以对输入的参数做容错，从而保护数据。如果是自己使用，可适当取舍

* 方法前面加\_\_来定义私有方法

* `__init__`这种格式的不是私有方法，也可以自定义这种方法

## 没有什么是不能访问

* 不能动态添加私有变量

* python并没有绝对的私有属性，但并不建议去访问

```py
class Student():
    sum = 0
    def __init__(self, name, age):
        self.name = name
        self.age = age
        self.__score = 0
    @classmethod
    def plus_sum(cls):
        cls.sum += 1
    def marking(self, score):
        self.__score = score
        print('分数是：' + str(self.__score))

student1 = Student('zhangsan', 18)
student1.marking(59)
student1.__score = 88
print(student1.__dict__)
print(student1._Student__score)
```

## 面向对象三大特性

* 继承性

* 封装性

* 多态性

## 继承

* 避免定义重复的方法和重复的变量

* 建议一个模块只写一个类

* 子类继承父类的类变量

* 类调用实例方法，在其他语言中不允许，python可以强制调用，例如Student.do\_homework\(''\)

* 开闭原则：代码扩展是开放的，但对代码本身的更改是关闭的；`Human.__init__`这种方法不可取

```
class Human():
    sum = 88
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def getName(self):
        print(self.name)

class Student(Human):
    def __init__(self, name, age, school):
        #普通方法的调用，需要把参数都传进去。另，类调用实例方法，不合逻辑
        Human.__init__(self, name, age)
        self.school = school
    def do_homework(self):
        print('english homework')

student1 = Student('zhangsan', 18, 'middle school')
print(Student.sum)
print(student1.name)
print(student1.age)
print(student1.school)
print(student1.sum)
student1.getName()
```

## python相比其他编程语言的特殊之处：可以多继承；一个类可以有多个父类

## 子类方法调用父类方法：super关键字

* `super(Student, self).__init__(name, age)`

* 允许子类方法和父类方法同名，对象会优先调用子类的方法

```
class Human():
    sum = 88
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def getName(self):
        print(self.name)
    def do_homework(self):
        print('This is a parent method.')

class Student(Human):
    def __init__(self, name, age, school):
        super(Student, self).__init__(name, age)
        self.school = school
    def do_homework(self):
        super(Student, self).do_homework()
        print('do english homework')


student1 = Student('zhangsan', 18, 'middle school')
student1.do_homework()
```



