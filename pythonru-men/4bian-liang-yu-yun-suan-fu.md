##变量

- 变量命名可读性要强

- 首字符不能是数字

- 字母，下划线，数字

- 区分大小写

- 变量没有类型    动态语言

- 把type,print当做变量，不能再调用其方法




##int str tuple (不可改变) 值类型    list set dict (可变) 引用类型

- `'python'[0] = 'x'`会报错

- 元组定义不可改变的值，列表相反

```
a = [1,2,3]
a[0] = '1'
b = (1,2,3)
b[0] = '1'    //报错
```




##id()显示某一个变量在内存中的地址



##运算符

- 算数运算符：加+，减-，乘*，除/，取余%，整除//，幂`2**8`

- 赋值运算符

    - =，+=，-=,*=,/=,%=,**=,//=

- 比较(关系)运算符

    - `'a' > 'b'`比较的是asc码，ord('a')
    
    - `'abc'<'abd'`会把字母单独做比较，ord('abc')报错
    
    - `[1,2,3<[2,3,4]]`单独作比较
    
    - `(1,2,3)<(1,3,2)`单独比较

- 逻辑运算符： and,or,not；操作布尔类型，返回布尔类型，可以转换

- 成员运算符：in,not in；一个元素是否在另外的一组元素里；返回值是布尔；用于字符串、列表、元组、结合、字典

    - 字典是根据key来判断的。

- 身份运算符： is,not is；如果两个变量取值相等，则is返回True。

    - 关系运算符比较两个变量的--值是否相等
    
    - is比较的是两个变量的身份(内存地址)是否相等。
    
    
    


##各类型中的False，int中0，s空字符串''，空列表[]，空的元组、集合、字典





##如何判断变量的值、身份与类型

- 集合：由于集合的无序性，所以{1,2,3}和{3,2,1}比较结果是相等的，但它们的内存地址不相同。

- 值，身份，类型是对象的三个特征。

- 判断类型：isinstanceof

- type做类型判断是不能判断变量的子类是某种类型的。isinstanceof可以用。

```
a = 'hello'
isinstanceof(a,str)    //True

isinstanceof(a,(int,str,float))    //True
```




##位运算符，把数字当做二进制数进行运算

- &按位与

- |按位或

- ^按位异或

- ~按位取反

- `<<`左移动运算符

- `>>`右移动运算符


