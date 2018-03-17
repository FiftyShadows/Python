##函数

- round()四舍五入，第一个参数操作的变量，第二个参数小数点位数

- 查看内置函数

    - 进入python命令行
    
    - help(round)
    
    - import this查看python之禅
    
1. 功能性

2. 隐藏细节

3. 避免编写重复的代码






##自定义函数

- 设置最大递归次数；

```
import sys
sys.setrecursionlimit(10000)
```

- 函数多结果的返回

- 参数

    - 必须参数，定义的参数个数要和传入的个数一致，形参和实参
    
    - 关键字参数，让实参和形参相对应，不用考虑顺序，增加代码可读性`c = add(y=3,x=2)`
    
    - 默认参数，可用关键字参数给默认参数赋值，但传参时不可以把必须参数放在默认参数后边

```
def damage(skill1, skill2):
    damages1 = skill1 * 3
    damages2 = skill2 * 2 + 10
    return damages1, damages2
#序列解包
skill1_damage, skill2_damage = damage(2,3)
print(skill1_damage, skill2_damage)
```



##序列解包与链式赋值

- 两边的个数要相等

```
d = 5,6,7,8
type(d)
a,b,c,e = d
print(a,b,c,e)
```


