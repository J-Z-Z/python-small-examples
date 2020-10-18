
#### 1 实现 relu

在神经网络中，`relu`作为神经元的激活函数， 实际上是和0比大小。
如果输入的值大于0，返回这个数字； 
如果输入值值小于等于0，返回0；

max 系统自带函数， 返回参数中最大的那个值。参数可以是两个及以上的，或者是一个非空的集合。
```python

def relu(x):
    """
    x: 输入参数
    return：输出relu值
    """
    return max(0,x)                                                                 
```

测试：

```python
relu(5) # 5

relu(-1) # 0

>>> max(1,2,3,4,5)
5
>>> max([1,2,3,4,5])
5
```


#### 2  进制转化

十进制转换为二进制：
```python
In [2]: bin(10)                                                                 
Out[2]: '0b1010'
```

十进制转换为八进制：
```python
In [3]: oct(9)                                                                  
Out[3]: '0o11'
```

十进制转换为十六进制：
```python
In [4]: hex(15)                                                                 
Out[4]: '0xf'
```

#### 3 整数和ASCII互转

十进制整数对应的`ASCII字符`

```python
In [1]: chr(65)
Out[1]: 'A'
```

查看某个`ASCII字符`对应的十进制数
```python
In [1]: ord('A')
Out[1]: 65

ASCII ((American Standard Code for Information Interchange): 美国信息交换标准代码）是基于拉丁字母的一套电脑编码系统，主要用于显示现代英语和其他西欧语言。它是最通用的信息交换标准，并等同于国际标准ISO/IEC 646。ASCII第一次以规范标准的类型发表是在1967年，最后一次更新则是在1986年，到目前为止共定义了128个字符 [1]  。
'A'-65, 'B'-66, 'C'-67, 'D'-68, ...
'a'-97, 'b'-98, 'c'-99, 'd'-100, ...
'0'-48, '1'-49, '2'-50, '3'-51  ...
详细参考链接[ASCII的说明](https://baike.baidu.com/item/ASCII)

```


#### 4 元素都为真检查

所有元素都为真，返回 `True`，否则为`False`  
内置函数： all(iterable)   
  如果 iterable 的所有元素均为真值（或可迭代对象为空）则返回 True 。  
 
```python
In [5]: all([1,0,3,6])                                                          
Out[5]: False
```
```python
In [6]: all([1,2,3])                                                            
Out[6]: True
```

#### 5 至少一个为真检查　

至少有一个元素为真返回`True`，否则`False`
any(iterable)
  如果 iterable 的任一元素为真值则返回 True。 
  如果可迭代对象为空，返回 False。

```python
In [7]: any([0,0,0,[]])                                                         
Out[7]: False
```

```python
In [8]: any([0,0,1])                                                            
Out[8]: True
```

#### 6 判断是真是假　　

测试一个对象是True, 还是False.
```python
In [9]: bool([0,0,0])                                                           
Out[9]: True

In [10]: bool([])                                                               
Out[10]: False

In [11]: bool([1,0,1])                                                          
Out[11]: True
```

#### 7  创建复数
  
创建一个复数  
  我们把形如z=a+bi（a,b均为实数）的数称为复数，其中a称为实部，b称为虚部，i称为虚数单位。  
  
```python

In [1]: complex(1,2)
Out[1]: (1+2j)
```

#### 8 取商和余数　　
  
分别取商和余数  
 使用内置函数divmod它将两个（非复数）数字作为实参，并在执行整数除法时返回一对商和余数。  
 
```python
In [1]: divmod(10,3)
Out[1]: (3, 1)
```
#### 9 转为浮点类型　

将一个整数或数值型字符串转换为浮点数

```python
In [1]: float(3)
Out[1]: 3.0
```

如果不能转化为浮点数，则会报`ValueError`:

```python
In [2]: float('a')
# ValueError: could not convert string to float: 'a'
```

#### 10  转为整型　　

int(x, base =10) , x可能为字符串或数值，将x转换为一个普通整数。如果参数是字符串，那么它可能包含符号和小数点。如果超出了普通整数的表示范围，一个长整数被返回。  

```python
In [1]: int('12',16)  #将16进制的'12'转化为10进制，是18.
Out[1]: 18

>>> int('20', 8)
16
>>> int('20', 12)
24
```

#### 11 次幂

base为底的exp次幂，如果mod给出，取余
pow(x, y) 方法返回 xy（x 的 y 次方） 的值。
```python
In [1]: pow(3, 2, 4)
Out[1]: 1
>>> pow(2,3)
8
>>> pow(2,9)
512
>>> pow(2,5)
32
>>> pow(2,5,16)
0
>>> pow(2,5,3)
2
>>> pow(2,5,4)
0
```

#### 12 四舍五入

四舍五入，`ndigits`代表小数点后保留几位：

```python
In [11]: round(10.0222222, 3)
Out[11]: 10.022

In [12]: round(10.05,1)
Out[12]: 10.1
```

#### 13 链式比较

```python
i = 3
print(1 < i < 3)  # False
print(1 < i <= 3)  # True
```

#### 14  字符串转字节　　

字符串转换为字节类型  
常见的字符编码有utf-8， GBK， GB18032等等。。 
因为不同的国家的字符有自己的编码方式，参见下面的链接  
[字符编码扩展阅读](https://baike.baidu.com/item/%E5%AD%97%E7%AC%A6%E7%BC%96%E7%A0%81)
```python
In [12]: s = "apple"                                                            

In [13]: bytes(s,encoding='utf-8')                                              
Out[13]: b'apple'

>>> s = 'aaa'
>>> bytes(s, encoding='utf-8')
b'aaa'
>>> bytes(s, encoding='utf-16')
b'\xff\xfea\x00a\x00a\x00'
>>> bytes(s, encoding='GBK')
b'aaa'
>>> s = '中国'
>>> bytes(s, encoding='GBK')
b'\xd6\xd0\xb9\xfa'
>>> bytes(s, encoding='utf-8')
b'\xe4\xb8\xad\xe5\x9b\xbd'
```

#### 15 任意对象转为字符串　　

```python
In [14]: i = 100                                                                

In [15]: str(i)                                                                 
Out[15]: '100'

In [16]: str([])                                                                
Out[16]: '[]'

In [17]: str(tuple())                                                           
Out[17]: '()'
```

#### 16 执行字符串表示的代码

将字符串编译成python能识别或可执行的代码，也可以将文字读成字符串再编译。  
compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)  
将 source 编译成代码或 AST 对象。代码对象可以被 exec() 或 eval() 执行。source 可以是常规的字符串、字节字符串。  
eval() 直接返回值就是表达式的求值结果
```python
In [1]: s  = "print('helloworld')"
    
In [2]: r = compile(s,"<string>", "exec")
    
In [3]: r
Out[3]: <code object <module> at 0x0000000005DE75D0, file "<string>", line 1>
    
In [4]: exec(r)
helloworld
>>> eval(s)   # 直接输出字符串的语句的执行结果 见17
helloworld
```

#### 17 计算表达式

将字符串str 当成有效的表达式来求值并返回计算结果取出字符串中内容
eval() 直接返回值就是表达式的求值结果
```python

In [1]: s = "1 + 3 +5"
    ...: eval(s)
Out[1]: 9
```

#### 18 字符串格式化　

