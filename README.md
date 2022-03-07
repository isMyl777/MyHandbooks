# Python学习笔记  
# python语言特性  
强类型动态语言  
基础数据类型  
Number数字  String字符串  list列表  tuple元组  set集合  dictionary字典  
可变  list set dict  
不可变  数字 元组 字符串  
number又包含 int  float  long complex  

# 判断python变量的类型
type()  # 直接输出类型  
isinstance(1,int) # 输出是true or false，判断1整型  
python 变量和对象  
python 空类型表示：None  

# 编码和解码
encode编码，将人类认识的字符转换为计算机可识别的过程  
decode解码，编码的反向过程  
python2默认是ascii码  
python3默认是unicode，可识别中文字符 。utf-8可以看做是unicode的一个扩展集  
比特 /bit：计算机中最小的数据单位，是单个的二进制数值 0 或 1  
字节 / byte：计算机存储数据的单元，1 个字节由 8 个比特组成  
字符：人类能够识别的符号  
编码：将人类可识别的字符转换为机器可识别的字节码 / 字节序列  
解码：编码的反向过程叫解码  
概述：Unicode 是人类可识别的字符格式；ASCII 、UTF-8 、GBK 等都是机器可识别的字节码格式。  
我们写在文件中的 py3 代码，是由字符组成的，它们的格式，就是 Unicode，而字符是以字节为存储单位保存在文件中，文件保存在内存 / 物理磁盘中  

# 标识符  
标识符由字符，下划线，数字组成，但是第一个字符不能是数字  

# 运算符
```text
+ - × / (加减乘除) %(取余) // (向下取整)  ×× (乘方运算符） 
```

# 比较运算符
```text
==  !=  > <  >= <=  <>(python3已废弃)  
```

# 位运算符
按位运算符是把数字看作二进制来计算  
```text
& 按位与运算，都为1,结果为1
| 按位或运算，有一个为1结果为1
^ 按位异或运算，相异为1
~ 按位取反
<<左移运算符
>>右移运算符
```
# 逻辑运算符  
```text
not  布尔非
and  布尔与     x and y 如果x是false，x and y 返回false，否则返回y的计算值
or   布尔或     x or y 如果x是非0,它返回x的计算值，否则返回y的计算值
and如果没有假值，返回的是最后一个真值，如果有假值，则返回的是第一个假值。
or如果没有真值，返回的是最后一个假值，如果有真值，则返回的是第一个真值  
```

# is和==区别
```text
is 和 == 区别
is表示内存地址
==表示值
小整数池[-5，256]python预先设置好内存地址，所以在该范围内的内存地址相同
```

# 格式化输出
```text
&d   print('周长: %d' %a)
%s 字符型
%f float型
%c 字符
```

# 数学运算类
```python
    abs(x)                              # 求绝对值，参数可以是整型，也可以是复数，若参数是复数，则返回复数的模
    complex([real[, imag]])             # 创建一个复数
    divmod(a, b)                        # 分别取商和余数，注意：整型、浮点型都可以
    float([x])                          # 将一个字符串或数转换为浮点数。如果无参数将返回0.0
    int([x[, base]])                    # 将一个字符串或浮点数转换为int类型，base表示进制
    long([x[, base]])                   # 将一个字符串或浮点数转换为long类型
    pow(x, y)                           # 返回x的y次幂
    range([start], stop[, step])        # 产生一个序列，默认从0开始
    round(x[, n])                       # 四舍五入
    sum(iterable[, start])              # 对集合求和
    oct(x)                              # 将一个数字转化为8进制字符串
    hex(x)                              # 将一个数字转换为16进制字符串
    chr(i)                              # 返回给定int类型对应的ASCII字符
    unichr(i)                           # 返回给定int类型的unicode
    ord(c)                              # 返回ASCII字符对应的整数
    bin(x)                              # 将整数x转换为二进制字符串
    bool([x])                           # 将x转换为Boolean类型
```
# 变量的本质
```text
变量的本质是指向存储实体的指针
变量在使用前必须赋值，变量赋值后该变量才会被创建
```

# 垃圾回收机制
```text
垃圾回收机制简称GC,是python解释器自带的一种机制，专门用来回收不可用的变量值所占用的内存空间
程序运行过程中会申请大量的内存空间，对于一些无用的内存空间如果不及时清理就会导致内存使用殆尽（内存溢出）
解决方法
引用计数： 一旦为0，其占用的内存地址就应该被解释器的垃圾回收机制回收
标记清除：从栈区删除
分代回收：在经历多次扫描的情况下，都没有被回收的变量，GC机制就会认为，该变量为常用变量
```

# map
```python
num = 123
print(sum(map(int,str(num)))) #输出是6
map 用法
map(function, iterable, ...)
python3 输出是迭代器
```

