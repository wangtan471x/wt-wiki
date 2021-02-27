### 知识

#### def __init__(self):

[关于def __init__(self)的一些知识点](https://zhuanlan.zhihu.com/p/55237543)

而Python中就规定好了，函数的第一个参数，就必须是实例对象本身，并且建议，约定俗成，把其名字写为self,以safe为前缀的变量都可供类中的**所有方法使用**



#### python中for in的用法

```python
for x in y:
  ``循环体
```

执行流程：x依次表示y中的一个元素，遍历完所有元素循环结束。

```python
s = 'I love you more than i can say'
for i in s:
  ``print(i)
```



#### python if not的用法

1. 

```python
if not (1 > 2):        #如果()中的表达式为假   
	print("hahaha")    #1 > 2结果是假,所以执行hahaha 
else:   
    print("hihihi")
```

2. 

```python
if not 1:              #1为真,并不为假,因此不执行hahaha,执行hihihi
   print("hahaha")
else:
   print("hihihi")
```

3. 

```python
python中非空即为真,空即为假,因此也常用来判断变量是否为空
while(1):
   data = input()              #输入数据
   if not data:                   #如果data为假(即data为空)
       print("hahaha")
   else:                        #如果data不为空
       print("hihihi")
```

#### 函数定义

```
def interview():
    print("把求职者带到3号会议室")
    print("请求职者 完成答卷")
    print("让测试经理来面试 求职者")
    print("让技术总监面试 求职者")
```

**def** 是关键字 表示定义一个函数

后面是函数的**名字**，紧接着后面需要一个**括号** ，这个括号中间，根据需要还可以有 **参数**,这里我们先不讲它

最后是一个**冒号**，下面的缩进的代码表示这个函数名字代表的具体动作是什么，称之为**函数体**。

那么如果我们就是需要在函数内部 把全局变量进行重新赋值，该怎么办呢？

这时，就需要我们在函数内部使用 `global` 关键字声明，使用的是全局变量。

```
var = '桌子'
def test():
    global  var
    var = '椅子'
    print(f"在函数中，var的值是：{var}")
test()
print(f"在函数外，var的值是：{var}")
```

def  printAge(*students) :

这种前面加**一个星号**的参数，称之为可变参数，

#### 列表和元组

```
元组（Tuple）也是一种sequence特性的类型， 它和列表非常相似，也可以存放任何类型的数据对象，除了一点： 元组的内容是 不能改变 的
如果元组中只有一个元素，必须要在后面加上逗号，像这样
a = (1, )

列表（List）对象 经常被用来 存储 数据对象。
a = [1, 2, 3.14, 'hello']
```

#### 自带函数

```python
isdigit：是否全是数字
startswith('1') 是否以1开头
reverse()将列表元素倒过来

```

#### 循环

```python
# range里面的参数100 指定循环100次
# 其中 n 依次为 0,1,2,3,4... 直到 99
for n in range(100):  
    print(n)      
    print('python，我爱你')
```

#### with语句

```python
# open返回的对象 赋值为 变量 f
with open('tmp.txt') as f:
    linelist = f.readlines() 
    for line in linelist:
        print(line)
```

#### 模块和库

```
在Python中，一个代码文件（也就是一个.py文件），我们也叫它一个模块（Module）

这些放模块文件的目录，Python中把他们称之为 包 (Package) 
在 Python 3.3 以前的版本，包目录里面需要有一个名字为 __init__.py 的初始化文件，有了它，Python才认为这是一个Python包。
Python 3.3 以后版本的解释器， 如果目录只是用来存放模块文件，就不需要一个空的 __init__.py 了。
但是 __init__.py 可以作为包的初始化文件，里面放入一些初始化代码，有独特的作用。这个英文帖子有细致的描述，感兴趣的朋友可以阅读一下。
```

#### 字典定义

```
字典对象定义用花括号 {} , 字典里面的 每个元素之间用 逗号 隔开。
每个元素都是一个键值对，键和值之间用 冒号 隔开。
members = {
    'account1'  : 13 ,
    'account2'  : 12 
}
根据键去获取值，是这样的语法 var[key] 。
如果我们要删除一个元素，可以使用字典对象的pop方法
也可以使用 del 关键字来删除一个元素
1. 有时候，我们要检查字典的key中，是否有我们要找的元素，可以通过 in 这个关键字 ，比如
a in var   # 检查 a 是否在var 中存在，存在返回True，否则返回False

items方法，返回的是一个类似列表一样的对象，其中每个元素就是 键值组成的元组
上面的字典，其items方法返回的是类似这样的对象
for account,level in members.items():
    print (f'account:{account}, level:{level}')
```

#### 类

```
定义一个类 用关键字 class 后面加 类的名称。
 @staticmethod 的修饰， 说明这是该类的一个 静态方法
 实例属性通常是在类的 初始化方法 __init__ 里面定义的。
 
 要特别注意的是， 子类的初始化方法里面，如果有一部分的初始化代码和父类的初始化相同（通常都是这样），需要显式的 调用父类的初始化方法 __init__
而且要传入相应的参数， 像上面那样，然后可以加上自己的特有的初始化代码。如下所示
def __init__(self,color,engineSN,weight):
    # 先调用父类的初始化方法
    BenzCar.__init__(self,color,engineSN)
    self.weight = weight 
    self.oilweight = 0  
使用super的好处之一就是：子类中调用父类的方法，不需要 显式指定 父类的名字。 代码的可维护性更好。
```

#### 异常捕获

```
如果我们在编码的时候，就预料到了某些代码运行时可能出现某些异常，就可以使用 try...except... 这样的方法来捕获和处理异常。
```

#### if __name__ == '__main__':的作用

一个python文件通常有两种使用方法，第一是作为脚本直接执行，第二是 import 到其他的 python 脚本中被调用（模块重用）执行。因此 if __name__ == 'main': 的作用就是控制这两种情况执行代码的过程，在 if __name__ == 'main': 下的代码只有在第一种情况下（即文件作为脚本直接执行）才会被执行，而 import 到其他脚本中是不会被执行的。