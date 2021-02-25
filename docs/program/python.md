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