# 深浅拷贝
```text
list1 = [1,2,3]
#浅拷贝
list2 = list1.copy()
#深拷贝,可变和不可变类型加以区分
list3 = list1.deepcopy()
```

# 设计模式
```text
单例模式
工厂模式
```
# 流程控制
```text
短路运算：偷懒原则，偷懒到那个位置，就把当前位置的值返回
if循环
if 条件判断：
    代码1
else：
    代码2
例子2
if 条件判断：
    code1
elif 条件判断：
    code2
else：
    code3
while循环
while 条件判断：
    代码1
    代码2    
break    终止当前循环,之后的代码不再执行
continue 跳出当前循环，继续 continue之后同级代码毫无意义，永远不会执行
例子1：
a = 0 
while a <10:
    a+=1
    if a =='7':
        continue
    print(a)
死循环while 1 比 while true效率要高
```

# 简单函数
```python
def changeme(myList):  //定义函数
    myList.append(4)
    print(myList)
    return
mylist = [1,2,3]
changeme(mylist)  //调用函数
输入输出函数
input()  //输入永远是一个str类型
print()
匿名函数lambda
num2 = 100
sum1 = lambda num1,num2 : num1 + num2
num2 = 10000
sum2 = lambda num1 : num1 + num2
print(sum1(1))
print(sum2(1))
#num2是一个自由变量，在运行时绑定值，而不是定义时就绑定，这跟函数的默认值参数定义是不同的
```

# 局部变量和全局变量
```text
全局变量和局部变量的区别在于作用域，全局变量在全局范围内都可以使用，局部变量只能在函数内部使用。
在函数内部，如果局部变量和全局变量变量名一样，则优先调用局部变量
在函数内部改变全局变量，需要在前面机上global关键字，函数执行后，全局变量也会发生改变。
global与nonlocal的区别
功能不同，nonlocal关键字修饰变量后标识该变量是上一级函数中的局部变量，如果上一级函数中不存在该局部变量，nonlocal 位置会发送错误
使用范围不同，global关键字可以用在任何地方，而nonlocal关键字只能用于嵌套函数中，并且外层函数中定义路相应的局部变量，否则会报错

nonlocal声明的变量不是局部变量,也不是全局变量,而是外部嵌套函数内的变量
```

# python字符串操作
```python
查找
str1 = 'hello world in the world'
# find()
print(str1.find('in'))  # 子串不存在返回-1
print(str1.find('world'))
print(str1.find('world',15,30))
# index()
print(str1.index('world'))
print(str1.index('world',15,30))
# index 查找子串不存在会报错
# count
print(str1.count('world'))
# rfind() rindex() 查找方向从右侧开始
# 修改  replace
print(str1.replace('world','世界'))
print(str1)
# 分割 split  返回一个列表，丢失分割字符
print(str1.split(' '))
# example
url = "www.baidu.com_1.jpg"
file_name = url.split('_')[0] #取下划线左边
file_name1 = url.split('_')[1] #取下划线右边部分
str1.strip()
#用于移除字符串头尾指定的字符，默认为空格或者字符序列
# join
list1 = ['1','2','3','4']
list2 = ['a','b','c','d']
print(type(list1))
print('to'.join(list1))  //''中为自定义部分
print(''.join(list2))
capitalize()  #将字符串第一个字符转换成大写
注意：capitalize()函数转换后，只有字符串第一个字符大写，其他字符全部小写
# title()   # 将字符串首字母都转换成大写
# lower()   # 将字符串转换成小写
# upper()   # 将字符串转换成大写
# str1 = 'hello world in the world'
# print(str1.capitalize())
# print(str1.title())
# print(str1.lower())
# print(str1.upper())
# 删除字符串首尾空格
# str1 = '   hello   world   '
# print(str1.lstrip())
# print(str1.rstrip())
# print(str1.strip())
# 字符串对齐
# str1 = 'hello'
# print(str1.ljust(10))
# print(str1.ljust(10,'.'))
# print(str1.rjust(10))
# print(str1.rjust(10,'.'))
# print(str1.center(10))
# print(str1.center(10,'.'))
# 字符串的判断 返回的结果为bool True  False
str1 = 'hello world with python'
print(str1.startswith('hello'))
print(str1.endswith('pythons'))
print(str1.isalpha())  #字母
print(str1.isdigit())  #数字
print(str1.isalnum())  #字母数字的组合
print(str1.isspace())  #空白
```