格式化输出字符串，format(value, format_spec)实质上是调用了value的__format__(format_spec)方法。
字符串的格式化，有多种方法，请参加[格式化输出](https://docs.python.org/zh-cn/3/tutorial/inputoutput.html)
```
In [104]: print("i am {0},age{1}".format("tom",18))
i am tom,age18
```

| 3.1415926  | {:.2f}  | 3.14      | 保留小数点后两位             |
| ---------- | ------- | --------- | ---------------------------- |
| 3.1415926  | {:+.2f} | +3.14     | 带符号保留小数点后两位       |
| -1         | {:+.2f} | -1.00     | 带符号保留小数点后两位       |
| 2.71828    | {:.0f}  | 3         | 不带小数                     |
| 5          | {:0>2d} | 05        | 数字补零 (填充左边, 宽度为2) |
| 5          | {:x<4d} | 5xxx      | 数字补x (填充右边, 宽度为4)  |
| 10         | {:x<4d} | 10xx      | 数字补x (填充右边, 宽度为4)  |
| 1000000    | {:,}    | 1,000,000 | 以逗号分隔的数字格式         |
| 0.25       | {:.2%}  | 25.00%    | 百分比格式                   |
| 1000000000 | {:.2e}  | 1.00e+09  | 指数记法                     |
| 18         | {:>10d} | ' 18'     | 右对齐 (默认, 宽度为10)      |
| 18         | {:<10d} | '18 '     | 左对齐 (宽度为10)            |
| 18         | {:^10d} | ' 18 '    | 中间对齐 (宽度为10)          |

#### 19 拿来就用的排序函数

排序： 
sorted(iterable, *, key=None, reverse=False)  
根据 iterable 中的项返回一个新的已排序列表。  

具有两个可选参数，它们都必须指定为关键字参数。  


```python
In [1]: a = [1,4,2,3,1]

In [2]: sorted(a,reverse=True)
Out[2]: [4, 3, 2, 1, 1]

In [3]: a = [{'name':'xiaoming','age':18,'gender':'male'},{'name':'
     ...: xiaohong','age':20,'gender':'female'}]
In [4]: sorted(a,key=lambda x: x['age'],reverse=False)
Out[4]:
[{'name': 'xiaoming', 'age': 18, 'gender': 'male'},
 {'name': 'xiaohong', 'age': 20, 'gender': 'female'}]
```

#### 20 求和函数

求和：

```python
In [181]: a = [1,4,2,3,1]

In [182]: sum(a)
Out[182]: 11

In [185]: sum(a,10) #求和的初始值为10
Out[185]: 21
```

#### 21 nonlocal用于内嵌函数中

关键词`nonlocal`常用于函数嵌套中，声明变量`i`为非局部变量；
如果不声明，`i+=1`表明`i`为函数`wrapper`内的局部变量，因为在`i+=1`引用(reference)时,i未被声明，所以会报`unreferenced variable`的错误。

```python
def excepter(f):
    i = 0
    t1 = time.time()
    def wrapper(): 
        try:
            f()
        except Exception as e:
            nonlocal i
            i += 1
            print(f'{e.args[0]}: {i}')
            t2 = time.time()
            if i == n:
                print(f'spending time:{round(t2-t1,2)}')
    return wrapper
```

#### 22 global 声明全局变量

先回答为什么要有`global`，一个变量被多个函数引用，想让全局变量被所有函数共享。有的伙伴可能会想这还不简单，这样写：

```python
i = 5
def f():
    print(i)

def g():
    print(i)
    pass

f()
g()

```

f和g两个函数都能共享变量`i`，程序没有报错，所以他们依然不明白为什么要用`global`.

但是，如果我想要有个函数对`i`递增，这样：

```python
def h():
    i += 1

h()
```

此时执行程序，bang, 出错了！ 抛出异常：`UnboundLocalError`，原来编译器在解释`i+=1`时会把`i`解析为函数`h()`内的局部变量，很显然在此函数内，编译器找不到对变量`i`的定义，所以会报错。

`global`就是为解决此问题而被提出，在函数h内，显式地告诉编译器`i`为全局变量，然后编译器会在函数外面寻找`i`的定义，执行完`i+=1`后，`i`还为全局变量，值加1：

```python
i = 0
def h():
    global i
    i += 1

h()
print(i)
```

#### 23 交换两元素

```python
def swap(a, b):
    return b, a


print(swap(1, 0))  # (0,1)
```

#### 24 操作函数对象

```python
In [31]: def f():
    ...:     print('i\'m f')
    ...:

In [32]: def g():
    ...:     print('i\'m g')
    ...:

In [33]: [f,g][1]()
i'm g
```

创建函数对象的list，根据想要调用的index，方便统一调用。

#### 25 生成逆序序列

```python
list(range(10,-1,-1)) # [10, 9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
```

第三个参数为负时，表示从第一个参数开始递减，终止到第二个参数(不包括此边界)

#### 26 函数的五类参数使用例子

python五类参数：位置参数，关键字参数，默认参数，可变位置或关键字参数的使用。

```python
def f(a,*b,c=10,**d):
  print(f'a:{a},b:{b},c:{c},d:{d}')
```

*默认参数`c`不能位于可变关键字参数`d`后.*

调用f:

```python
In [10]: f(1,2,5,width=10,height=20)
a:1,b:(2, 5),c:10,d:{'width': 10, 'height': 20}
```

可变位置参数`b`实参后被解析为元组`(2,5)`;而c取得默认值10; d被解析为字典.

再次调用f:

```python
In [11]: f(a=1,c=12)
a:1,b:(),c:12,d:{}
```

a=1传入时a就是关键字参数，b,d都未传值，c被传入12，而非默认值。

注意观察参数`a`, 既可以`f(1)`,也可以`f(a=1)` 其可读性比第一种更好，建议使用f(a=1)。如果要强制使用`f(a=1)`，需要在前面添加一个**星号**:

```python
def f(*,a,**b):
  print(f'a:{a},b:{b}')
```

此时f(1)调用，将会报错：`TypeError: f() takes 0 positional arguments but 1 was given`

只能`f(a=1)`才能OK.

说明前面的`*`发挥作用，它变为只能传入关键字参数，那么如何查看这个参数的类型呢？借助python的`inspect`模块：

```python
In [22]: for name,val in signature(f).parameters.items():
    ...:     print(name,val.kind)
    ...:
a KEYWORD_ONLY
b VAR_KEYWORD
```

可看到参数`a`的类型为`KEYWORD_ONLY`，也就是仅仅为关键字参数。

但是，如果f定义为：

```python
def f(a,*b):
  print(f'a:{a},b:{b}')
```

查看参数类型：

```python
In [24]: for name,val in signature(f).parameters.items():
    ...:     print(name,val.kind)
    ...:
a POSITIONAL_OR_KEYWORD
b VAR_POSITIONAL
```

可以看到参数`a`既可以是位置参数也可是关键字参数。

#### 27  使用slice对象

生成关于蛋糕的序列cake1：

```python
In [1]: cake1 = list(range(5,0,-1))

In [2]: b = cake1[1:10:2]

In [3]: b
Out[3]: [4, 2]

In [4]: cake1
Out[4]: [5, 4, 3, 2, 1]
```

再生成一个序列：

```python
In [5]: from random import randint
   ...: cake2 = [randint(1,100) for _ in range(100)]
   ...: # 同样以间隔为2切前10个元素，得到切片d
   ...: d = cake2[1:10:2]
In [6]: d
Out[6]: [75, 33, 63, 93, 15]
```

你看，我们使用同一种切法，分别切开两个蛋糕cake1,cake2. 后来发现这种切法`极为经典`，又拿它去切更多的容器对象。

那么，为什么不把这种切法封装为一个对象呢？于是就有了slice对象。

定义slice对象极为简单，如把上面的切法定义成slice对象：

```python
perfect_cake_slice_way = slice(1,10,2)
#去切cake1
cake1_slice = cake1[perfect_cake_slice_way] 
cake2_slice = cake2[perfect_cake_slice_way]

In [11]: cake1_slice
Out[11]: [4, 2]

In [12]: cake2_slice
Out[12]: [75, 33, 63, 93, 15]
```

与上面的结果一致。

对于逆向序列切片，`slice`对象一样可行：

```python
a = [1,3,5,7,9,0,3,5,7]
a_ = a[5:1:-1]

named_slice = slice(5,1,-1)
a_slice = a[named_slice] 

In [14]: a_
Out[14]: [0, 9, 7, 5]

In [15]: a_slice
Out[15]: [0, 9, 7, 5]
```

频繁使用同一切片的操作可使用slice对象抽出来，复用的同时还能提高代码可读性。

#### 28  lambda 函数的动画演示

有些读者反映，`lambda`函数不太会用，问我能不能解释一下。

比如，下面求这个 `lambda`函数：

```python
def max_len(*lists):
    return max(*lists, key=lambda v: len(v))
```

有两点疑惑：

- 参数`v`的取值？ 
- `lambda`函数有返回值吗？如果有，返回值是多少？

调用上面函数，求出以下三个最长的列表：

```python
r = max_len([1, 2, 3], [4, 5, 6, 7], [8])
print(f'更长的列表是{r}')
```


结论：

- 参数v的可能取值为`*lists`，也就是 `tuple` 的一个元素。

- `lambda`函数返回值，等于`lambda v`冒号后表达式的返回值。

#### 29  转为字典　　

创建数据字典

```python
In [1]: dict()
Out[1]: {}

In [2]: dict(a='a',b='b')
Out[2]: {'a': 'a', 'b': 'b'}

In [3]: dict(zip(['a','b'],[1,2]))
Out[3]: {'a': 1, 'b': 2}

In [4]: dict([('a',1),('b',2)])
Out[4]: {'a': 1, 'b': 2}
```

#### 30 冻结集合　　

创建一个不可修改的集合。

```python
In [1]: frozenset([1,1,3,2,3])
Out[1]: frozenset({1, 2, 3})
```

因为不可修改，所以没有像`set`那样的`add`和`pop`方法

#### 31 转为集合类型

返回一个set对象，集合内不允许有重复元素：

```python
In [159]: a = [1,4,2,3,1]

In [160]: set(a)
Out[160]: {1, 2, 3, 4}
```

#### 32 转元组

 `tuple()` 将对象转为一个不可变的序列类型

 ```python
 In [16]: i_am_list = [1,3,5]
 In [17]: i_am_tuple = tuple(i_am_list)
 In [18]: i_am_tuple
 Out[18]: (1, 3, 5)
 ```

#### 33 对象是否可调用　　

检查对象是否可被调用

```python
In [1]: callable(str)
Out[1]: True

In [2]: callable(int)
Out[2]: True
```

```python
In [18]: class Student(): 
    ...:     def __init__(self,id,name): 
    ...:         self.id = id 
    ...:         self.name = name 
    ...:     def __repr__(self): 
    ...:         return 'id = '+self.id +', name = '+self.name 
    ...

In [19]: xiaoming = Student('001','xiaoming')                                   

In [20]: callable(xiaoming)                                                     
Out[20]: False
```
如果能调用`xiaoming()`, 需要重写`Student`类的`__call__`方法：

```python
In [1]: class Student():
    ...:     def __init__(self,id,name):
    ...:         self.id = id
    ...:         self.name = name
    ...:     def __repr__(self):
    ...:         return 'id = '+self.id +', name = '+self.name
    ...:     def __call__(self):
    ...:         print('I can be called')
    ...:         print(f'my name is {self.name}')
    ...: 

In [2]: t = Student('001','xiaoming')

In [3]: t()
I can be called
my name is xiaoming
```

#### 34  ascii 展示对象　　

调用对象的 `__repr__` 方法，获得该方法的返回值，如下例子返回值为字符串

```python
>>> class Student():
    def __init__(self,id,name):
        self.id = id
        self.name = name
    def __repr__(self):
        return 'id = '+self.id +', name = '+self.name
```
调用：
```python
>>> xiaoming = Student(id='1',name='xiaoming')
>>> xiaoming
id = 1, name = xiaoming
>>> ascii(xiaoming)
'id = 1, name = xiaoming'
```

#### 35 类方法　

`classmethod` 装饰器对应的函数不需要实例化，不需要 `self `参数。

但第一个参数需要是表示自身类的 `cls` 参数，可以来调用类的属性，类的方法，实例化对象等。

```python
In [1]: class Student():
    ...:     def __init__(self,id,name):
    ...:         self.id = id
    ...:         self.name = name
    ...:     def __repr__(self):
    ...:         return 'id = '+self.id +', name = '+self.name
    ...:     @classmethod
    ...:     def f(cls):
    ...:         print(cls)
```

#### 36 动态删除属性　　

```python
>>> class Student():
    def __init__(self,id,name):
        self.id = id
        self.name = name
    def __repr__(self):
        return 'id = '+self.id +', name = '+self.name
```
调用：
```python
>>> xiaoming = Student(id='1',name='xiaoming')
>>> xiaoming
id = 1, name = xiaoming
>>> ascii(xiaoming)
'id = 1, name = xiaoming'
```

删除对象的属性

```python
In [1]: delattr(xiaoming,'id')

In [2]: hasattr(xiaoming,'id')
Out[2]: False
```

#### 37 一键查看对象所有方法　

不带参数时返回`当前范围`内的变量、方法和定义的类型列表；带参数时返回`参数`的属性，方法列表。

```python
In [96]: dir(xiaoming)
Out[96]:
['__class__',
 '__delattr__',
 '__dict__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__gt__',
 '__hash__',
 '__init__',
 '__init_subclass__',
 '__le__',
 '__lt__',
 '__module__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__setattr__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 '__weakref__',
 
 'name']
```

#### 38 动态获取对象属性　

获取对象的属性

```python
In [1]: class Student():
   ...:     def __init__(self,id,name):
   ...:         self.id = id
   ...:         self.name = name
   ...:     def __repr__(self):
   ...:         return 'id = '+self.id +', name = '+self.name

In [2]: xiaoming = Student(id='001',name='xiaoming')
In [3]: getattr(xiaoming,'name') # 获取xiaoming这个实例的name属性值
Out[3]: 'xiaoming'
```

#### 39 对象是否有某个属性

```python
In [1]: class Student():
   ...:     def __init__(self,id,name):
   ...:         self.id = id
   ...:         self.name = name
   ...:     def __repr__(self):
   ...:         return 'id = '+self.id +', name = '+self.name

In [2]: xiaoming = Student(id='001',name='xiaoming')
In [3]: hasattr(xiaoming,'name')
Out[3]: True

In [4]: hasattr(xiaoming,'address')
Out[4]: False
```

#### 40 对象门牌号　

```python
In [1]: class Student():
   ...:     def __init__(self,id,name):
   ...:         self.id = id
   ...:         self.name = name
   ...:     def __repr__(self):
   ...:         return 'id = '+self.id +', name = '+self.name

In [2]: xiaoming = Student(id='001',name='xiaoming')
```

返回对象的内存地址

```python
In [1]: id(xiaoming)
Out[1]: 98234208
```

#### 41 isinstance

判断*object*是否为类*classinfo*的实例，是返回true

```python
In [1]: class Student():
   ...:     def __init__(self,id,name):
   ...:         self.id = id
   ...:         self.name = name
   ...:     def __repr__(self):
   ...:         return 'id = '+self.id +', name = '+self.name

In [2]: xiaoming = Student(id='001',name='xiaoming')

In [3]: isinstance(xiaoming,Student)
Out[3]: True
```

#### 42 issubclass父子关系鉴定

```python
In [1]: class undergraduate(Student):
    ...:     def studyClass(self):
    ...:         pass
    ...:     def attendActivity(self):
    ...:         pass

In [2]: issubclass(undergraduate,Student)
Out[2]: True

In [3]: issubclass(object,Student)
Out[3]: False

In [4]: issubclass(Student,object)
Out[4]: True
```

如果class是classinfo元组中某个元素的子类，也会返回True

```python
In [1]: issubclass(int,(int,float))
Out[1]: True
```

#### 43 所有对象之根

object 是所有类的基类

```python
In [1]: o = object()

In [2]: type(o)
Out[2]: object
```

#### 44  创建属性的两种方式

返回 property 属性，典型的用法：

```python
class C:
    def __init__(self):
        self._x = None

    def getx(self):
        return self._x

    def setx(self, value):
        self._x = value

    def delx(self):
        del self._x
    # 使用property类创建 property 属性
    x = property(getx, setx, delx, "I'm the 'x' property.")
```

使用python装饰器，实现与上完全一样的效果代码：

```python
class C:
    def __init__(self):
        self._x = None

    @property
    def x(self):
        return self._x

    @x.setter
    def x(self, value):
        self._x = value

    @x.deleter
    def x(self):
        del self._x
```

#### 45 查看对象类型

*class* `type`(*name*, *bases*, *dict*)

传入一个参数时，返回 *object* 的类型：

```python
In [1]: class Student():
   ...:     def __init__(self,id,name):
   ...:         self.id = id
   ...:         self.name = name
   ...:     def __repr__(self):
   ...:         return 'id = '+self.id +', name = '+self.name
   ...: 

In [2]: xiaoming = Student(id='001',name='xiaoming')
In [3]: type(xiaoming)
Out[3]: __main__.Student

In [4]: type(tuple())
Out[4]: tuple
```

#### 46 元类使用介绍

`xiaoming`, `xiaohong`, `xiaozhang` 都是学生，这类群体叫做 `Student`. 

Python 定义类的常见方法，使用关键字 `class`

```python
In [36]: class Student(object):
    ...:     pass
```

`xiaoming`, `xiaohong`, `xiaozhang` 是类的实例，则：

```python
xiaoming = Student()
xiaohong = Student()
xiaozhang = Student()
```

创建后，xiaoming 的 `__class__` 属性，返回的便是 `Student`类

```python
In [38]: xiaoming.__class__
Out[38]: __main__.Student
```

问题在于，`Student` 类有 `__class__`属性，如果有，返回的又是什么？

```python
In [39]: xiaoming.__class__.__class__
Out[39]: type
```

哇，程序没报错，返回 `type`

那么，我们不妨猜测：`Student` 类，类型就是 `type`

换句话说，`Student`类就是一个**对象**，它的类型就是 `type`

所以，Python 中一切皆对象，**类也是对象**

Python 中，将描述 `Student` 类的类被称为：元类。

按照此逻辑延伸，描述元类的类被称为：*元元类*，开玩笑了~ 描述元类的类也被称为元类。

聪明的朋友会问了，既然 `Student` 类可创建实例，那么 `type` 类可创建实例吗？ 如果能，它创建的实例就叫：类 了。 你们真聪明！

说对了，`type` 类一定能创建实例，比如 `Student` 类了。

```python
In [40]: Student = type('Student',(),{})

In [41]: Student
Out[41]: __main__.Student
```

它与使用 `class` 关键字创建的 `Student` 类一模一样。

Python 的类，因为又是对象，所以和 `xiaoming`，`xiaohong` 对象操作相似。支持：

- 赋值
- 拷贝
- 添加属性
- 作为函数参数

```python
In [43]: StudentMirror = Student # 类直接赋值 # 类直接赋值
In [44]: Student.class_property = 'class_property' # 添加类属性
In [46]: hasattr(Student, 'class_property')
Out[46]: True
```

元类，确实使用不是那么多，也许先了解这些，就能应付一些场合。就连 Python 界的领袖 `Tim Peters` 都说：

“元类就是深度的魔法，99%的用户应该根本不必为此操心。

#### 47 枚举对象　　

返回一个可以枚举的对象，该对象的next()方法将返回一个元组。

```python
In [1]: s = ["a","b","c"]
    ...: for i ,v in enumerate(s,1):
    ...:     print(i,v)
    ...:
1 a
2 b
3 c
```

#### 48 查看变量所占字节数

```python
In [1]: import sys

In [2]: a = {'a':1,'b':2.0}

In [3]: sys.getsizeof(a) # 占用240个字节
Out[3]: 240
```

#### 49 过滤器　　

在函数中设定过滤条件，迭代元素，保留返回值为`True`的元素：

```python
In [1]: fil = filter(lambda x: x>10,[1,11,2,45,7,6,13])

In [2]: list(fil)
Out[2]: [11, 45, 13]
```

#### 50 返回对象哈希值　　

返回对象的哈希值，值得注意的是自定义的实例都是可哈希的，`list`, `dict`, `set`等可变对象都是不可哈希的(unhashable)

  ```python
In [1]: hash(xiaoming)
Out[1]: 6139638

In [2]: hash([1,2,3])
# TypeError: unhashable type: 'list'
  ```

#### 51  help 一键帮助　

返回对象的帮助文档

```python
In [1]: help(xiaoming)
Help on Student in module __main__ object:

class Student(builtins.object)
 |  Methods defined here:
 |
 |  __init__(self, id, name)
 |
 |  __repr__(self)
 |
 |  Data descriptors defined here:
 |
 |  __dict__
 |      dictionary for instance variables (if defined)
 |
 |  __weakref__
 |      list of weak references to the object (if defined)
```

### 52 获取用户输入　

获取用户输入内容

```python
In [1]: input()
aa
Out[1]: 'aa'
```

#### 53 创建迭代器

使用`iter(obj, sentinel)`, 返回一个可迭代对象, sentinel可省略(一旦迭代到此元素，立即终止)

```python
In [1]: lst = [1,3,5]

In [2]: for i in iter(lst):
    ...:     print(i)
    ...:
1
3
5
```

```python
In [1]: class TestIter(object):
    ...:     def __init__(self):
    ...:         self.l=[1,3,2,3,4,5]
    ...:         self.i=iter(self.l)
    ...:     def __call__(self):  #定义了__call__方法的类的实例是可调用的
    ...:         item = next(self.i)
    ...:         print ("__call__ is called,fowhich would return",item)
    ...:         return item
    ...:     def __iter__(self): #支持迭代协议(即定义有__iter__()函数)
    ...:         print ("__iter__ is called!!")
    ...:         return iter(self.l)
In [2]: t = TestIter()
In [3]: t() # 因为实现了__call__，所以t实例能被调用
__call__ is called,which would return 1
Out[3]: 1

In [4]: for e in TestIter(): # 因为实现了__iter__方法，所以t能被迭代
    ...:     print(e)
    ...: 
__iter__ is called!!
1
3
2
3
4
5
```

#### 54 文件读写和mode 取值表

返回文件对象

```python
In [1]: fo = open('D:/a.txt',mode='r', encoding='utf-8')

In [2]: fo.read()
Out[2]: '\ufefflife is not so long,\nI use Python to play.'
In [3]: fo.close() # 关闭文件对象
```

mode 取值表：

| 字符  | 意义                             |
| :---- | :------------------------------- |
| `'r'` | 读取（默认）                     |
| `'w'` | 写入，并先截断文件               |
| `'x'` | 排它性创建，如果文件已存在则失败 |
| `'a'` | 写入，如果文件存在则在末尾追加   |
| `'b'` | 二进制模式                       |
| `'t'` | 文本模式（默认）                 |
| `'+'` | 打开用于更新（读取与写入）       |

文件读操作

```python
import os
# 创建文件夹

def mkdir(path):
    isexists = os.path.exists(path)
    if not isexists:
        os.mkdir(path)
# 读取文件信息

def openfile(filename):
    f = open(filename)
    fllist = f.read()
    f.close()
    return fllist  # 返回读取内容
```

文件写操作

```python
# 写入文件信息
# example1
# w写入，如果文件存在，则清空内容后写入，不存在则创建
f = open(r"./data/test.txt", "w", encoding="utf-8")
print(f.write("测试文件写入"))
f.close

# example2
# a写入，文件存在，则在文件内容后追加写入，不存在则创建
f = open(r"./data/test.txt", "a", encoding="utf-8")
print(f.write("测试文件写入"))
f.close

# example3
# with关键字系统会自动关闭文件和处理异常
with open(r"./data/test.txt", "w") as f:
    f.write("hello world!")
```

#### 55 创建range序列

1) range(stop)
2) range(start, stop[,step])

