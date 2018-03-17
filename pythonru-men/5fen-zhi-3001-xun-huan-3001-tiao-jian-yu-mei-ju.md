##表达式

- 表达式是运算符和操作数所构成的序列。

- 从左向右，左结合。

- 如果有赋值运算符，则右结合。

![](/assets/360截图20180317131955905.jpg)





##开发工具

- pycharm vscode

- 智能感知，断点调试

- ctrl + p检索文件

- 单行注释#

- 多行注释'''    alt + shift + a

- 不可压缩，混合

- python建议用下划线分割两个组合单词

- 常量所有字母大写

- python建议每个模块都应该有模块说明

- pass占位语句

- 要有封装思维，而非面向过程





##流程控制语句之条件控制

- elif简化代码级别，代码行数

- elif不能单独使用，配合if使用

- 没有switch语句

- input()接收到的是字符串



```
#接收到的是字符串类型
a = input()
print('a is ' + a)
a = int(a)
if a == 1:
    print('apple')
else:
    if a == 2:
        print('orange')
    else:
        if a == 3:
            print('banana')
        else:
            print('shopping')
```

```
a = input()
a = int(a)
if a == 1:
    print('apple')
elif a == 2:
    print('orange')
elif a == 3:
    print('banana')
else:
    print('shopping')
```