# python列表
```python
list1 = []  # 定义一个空列表
list1 = [1,2,3,4]
list1.append(5)  #增加列表
list1.extend(5)
#append 是添加整个对象， extend是添加可迭代的对象
list1.insert(index,value)
print(list1)
del list1[0]     #删除列表
list1.remove(value) #移除指定值 leetcode 刷题遇到过
list1.clear()    #清空列表
print(list1)
list1[0] = 'hhhh' #修改列表
print(list1)
list1.reverse() #倒序 源数据的逆序
list1.sort() 升序
list1.sort(reverse = true) 降序
list1[::-1] 降序
list2 = list1.copy()  # 列表复制
print(1 in list1)  # 查询 返回 True False  not in：判断指定数据不在某个列表序列
print(list1[1:])  #截取 左闭右开
#列表遍历的三种方式
list1 = [1,2,3,4]
for i in list1:
    print(i,list1.index(i))
for i in range(len(list1)):
    print(i,list1[i])
for i,value in enumerate(list1):
    print(i,value)
```

# 队列和堆栈
队列：先进先出  
堆栈：先进后出  

# python元组
```text
#定义元祖
t1 = ()
#元组中只包含一个元素时，需要在元素后面添加逗号来消除歧义
t1 = (1,)
元组是不可修改的
删除元组，元祖是不可删除的，只能删除整个元组来达到删除的效果
Python元组包含了以下内置函数
1、cmp(tuple1, tuple2)：比较两个元组元素
2、len(tuple1)：计算元组元素个数
3、max(tuple1)：返回元组中元素最大值
4、min(tuple1)：返回元组中元素最小值
5、tuple(seq)：将列表转换为元组
```

# python字典
```python
# 字典
dict1 = {'name':'xiaoma','age':'18'}
print(dict1)
print(type(dict1))
# 创建空字典
dict2 = {}
dict3 = dict()
#字典新增
dict1['name'] = 'xiaosu'
print(dict1)
#如果key存在则修改这个key对应的值，如果key不存在则新增词键值对
#字典是可变类型
dict1['id'] = '0010'
print(dict1)
#字典删除
del dict1['name']
print(dict1)
dict1.clear()
print(dict1)
#字典修改
#字典查找
#key值查找
print(dict1['name'])
#get()
print(dict1.get('name'))
print(dict1.get('id'))
print(dict1.keys())
print(dict1.values())
print(dict1.items())
# 字典的遍历
for key in dict1.keys():
    print(key)
for value in dict1.values():
    print(value)
for item in dict1.items():
    print(item)
for key,value in dict1.items():
    print(f"{key}={value}")
#合并字典
1、dict(a, **b)
2、c = {}
c.update(a)
c.update(b)
3、dict(list(a.items()) + list(b.items()))
```

python集合
# 集合
s1 = {10,20,30,40,50}
print(type(s1))
print(s1)  #集合是无序的，不支持下标
# s2 = set('abcdefgh')
# print(s2)
# #创建空集合
# s3 = set()
# print(s3)
# print(s4)
# 增加数据
# add() 集合有去重功能
# s1.add(60)
# print(s1)
# # update()
# s1.update([70])  #追加的数据是序列
# print(s1)
#删除数据
#remove()  删除集合中的指定数据
# s1.remove(50)
# print(s1)
#discard()
# s1.discard(40)
# print(s1)
#pop()
# s1.pop()  # 随机删除一个数字
# print(s1)
#查找数据
# in 判断数据在集合序列
# not in 判断数据不在集合序列
# 返回值是布尔类型
# status = 10 in s1
# print(status)
# status1 = 90 not in s1
# print(status1)
公共运算符




推导式
# 推导式
list1 = [x for x in range(11)]
print(type(list1))
print(list1)
# 带if的推导式
list2 = [x for x in range(11) if x%2 == 0]
print(list2)
#根据步长实现要求
list3 = [x for x in range(0,11,2)]
print(list3)
#多个for循环实现列表推导式
# list1 = [(i,j) for i in range(0,3) for j in range(0,3)]
# print(list1)
#多for的列表推导式等同于嵌套循环
# 字典推导式
list1 = ['name','age','id']
list2 = ['tom','18','10001']
dict1 = { i:j  for i in list1 for j in list2}
print(dict1)
# 字典推导式
# list1 = ['name','age','id']
# list2 = ['tom','18','10001','100']
# dict1 = { i:j  for i in list1 for j in list2}
# dict1 = {list1[i]:list2[i] for i in range(len(list1))}
# print(dict1)
# 提取字典中的目标数据
# counts = {'mbp':268,'hp':125,'dell':201,'lenovo':199,'acer':99}
# count1 = {key:value for key,value in counts.items() if value >= 200}
# print(count1)
#集合推导式
# list1 = [1,1,2]
# ll = {i**2 for i in list1}
# print(ll)
# print(type(ll))
迭代器和生成器
迭代：就是循环遍历的过程。迭代器只能往前，由iter() 和next() 组成
生成器：带有yield的函数为生成器
yield

函数
函数的作用
封装代码，高效的代码重用
函数的使用步骤
def 函数名(参数)：
    代码1
    代码2
    ....
