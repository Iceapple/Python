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
(a)让用户输入三个数 并分别将它们保存到3个不同的变量中。不使用列表或排序算法，自己来写代码来对这三个数由小到大排序。
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
## Chapter 5 数字

### 5-2 运算符 
(a) 写一个函数，计算并返回两个数的乘积 
(b) 写一段代码调用这个函数，并显示它的结果

```python
def mul(arg1, arg2):
	return arg1 * arg2

if __name__ == '__main__':
	myInput1 = float(raw_input('>input num1: '))
	myInput2 = float(raw_input('>input num2: '))
	my_value = mul(myInput1, myInput2)
	print("the mul of two number is {}".format(my_value))
```
### 5-3 标准类型运算符
写一段脚本，输入一个测验成绩，根据下面的标准，输出他的评分成绩（A-F）。   
A: 90–100  
B: 80–89  
C: 70–79  
D: 60–69  
F: <60 

```python
def grade(arg):
	if (arg > 100 or arg < 0):
		return 'Out of range!'
	if arg < 60:
		return 'F'
	if arg >=60 and arg <= 69:
		return 'D'
	if arg >=70 and arg <= 79:
		return 'C'
	if arg >=80 and arg <= 89:
		return 'B'
	if arg >=90 and arg <= 100:
		return 'A'

if __name__ == '__main__':
	myInput = float(raw_input('input you score number: '))
	print(grade(myInput))
```
 
### 5-4 取余
判断给定年份是否是闰年。使用下面的公式：  
一个闰年就是指它可以被 4 整除，但不能被 100 整除， 或者它既可以被 4 又可以被 100 整除。
比如 1992，1996 和 2000 年是闰年，但 1967 和 1900 则不是闰年。下一个是闰年的整世
纪是 2400 年。

```python
def leap_year(arg):
	if arg % 400 == 0 or (arg % 4 == 0 and arg % 100 != 0):
		return 'leap year'
	else:
		return 'not leap year'

if __name__ == '__main__':
	myInput = int(raw_input('input the year: '))
	print(leap_year(myInput))
```
 
### 5-5 取余
取一个任意小于 1 美元的金额，然后计算可以换成最少多少枚硬币。  
硬币有 1 美分，5 美分，10 美分，25 美分四种。1 美元等于 100 美分。举例来说，0.76 美元换算结果
应该是 3 枚 25 美分，1 枚 1 美分。类似 76 枚 1 美分，2 枚 25 美分+2 枚 10 美分+1 枚 5 美分+1 枚 1 美分这样的结果都是不符合要求的。 

```python
def dollar_change(arg):
	arg_cent = int(arg * 100)
	if arg_cent >= 100 or arg_cent <= 0:
		return 'error'
	else:
		(h, a) = divmod(arg_cent, 25)
		(i, b) = divmod(a, 10)
		(j, k) = divmod(b, 5)
		return [h, i, j, k]

if __name__ == '__main__':
	myInput = float(raw_input('how much dollar: '))
	print(dollar_change(myInput))
```
 
### 5-6 算术
写一个计算器程序 你的代码可以接受这样的表达式:  
两个操作数加一个运算符：`N1 运算符 N2`. 其中 N1 和 N2 为整数或浮点数，运算符可以是 `+, -, *, /, %, **` 分别表示加法，减法， 乘法， 整数除，取余和幂运算。  
计算这个表达式的结果，然后显示出来。
提示：可以使用字符串方法 `split()`,但不可以使用内建函数 `eval()`. 

```python
def calc(N1, ope, N2):
	N1, N2 = float(N1), float(N2)
	if ope == '+':
		return N1 + N2
	if ope == '-':
		return N1 - N2
	if ope == '*':
		return N1 * N2
	if ope == '/':
		return N1 / N2
	if ope == '%':
		return N1 % N2
	if ope == '**':
		return N1 ** N2

if __name__ == '__main__':
	[N1, ope, N2] = raw_input('blabla ').split(' ')
	print(calc(N1, ope, N2))
```
 
### 5-7 营业税
随意取一个商品金额，然后根据当地营业税额度计算应该交纳的营业税。 

```python
(略)
```
  
