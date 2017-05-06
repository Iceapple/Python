Python核心编程》练习题
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

for i in range(0, 11):
	print i
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
def divisor(arg):
	alist = []
	for i in range(1, arg+1):
		if arg % i == 0:
			alist.append(i)	 
	return alist

def lcm(arg1, arg2):
	alist, blist = divisor(arg1), divisor(arg2)
	return max([value for value in alist if value in blist]) # 取交集

def gcd(arg1, arg2):
	return (arg1 * arg2) / lcm(arg1, arg2)

if __name__ == '__main__':
	num1 = int(raw_input('> num1: '))
	num2 = int(raw_input('> num2: '))
	print lcm(num1, num2)
	print gcd(num1,num2)
```
以上是分解公因数法求最小公倍数，下面是辗转相除法求最大公约数：

```python
def lcm(arg1, arg2):
	amax = max(arg1, arg2) 
	amin = min(arg1, arg2)
	t = amax % amin
	while t != 0:
		amax, amin = amin, t
		t = amax % amin 
	
	return amin
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
def payment(arg1, arg2):
	print('Amount Remaining')
	print('Pymt#  Paid     Balance') 
	print ('----- ------   ---------')
	count = 0
	paid = 0.00
	balance = arg1
	print('{}     $ {}     $ {}'.format(count, paid, balance))
	while balance > paid:
		count += 1
		paid = arg2
		balance = balance - paid
		print('{}     $ {}     $ {}'.format(count, paid, balance))
	count += 1
	print('{}     $ {}     $ 0.00').format(count, balance)	

if __name__ == '__main__':
	n1 = float(raw_input('Enter opening balace: '))
	n2 = float(raw_input('Enter monthly payment: '))
	payment(n1, n2)
```
 
### 5-17 随机数
熟读随机数模块然后解下面的题： 
生成一个有 N 个元素的由随机数 n 组成的列表， 其中 N 和 n 的取值范围分别为： `(1 < N <= 100), (0 <= n <= 231  -1)`。
然后再随机从这个列表中取 `N (1 <= N <= 100)`个随机数出来， 对它们排序，然后显示这个子集。 

```python
import random

N = random.randint(2, 100)
k = 2 ** 31 - 1

count = 0
alist = []
while count < N:
	n = random.randint(0, k)
	alist.append(n)
	count += 1

N2 = random.randint(1, 100)
count2 = 0
blist = []
while count2 < N2:
	n2 = random.choice(alist)
	blist.append(n2)
	count2 += 1
blist.sort()
print(blist)
```
 
## Chapter 6 序列 

### 6–1.   字符串
`string` 模块中是否有一种字符串方法或者函数可以帮我鉴定一下一个字符串是否是另一个大字符串的一部分? 

```python
str.index(),若不在抛出 Value Error
str.find()，若不在 返回 -1
``` 
### 6–2.   字符串标识符.
修改例 6-1 的 `idcheck.py` 脚本,使之可以检测长度为一的标识符,并且
可以识别 Python 关键字,对后一个要求,你可以使用 `keyword` 模块(特别是 `keyword.kelist`)来帮你. 
 
```python
if True:
	if myInput[0] in alphas 
```

### 6–3.   排序 
 (a) 输入一串数字,从大到小排列之.  
 (b) 跟 a 一样,不过要用字典序从大到小排列之. 

```python
1
``` 
 
### 6–4.   算术. 
更新上一章里面你的得分测试练习方案,把测试得分放到一个列表中去.你的代
码应该可以计算出一个平均分,见练习 2-9 和练习 5-3. 

```python


```

### 6–5.   字符串 
(a)更新你在练习 2-7 里面的方案,使之可以每次向前向后都显示一个字符串的一个字符.  
(b)通过扫描来判断两个字符串是否匹配(不能使用比较操作符或者 `cmp()`内建函数)。附加题：
在你的方案里加入大小写区分.  
(c)判断一个字符串是否重现(后面跟前面的一致).附加题：在处理除了严格的回文之外,加入对


例如控制符号和空格的支持。  
(d)接受一个字符,在其后面加一个反向的拷贝,构成一个回文字符串. 
 
```python
``` 

### 6–6.   字符串.
创建一个 `string.strip()`的替代函数:接受一个字符串,去掉它前面和后面的
空格(如果使用 `string.*strip()`函数那本练习就没有意义了) 

```python
``` 
### 6–7.   调试.
看一下在例 6.5 中给出的代码(`buggy.py`) 
(a)研究这段代码并描述这段代码想做什么.在所有的(#)处都要填写你的注释.  
(b)这个程序有一个很大的问题,比如输入 6,12,20,30,等它会死掉,实际上它不能处理任何的偶
数,找出原因.  
(c)修正(b)中提出的问题. 

```python
```  
### 6–8.   列表.
给出一个整数值,返回代表该值的英文， 比如输入89返回"eight-nine"。 附加题：
能够返回符合英文语法规则的形式，比如输入“89”返回“eighty-nine” 。本练习中的值限定在家 0
到 1,000. 

```python