#不同的需求，参数可有可无
#先定义在使用
函数的参数作用
形参 和 实参
def sum(a, b): 形参
     return a+b
sum(10, 3.14)  实参
函数的返回值
def sum(a, b):
     return a+b
b = sum(10, 3.14)
print(b)
函数的说明文档
help(len)  查看函数的说明文档
def sum():
    '''说明文档'''
函数的嵌套调用
变量的作用域
全局变量
局部变量
多函数程序执行流程
返回值作为参数传递
def testA():
    return 50
def testB(num):
    print(num)
result = testA()
testB(result)
函数的返回值
def more_return():
    return  1,2
res = more_return()
print(res)
print(type(res))
return后面可以连接列表，元组或字典，以返回多个值
return a,b 写法，返回多个数据的时候，默认是元组类型
函数的参数
1、位置参数：调用函数时根据函数定义的参数位置来传递参数
2、关键字参数： 函数调用，通过键 = 值 形式加以指定
3、缺省参数
4、不定长参数
def person(name,age,id):
    print(f"姓名是{name},年龄{age}，学号是{id}")
person('Tom',18,'10001')

def person(name,age,id):
    print(f"姓名是{name},年龄{age}，学号是{id}")
person('james',id = 10001,age = 26)


Python中*args和**kwargs的区别
 *args 用来将参数打包成tuple给函数体调用
 **kwargs 打包关键字参数成dict给函数体调用
拆包
# 拆包 元组
def return_num():
    return 100,200
num1,num2 = return_num()
print(num1)
print(num2)
# 拆包：字典
dict1 ={'name':'Tom','age':18}
a,b = dict1
#对字典拆包，取出来的是字典的key
print(dict1[a])
print(dict1[b])
引用
在python中，值是靠引用来传递的
引用当做实参
def test(a):
    print(a)
    print(id(a))
    a += a
    print(a)
    print(id(a))

b = [10,20]
test(b)
递归
def jiecheng(n):
    if n <= 1:
        return 1
    return n * jiecheng(n-1)
res = jiecheng(4)
print(res)
lambda
# lambda 匿名函数
# lambda 参数列表 ： 表达式
#直接打印lambda,打印的是lambda的地址
# fn2 = lambda : 'annotation'
# print(fn2())
# fn1 = lambda  a,b : a*b
# print(fn1(3,2))
# lambda 参数
#无参数
# fn1 = lambda :100
# print(fn1())
#一个参数
# fn1 = lambda  a : a
# print(fn1('hello world'))
# #默认参数
# fn1 = lambda a,b,c =100: a+b+c
# print(fn1(200,300))
# #可变参数
# fn1 = lambda  *args:args
# print(fn1(10,20,30))
# # 注意：这里的可变参数传入lambda之后，返回值 为元组
# fn1 = lambda  **kwargs:kwargs
# print(fn1(name = 'python',age = 3))
#lambda 的应用
# fn1 = lambda  a,b : a if a>b else b
# print(fn1(100,200))

#列表数据按照字典key值排序
student = [{'name':'xiaosu','age':10},{'name':'xiaoma','age':11},{'name':'xiaolin','age':9}]
student.sort(key = lambda  x:x['age'])
print(student)
高阶函数
#绝对值
# a = abs(-10.01)
# print(a)
#四舍五入
# b =round(3.7)
# print(b)
#高阶函数体验
# def sum_num(a,b,f):
#     return f(a)+f(b)
# res = sum_num(-1,2,abs)  # 此处的为abs，不是abs()
# print(res)

#内置的高阶函数
#map(func,list1)  python2 返回列表，python3 返回迭代器
# list1 = [1,2,3,4,5]
# def func(x):
#     return x**2
# res = map(func,list1)
# print(res) #<map object at 0x0000026A9A2E6940>
# print(list(res))
#reduce(func,list1) 其中func必须有2个参数，每次func计算的结果继续和序列的下一个元素做累计计算
# import  functools
# list1 = [1,2,3,4,5]
# def func(x,y):
#     return x+y
# res = functools.reduce(func,list1)
# print(res)
#filter() 用于过滤序列，过滤掉不符合条件的元素，返回一个filter对象。
# list1 = [1,2,3,4,5,6,7,8,9,10]
# 
# def func(x):
#     if x%2 == 0:
#      return x
# res =filter(func, list1)
# print(list(res))
# print(res) #<filter object at 0x00000202F77A6FD0>
文件操作
文件操作的作用就是把一些内容数据存储起来，可以让程序下一次执行的时候直接使用，而不必重新制作一份