生成一个不可变序列：

```python
In [1]: range(11)
Out[1]: range(0, 11)

In [2]: range(0,11,1)
Out[2]: range(0, 11)
```

#### 56 反向迭代器reversed

```python
In [1]: rev = reversed([1,4,2,3,1])

In [2]: for i in rev:
     ...:     print(i)
     ...:
1
3
2
4
1
```

#### 57 zip迭代器

创建一个聚合了来自每个可迭代对象中的元素的迭代器：

```python
In [1]: x = [3,2,1]
In [2]: y = [4,5,6]
In [3]: list(zip(y,x))
Out[3]: [(4, 3), (5, 2), (6, 1)]

In [4]: a = range(5)
In [5]: b = list('abcde')
In [6]: b
Out[6]: ['a', 'b', 'c', 'd', 'e']
In [7]: [str(y) + str(x) for x,y in zip(a,b)]
Out[7]: ['a0', 'b1', 'c2', 'd3', 'e4']
```

#### 58 operator使用举例

```python
from operator import (add, sub)


def add_or_sub(a, b, oper):
    return (add if oper == '+' else sub)(a, b)


add_or_sub(1, 2, '-')  # -1
```

#### 60 传输json对象

对象序列化，是指将内存中的对象转化为可存储或传输的过程。很多场景，直接一个类对象，传输不方便。

但是，当对象序列化后，就会更加方便，因为约定俗成的，接口间的调用或者发起的 web 请求，一般使用 json 串传输。

实际使用中，一般对类对象序列化。先创建一个 Student 类型，并创建两个实例。

```python
class Student():
    def __init__(self,**args):
        self.ids = args['ids']
        self.name = args['name']
        self.address = args['address']
xiaoming = Student(ids = 1,name = 'xiaoming',address = '北京')
xiaohong = Student(ids = 2,name = 'xiaohong',address = '南京')
```

导入 json 模块，调用 dump 方法，就会将列表对象 [xiaoming,xiaohong]，序列化到文件 json.txt 中。

```python
import json

with open('json.txt', 'w') as f:
    json.dump([xiaoming,xiaohong], f, default=lambda obj: obj.__dict__, ensure_ascii=False, indent=2, sort_keys=True)
```

生成的文件内容，如下：

```json
[
    {
        "address":"北京",
        "ids":1,
        "name":"xiaoming"
    },
    {
        "address":"南京",
        "ids":2,
        "name":"xiaohong"
    }
]
```
#### 61 不用else和if实现计算器

```python
from operator import *


def calculator(a, b, k):
    return {
        '+': add,
        '-': sub,
        '*': mul,
        '/': truediv,
        '**': pow
    }[k](a, b)


calculator(1, 2, '+')  # 3
calculator(3, 4, '**')  # 81
```
#### 61 去最求平均

```python
def score_mean(lst):
    lst.sort()
    lst2=lst[1:(len(lst)-1)]
    return round((sum(lst2)/len(lst2)),1)

lst=[9.1, 9.0,8.1, 9.7, 19,8.2, 8.6,9.8]
score_mean(lst) # 9.1
```

#### 62 打印99乘法表

打印出如下格式的乘法表

```python
1*1=1
1*2=2   2*2=4
1*3=3   2*3=6   3*3=9
1*4=4   2*4=8   3*4=12  4*4=16
1*5=5   2*5=10  3*5=15  4*5=20  5*5=25
1*6=6   2*6=12  3*6=18  4*6=24  5*6=30  6*6=36
1*7=7   2*7=14  3*7=21  4*7=28  5*7=35  6*7=42  7*7=49
1*8=8   2*8=16  3*8=24  4*8=32  5*8=40  6*8=48  7*8=56  8*8=64
1*9=9   2*9=18  3*9=27  4*9=36  5*9=45  6*9=54  7*9=63  8*9=72  9*9=81
```

一共有10 行，第`i`行的第`j`列等于：`j*i`，

其中,

 `i`取值范围：`1<=i<=9`

 `j`取值范围：`1<=j<=i`

根据`例子分析`的语言描述，转化为如下代码：

```python
for i in range(1, 10):
    for j in range(1, i+1):
        print('%d * %d = %d' % (j, i, j * i) , end="\t")
    print()
```

#### 63 递归版flatten函数

对于如下数组：

```
[[[1,2,3],[4,5]]]
```

如何完全展开成一维的。这个小例子实现的`flatten`是递归版，两个参数分别表示带展开的数组，输出数组。

```python
from collections.abc import *

def flatten(lst, out_lst=None):
    if out_lst is None:
        out_lst = []
    for i in lst:
        if isinstance(i, Iterable): # 判断i是否可迭代
            flatten(i, out_lst)  # 尾数递归
        else:
            out_lst.append(i)    # 产生结果
    return out_lst
```

调用`flatten`:

```python
print(flatten([[1,2,3],[4,5]]))
print(flatten([[1,2,3],[4,5]], [6,7]))
print(flatten([[[1,2,3],[4,5,6]]]))
# 结果：
[1, 2, 3, 4, 5]
[6, 7, 1, 2, 3, 4, 5]
[1, 2, 3, 4, 5, 6]
```

