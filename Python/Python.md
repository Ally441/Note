## Python

### 列表

是有一系列按特定顺序排列的元素组成。用方括号([])来表示列表，并用逗号来分隔其中的元素。

#### 访问列表元素

索引从0开始，访问最后一个列表元素可以通过将索引指定为-1来访

```python
a = ['h','e','l','l','o']
print(a[-1])  #o
print(a[-2])  #l
```

#### 添加、修改和删除元素

```python
1.在列表末尾添加元素
    b = ['jack', 'lucky']
    b.append('ally')  #['jack','lucky','ally']
2.在列表中插入元素
    c = ['jack','Mike','lucky']
    c.insert(0,'ally') #['ally','jack','Mike','lucky']
3.修改
	d = ['jack','Mike','lucky']
	d[0] = 'ally' #['ally','Mike','lucky']
4.删除
	使用del语句删除元素
	del d[0] #['Mike','lucky']
	使用方法pop()删除元素（可以删除列表末尾的元素）
	e = c.pop() # e='ally' c = ['jack','Mike','lucky']
	使用方法pop()来删除列表中任何位置的元素
	f = c.pop(1) # f='jack' c = ['ally','Mike','lucky']
    根据值删除元素
    c.remove('ally') #c = ['jack','Mike','lucky']
	
```

#### 组织列表

使用方法sort()对列表进行永久性排序

![image-20201203224026973](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201203224026973.png)

也可以进行倒序排序

![image-20201203224127790](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201203224127790.png)

使用函数sorted()对列表进行临时排序

![image-20201203224339605](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201203224339605.png)

使用方法reverse()反转列表元素的排列顺序

![image-20201203224511007](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201203224511007.png)

确定列表的长度

![image-20201203224557236](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201203224557236.png)

#### 创建数值列表

​	使用函数range()

​			![image-20201205171500764](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201205171500764.png)

​	函数range()让Python从你指定的第一个值开始数，并在到达你指定的第二个值后停止

​	使用range()创建数字列表

​		![image-20201205171740101](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201205171740101.png)

​	range()可以指定步长

​	![image-20201205171845451](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201205171845451.png)

​	python的乘方是**

​	![image-20201205172415605](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201205172415605.png)

#### 列表解析

将for循环和创建新元素的代码合并成一行，并自动附加新元素

![image-20201205172718839](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201205172718839.png)

#### 切片

要创建切片，可指定要使用的第一个元素和最后一个元素的索引

![image-20201206100613614](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206100613614.png)

如果没有指定第一个索引，Python将自动从列表开头开始

![image-20201206100832821](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206100832821.png)

同时切片终止与列表尾部

![image-20201206101255653](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206101255653.png)

![image-20201206101456194](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206101456194.png)

遍历切片

![image-20201206103604798](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206103604798.png)

复制列表

![image-20201206105306507](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206105306507.png)

变量friends关联到包含在players中的列表，两个变量指向同一个变量

![image-20201206105822367](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206105822367.png)

#### 元组

不可变的列表称为元组

```
number = (10,20)
print(number) # (10,20)
```

```
# 遍历元祖中的所有值
number = (10,20)
for i in number:
	print(number)
# 10
# 20
```

不能修改元组的元素，但可以给存储元组的变量赋值

![image-20201206113633277](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206113633277.png)

### if语句

```
cars = ['audi','bmw']
for car in cars:
	if car == 'bmw':
		print(car.super())
	else:
		print(car,title())
```

```
#检查多个条件
#使用and
age1 = 20
age2 = 30 
age1 >= 19 and age2 >= 29
True
#使用or
age1 >= 21 or age2 > 29
True
```

```
#检查特定值是否包含在列表中
>>>requests = ['room','gym','playground']
>>>'gym' in requests
True
```

```
#检查特定值是否不包含在列表中
users = ['jack','mark','lucy']
banned_user = 'ally'
if banned_user in users:
	print(banned_user +"is not here")
```

布尔表达式的结果要么为True,要么为False

#### if-elif-else

```
age = 12
if age < 10:
	price = 0
elif age < 12:
	price = 5
elif age == 12:
	price = 10
else:
	price = 20
print(price)
```

else根据条件情况可以省略

#### 判断列表是否为空

```
request = []
if request:
	print("is not null")
else:
	print("is null")
```

### 字典

字典是一系列键-值对

```
alien = {'color': 'blue', 'points': 5}
print(alien['color'])
#blue
```

#### 添加键-值对

![image-20201206141059283](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206141059283.png)

#### 修改字典中的值

![image-20201206141512153](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206141512153.png)

#### 删除键-值对

![image-20201206141802225](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206141802225.png)

#### 遍历字典

![image-20201206143013631](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206143013631.png)