file = open('C:\\Users\\EDZ\\Desktop\\newtest.txt','r')
#read 不写参数表示读取所有
#文件换行\n,会有字节占位
# print(file.read())
# print(file.readlines())  # 返回的是一个列表，输出[]
# con = file.readline()
# print(con)
# file.close()
'''
r+  r没有文件则报错；文件指针在开头
w+  w没有文件会创建，文件指针在开头，但是新内容会覆盖原内容
a+  a没有文件会创建，文件指针在结尾，无法读取数据
'''
# seek() 作用：用来移动文件指针
# file.seek(22)
# print(file.read())
# file.close()
文件备份
oldFile = input('请输入文件名')
#C:\\Users\\EDZ\\Desktop\\newtest.txt
index = oldFile.rfind('.')
s1 = oldFile[:index]
s2 = oldFile[index:]
newFile = s1 + 'copy' + s2
old_File = open(oldFile,'rb')
new_File = open(newFile,'wb')
while True:
    con = old_File.read()
    if len(con) == 0:
        break
    new_File.write(con)
old_File.close()
new_File.close()
文件操作
import  os
# 重命名
#os.rename('oldName','newName')
#删除文件
#os.remove(目标文件名)
#os.remove('C:/Users/EDZ/PycharmProjects/newPython/01day/1.txt')
#创建文件
# os.mkdir('C:/Users/EDZ/PycharmProjects/newPython/02day')
#删除文件夹
#os.rmdir('C:/Users/EDZ/PycharmProjects/newPython/02day')
#获取当前目录
# path = os.getcwd()
# print(path)
#改变目录路径
# path1 = os.chdir('newpath')
# print(path1)
#获取目录列表
# path = 'C:/Users/EDZ/PycharmProjects/newPython/01day'
# dir = os.listdir(path)  # 返回的是列表
# for file in dir:
#     print(file)
#修改文件名
path = 'C:\\Users\\EDZ\\Desktop\\test\\'
dir = os.listdir(path)  # 返回的是列表

flag =1
for file in dir:
    if flag == 1:
         new_name = 'python '+ file
    else:
        num = len('python')
        new_name=file[num:]
        
    os.rename(path+file,path+new_name)
由于反斜杠在python中被视为转义标记，为保证在windows下正确，应以原始字符串的方式指定路径，即在开头的单引号前加上r,如下

new_dir=r'D:\workspace\drtm\release_bin\tasks\file_luanxian#steel_luanxian_5_detector\img'
面向对象
类和对象
用类去创建一个对象，或者用类实例化对象 
对象是“容器”，对象存放数据与功能
注意：先有类，再有对象
定义类： 语法
class 类名():
    代码
#类名要满足标识符命名规则，同时遵循大驼峰命名习惯
创建对象：对象又名实例
对象名 = 类名()
添加和获取对象属性
1、类外面添加对象属性
2、类里面获取对象属性
class washer():
    def wash(self):
        print('洗衣服')
        print(self)
    # 类里面调用对象属性
    def print_info(self):
        print(self.width)
        print(self.height)

# 一个类可以定义多个对象
haier = washer()
nokia = washer()
#类外面添加对象属性
haier.width = 500
haier.height = 800
#
haier.wash()
nokia.wash()
haier.print_info()
魔法方法
__init__:对象初始化方法
__new__:创建对象时候执行的方法，单列模式会用到
__str__:当使用print输出对象的时候，只要自己定义了__str__(self)方法，那么就会打印从在这个方法中return的数据
__del__:删除对象执行的方法
在python中，__xx__()的函数叫做魔法方法，指的是具有特殊功能的函数
#__init__()方法的作用：初始化对象
class washer():
    def __init__(self):
        self.width = 500
        self.height = 600
'''
注意：__init__()方法，在创建一个对象时默认被调用，不需要手动调用
     __init__(self)中的self参数，不需要开发者传递，python解释器会自动把当前的对象引用传递过去
'''
     def wash(self):
        print('洗衣服')
        # print(self)
    #类里面调用对象属性
    def print_info(self):
        print(self.width)
        print(self.height)

haier = washer()

haier.wash()
haier.print_info()
带参数的__init__(参数)方法
class washer():
    def __init__(self, a, b,c):
        self.width = a
        self.height = b

    def print_info(self):
        print(self.width)
        print(self.height)

haier = washer(500, 800,0)
haier.print_info()

nokia = washer(500, 1000,0)
nokia.print_info()
__str__()方法
#__str__()
# 当使用print输出对象的时候，默认打印对象的内存地址。如果类定义了__str__()方法，那么就会打印从在这个方法众人return的数据
class washer():
    def __init__(self, a, b):
        self.width = a
        self.height = b
# 没有str，print(对象) 输出类的地址； 定义了str之后。输出的内容为return返回的值
    def __str__(self):
        return "hello world" # return 解释说明：类的说明或者对象的说明

    def print_info(self):
        print(self.width)
        print(self.height)

haier = washer(500, 800)
print(haier)
haier.print_info()