numpy里的`flatten`与上面的函数实现有些微妙的不同：

```python
import numpy
b = numpy.array([[1,2,3],[4,5]])
b.flatten()
array([list([1, 2, 3]), list([4, 5])], dtype=object)
```

#### 64 列表等分

```python
from math import ceil

def divide(lst, size):
    if size <= 0:
        return [lst]
    return [lst[i * size:(i+1)*size] for i in range(0, ceil(len(lst) / size))]
```

测试举例：

```python
r = divide([1, 3, 5, 7, 9], 2)
print(r)  # [[1, 3], [5, 7], [9]]

r = divide([1, 3, 5, 7, 9], 0)
print(r)  # [[1, 3, 5, 7, 9]]

r = divide([1, 3, 5, 7, 9], -3)
print(r)  # [[1, 3, 5, 7, 9]]
```


#### 65 压缩列表

```python
def filter_false(lst):
    return list(filter(bool, lst))


r = filter_false([None, 0, False, '', [], 'ok', [1, 2]])
print(r)  # ['ok', [1, 2]]

```

#### 66 求更长的列表

```python
def max_length(*lst):
    return max(*lst, key=lambda v: len(v))


r = max_length([1, 2, 3], [4, 5, 6, 7], [8])
print(f'更长的列表是{r}')  # [4, 5, 6, 7]

r = max_length([1, 2, 3], [4, 5, 6, 7], [8, 9])
print(f'更长的列表是{r}')  # [4, 5, 6, 7]
```

#### 67 求众数

```python
def top1(lst):
    return max(lst, default='列表为空', key=lambda v: lst.count(v))
```

测试举例：

```python
lst = [1, 3, 3, 2, 1, 1, 2]
r = top1(lst)
print(f'{lst}中出现次数最多的元素为:{r}')  
# [1, 3, 3, 2, 1, 1, 2]中出现次数最多的元素为:1
```


#### 68 所有多个列表的最大值
```python 
def max_lists(*lst):
    return max(max(*lst, key=lambda v: max(v)))


r = max_lists([1, 2, 3], [6, 7, 8], [4, 5])
print(r)  # 8
```

#### 69 列表检查重复

```python
def has_duplicates(lst):
    return len(lst) == len(set(lst))


x = [1, 1, 2, 2, 3, 2, 3, 4, 5, 6]
y = [1, 2, 3, 4, 5]
has_duplicates(x)  # False
has_duplicates(y)  # True
```

#### 70 一行代码实现列表反转

```python
def reverse(lst):
    return lst[::-1]


r = reverse([1, -2, 3, 4, 1, 2])
print(r)  # [2, 1, 4, 3, -2, 1]
```

#### 71 浮点数等差数列

```python
def float_range(start, stop, n):
    start,stop,n = float('%.2f' % start), float('%.2f' % stop),int('%.d' % n)
    step = (stop-start)/n
    lst = [start]
    while n > 0:
        start,n = start+step,n-1
        lst.append(round((start), 2))
    return lst
```

测试举例：

```python
float_range(1, 8, 10) 
# [1.0, 1.7, 2.4, 3.1, 3.8, 4.5, 5.2, 5.9, 6.6, 7.3, 8.0]
```


#### 72 按条件分组

```python
def bif_by(lst, f):
    return [ [x for x in lst if f(x)],[x for x in lst if not f(x)]]
```

测试举例：

```python
records = [25,89,31,34] 
bif_by(records, lambda x: x<80) # [[25, 31, 34], [89]]
```


#### 73 map实现向量运算

多序列运算函数

`map(function,iterabel,iterable2)`

```python
lst1=[1,2,3,4,5,6]
lst2=[3,4,5,6,3,2]
list(map(lambda x,y:x*y+1,lst1,lst2))
### [4, 9, 16, 25, 16, 13]
```

#### 74 值最大的字典

```python
def max_pairs(dic):
    if len(dic) == 0:
        return dic
    max_val = max(map(lambda v: v[1], dic.items()))
    return [item for item in dic.items() if item[1] == max_val]
```

测试举例：

```python
r = max_pairs({'a': -10, 'b': 5, 'c': 3, 'd': 5})
print(r)  # [('b', 5), ('d', 5)]
```


#### 75 合并两个字典

Python 3.5 后支持的一行代码实现合并字典

```python
def merge_dict(dic1, dic2):
    return {**dic1, **dic2} 
```

测试：

```python
merge_dict({'a': 1, 'b': 2}, {'c': 3}) 
# {'a': 1, 'b': 2, 'c': 3}
```


#### 76 Topn 字典

返回字典d前n个最大值对应的键

```python
from heapq import nlargest
def topn_dict(d, n):
    return nlargest(n, d, key=lambda k: d[k])
```

测试：

```python
topn_dict({'a': 10, 'b': 8, 'c': 9, 'd': 10}, 3)  
# ['a', 'd', 'c']
```


#### 77 异位词

两个字符串含有相同字母，但排序不同，简称：互为变位词

```python
from collections import Counter

# 

def anagram(str1, str2):
    return Counter(str1) == Counter(str2)

anagram('eleven+two', 'twelve+one')  # True 这是一对神器的变位词
anagram('eleven', 'twelve')  # False
```

#### 78 逻辑上合并字典
(1) 两种合并字典方法
这是一般的字典合并写法

```python
dic1 = {'x': 1, 'y': 2 }
dic2 = {'y': 3, 'z': 4 }
merged1 = {**dic1, **dic2} # {'x': 1, 'y': 3, 'z': 4}
```

修改merged['x']=10，dic1中的x值`不变`，`merged`是重新生成的一个`新字典`。

但是，`ChainMap`却不同，它在内部创建了一个容纳这些字典的列表。因此使用ChainMap合并字典，修改merged['x']=10后，dic1中的x值`改变`，如下所示：

```python
from collections import ChainMap
merged2 = ChainMap(dic1,dic2)
print(merged2) # ChainMap({'x': 1, 'y': 2}, {'y': 3, 'z': 4})
```

#### 79  带名字的元组

定义名字为Point的元祖，字段属性有`x`,`y`,`z`

```python
from collections import namedtuple
Point = namedtuple('Point', ['x', 'y', 'z'])  
lst = [Point(1.5, 2, 3.0), Point(-0.3, -1.0, 2.1), Point(1.3, 2.8, -2.5)]
print(lst[0].y - lst[1].y)
```

使用命名元组写出来的代码可读性更好，尤其处理上百上千个属性时作用更加凸显。

#### 80 sample 样本抽样

使用`sample`抽样，如下例子从100个样本中随机抽样10个。

```python
from random import randint,sample
lst = [randint(0,50) for _ in range(100)]
print(lst[:5])# [38, 19, 11, 3, 6]
lst_sample = sample(lst,10)
print(lst_sample) # [33, 40, 35, 49, 24, 15, 48, 29, 37, 24]
```

#### 81 shuffle 重洗数据集

使用`shuffle`用来重洗数据集，值得注意`shuffle`是对lst就地(in place)洗牌，节省存储空间。

```python
from random import shuffle
lst = [randint(0,50) for _ in range(100)]
shuffle(lst)
print(lst[:5]) # [50, 3, 48, 1, 26]
```

#### 82 10个均匀分布的坐标点

random模块中的`uniform(a,b)`生成[a,b)内的一个随机数。

如下生成10个均匀分布的二维坐标点

```python
from random import uniform
In [1]: [(uniform(0,10),uniform(0,10)) for _ in range(10)]
Out[1]: 
[(9.244361194237328, 7.684326645514235),
 (8.129267671737324, 9.988395854203773),
 (9.505278771040661, 2.8650440524834107),
 (3.84320100484284, 1.7687190176304601),
 (6.095385729409376, 2.377133802224657),
 (8.522913365698605, 3.2395995841267844),
 (8.827829601859406, 3.9298809217233766),
 (1.4749644859469302, 8.038753079253127),
 (9.005430657826324, 7.58011186920019),
 (8.700789540392917, 1.2217577293254112)]
```

#### 83 10个高斯分布的坐标点

random模块中的`gauss(u,sigma)`生成均值为u, 标准差为sigma的满足高斯分布的值，如下生成10个二维坐标点，样本误差(y-2*x-1)满足均值为0，标准差为1的高斯分布：

```python
from random import gauss
x = range(10)
y = [2*xi+1+gauss(0,1) for xi in x]
points = list(zip(x,y))
### 10个二维点：
[(0, -0.86789025305992),
 (1, 4.738439437453464),
 (2, 5.190278040856102),
 (3, 8.05270893133576),
 (4, 9.979481700775292),
 (5, 11.960781766216384),
 (6, 13.025427054303737),
 (7, 14.02384035204836),
 (8, 15.33755823101161),
 (9, 17.565074449028497)]
```

#### 84 chain串联小容器为大容器

`chain`函数串联a和b，兼顾内存效率同时写法更加优雅。

```python
from itertools import chain
a = [1,3,5,0]
b = (2,4,6)

for i in chain(a,b):
  print(i)
### 结果
1
3
5
0
2
4
6
```

#### 85 product 案例

```python
def product(*args, repeat=1):
    pools = [tuple(pool) for pool in args] * repeat
    result = [[]]
    for pool in pools:
        result = [x+[y] for x in result for y in pool]
    for prod in result:
        yield tuple(prod)
```


调用函数：

```python
rtn = product('xyz', '12', repeat=3)
print(list(rtn))
```

#### 86 反转字符串的两个方法

```python
st="python"
```

方法1：

```python
''.join(reversed(st))
```

方法2:

```python
st[::-1]
```


#### 87 join 串联字符串

用逗号连接字符串

```python
In [4]: mystr = ['1','2','java','4','python','java','7','8','java','python','11','java','13','14']

In [5]: ','.join(mystr) #用逗号连接字符串
Out[5]: '1,2,java,4,python,java,7,8,java,python,11,java,13,14'
```

#### 88 字符串字节长度

```python
def str_byte_len(mystr):
    return (len(mystr.encode('utf-8')))
```

测试：

```python
str_byte_len('i love python')  # 13(个字节)
str_byte_len('字符')  # 6(个字节)
```


### 89 正则中字符 `r`是干啥的？

经常见过正则表达式前有一个字符 `r`，它的作用是告诉解释器后面的一串是原生字符串，按照字面意思解释即可。如：

```python
s1 = r'\n.*'
print(s1) 
```

它告诉编译器s串第一个字符是`\`，第二个字符是`n`.打印的结果就是它本身：

```python
\n.*
```

而如果不带前缀字符`r`，即：

```python
s2 = '\n.*'
print(s2)
```

解释器认为前两个字符`\n`为转义字符，一个新行的意思，打印结果为一个换行加.*，如下所示：

```python
.*
```

### 90 什么是一个原子操作？

微观世界中，如果定义原子是组成事物的最基本单元，那么就可理解为原子不能再分了。同理此处，正则的原子操作是指不能再被分割的正则表达式操作。

如正则中的`+`指前面的一个原子操作出现至少1次。

例如：`66+`表示第一个字符为6，第二个字符6和第三个字符+联合起来表示至少出现1次字符6，因此综合起来至少要有2个6紧邻的串才能满足此正则表达式(下面会详细讲到)。

`\w+`表示*字母数字下划线*中的任意一个字符(`\w`指代的)至少出现1次，那么`\w`就是一个原子操作。

因此，普通字符是原子，正则中的通用字符(下面会讲到)也是原子。

大家记住*原子*这个概念。

### 91 怎么理解正则中的转义？

正则世界中，重新定义了几个新的转义字符。

一个转义字符`\`+一个字符，转义后会改变原字符的意义，它不再是它，而是赋予一个新的含义。

例如，`w`本身就是一个英文字符`w`，没有其他任何含义。但是，前面加一个转义字符 `\` 后，含义发生重大改变，`w`它不再是`w`，而是`\`要与`w`连在一起，被解释器解释为匹配以下字符集合中的任意一个：

```python
pat = '\w'
```

等于：

```python
pat = '[0123456789
      AaBbCcDdEeFfGgHhIiJjKkLlMmNnOoPpQqRrSsTtUuVvWwXxYyZz
      _]'
