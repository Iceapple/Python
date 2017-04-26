《Python核心编程》练习题
=========================
## Chapter 2
### 2-5 循环和数字
分别使用 `while` 和 `for` 创建一个循环: 
(a) 写一个 `while` 循环，输出整数从0到10。（要确保是从 0到 10，而不是从 0到9或从 1到 10） 
(b) 同(a)，不过这次使用 `range()` 内建函数。
```python
counter = 0
while counter < 11:
	print counter
	counter += 1

for i in range(0, 11):print i
```
### 2-6 条件判断
判断一个数是正数，还是负数，或者等于 `0`. 开始先用固定的数值，然后修改你的代码支持用户输入数值再进行判断。

```python
numA = int(raw_input('>input a number: '))
if numA > 0:
	print('>0')
elif numA < 0:
	print('<0')
else:
	print('=0')
```

### 2-7 #循环和字串# 
从用户那里接受一个字符串输入，然后逐字符显示该字符串。先用`while`循环实现，然后再用 `for` 循环实现。
for loop
```python
strA = raw_input('>input some str: ')
for i in strA:print i
```
while loop
```python
strA = raw_input('>input some str: ')
counter = 0
while counter < len(strA):
	print strA[counter]
	counter += 1
```
### 2-8 循环和运算符 
创建一个包含五个固定数值的列表或元组，输出他们的和。然后修改你的代码为接受用户输入数值。分别使用 `while` 和 `for` 循环实现。
```python
L = raw_input(">input 5 numbers,split with ',': ").split(',')

counter = 0
i = 0
while counter < len(L):
	i = int(L[counter]) + i
	print i
	counter += 1
 
s = 0
for i in range(0, len(L)):
	s = s + int(L[i])
 	print(s)
```

### 2-9 循环和运算符 
创建一个包含五个固定数值的列表或元组，输出他们的平均值。本练习的难点之一是通过除法得到平均值。 你会发现整数除会截去小数，因此你必须使用浮点除以得到更
精确的结果。`float()`内建函数可以帮助你实现这一功能。 
```python
L = raw_input(">input 5 numbers,split with ',': ").split(',')
L = ['1.5','2','3','4','5']
s = 0
for i in range(0,len(L)):
 	s = s + float(L[i])
	print(s)
ave = s / len(L)
print(ave)
```
### 2-10 带循环和条件判断的用户输入
使用 `raw_input()` 函数来提示用户输入一个1和100之间的数，如果用户输入的数满足这个条件，显示成功并退出。否则显示一个错误信息然后再次提示用户输入数值，直到满足条件为止。
```python
num = int(raw_input('>input a number between 1 to 100:'))

while (num < 1 or num > 100):
 	print('Wrong number!Plz input a number between 1 to 100')
	num = int(raw_input('>input a number between 1 to 100:'))
 
print('Done!')
```

### 2-11 带文本菜单的程序
写一个带文本菜单的程序，菜单项如下 `（1）取五个数的和 (2) 取五个数的平均值....（X）退出` 。
由用户做一个选择，然后执行相应的功能。当用户选择退出时程序结束。这个程序的有用之处在于用户在功能之间切换不需要一遍一遍的重新启动你的脚本。（这对开发人员测试自己的程序也会大有用处）

```python
"""1.取5个数之和；2. 取5个数的平均值；...(X)退出"""		
 
print（"""
 	(1)sum
 	(2)ave
 	...
 	(x)quit""")
 
str = raw_input('> ')
L = [1, 2, 3, 4, 5]
sum = 0
while str != 'x':
 	for counter in range(len(L)):
 		sum += L[counter]
 	
 	if str == '1':
 		print(sum)		
 	elif str == '2':
 		ave = sum / 5
 		print(ave)		
 	else:	
 		print('plz enter your choice')
 		
 	str = raw_input('> ')
 	sum = 0	
```

###  2-12 dir()内建函数  
(a) 启动 Python 交互式解释器， 通过直接键入`dir()`回车以执行 `dir()`内建函数。你看到什么？显示你看到的每一个列表元素的值，记下实际值和你想像的值

(b) 你会问, `dir()`函数是干什么的？我们已经知道在 `dir` 后边加上一对括号可以执行 `dir()` 内建函数，如果不加括号会如何？解释器返回给你什么信息？你认为这个信息表示什么意思？ 

(c) `type()` 内建函数接收任意的 Python 对象做为参数并返回他们的类型。 在解释器中键入 `type(dir)`， 看看你得到的是什么？ 

(d) 我们来瞧一瞧 Python的文档字符串。 通过 `dir.__doc__` 可以访问 `dir()`内建函数的文档字符串。`print dir.__doc__` 可以显示这个字符串的内容。许多内建函数，方法，模块及模块属性都有相应的文档字符串。 

```python
`>>> dir()`

['__builtins__', '__doc__', '__name__', '__package__']
```

### 2-15 元素排序
(a)让用户输入三个数 并分别将它们保存到3个不同的变量中。不使用列表或排序算法，自己来写代来码对这三个数由小到大排序。
(b)修改(a)的解决方案,使之从大到小排序
```python
numA = raw_input('>numA: ')
numB = raw_input('>numB: ')
numC = raw_input('>numC: ')
 
def small2big(a, b, c):
	if (a < b) and (a < c) and (b < c):
		return [a, b, c]
 	if (a < b) and (a < c) and (c < b):
 		return [a, c, b]
 	if (b < a) and (b < c) and (a < c):
 		return [b, a, c]
 	if (b < a) and (b < b) and (c < a):
 		return [b, c, a]
 	if (c < a) and (c < b) and (a < b):
 		return [c, a, b]
 	return [c, b, a]
 
print(small2big(numA, numB, numC))
```