##__del__()方法的使用
# class washer():
#     def __init__(self,a,b):
#         self.a = a
#         self.b = b
#     def __del__(self):
#         print(f"{self}对象已经被删除")
# 
# haier =  washer(10,20)
搬家具案例
class house():
    def __init__(self,local,area):
        self.local = local
        self.area = area
        self.free_area = area
        self.desk = []

    def add_desk(self,item):
        if self.free_area >= item.area:
            self.desk.append(item.name)
            self.free_area = self.free_area - item.area
        else:
            print("家具太大，剩余面积不足，无法容纳")

    def __str__(self):
        return f'房子坐落于{self.local},占地面积{self.area},剩余面积{self.free_area}'

class desk():
    def __init__(self,name,area):
        self.name = name
        self.area = area

home1 = house('上海',100)
desk1 = desk("餐桌",10)
desk2 = desk("沙发",10)
home1.add_desk(desk1)
home1.add_desk(desk2)
print(home1)
面向对象-继承
class 类名：
    代码
    ......
class 类名(object):
    代码
    .....
##案例 
class A(object):
    def __init__(self):
        self.num = 1
    def info_print(self):
        print(self.num)
    def __str__(self):
        return f"{self.num}"
# 定义子类，继承父类
class B(A):
    pass

res = B()
res.info_print()
print(res)
## 多继承
注意：当一个类有多个父类的时候，默认使用第一个父类的同名属性和方法
class master(object):
    def __init__(self):
        self.kongfu = '牛肉面配方'

    def make_noodles(self):
        print(f"运用{self.kongfu}制作拉面")

class School(object):
    def __init__(self):
        self.kongfu = '黑马牛肉面配方'
    def make_noodles(self):
        print(f"运用{self.kongfu}制作拉面")

class prentice(School,master):
    pass

yiwanmian = prentice()
yiwanmian.make_noodles()
继承案例
#定义汽车类
class Car():

    def __init__(self,make,model,year):
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0
    def get_desc_name(self):
        print(self.model + self.make + self.year)
    def read_odometer(self):
        print('this car has' + str(self.odometer_reading) + "miles on it.")
    def update_odometer(self,mileage):
        self.odometer_reading = mileage

audi = Car('audi','Q7','2020')
audi.update_odometer(800)
audi.get_desc_name()
audi.read_odometer()
#电动车类继承汽车
class electCar(Car):
    def __init__(self,make,model,year):
        super().__init__(make,model,year)
tesla = electCar('tesla','model 3','2017')
tesla.update_odometer(300)
tesla.get_desc_name()
tesla.read_odometer()
子类重写父类同名方法和属性

子类调用父类的同名方法和属性

类属性的优点：
记录的某项数据始终保持一致时，则定义类属性
实例属性要求每个对象为其单独开辟一份内存空间来记录数据，
而类属性为全类所共有，仅占用一份内存，更加节省内存空间
类方法和静态方法
#类方法和静态方法
#类方法一般和类属性配合使用，当方法中需要使用类对象时，定义类方法
# class dog(object):
#     __tooth =10
#     @classmethod
#     def get_tooth(cls):
#         return cls.__tooth
#
# wangcai = dog()
# res = wangcai.get_tooth()
# print(res)

#静态方法 @staticmethod
# class dog(object):
#     @staticmethod
#     def info_print():
#         print("这是一个狗类，用于创建狗实例")
# wangcai = dog()
# wangcai.info_print()
# dog.info_print()
异常
#异常
import os

# file = open('text.txt','r')
# file.readline()
# print(file.readline())
#捕获指定异常
# try:
#     file =  with open('text.txt', 'r+')
#     file.read()
#     print('hhh')
# except FileNotFoundError:
#     file = open('text.txt', 'w')
#     file.write("new create file")
#     print("file create")
#捕获多个指定异常
# try:
#     print(1/0)
# except (NameError,ZeroDivisionError):
#     print('有错误')
#捕获异常描述信息
# try:
#      print(1/0)
# except (NameError,ZeroDivisionError) as res:
#      print(res)
#捕获所有异常
#exception 是所有程序异常类的父类
# try:
#     print(num)
# except Exception as res:
#     print(res)

#异常的else
# try:
#     print("hello")
# except Exception as res:
#     print(res)
# else:
#     print("这是没有异常的情况下执行的代码")
#异常的finally
# try:
#     print(1)
# except Exception as res:
#     print(res)
# finally:
#     print("这是最终都要执行的部分")
#异常的传递
# try:
#      with open("C:\\Users\\EDZ\\Desktop\\test\\newtest.txt",'r') as file:
#          try:
#              while True:
#
#                  if len(file.read()) != 0:
#                      print(file.read())
#                      print("hello world")
#                  else:
#                      break
#                      pass
#          except Exception as res:
#              print(res)
# except:
#      print("该文件不存在")
# finally:
#      file.close()
#      print("文件关闭")
#自定义异常
#抛出自定义异常的语法为raise shortinputerror(len(con),3)
class shortinputerror(Exception):
    def __init__(self,length,min_len):
        self.length = length
        self.min_len = min_len

    def __str__(self):
        return f'你输入的长度是{self.length}，不能少于{self.min_len}个字符'

