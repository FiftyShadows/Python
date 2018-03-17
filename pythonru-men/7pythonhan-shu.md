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

```
def damage(skill1, skill2):
    damages1 = skill1 * 3
    damages2 = skill2 * 2 + 10
    return damages1, damages2
#序列解包
skill1_damage, skill2_damage = damage(2,3)
print(skill1_damage, skill2_damage)
```



