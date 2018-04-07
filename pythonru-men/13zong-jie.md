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



