```

即匹配数字、大小写字母和下划线`_`字符集合中的任意一个。

你看，一个通用转义字符`\w`直接就指代上面这一大串，写法多么简便，同时在正则的世界里又经常被用到，故被称为：**通用正则字符**

类似的通用正则字符还有几个，下面也会讲到。

做一件事前，把规则弄清，触类旁通，相信大家理解其他几个也没问题。
### 92 正则最普通查找

最普通查找就是需要找啥就写啥，没有使用正则的规则。如下是关于小说《灿烂千阳》中的一段话，从中找出单词`friendship`，可能出现多次：

```
s = """
# Mariam is only fifteen 
# when she is sent to Kabul to marry the troubled and bitter Rasheed,
# who is thirty years her senior. 
# Nearly two decades later, 
# in a climate of growing unrest, tragedy strikes fifteen-year-old Laila, 
# who must leave her home and join Mariam's unhappy household. 
# Laila and Mariam are to find consolation in each other, 
# their friendship to grow as deep as the bond between sisters, 
# as strong as the ties between mother and daughter. 
# With the passing of time comes Taliban rule over Afghanistan, 
# the streets of Kabul loud with the sound of gunfire and bombs, 
# life a desperate struggle against starvation, brutality and fear, 
# the women's endurance tested beyond their worst imaginings. 
# Yet love can move a person to act in unexpected ways, 
# lead them to overcome the most daunting obstacles with a startling heroism. 
# In the end it is love that triumphs over death and destruction. 
# A Thousand Splendid Suns is an unforgettable portrait of a wounded country and
#  a deeply moving story of family and friendship. 
#  It is a beautiful, heart-wrenching story of an unforgiving time, 
#  an unlikely bond and an indestructible love.
"""
```

使用正则前，先导入re模块，再定义正则表达式，然后使用`findall`方法找出所有匹配

```python
import re
pat = 'friendship'
result = re.findall(pat,s)
print(result) 

# 共找到两处：
# ['friendship', 'friendship']
```

以上就是使用正则的最普通例子。如果要找出前缀为grow的单词，比如可能为grows, growing 等，最普通查找实现起来就不方便。

然而，借助于下面介绍的元字符、通用字符和捕获组合起来，便能应对解决复杂的匹配查找问题。### 93 使用通用字符查找

在正则的世界里，通用字符指帮助我们更加简便的写出匹配规则的字符。

如上面文字，下面正则匹配串能找出以d开始，[a-z]表示的任意一个小写英文字符，{7}表示小写英文字符出现7次(下面情况3会说到)，也就是匹配出来的子串长度为1+7=8:

```python
pat = 'd[a-z]{7}'
result = re.findall(pat,s)
```

匹配结果为：

```python
['daughter', 'desperat', 'daunting', 'destruct', 'destruct']
```

同理，模式串`pat = 'd[a-z]{10}'`匹配的结果为：

```
['destruction', 'destructibl']
```

模式串`pat = 'd[a-z]{11}'`匹配的结果为：

```
[ 'destructible']
```

你看，通用字符`[a-z]`使用真方便，5个字符一下就表达了所有26个小写的字符，但是注意`[a-z]`匹配26个小写字符的任意**一个**.

类似功能的通用字符还包括：

```
[A-Z]  匹配大写英文字母
[0-9]  匹配一个0-9之间的数字
```

还有更加强大的通用字符：

```
\s  匹配空白字符，如\n \t \b等
\w  匹配任意字母、数字、下划线 
\d  匹配十进制数字0-9
```

而\S, \W, \D 分别对应 \s, \w, \d匹配字符集的补集，例如\S 的意思是匹配 \s 以外的其他任意字符。


### 94 使用元字符查找

`元`的含义大家不妨理解为用来描述它后面事物的类，如*元类*用来创建描述类的类，*元模型*描述一个模型的模型，因此推而广之，*元字符*用来描述字符的字符。

理解以上后，你再看正则中使用最普遍的一个元字符 `+`，它是用来描述前面一个原子出现次数的字符，表示前一个原子出现1次或多次都可。

例如，在寻找手机靓号时，正则表达式`66+`，表示前一个原子`6`至少出现1次，因此连上第一个6，表示电话号码中至少有两个66紧邻。因此，电话号码`18612652166`、`17566665656`都满足要求，而号码`18616161616`不符合要求。

类似功能的元字符，还包括如下。功能相似，不再赘述：

```
* 前面的原子重复0次、1次、多次 
? 前面的原子重复0次或者1次 
+ 前面的原子重复1次或多次
{n} 前面的原子出现了 n 次
{n,} 前面的原子至少出现 n 次
{n,m} 前面的原子出现次数介于 n-m 之间
```
## 95 捕获子串

今天以我写过的《Python 60天》专栏中的一段文字，提取出里面的链接为例，阐述提取子串的实用性。

先贴上文字(有删减改动)，将这段文字赋值给变量 `urls`：

```
urls = """
基于 Python 的包更是枝繁叶茂，遍地开花，“Tiobe 编程语言排行榜”最新统计显示 Python 是增长最快的语言。

![image-20200131192231967](https://images.gitbook.cn/2020-02-05-014719.png)

接下来，与大家，还有远在美国做 AI 博士后研究的 Alicia，一起开始我们的 60 天 Python 探索之旅吧。

所有的这些考虑，都是为了让大家在短时间内掌握 Python 技术栈，多一个生存的本领。拿到理想的 Offer 后，早日过上自己想要的生活。

让我们开始吧。

如下，按照是否为静态/动态语言，弱类型/强类型两个维度，

总结常用的语言分类。

![image-20200205155429583](https://images.gitbook.cn/2020-02-05-080211.png) ### 四大基本语法
"""
```

你可能很快写出如下的正则表达式：

```
# 元字符.表示匹配除\n字符外的任意一个字符
# 元字符*表示匹配前面一个原子0次或多次
pat = r'https:.*' 
```

然后导入`re`模块，使用`findall`方法找出所有匹配：

```python
import re
result = re.findall(pat,urls)
print(result)
```

运行结果显示如下，观察发现2个匹配，但是每个匹配链接都包括冗余字符，因此匹配错误：

```
['https://images.gitbook.cn
/2020-02-05-014719.png)',

'https://images.gitbook.cn
/2020-02-05-080211.png) ### 四大基本语法']
```

我们再稍微优化原正则表达式为：

```python
# 添加 \) 表示待匹配子串以右括号结尾
pat = r'https:.*\)'
```

打印结果显示如下，结果确实好一点，但是依然包括右括号，结果还是错误的：

```
['https://images.gitbook.cn/
2020-02-05-014719.png)', 

'https://images.gitbook.cn/
2020-02-05-080211.png)']
```

所以掌握**提取**子串的技能就很重要，实现提取子串也很简单，只需把想要返回的子串加上一对括号就行，如下所示：

```python
# 把想要返回的子串外面添加一对括号

pat = r'(https:.*)\)'
```

此时返回结果完全正确，无任何多余字符。想要返回的子串外面添加一对括号还有个专业叫法：**捕获**或**分组**。
#### 96 贪心捕获和非贪心捕获

捕获功能非常实用，使用它需要区分一点，贪婪捕获和非贪婪捕获。前者指在满足匹配模式前提下，返回包括尽可能多的字符匹配模式；后者指满足匹配条件下，尽可能少的捕获。

我们伪造一个理想状况下的案例：

```
htmlContent = """
        <div><div><h2>这是二级标题</h2></div><div><p> 这是一个段落>/p></div></div>
"""
```

贪心捕获使用`(.*)`，如下所示：

```
pat = r"<div>(.*)</div>"

result = re.findall(pat,htmlContent)
```

结果为如下，尽可能长的捕获，而不是遇到第一个`</div>`时就终止：

```
['<div><h2>这是二级标题</h2></div><div><p> 这是一个段落>/p></div>']
```

而非贪心捕获的正则表达式为`<div>(.*?)</div>"`，如下：

```
pat = r"<div>(.*?)</div>"

result = re.findall(pat,htmlContent)

print(result)
```

结果为两个元素，遇到第一个`</div>`时终止，然后继续捕获出第二子串：

```
['<div><h2>这是二级标题</h2>', 
  '<p> 这是一个段落>/p>']
```

以上例子仅仅用作演示两者区别，实际的html结构含有换行符等，环境比上面要复杂的多，贪心和非贪心捕获的写法可能不会导致结果不同，但是我们依然需要理解它们的区别。

#### 97 使用正则做密码安全检查

密码安全要求：

1)要求密码为6到20位; 

2)密码只包含英文字母和数字

```python
pat = re.compile(r'\w{6,20}') # 这是错误的，因为\w通配符匹配的是字母，数字和下划线，题目要求不能含有下划线
# 使用最稳的方法：\da-zA-Z满足`密码只包含英文字母和数字`
pat = re.compile(r'[\da-zA-Z]{6,20}')
```
选用最保险的`fullmatch`方法，查看是否整个字符串都匹配：
```python
pat.fullmatch('qaz12') # 返回 None, 长度小于6
pat.fullmatch('qaz12wsxedcrfvtgb67890942234343434') # None 长度大于22
pat.fullmatch('qaz_231') # None 含有下划线
pat.fullmatch('n0passw0Rd')
Out[4]: <re.Match object; span=(0, 10), match='n0passw0Rd'>
```

#### 98 爬取百度首页标题

```python
import re
from urllib import request

#爬虫爬取百度首页内容
data=request.urlopen("http://www.baidu.com/").read().decode()

#分析网页,确定正则表达式
pat=r'<title>(.*?)</title>'

result=re.search(pat,data)
print(result) <re.Match object; span=(1358, 1382), match='<title>百度一下，你就知道</title>'>

result.group() # 百度一下，你就知道
```

#### 99 批量转化为驼峰格式(Camel)

数据库字段名批量转化为驼峰格式

分析过程

```python
# 用到的正则串讲解
# \s 指匹配： [ \t\n\r\f\v]
# A|B：表示匹配A串或B串
# re.sub(pattern, newchar, string): 
# substitue代替，用newchar字符替代与pattern匹配的字符所有.
```



```python
# title(): 转化为大写，例子：
# 'Hello world'.title() # 'Hello World'
```



```python
# print(re.sub(r"\s|_|", "", "He llo_worl\td"))
s = re.sub(r"(\s|_|-)+", " ",
           'some_database_field_name').title().replace(" ", "")  
#结果： SomeDatabaseFieldName
```



```python
# 可以看到此时的第一个字符为大写，需要转化为小写
s = s[0].lower()+s[1:]  # 最终结果
```

 

整理以上分析得到如下代码：

```python
import re
def camel(s):
    s = re.sub(r"(\s|_|-)+", " ", s).title().replace(" ", "")
    return s[0].lower() + s[1:]

# 批量转化
def batch_camel(slist):
    return [camel(s) for s in slist]
```

测试结果：

```python
s = batch_camel(['student_id', 'student\tname', 'student-add'])
print(s)
# 结果
['studentId', 'studentName', 'studentAdd']
```

#### 100 是否互为排序词

排序词(permutation)：两个字符串含有相同字符，但字符顺序不同。

```python
from collections import defaultdict


def is_permutation(str1, str2):
    if str1 is None or str2 is None:
        return False
    if len(str1) != len(str2):
        return False
    unq_s1 = defaultdict(int)
    unq_s2 = defaultdict(int)
    for c1 in str1:
        unq_s1[c1] += 1
    for c2 in str2:
        unq_s2[c2] += 1

    return unq_s1 == unq_s2
```

这个小例子，使用python内置的`defaultdict`，默认类型初始化为`int`，计数默次数都为0. 这个解法本质是 `hash map lookup`

统计出的两个defaultdict：unq_s1，unq_s2，如果相等，就表明str1、 str2互为排序词。

下面测试：

```python
r = is_permutation('nice', 'cine')
print(r)  # True

r = is_permutation('', '')
print(r)  # True

r = is_permutation('', None)
print(r)  # False

r = is_permutation('work', 'woo')
print(r)  # False

```

#### 101 str1是否由str2旋转而来

`stringbook`旋转后得到`bookstring`,写一段代码验证`str1`是否为`str2`旋转得到。

