##用字典映射代替switch case语句


```py
def get_sunday():
    return 'sunday'

def get_monday():
    return 'monday'

def get_tuesday():
    return 'tuesday'

def get_default():
    return 'unknow'

switcher = {
    0: get_sunday,
    1: get_monday,
    2: get_tuesday
}

day = 6

# dayName = switcher[day]

# get方法具有容错性
dayName = switcher.get(day, get_default)()

print(dayName)
```




##列表推导式

```
'''
    列表推导式
    集合推导式
    map filter
    set 也可以被推导
    dict
'''

a = [2,4,6,8,10,20,40,60]

b = [i**2 for i in a if i > 20]

c = {1,2,3,4,5,6,7}

d = {i**2 for i in c if i > 3}

students = {
    '喜小乐': 18,
    '石敢当': 20,
    '横小五': 15
}

e = {value: key for key,value in students.items()}

#元祖不可变，生成的是generator对象；推荐使用列表
f = (value for key, value in students.items())

for x in f:
    print(x)

print(f)

```




##None

- None是一种类型NoneType，不等同于'',[],False

- 判空操作，`if a`和`if not a`

```
print(type(None))

print('' is None)
```





##对象存在不一定是True

- 自定义对象的True和False是和内置方法`__len__`和`__bool__`有关

```
class Test():
    def __len__(self):
        print('len called')
        return 10
        #这里可以返回int类型或者bool类型

    def __bool__(self):
        print('bool called')
        return True
        #这里必须返回bool类型

#len方法需要对象内部定义__len__才可以调用
print(len(Test()))
#对象有了bool方法，不再调用len方法
print(bool(Test()))
```





