### 5-8 几何
计算面积和体积： 
(a) 正方形 和 立方体 
(b) 圆 和 球 

```python
(略)
```
 
### 5–9  数值形式
回答下面关于数值格式的问题： 
(a) 为什么下面的例子里 17+32 等于 49， 而 017+32 等于 47， 017+032 等于 41？ 
```
>>> 17 + 32 
49 
>>> 017+ 32 
47 
>>> 017 + 032 
41
``` 
（b）为什么下面这个表达式我们得到的结果是 134L 而不是 1342 ？ 
```
>>> 56l + 78l 
134L 
``` 

```python
(a) 017是8进制
(b) 长整数
```
 
### 5-10 转换
写一对函数来进行华氏度到摄氏度的转换。转换公式为 `C = (F - 32) * (5 / 9)` 
应该在这个练习中使用真正的除法， 否则你会得到不正确的结果。 

```python
def f_c(F):
	return (F - 32) * (5.0 / 9)
if __name__ == '__main__':
	f = float(raw_input('input F:'))
	print(f_c(f))
```
  
### 5-11 取余 
(a) 使用循环和算术运算，求出 `0－20` 之间的所有偶数 
(b) 同上，不过这次输出所有的奇数 
(c) 综合 (a) 和 (b)， 请问辨别奇数和偶数的最简单的方法是什么？ 
(d) 使用(c)的成果，写一个函数，检测一个整数能否被另一个整数整除。 
先要求用户输入两个数，然后你的函数判断两者是否有整除关系，根据判断结果分别返回 True 和 False; 

```python
def odd(arg):
	alist = []
	for i in range(0, arg+1):
		if  i % 2 == 0:
			alist.append(i)
	return alist

def even(arg):
	alist = []
	for i in range(1, arg+1):
		if  i % 2 == 1:
			alist.append(i)
	return alist

def divisi(a, b):
	if (a % b == 0) or (b % a == 0):
		return True
	else:
		return False

if __name__ == '__main__':
	myInput1 = int(raw_input('input a '))
	myInput2 = int(raw_input('input b '))
	print(divisi(myInput1, myInput2))
```
  
### 5-12 系统限制
写一段脚本确认一下你的 Python 所能处理的整数，长整数，浮点数和复
数的范围。 

```python
(略)
```
  
### 5-13 转换
写一个函数把由小时和分钟表示的时间转换为只用分钟表示的时间。  

```python
略
```
  
### 5-14 银行利息
写一个函数，以定期存款利率为参数， 假定该账户每日计算复利，请计
算并返回年回报率。 

```python
def ROI(rate_day):
	rate_year = (1 + rate_day) ** 365 - 1
	return rate_year

if __name__ == '__main__':
	myInput = float(raw_input('input daily rate '))
	print(ROI(myInput))
```
  
### 5–15 最大公约数和最小公倍数
请计算两个整数的最大公约数和最小公倍数。 

```python

```
  
### 5-16 家庭财务
给定一个初始金额和月开销数， 使用循环，确定剩下的金额和当月的支出数， 包括最后的支出数。 Payment() 函数会用到初始金额和月额度， 输出结果应该类似下面的格式（例子中的数字仅用于演示） ：  

```
Enter opening balance:100.00 
Enter monthly payment: 16.13 
Amount Remaining 
Pymt#  Paid     Balance 
----- ------   --------- 
0     $ 0.00     $ 100.00 
1     $ 16.13    $ 83.87 
2     $ 16.13    $ 67.74 
3     $ 16.13    $ 51.61 
4     $ 16.13    $ 35.48 
5     $ 16.13    $ 19.35 
6     $ 16.13    $ 3.22 
7     $ 3.22     $ 0.00 
------------------------
```

```python

```
 
### 5-17 随机数
熟读随机数模块然后解下面的题： 
生成一个有 N 个元素的由随机数 n 组成的列表， 其中 N 和 n 的取值范围分别为： `(1 < N <= 100), (0 <= n <= 231  -1)`。然后再随机从这个列表中取 `N (1 <= N <= 100)`个随机数
出来， 对它们排序，然后显示这个子集。 

```python

```
  