#### 遍历字典中的所有键

![image-20201206143502762](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206143502762.png)

方法keys()返回一个列表，其中包含字典中的所有键

#### 遍历字典中的所有值

![image-20201206144007733](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206144007733.png)

方法values()返回一个列表，其中包含字典中的所有值

#### 嵌套

##### 字典列表

![image-20201206144403860](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206144403860.png)

### 用户输入和while循环

```
#函数input()
name = input("Please enter your name: ")
print("Hello" +  name + "!")
```

#### 使用int()来获取数值输入

```
>>>age = input("How old are you?")
How old are you? 21
>>>age = int(age)
>>>age >= 18
True
```

#### 求模运算符

```
>>>4%3
1
```

#### while循环

```
current_number = 1
while current_number <= 5:
	print(current_number)
	current_number += 1
```

#### 使用标志

可以定义一个变量，用于判断整个程序是否处于活动状态

#### 使用break退出循环

```
while True:
	city = input("where is your city?")
	if city == 'quit':
		break
	else:
    	print("I will go to this city" + city)
```

#### 使用continue退出循环

```
current_number = 0
while current_number < 10:
	current_number += 1
	if current_number % 2 == 0:
		continue
		print(current_time)
#输出表示
1
3
5
7
9
```

### 函数

#### 关键字实参

```
def describe_pet(animal_type, pet_name):
	print("\n I have a" + animal_type + ".")
	print("My " + animal_type + " 's name is " + pet_name.title() + ".")
```

```
#两个函数调用是等效的
describe_pet(animal_type='hamster', pet_name='harry')
describe_pet(pet_name='harry',animal_type='hamster')
```

#### 默认值

```
def describe(pet_name, animal_type = 'dog'):
	print("My " + animal_type + " 's name is " + pet_name.title() + ".")
describe(pet_name='jack')
#My dog's name is jack.
describe(pet_name='jack', animal_type='bird')
#My bird's name is jack.
#由于显式地给animal_type提供了实参，因此Python将忽略这个形参的默认值
```

#### 传递任意数量的实参

```
#形参名*top中的星号让Python创建一个名为top的空元组，并将收到的所有值都封装到这个元组中
def test(*top):
	print(top)
test('ally')
test('ally','jack','lucky')
```

![image-20201206221047230](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206221047230.png)

#形参名**user_info的两个星号让Python创建一个名为user_info的空字典，并将收到的所有名称-值对都封装到这个字典中。

![image-20201206222601485](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201206222601485.png)

#### 导入模块

```
1.import 模块名
2.from moudle_name import function_name
```

#### 指定别名

```
#函数指定别名
from module_name import function_name as fn
#模块指定别名
import module_name as mn
```

#### 导入模块中的所有函数

```
from module_name import *
```

### 类

#### 创建类

```
在Python中，首字母大写的名称指的式类，这个类定义中的括号是空的
方法_init_():当类创建实例的时候，Python都会自动运行它。
在这个方法中定义包含了形参self,当Python调用这个_init_()方法来创建实例时，会自动传入实参self
```

#### 继承

```
class Car():
	def _init_(self,make,model,year):
		self.make = make
		self.model = model
		self.year = year

class ElectricCar(Car):
	def _init_(self,model,year):
		super()._init_(make,model,year)
		
		
#Python2.7
class Car(object):
	def _init_(self,make,model,year):
		--snip--

class ElectricCar(Car):
	def _init_(self,make,model,year):
		super(ElectricCar,self)._init_(make,model,year)
```

##### 重写父类方法：

```
class Car():
	def test():
		print("Hello world")
       
class ElectricCar(Car):
	def test():
		print("Hello everyone")
```

##### 导入类：

```
#单个类
from car import Car

#多个类
from car import Car,ElectricCar
```

##### 导入整个模块：

```
import car
```

##### 导入模块中的所有类：

```
from module_name import *
```

##### 在一个模块中导入另一个模块

```
from car import Car
```

### 文件和异常

#### 从文件中读取数据

![image-20201208201904595](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201208201904595.png)

#### 逐行读取

![image-20201208203103713](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201208203103713.png)

#### 创建一个包含文件各行内容的列表

![image-20201208203641343](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201208203641343.png)

#### 写入文件

![image-20201208204807515](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201208204807515.png)

#### 写入多行

![image-20201208204933846](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201208204933846.png)

#### 附加到文件

![image-20201208205352687](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201208205352687.png)

### 异常

#### 使用try-except代码块

```
try:
	print(5/0)
except ZeroDivisionError:
	print("You can't divide by zero!")
```

#### else代码块

```
try:
	print(5/0)
except ZeroDivisionError:
	print("You can't divide by zero!")
else:
	print("Hello world")
```

