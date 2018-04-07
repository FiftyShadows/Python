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




