**思路**

转化为判断：`str1`是否为`str2+str2`的子串

```python
def is_rotation(s1: str, s2: str) -> bool:
    if s1 is None or s2 is None:
        return False
    if len(s1) != len(s2):
        return False

    def is_substring(s1: str, s2: str) -> bool:
        return s1 in s2
    return is_substring(s1, s2 + s2)
```

**测试**

```python
r = is_rotation('stringbook', 'bookstring')
print(r)  # True

r = is_rotation('greatman', 'maneatgr')
print(r)  # False
```

#### 102 使用正则判断是否为正浮点数

从一系列字符串中，挑选出所有正浮点数。

该怎么办？

玩玩正则表达式，用正则搞它！

关键是，正则表达式该怎么写呢？

有了！

`^[1-9]\d*\.\d*$`

`^` 表示字符串开始

`[1-9]` 表示数字1,2,3,4,5,6,7,8,9

`^[1-9]` 连起来表示以数字 `1-9` 作为开头

`\d` 表示一位 `0-9` 的数字

`*` 表示前一位字符出现 0 次，1 次或多次

`\d*` 表示数字出现 0 次，1 次或多次 

`\.` 表示小数点

`\$` 表示字符串以前一位的字符结束

`^[1-9]\d*\.\d*$` 连起来就求出所有大于 1.0 的正浮点数。

那 0.0 到 1.0 之间的正浮点数，怎么求，干嘛不直接汇总到上面的正则表达式中呢？

这样写不行吗：`^[0-9]\d*\.\d*$`

```python
In [85]: import re

In [87]: recom = re.compile(r'^[0-9]\d*\.\d*$')

In [88]: recom.match('000.2')
Out[88]: <re.Match object; span=(0, 5), match='000.2'>
```

结果显示，正则表达式 `^[0-9]\d*\.\d*$` 竟然匹配到 `000.2 `，认为它是一个正浮点数。

所以知道为啥要先匹配大于 1.0 的浮点数了吧！

如果能写出这个正则表达式，再写另一部分就不困难了！

0.0 到 1.0 间的浮点数：`^0\.\d*[1-9]\d*$`

两个式子连接起来就是最终的结果：

`^[1-9]\d*\.\d*|0\.\d*[1-9]\d*$`

#### 103 获取后缀名

```python
import os
file_ext = os.path.splitext('./data/py/test.py')
front,ext = file_ext
In [5]: front
Out[5]: './data/py/test'

In [6]: ext
Out[6]: '.py'
```

#### 104 获取路径中的文件名

```python
In [11]: import os
    ...: file_ext = os.path.split('./data/py/test.py')
    ...: ipath,ifile = file_ext
    ...:

In [12]: ipath
Out[12]: './data/py'

In [13]: ifile
Out[13]: 'test.py'
```

#### 105 批量修改文件后缀

**批量修改文件后缀**

本例子使用Python的`os`模块和 `argparse`模块，将工作目录`work_dir`下所有后缀名为`old_ext`的文件修改为后缀名为`new_ext`

通过本例子，大家将会大概清楚`argparse`模块的主要用法。

导入模块

```python
import argparse
import os
```

定义脚本参数

```python
def get_parser():
    parser = argparse.ArgumentParser(
        description='工作目录中文件后缀名修改')
    parser.add_argument('work_dir', metavar='WORK_DIR', type=str, nargs=1,
                        help='修改后缀名的文件目录')
    parser.add_argument('old_ext', metavar='OLD_EXT',
                        type=str, nargs=1, help='原来的后缀')
    parser.add_argument('new_ext', metavar='NEW_EXT',
                        type=str, nargs=1, help='新的后缀')
    return parser
```

后缀名批量修改

```python
def batch_rename(work_dir, old_ext, new_ext):
    """
    传递当前目录，原来后缀名，新的后缀名后，批量重命名后缀
    """
    for filename in os.listdir(work_dir):
        # 获取得到文件后缀
        split_file = os.path.splitext(filename)
        file_ext = split_file[1]
        # 定位后缀名为old_ext 的文件
        if old_ext == file_ext:
            # 修改后文件的完整名称
            newfile = split_file[0] + new_ext
            # 实现重命名操作
            os.rename(
                os.path.join(work_dir, filename),
                os.path.join(work_dir, newfile)
            )
    print("完成重命名")
    print(os.listdir(work_dir))
```

实现Main

```python
def main():
    """
    main函数
    """
    # 命令行参数
    parser = get_parser()
    args = vars(parser.parse_args())
    # 从命令行参数中依次解析出参数
    work_dir = args['work_dir'][0]
    old_ext = args['old_ext'][0]
    if old_ext[0] != '.':
        old_ext = '.' + old_ext
    new_ext = args['new_ext'][0]
    if new_ext[0] != '.':
        new_ext = '.' + new_ext

    batch_rename(work_dir, old_ext, new_ext)
```

#### 106 xls批量转换成xlsx

```python
import os


def xls_to_xlsx(work_dir):
    """
    传递当前目录，原来后缀名，新的后缀名后，批量重命名后缀
    """
    old_ext, new_ext = '.xls', '.xlsx'
    for filename in os.listdir(work_dir):
        # 获取得到文件后缀
        split_file = os.path.splitext(filename)
        file_ext = split_file[1]
        # 定位后缀名为old_ext 的文件
        if old_ext == file_ext:
            # 修改后文件的完整名称
            newfile = split_file[0] + new_ext
            # 实现重命名操作
            os.rename(
                os.path.join(work_dir, filename),
                os.path.join(work_dir, newfile)
            )
    print("完成重命名")
    print(os.listdir(work_dir))


xls_to_xlsx('./data')

# 输出结果：
# ['cut_words.csv', 'email_list.xlsx', 'email_test.docx', 'email_test.jpg', 'email_test.xlsx', 'geo_data.png', 'geo_data.xlsx',
'iotest.txt', 'pyside2.md', 'PySimpleGUI-4.7.1-py3-none-any.whl', 'test.txt', 'test_excel.xlsx', 'ziptest', 'ziptest.zip']
```

#### 107 获取指定后缀名的文件

```python
import os

def find_file(work_dir,extension='jpg'):
    lst = []
    for filename in os.listdir(work_dir):
        print(filename)
        splits = os.path.splitext(filename)
        ext = splits[1] # 拿到扩展名
        if ext == '.'+extension:
            lst.append(filename)
    return lst

r = find_file('.','md') 
print(r) # 返回所有目录下的md文件
```

#### 108 批量压缩文件


```python
import zipfile  # 导入zipfile,这个是用来做压缩和解压的Python模块；
import os
import time


def batch_zip(start_dir):
    start_dir = start_dir  # 要压缩的文件夹路径
    file_news = start_dir + '.zip'  # 压缩后文件夹的名字

    z = zipfile.ZipFile(file_news, 'w', zipfile.ZIP_DEFLATED)
    for dir_path, dir_names, file_names in os.walk(start_dir):
        # 这一句很重要，不replace的话，就从根目录开始复制
        f_path = dir_path.replace(start_dir, '')
        f_path = f_path and f_path + os.sep  # 实现当前文件夹以及包含的所有文件的压缩
        for filename in file_names:
            z.write(os.path.join(dir_path, filename), f_path + filename)
    z.close()
    return file_news


batch_zip('./data/ziptest')


```

#### 109 32位加密

```python
import hashlib
# 对字符串s实现32位加密


def hash_cry32(s):
    m = hashlib.md5()
    m.update((str(s).encode('utf-8')))
    return m.hexdigest()


print(hash_cry32(1))  # c4ca4238a0b923820dcc509a6f75849b
print(hash_cry32('hello'))  # 5d41402abc4b2a76b9719d911017c592
```

#### 110 年的日历图

```python
import calendar
from datetime import date
mydate = date.today()
year_calendar_str = calendar.calendar(2019)
print(f"{mydate.year}年的日历图：{year_calendar_str}\n")
```

打印结果：

```python
2019

      January                   February                   March
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
    1  2  3  4  5  6                   1  2  3                   1  2  3
 7  8  9 10 11 12 13       4  5  6  7  8  9 10       4  5  6  7  8  9 10
14 15 16 17 18 19 20      11 12 13 14 15 16 17      11 12 13 14 15 16 17
21 22 23 24 25 26 27      18 19 20 21 22 23 24      18 19 20 21 22 23 24
28 29 30 31               25 26 27 28               25 26 27 28 29 30 31

       April                      May                       June
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
 1  2  3  4  5  6  7             1  2  3  4  5                      1  2
 8  9 10 11 12 13 14       6  7  8  9 10 11 12       3  4  5  6  7  8  9
15 16 17 18 19 20 21      13 14 15 16 17 18 19      10 11 12 13 14 15 16
22 23 24 25 26 27 28      20 21 22 23 24 25 26      17 18 19 20 21 22 23
29 30                     27 28 29 30 31            24 25 26 27 28 29 30

        July                     August                  September
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
 1  2  3  4  5  6  7                1  2  3  4                         1
 8  9 10 11 12 13 14       5  6  7  8  9 10 11       2  3  4  5  6  7  8
15 16 17 18 19 20 21      12 13 14 15 16 17 18       9 10 11 12 13 14 15
22 23 24 25 26 27 28      19 20 21 22 23 24 25      16 17 18 19 20 21 22
29 30 31                  26 27 28 29 30 31         23 24 25 26 27 28 29
                                                    30

      October                   November                  December
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
    1  2  3  4  5  6                   1  2  3                         1
 7  8  9 10 11 12 13       4  5  6  7  8  9 10       2  3  4  5  6  7  8
14 15 16 17 18 19 20      11 12 13 14 15 16 17       9 10 11 12 13 14 15
21 22 23 24 25 26 27      18 19 20 21 22 23 24      16 17 18 19 20 21 22
28 29 30 31               25 26 27 28 29 30         23 24 25 26 27 28 29
                                                    30 31
```

#### 111 判断是否为闰年

```python
import calendar
from datetime import date

mydate = date.today()
is_leap = calendar.isleap(mydate.year)
print_leap_str = "%s年是闰年" if is_leap else "%s年不是闰年\n"
print(print_leap_str % mydate.year)
```

打印结果：

```python
2019年不是闰年
```
#### 112 判断月有几天

```python
import calendar
from datetime import date

mydate = date.today()
weekday, days = calendar.monthrange(mydate.year, mydate.month)
print(f'{mydate.year}年-{mydate.month}月的第一天是那一周的第{weekday}天\n')
print(f'{mydate.year}年-{mydate.month}月共有{days}天\n')
```

打印结果：

```python
2019年-12月的第一天是那一周的第6天

2019年-12月共有31天
```#### 113 月的第一天

```python
from datetime import date
mydate = date.today()
month_first_day = date(mydate.year, mydate.month, 1)
print(f"当月第一天:{month_first_day}\n")
```

打印结果：

```python
# 当月第一天:2019-12-01
```
#### 114 月最后一天

```python
from datetime import date
import calendar
mydate = date.today()
_, days = calendar.monthrange(mydate.year, mydate.month)
month_last_day = date(mydate.year, mydate.month, days)
print(f"当月最后一天:{month_last_day}\n")
```

打印结果：

```python
当月最后一天:2019-12-31
```

#### 115 获取当前时间

```python
from datetime import date, datetime
from time import localtime, strftime

today_date = date.today()
print(today_date)  # 2019-12-22

today_time = datetime.today()
print(today_time)  # 2019-12-22 18:02:33.398894

local_time = localtime()
print(strftime("%Y-%m-%d %H:%M:%S", local_time))  # 转化为定制的格式 2019-12-22 18:13:41
```

#### 116 字符时间转时间

```python
from time import strptime

# parse str time to struct time
struct_time = strptime('2019-12-22 10:10:08', "%Y-%m-%d %H:%M:%S")
print(struct_time) # struct_time类型就是time中的一个类

# time.struct_time(tm_year=2019, tm_mon=12, tm_mday=22, tm_hour=10, tm_min=10, tm_sec=8, tm_wday=6, tm_yday=356, tm_isdst=-1)
```

#### 117 时间转字符时间

