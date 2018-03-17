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