```  
### 6–9.   转换.
为练习 5-13 写一个姊妹函数, 接受分钟数, 返回小时数和分钟数. 总时间不
变,并且要求小时数尽可能大.  

```python

```   
### 6–10.字符串.
写一个函数,返回一个跟输入字符串相似的字符串,要求字符串的大小写反转.
比如,输入"Mr.Ed",应该返回"mR.eD"作为输出. 
Example 6.4  有 bug 的程序(buggy.py) 
 
这是一个用于练习 6-7 的程序,判断这个程序是干什么的,在"#"处添加你的注释,找出其中的错
误,并修改之. 
``` 
1 #!/usr/bin/env python 
2 
3 # 
4 num_str = raw_input('Enter a number: ') 
5 
6 #  
7 num_num = int(num_str) 
8 
9# 
10 fac_list = range(1, num_num+1) 
11 print "BEFORE:", 'fac_list' 
12 
13 # 
14 i = 0 
15 
16 # 
17 while i < len(fac_list): 
18 
19 # 
20 if num_num % fac_list[i] == 0: 
21 del fac_list[i] 
22 
23 # 
24 i = i + 1 
25 
26 # 
27 print "AFTER:", 'fac_list' 
```

```python

```  

### 6–11.转换 
(a)创建一个从整数到 IP 地址的转换程序,如下格式: `WWW.XXX.YYY.ZZZ`.   
(b)更新你的程序,使之可以逆转换. 

```python

```   
### 6–12.字符串 
(a)创建一个名字为 findchr()的函数,函数声明如下:  `def findchr(string, char)`  
 `findchr()`要在字符串 `string` 中查找字符 `char`,找到就返回该值的索引,否则返回-1.不能用
`string.*find()`或者 `string.*index()`函数和方法  
(b)创建另一个叫 `rfindchr()`的函数,查找字符 `char` 最后一次出现的位置.它跟 `findchr()`工作
类似,不过它是从字符串的最后开始向前查找的.  
(c)创建第三个函数,名字叫 `subchr()`,声明如下: 
  `def subchr(string, origchar, newchar)`  
 `subchr()`跟 `findchr()`类似,不同的是,如果找到匹配的字符就用新的字符替换原先字符.返回
修改后的字符串.


```python

```  

### 6–13.字符串.
`string` 模块包含三个函数,`atoi()`,`atol()`,和 `atof()`,它们分别负责把字符串转
换成整数,长整型,和浮点型数字.从Python1.5起,Python的内建函数`int()`,`long()`,`float()`也可以
做相同的事了, `complex()`函数可以把字符串转换成复数.(然而 1,5 之前,这些转换函数只能工作于
数字之上) 
   `string`模块中并没有实现一个`atoc()`函数,那么你来实现一个.`atoc()`接受单个字符串做参
数输入,一个表示复数的字符串,例如,'-1.23e+4-5.67j',返回相应的复数对象.你不能用 eval()函
数,但可以使用 `complex()`函数,而且你只能在如下的限制之下使用 `complex():complex(real,imag)``
的 `real` 和 `imag` 都必须是浮点值. 

```python

```  

### 6–14.随机数.
设计一个"石头,剪子,布"游戏,有时又叫"Rochambeau",你小时候可能玩过,下面
是规则.你和你的对手,在同一时间做出特定的手势,必须是下面一种手势:石头,剪子,布.胜利者从
下面的规则中产生,这个规则本身是个悖论.  
(a) the paper covers the rock,  布包石头.  
(b)石头砸剪子,  
(c)剪子剪破布.在你的计算机版本中,用户输入她/他的选项,计算机找一个随机选项,然后由你
的程序来决定一个胜利者或者平手.注意:最好的算法是尽量少的使用 `if` 语句. 

```python

```   
### 6–15.转换 
(a)给出两个可识别格式的日期,比如 `MM/DD/YY` 或者 `DD/MM/YY` 格式,计算出两个日期间的天
数.  
(b)给出一个人的生日,计算从此人出生到现在的天数,包括所有的闰月.  
(c)还是上面的例子,计算出到此人下次过生日还有多少天. 

```python

```   
### 6–16.矩阵.
处理矩阵M和N 的加和乘操作. 

```python

```   
### 6–17.方法.
实现一个叫 `myPop()`的函数,功能类似于列表的 `pop()`方法,用一个列表作为输入,
移除列表的最新一个元素,并返回它. 

```python

```      
### 6–18. zip() 内建函数  
在6.13.2节里面关于`zip()`函数的例子中,`zip(fn,ln)`返回的是什么? 

```python

```   
### 6–19.多列输出.
有任意项的序列或者其他容器,把它们等距离分列显示.由调用者提供数据和
输出格式.例如,如果你传入100个项并定义3列输出,按照需要的模式显示这些数据.这种情况下,应
该是两列显示 33 个项,最后一列显示 34 个.你可以让用户来选择水平排序或者垂直排序. 

```python

```  