```python
from time import strftime, strptime, localtime

In [2]: print(localtime()) #这是输入的时间
Out[2]: time.struct_time(tm_year=2019, tm_mon=12, tm_mday=22, tm_hour=18, tm_min=24, tm_sec=56, tm_wday=6, tm_yday=356, tm_isdst=0)

print(strftime("%m-%d-%Y %H:%M:%S", localtime()))  # 转化为定制的格式
# 这是字符串表示的时间：   12-22-2019 18:26:21
```

#### 118 默认启动主线程

一般的，程序默认执行只在一个线程，这个线程称为主线程，例子演示如下：

导入线程相关的模块 `threading`:

```python
import threading
```

threading的类方法 `current_thread()`返回当前线程：

```python
t = threading.current_thread()
print(t) # <_MainThread(MainThread, started 139908235814720)>
```

所以，验证了程序默认是在`MainThead`中执行。

`t.getName()`获得这个线程的名字，其他常用方法，`getName()`获得线程`id`,`isAlive()`判断线程是否存活等。

```python
print(t.getName()) # MainThread
print(t.ident) # 139908235814720
print(t.isAlive()) # True
```

#### 119 创建线程

创建一个线程：

```python
my_thread = threading.Thread()
```

创建一个名称为`my_thread`的线程：

```python
my_thread = threading.Thread(name='my_thread')
```

创建线程的目的是告诉它帮助我们做些什么，做些什么通过参数`target`传入，参数类型为`callable`，函数就是可调用的：

```python
def print_i(i):
    print('打印i:%d'%(i,))
my_thread = threading.Thread(target=print_i,args=(1,))
```

`my_thread`线程已经全副武装，但是我们得按下发射按钮，启动start()，它才开始真正起飞。

```python
my_thread().start()
```

打印结果如下，其中`args`指定函数`print_i`需要的参数i，类型为元祖。

```python
打印i:1
```

至此，多线程相关的核心知识点，已经总结完毕。但是，仅仅知道这些，还不够！光纸上谈兵，当然远远不够。

#### 120 交替获得CPU时间片

为了更好解释，假定计算机是单核的，尽管对于`cpython`，这个假定有些多余。

开辟3个线程，装到`threads`中:

```python
import time
from datetime import datetime
import threading


def print_time():
    for _ in range(5): # 在每个线程中打印5次
        time.sleep(0.1) # 模拟打印前的相关处理逻辑
        print('当前线程%s,打印结束时间为:%s'%(threading.current_thread().getName(),datetime.today()))


threads = [threading.Thread(name='t%d'%(i,),target=print_time) for i in range(3)]
```

启动3个线程：

```python
[t.start() for t in threads]
```

打印结果如下，`t0`,`t1`,`t2`三个线程，根据操作系统的调度算法，轮询获得CPU时间片，注意观察，`t2`线程可能被连续调度，从而获得时间片。

```markdown
当前线程t0,打印结束时间为:2020-01-12 02:27:15.705235
当前线程t1,打印结束时间为:2020-01-12 02:27:15.705402
当前线程t2,打印结束时间为:2020-01-12 02:27:15.705687
当前线程t0,打印结束时间为:2020-01-12 02:27:15.805767
当前线程t1,打印结束时间为:2020-01-12 02:27:15.805886
当前线程t2,打印结束时间为:2020-01-12 02:27:15.806044
当前线程t0,打印结束时间为:2020-01-12 02:27:15.906200
当前线程t2,打印结束时间为:2020-01-12 02:27:15.906320
当前线程t1,打印结束时间为:2020-01-12 02:27:15.906433
当前线程t0,打印结束时间为:2020-01-12 02:27:16.006581
当前线程t1,打印结束时间为:2020-01-12 02:27:16.006766
当前线程t2,打印结束时间为:2020-01-12 02:27:16.007006
当前线程t2,打印结束时间为:2020-01-12 02:27:16.107564
当前线程t0,打印结束时间为:2020-01-12 02:27:16.107290
当前线程t1,打印结束时间为:2020-01-12 02:27:16.107741
```

#### 121 多线程抢夺同一个变量

多线程编程，存在抢夺同一个变量的问题。

比如下面例子，创建的10个线程同时竞争全局变量`a`:


```python
import threading


a = 0
def add1():
    global a    
    a += 1
    print('%s  adds a to 1: %d'%(threading.current_thread().getName(),a))
    
threads = [threading.Thread(name='t%d'%(i,),target=add1) for i in range(10)]
[t.start() for t in threads]
```

执行结果：

```python
t0  adds a to 1: 1
t1  adds a to 1: 2
t2  adds a to 1: 3
t3  adds a to 1: 4
t4  adds a to 1: 5
t5  adds a to 1: 6
t6  adds a to 1: 7
t7  adds a to 1: 8
t8  adds a to 1: 9
t9  adds a to 1: 10
```

结果一切正常，每个线程执行一次，把`a`的值加1，最后`a` 变为10，一切正常。

运行上面代码十几遍，一切也都正常。

所以，我们能下结论：这段代码是线程安全的吗？

NO！

多线程中，只要存在同时读取和修改一个全局变量的情况，如果不采取其他措施，就一定不是线程安全的。

尽管，有时，某些情况的资源竞争，暴露出问题的概率`极低极低`：

本例中，如果线程0 在修改a后，其他某些线程还是get到的是没有修改前的值，就会暴露问题。



但是在本例中，`a = a + 1`这种修改操作，花费的时间太短了，短到我们无法想象。所以，线程间轮询执行时，都能get到最新的a值。所以，暴露问题的概率就变得微乎其微。

#### 122 多线程变量竞争引起的问题

只要弄明白问题暴露的原因，叫问题出现还是不困难的。

想象数据库的写入操作，一般需要耗费我们可以感知的时间。

为了模拟这个写入动作，简化期间，我们只需要延长修改变量`a`的时间，问题很容易就会还原出来。

```python
import threading
import time


a = 0
def add1():
    global a    
    tmp = a + 1
    time.sleep(0.2) # 延时0.2秒，模拟写入所需时间
    a = tmp
    print('%s  adds a to 1: %d'%(threading.current_thread().getName(),a))
    
threads = [threading.Thread(name='t%d'%(i,),target=add1) for i in range(10)]
[t.start() for t in threads]
```

重新运行代码，只需一次，问题立马完全暴露，结果如下：

```python
t0  adds a to 1: 1
t1  adds a to 1: 1
t2  adds a to 1: 1
t3  adds a to 1: 1
t4  adds a to 1: 1
t5  adds a to 1: 1
t7  adds a to 1: 1
t6  adds a to 1: 1
t8  adds a to 1: 1
t9  adds a to 1: 1
```

看到，10个线程全部运行后，`a`的值只相当于一个线程执行的结果。

下面分析，为什么会出现上面的结果：

这是一个很有说服力的例子，因为在修改a前，有0.2秒的休眠时间，某个线程延时后，CPU立即分配计算资源给其他线程。直到分配给所有线程后，根据结果反映出，0.2秒的休眠时长还没耗尽，这样每个线程get到的a值都是0，所以才出现上面的结果。



以上最核心的三行代码：

```python
tmp = a + 1
time.sleep(0.2) # 延时0.2秒，模拟写入所需时间
a = tmp
```

#### 123 多线程锁

知道问题出现的原因后，要想修复问题，也没那么复杂。

通过python中提供的锁机制，某段代码只能单线程执行时，上锁，其他线程等待，直到释放锁后，其他线程再争锁，执行代码，释放锁，重复以上。

创建一把锁`locka`:

```python
import threading
import time


locka = threading.Lock()
```

通过 `locka.acquire()` 获得锁，通过`locka.release()`释放锁，它们之间的这些代码，只能单线程执行。

```python
a = 0
def add1():
    global a    
    try:
        locka.acquire() # 获得锁
        tmp = a + 1
        time.sleep(0.2) # 延时0.2秒，模拟写入所需时间
        a = tmp
    finally:
        locka.release() # 释放锁
    print('%s  adds a to 1: %d'%(threading.current_thread().getName(),a))
    
threads = [threading.Thread(name='t%d'%(i,),target=add1) for i in range(10)]
[t.start() for t in threads]
```

执行结果如下：

```python
t0  adds a to 1: 1
t1  adds a to 1: 2
t2  adds a to 1: 3
t3  adds a to 1: 4
t4  adds a to 1: 5
t5  adds a to 1: 6
t6  adds a to 1: 7
t7  adds a to 1: 8
t8  adds a to 1: 9
t9  adds a to 1: 10
```

一起正常，其实这已经是单线程顺序执行了，就本例子而言，已经失去多线程的价值，并且还带来了因为线程创建开销，浪费时间的副作用。

程序中只有一把锁，通过 `try...finally`还能确保不发生死锁。但是，当程序中启用多把锁，还是很容易发生死锁。

注意使用场合，避免死锁，是我们在使用多线程开发时需要注意的一些问题。

**124 时间转数组及常用格式**

```python
In [68]: str_to_struct = time.strptime(format_time,'%Y-%m-%d %H:%M:%S')

In [69]: str_to_struct
Out[69]: time.struct_time(tm_year=2020, tm_mon=2, tm_mday=22, tm_hour=11, tm_min=19, tm_sec=19, tm_wday=5, tm_yday=53, tm_isdst=-1)
```

最后再记住常用字符串格式

**常用字符串格式**

%m：月

%M: 分钟

```markdown
    %Y  Year with century as a decimal number.
    %m  Month as a decimal number [01,12].
    %d  Day of the month as a decimal number [01,31].
    %H  Hour (24-hour clock) as a decimal number [00,23].
    %M  Minute as a decimal number [00,59].
    %S  Second as a decimal number [00,61].
    %z  Time zone offset from UTC.
    %a  Locale's abbreviated weekday name.
    %A  Locale's full weekday name.
    %b  Locale's abbreviated month name.
```

#### 125 寻找第n次出现位置

```python
def search_n(s, c, n):
    size = 0
    for i, x in enumerate(s):
        if x == c:
            size += 1
        if size == n:
            return i
    return -1



print(search_n("fdasadfadf", "a", 3))# 结果为7，正确
print(search_n("fdasadfadf", "a", 30))# 结果为-1，正确
```

#### 126 斐波那契数列前n项

```python
def fibonacci(n):
    a, b = 1, 1
    for _ in range(n):
        yield a
        a, b = b, a + b


list(fibonacci(5))  # [1, 1, 2, 3, 5]
```

#### 127 找出所有重复元素

```python
from collections import Counter


def find_all_duplicates(lst):
    c = Counter(lst)
    return list(filter(lambda k: c[k] > 1, c))


find_all_duplicates([1, 2, 2, 3, 3, 3])  # [2,3]
```

#### 128 联合统计次数
Counter对象间可以做数学运算

```python
from collections import Counter
a = ['apple', 'orange', 'computer', 'orange']
b = ['computer', 'orange']

ca = Counter(a)
cb = Counter(b)
#Counter对象间可以做数学运算
ca + cb  # Counter({'orange': 3, 'computer': 2, 'apple': 1})


# 进一步抽象，实现多个列表内元素的个数统计


def sumc(*c):
    if (len(c) < 1):
        return
    mapc = map(Counter, c)
    s = Counter([])
    for ic in mapc: # ic 是一个Counter对象
        s += ic
    return s


#Counter({'orange': 3, 'computer': 3, 'apple': 1, 'abc': 1, 'face': 1})
sumc(a, b, ['abc'], ['face', 'computer'])

```

#### 129 groupby单字段分组

天气记录：

```python
a = [{'date': '2019-12-15', 'weather': 'cloud'},
 {'date': '2019-12-13', 'weather': 'sunny'},
 {'date': '2019-12-14', 'weather': 'cloud'}]
```

按照天气字段`weather`分组汇总：

```python
from itertools import groupby
for k, items in  groupby(a,key=lambda x:x['weather']):
     print(k)
```

输出结果看出，分组失败！原因：分组前必须按照分组字段`排序`，这个很坑~

```python
cloud
sunny
cloud
```

修改代码：

```python
a.sort(key=lambda x: x['weather'])
for k, items in  groupby(a,key=lambda x:x['weather']):
     print(k)
     for i in items:
         print(i)
```