def main():
    try:
        con = input('请输入密码：') 
        if len(con) < 3:
            raise shortinputerror(len(con),3)
    except Exception as res:
        print(res)
    else:
        print("密码已经输入完成")

if __name__ == '__main__':
    main()

python网络编程
IP地址
udpClientSocket = socket(AF_INET,SOCK_DGRAM)
udpServerSocket = socket(AF_INET,SOCK_DGRAM)
#socket.AF_INET 默认是ipv4
#socket.AF_INET 表示ipv6
#socket.DGRAM 数据报式 socket for udp
#socket.STREAM 流式socket for tcp
#address = (host,port)
socket.sendto(data,address)
socket.recvfrom()
UDP
TCP
python并发编程
参考文档：https://www.cnblogs.com/zhangyafei/p/9606765.html
协程：
1、利用greenlet
from greenlet import greenlet
def func1():
    print(1)        # 第1步：输出 1
    gr2.switch()    # 第3步：切换到 func2 函数
    print(2)        # 第6步：输出 2
    gr2.switch()    # 第7步：切换到 func2 函数，从上一次执行的位置继续向后执行
def func2():
    print(3)        # 第4步：输出 3
    gr1.switch()    # 第5步：切换到 func1 函数，从上一次执行的位置继续向后执行
    print(4)        # 第8步：输出 4
gr1 = greenlet(func1)
gr2 = greenlet(func2)
gr1.switch() # 第1步：去执行 func1 函数
2、利用yield 和yield from python 3.3
def func1():
    yield 1
    yield from func2()
    yield 2

def func2():
    yield 3
    yield 4

f1 = func1()
for item in f1:
    print(item)
3、asyncio
import asyncio

async  def test1():
    print(1)
    await asyncio.sleep(2)
    print(3)

async  def test2():
    print(2)
    await asyncio.sleep(2)
    print(4)

tasks = [asyncio.ensure_future(test1()),asyncio.ensure_future(test2())]
print(type(tasks)) #type is list
loop = asyncio.get_event_loop()
loop.run_until_complete(asyncio.wait(tasks))
#>>>out 1 2 3 4
1、并发&并行
并发：系统拥有处理多个任务的能力
并行：系统拥有同时处理多个任务的能力
import threading #线程
import time


def music():
    print('begin to listen music {}'.format(time.ctime()))
    time.sleep(3)
    print('stop to listen music {}'.format(time.ctime()))


def game():
    print('begin to play game {}'.format(time.ctime()))
    time.sleep(5)
    print('stop to play game {}'.format(time.ctime()))


if __name__ == '__main__':
    t1 = threading.Thread(target=music) #创建一个线程对象t1 子线程
    t2 = threading.Thread(target=game) #创建一个线程对象t2 子线程

    t1.start()
    t2.start()

    # t1.join() #等待子线程执行完 t1不执行完，谁也不准往下走
    t2.join()

    print('ending.......') #主线程
    print(time.ctime())
GIL(全局解释器锁）：
无论你启多少个线程，你有多少个cpu, Python在执行的时候会淡定的在同一时刻只允许一个线程运行。
同步& 异步
同步：当调用方法执行完成之后并返回结果，才能执行后续代码
异步：调用方法后不会等到执行完成，而是直接执行后续代码。结果通过状态通知猪线程，或者通过回调处理这次异步方法执行的结果

阻塞&非阻塞


粘包：TCP粘包是指发送方发送的若干包数据到接收方接收时粘成一包，从接收缓冲区看，后一包数据的头紧接着前一包数据的尾。出现粘包现象的原因是多方面的，它可能是由发送方造成的，也可能是接收方造成的
粘包的解决方案：
1、让发送端在发送数据前，把要发送的数据大小让接收端知道，然后接收端来一个死循环接收所有数据。
2、可以借助struct模块，把要发送的数据转换成固定长度的字节。这样客户端每次接收数据之前先接收这个固定长度的字节内容看一看接下来要接收的数据大小，
最终接收到的数据只要达到这个值就停止。


装饰器
装饰器使一个函数或方法包装在另一个函数里头，可以在被包装的函数添加一些额外的功能，比如日志，还可以对参数、返回结果进行修改。装饰器有点类似Java中的AOP。下面这个例子是打印被装饰的函数里面的参数的装饰器，
def print_args(function):
     def wrapper(*args, **kwargs):
         print 'Arguments:', args, kwargs
         return function(*args, **kwargs)
return wrapper

@print_args
def write(text):
    print text

write('foo')
Arguments: ('foo',) {}
foo

@是语法糖，它等价于：
write = print_args(write)
write('foo')
arguments: ('foo',) {}
foo

python正则表达式
https://note.youdao.com/s/L6wDn9V
数据库
数据库增删改查
数据库索引
Mysql 事务
MySQL 事务主要用于处理操作量大，复杂度高的数据。
比如说，在人员管理系统中，你删除一个人员，你既需要删除人员的基本资料，也要删除和该人员相关的信息，如信箱，文章等等，这样，这些数据库操作语句就构成一个事务！
特性：原子性，一致性，独立性，持久性

前端
浏览器发请求 --> HTTP协议 --> 服务端接收请求 --> 服务端返回响应 --> 服务端把HTML文件内容发给浏览器 --> 浏览器渲染页面
html
css
js
python包
system函数可以将字符串转化成命令在服务器上运行；其原理是每一条system函数执行时，其会创建一个子进程在系统上执行命令行，子进程的执行结果无法影响主进程；
上述原理会导致当需要执行多条命令行的时候可能得不到预期的结果；
os.system()
os.listdir()和os.walk()的区别
listdir不会执行子目录，walk会执行文件夹下所有文件。包括子目录

hashlib模块
import hashlib
m = hashlib.md5()
return m.hexdigest())

猴子补丁
属性在运动时的动态替换
get 和 post的区别
GET请求是通过URL直接请求数据，数据信息可以在URL中直接看到，比如浏览器访问；而POST请求是放在请求头中的，我们是无法直接看到的；
GET提交有数据大小的限制，一般是不超过1024个字节，而这种说法也不完全准确，HTTP协议并没有设定URL字节长度的上限，而是浏览器做了些处理，所以长度依据浏览器的不同有所不同；
POST请求在HTTP协议中也没有做说明，一般来说是没有设置限制的，但是实际上浏览器也有默认值。总体来说，少量的数据使用GET，大量的数据使用POST。
GET请求因为数据参数是暴露在URL中的，所以安全性比较低，比如密码是不能暴露的，就不能使用GET请求；
POST请求中，请求参数信息是放在请求头的，所以安全性较高，可以使用。在实际中，涉及到登录操作的时候，尽量使用HTTPS请求，安全性更好

session 和cookie的区别
session 在服务器端，cookie 在客户端（浏览器）
session 的运行依赖 session id，而 session id 是存在 cookie 中的，也就是说，如果浏览器禁用了 cookie ，同时 session 也会失效。
存储Session时，键与Cookie中的sessionid相同，值是开发人员设置的键值对信息，进行了base64编码，过期时间由开发人员设置
cookie安全性比session差
python的5种设计模式
单例模式，工厂模式，构建者模式，代理模式，观察者模式

os模块
import os
os.getcwd() # 获取当前目录
os.O_RDONLY #只读
os.chdir("/var/www/html" ) #切换目录
fd = os.open( "/tmp", os.O_RDONLY )
os.fchdir(fd)  #切换到新目录
python读csv文件
import csv
f = csv.reader(open('1111.csv','r'))
for i in f:
    print(i)
进程和线程
https://www.ruanyifeng.com/blog/2013/04/processes_and_threads.html



进程与线程的选择取决以下几点：
1、需要频繁创建销毁的优先使用线程；因为对进程来说创建和销毁一个进程代价是很大的。
2、线程的切换速度快，所以在需要大量计算，切换频繁时用线程，还有耗时的操作使用线程可提高应用程序的响应
3、因为对CPU系统的效率使用上线程更占优，所以可能要发展到多机分布的用进程，多核分布用线程；
4、并行操作时使用线程，如C/S架构的服务器端并发线程响应用户的请求；
5、需要更稳定安全时，适合选择进程；需要速度时，选择线程更好。
进程是运行中的程序，线程是进程内部的一个执行序列
进程是资源分配的单元，线程是执行单元
进程间切换代价大，线程间切换代价小
进程拥有资源多，线程拥有资源少
多个线程共享进程资源
__new__和__init__区别
new是静态方法，init是实例方法
new方法默认返回实例对象供init方法、实例方法调用
init方法是初始化方法，为类的实例提供一些属性
 __new__是一个静态方法，而__init__是一个实例方法
__new__方法会返回一个创建的实例，而__init__什么都不返回
只有在__new__返回一个cls的实例时，后面的__init__才能被调用
当创建一个新实例时调用__new__，初始化一个实例时用__init__
Python装饰器
python装饰器的本质：
函数闭包的语法糖

https://python3-cookbook.readthedocs.io/zh_CN/latest/c02/p01_split_string_on_multiple_delimiters.html