输出结果：

```python
cloud
{'date': '2019-12-15', 'weather': 'cloud'}
{'date': '2019-12-14', 'weather': 'cloud'}
sunny
{'date': '2019-12-13', 'weather': 'sunny'}
```

#### 130 groupby多字段分组

`itemgetter`是一个类，`itemgetter('weather')`返回一个可调用的对象，它的参数可有多个：

```python
from operator import itemgetter
from itertools import groupby

a.sort(key=itemgetter('weather', 'date'))
for k, items in groupby(a, key=itemgetter('weather')):
     print(k)
     for i in items:
         print(i)
```

结果如下，使用`weather`和`date`两个字段排序`a`，

```python
cloud
{'date': '2019-12-14', 'weather': 'cloud'}
{'date': '2019-12-15', 'weather': 'cloud'}
sunny
{'date': '2019-12-13', 'weather': 'sunny'}
```

注意这个结果与上面结果有些微妙不同，这个更多是我们想看到和使用更多的。

#### 131 itemgetter和key函数

注意到`sort`和`groupby`所用的`key`函数，除了`lambda`写法外，还有一种简写，就是使用`itemgetter`：

```python
a = [{'date': '2019-12-15', 'weather': 'cloud'},
 {'date': '2019-12-13', 'weather': 'sunny'},
 {'date': '2019-12-14', 'weather': 'cloud'}]
from operator import itemgetter
from itertools import groupby

a.sort(key=itemgetter('weather'))
for k, items in groupby(a, key=itemgetter('weather')):
     print(k)
     for i in items:
         print(i)
```

结果：

```python
cloud
{'date': '2019-12-15', 'weather': 'cloud'}
{'date': '2019-12-14', 'weather': 'cloud'}
sunny
{'date': '2019-12-13', 'weather': 'sunny'}
```

#### 132 sum函数计算和聚合同时做

Python中的聚合类函数`sum`,`min`,`max`第一个参数是`iterable`类型，一般使用方法如下：

```python
a = [4,2,5,1]
sum([i+1 for i in a]) # 16
```

使用列表生成式`[i+1 for i in a]`创建一个长度与`a`一行的临时列表，这步完成后，再做`sum`聚合。

试想如果你的数组`a`长度十百万级，再创建一个这样的临时列表就很不划算，最好是一边算一边聚合，稍改动为如下：

```python
a = [4,2,5,1]
sum(i+1 for i in a) # 16
```

此时`i+1 for i in a`是`(i+1 for i in a)`的简写，得到一个生成器(`generator`)对象，如下所示：

```python
In [8]:(i+1 for i in a)
OUT [8]:<generator object <genexpr> at 0x000002AC7FFA8CF0>
```

生成器每迭代一步吐出(`yield`)一个元素并计算和聚合后，进入下一次迭代，直到终点。

#### 133 获得某天后的1~n天

```python
import calendar
from datetime import date,datetime

def getEverydaySince(year,month,day,n=10):
    i = 0
    _, days = calendar.monthrange(year, month)
    while i < n: 
        d = date(year,month,day)    
        if day == days:
            month,day = month+1,0
            _, days = calendar.monthrange(year, month)
            if month == 13:
                year,month = year+1,1
                _, days = calendar.monthrange(year, month)
        yield d
        day += 1
        i += 1
```

测试结果：

```markdown
In [3]: for day in getEverydaySince(2020,2,1): 
   ...:     print(day)                                                                      
2020-02-01
2020-02-02
2020-02-03
2020-02-04
2020-02-05
2020-02-06
2020-02-07
2020-02-08
2020-02-09
2020-02-10
```

@version 
@date 2020/02/01
```

#### 134 list分组(生成器版)

```python
from math import ceil

def divide_iter(lst, n):
    if n <= 0:
        yield lst
        return
    i, div = 0, ceil(len(lst) / n)
    while i < n:
        yield lst[i * div: (i + 1) * div]
        i += 1

list(divide_iter([1, 2, 3, 4, 5], 0))  # [[1, 2, 3, 4, 5]]
list(divide_iter([1, 2, 3, 4, 5], 2))  # [[1, 2, 3], [4, 5]]
```
@version 
@date 2020/02/02
```

#### 135 列表全展开(生成器版)
```python
#多层列表展开成单层列表
a=[1,2,[3,4,[5,6],7],8,["python",6],9]
def function(lst):
    for i in lst:
        if type(i)==list:
            yield from function(i)
        else:
            yield i
print(list(function(a))) # [1, 2, 3, 4, 5, 6, 7, 8, 'python', 6, 9]
```
@version 
@date 2020/02/03
```

#### 136 测试函数运行时间的装饰器
```python
#测试函数执行时间的装饰器示例
import time
def timing_func(fn):
    def wrapper():
        start=time.time()
        fn()   #执行传入的fn参数
        stop=time.time()
        return (stop-start)
    return wrapper
```

使用装饰器：

```python
@timing_func
def test_list_append():
    lst=[]
    for i in range(0,100000):
        lst.append(i)  
@timing_func
def test_list_compre():
    [i for i in range(0,100000)]  #列表生成式
    
a=test_list_append()
c=test_list_compre()

print("test list append time:",a)
print("test list comprehension time:",c)
print("append/compre:",round(a/c,3))

#test list append time: 0.0219423770904541
#test list comprehension time: 0.007980823516845703
#append/compre: 2.749
```

@version 
@date 2020/02/04
```

#### 137 统计异常次数装饰器


写一个装饰器，统计某个异常重复出现指定次数时，经历的时长。

```python
import time
import math


def excepter(f):
    i = 0
    t1 = time.time()
    def wrapper(): 
        try:
            f()
        except Exception as e:
            nonlocal i
            i += 1
            print(f'{e.args[0]}: {i}')
            t2 = time.time()
            if i == n:
                print(f'spending time:{round(t2-t1,2)}')
    return wrapper

```

关键词`nonlocal`常用于函数嵌套中，声明变量i为非局部变量；

如果不声明，`i+=1`表明`i`为函数`wrapper`内的局部变量，因为在`i+=1`引用(reference)时,`i`未被声明，所以会报`unreferenced variable`的错误。

使用创建的装饰函数`excepter`, `n`是异常出现的次数。

共测试了两类常见的异常：`被零除`和`数组越界`。

```python
n = 10 # except count

@excepter
def divide_zero_except():
    time.sleep(0.1)
    j = 1/(40-20*2)

# test zero divived except
for _ in range(n):
    divide_zero_except()


@excepter
def outof_range_except():
    a = [1,3,5]
    time.sleep(0.1)
    print(a[3])
# test out of range except
for _ in range(n):
    outof_range_except()

```

打印出来的结果如下：

```python
division by zero: 1
division by zero: 2
division by zero: 3
division by zero: 4
division by zero: 5
division by zero: 6
division by zero: 7
division by zero: 8
division by zero: 9
division by zero: 10
spending time:1.01
list index out of range: 1
list index out of range: 2
list index out of range: 3
list index out of range: 4
list index out of range: 5
list index out of range: 6
list index out of range: 7
list index out of range: 8
list index out of range: 9
list index out of range: 10
spending time:1.01
```


#### 
@version 
@date 2020/02/05
```

#### 138 装饰器通俗理解

再看一个装饰器：

```python
def call_print(f):
  def g():
    print('you\'re calling %s function'%(f.__name__,))
  return g
```

使用`call_print`装饰器：

```python
@call_print
def myfun():
  pass
 
@call_print
def myfun2():
  pass
```

myfun()后返回：

```python
In [27]: myfun()
you're calling myfun function

In [28]: myfun2()
you're calling myfun2 function
```

**使用call_print**

你看，`@call_print`放置在任何一个新定义的函数上面，都会默认输出一行，你正在调用这个函数的名。

这是为什么呢？注意观察新定义的`call_print`函数(加上@后便是装饰器):

```python
def call_print(f):
  def g():
    print('you\'re calling %s function'%(f.__name__,))
  return g
```

它必须接受一个函数`f`，然后返回另外一个函数`g`.

**装饰器本质**

本质上，它与下面的调用方式效果是等效的：

```
def myfun():
  pass

def myfun2():
  pass
  
def call_print(f):
  def g():
    print('you\'re calling %s function'%(f.__name__,))
  return g
```

下面是最重要的代码：

```
myfun = call_print(myfun)
myfun2 = call_print(myfun2)
```

大家看明白吗？也就是call_print(myfun)后不是返回一个函数吗，然后再赋值给myfun.

再次调用myfun, myfun2时，效果是这样的：

```python
In [32]: myfun()
you're calling myfun function

In [33]: myfun2()
you're calling myfun2 function
```

你看，这与装饰器的实现效果是一模一样的。装饰器的写法可能更加直观些，所以不用显示的这样赋值：`myfun = call_print(myfun)`，`myfun2 = call_print(myfun2)`，但是装饰器的这种封装，猛一看，有些不好理解。
@version 
@date 2020/02/06
```
#### 139 定制递减迭代器

```python
#编写一个迭代器，通过循环语句，实现对某个正整数的依次递减1，直到0.
class Descend(Iterator):
    def __init__(self,N):
        self.N=N
        self.a=0
    def __iter__(self):
        return self 
    def __next__(self):
        while self.a<self.N:
            self.N-=1
            return self.N
        raise StopIteration
    
descend_iter=Descend(10)
print(list(descend_iter))
[9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
```

核心要点：

1 `__nex__ `名字不能变，实现定制的迭代逻辑

2 `raise StopIteration`：通过 raise 中断程序，必须这样写
    
@version 
@date 2020/02/07
```
		     
#### 140 turtle绘制奥运五环图

turtle绘图的函数非常好用，基本看到函数名字，就能知道它的含义，下面使用turtle，仅用15行代码来绘制奥运五环图。

1 导入库

```python
import turtle as p
```

2 定义画圆函数

```python
def drawCircle(x,y,c='red'):
    p.pu()# 抬起画笔
    p.goto(x,y) # 绘制圆的起始位置
    p.pd()# 放下画笔
    p.color(c)# 绘制c色圆环
    p.circle(30,360) #绘制圆：半径，角度
```

3 画笔基本设置

```python
p = turtle
p.pensize(3) # 画笔尺寸设置3
```

4 绘制五环图

调用画圆函数

```python
drawCircle(0,0,'blue')
drawCircle(60,0,'black')
drawCircle(120,0,'red')
drawCircle(90,-30,'green')
drawCircle(30,-30,'yellow')    

p.done()
```
@version 
@date 2020/02/08
```
		     
#### 141 turtle绘制漫天雪花


导入模块

导入 `turtle`库和 python的 `random`

```python
import turtle as p
import random
```

绘制雪花

```python
def snow(snow_count):
    p.hideturtle()
    p.speed(500)
    p.pensize(2)
    for i in range(snow_count):
        r = random.random()
        g = random.random()
        b = random.random()
        p.pencolor(r, g, b)
        p.pu()
        p.goto(random.randint(-350, 350), random.randint(1, 270))
        p.pd()
        dens = random.randint(8, 12)
        snowsize = random.randint(10, 14)
        for _ in range(dens):
            p.forward(snowsize)  # 向当前画笔方向移动snowsize像素长度
            p.backward(snowsize)  # 向当前画笔相反方向移动snowsize像素长度
            p.right(360 / dens)  # 顺时针移动360 / dens度

```

绘制地面

```python
def ground(ground_line_count):
    p.hideturtle()
    p.speed(500)
    for i in range(ground_line_count):
        p.pensize(random.randint(5, 10))
        x = random.randint(-400, 350)
        y = random.randint(-280, -1)
        r = -y / 280
        g = -y / 280
        b = -y / 280
        p.pencolor(r, g, b)
        p.penup()  # 抬起画笔
        p.goto(x, y)  # 让画笔移动到此位置
        p.pendown()  # 放下画笔
        p.forward(random.randint(40, 100))  # 眼当前画笔方向向前移动40~100距离
```

主函数

```python
def main():
    p.setup(800, 600, 0, 0)
    # p.tracer(False)
    p.bgcolor("black")
    snow(30)
    ground(30)
    # p.tracer(True)
    p.mainloop()

main()
```
