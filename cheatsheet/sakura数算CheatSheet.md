**\# 序列**

切片：

list\[a:b:c\]

#a为起始下标，b为结束下标，c为步长，左开右闭

&nbsp;

排序：

list=list.sort() #从小到大（按照字典序，如果元素是序列，则从第一个往后依次比较）

list=list.sort(reverse=True) #从大到小

&nbsp;

插入：

list.insert(i,x) #表示在列表的第i索引处插入x，插入后x的索引就是i

&nbsp;

查找某元素数量：

numl=list.count(a)

&nbsp;

查找某一元素的下标：

str.find(a,b,c)

list.index(a,b,c)

&nbsp;

\# 指定搜索范围

s = "apple banana apple"

print(s.find("apple")) # 输出：0（第一个apple）

print(s.find("apple", 1)) # 输出：13（从索引1开始找）

print(s.find("apple", 1, 10)) # 输出：-1（在1-10范围内未找到）

&nbsp;

区别：find只适用于字符串，index适用于列表和字符串。

&nbsp;

**\# 字典**

a=dict()

a={}

c=sorted(a) #将字典的键进行排序，返回一个有序的键列表

#a={1:1,1:2}

#c=sorted(a)

&nbsp;

#get() 方法用于获取字典中指定键的值。其语法为 dictionary.get(key, default=None)。

ver.get(vert, None)

&nbsp;

#items() 例如：

my_dict = {'a': 1, 'b': 2, 'c': 3}

for key, value in my_dict.items():

print(key, value)

\# 输出:

\# a 1 # b 2 # c 3

&nbsp;

去除一个列表中重复的元素:

numbers = list(map(int, input().split())

numbers = list(dict.fromkeys(numbers)) # remove duplicates

&nbsp;

**stack**

单调栈:：是一种常用的数据结构，通常用于解决一些数组或字符串相关的问题，特别是在需要寻找某个元素左右第一个比它大或小的位置时非常有用。在 Python 中，可以使用列表来实现单调栈的功能

&nbsp;

def monotonic_stack(nums):

stack = \[\] # 用列表模拟栈

result = \[-1\] \* len(nums) # 初始化结果列表，默认值为-1

&nbsp;

for i in range(len(nums)):

\# 当栈非空且当前元素比较顶元素大时，出栈并更新结果

while stack and nums\[i\] > nums\[stack\[-1\]\]:

result\[stack.pop()\] = i

\# 将当前元素的索引入栈

stack.append(i)

return result

&nbsp;

\# 示例

nums = \[3, 1, 5, 7, 2, 6\]

print("原始数组:", nums)

print("单调递增栈结果:", monotonic_stack(nums))

#这段代码实现了一个单调递增栈，找到数组中每个元素右边第一个比它大的元素的位置。

#要实现单调递减栈，只需在 while 循环中将 nums\[i\] > nums\[stack\[-1\]\] 改为 nums\[i\] < nums\[stack\[-1\]\] 即可。

&nbsp;

**输出/输入**

**输入：**

**n = int(input())**

**s = input()**

**\# 输入: 1 2 3**

**a, b, c = map(int, input().split())**

**print(a, b, c) # 1 2 3 （abc可以换成nums）**

**\# 输入: apple banana cherry**

**words = input().split()**

**print(words) # \['apple', 'banana', 'cherry'\]**

**\# 输入:**

**\# 3**

**\# line1**

**\# line2**

**\# line3**

**n = int(input())**

**lines = \[input() for _ in range(n)\]**

**print(lines) # \['line1', 'line2', 'line3'\]**

**\# 输入:**

**\# 2 3(2行3列)**

**\# 1 2 3**

**\# 4 5 6**

**n, m = map(int, input().split())**

**matrix = \[list(map(int, input().split())) for _ in range(n)\]**

同一行输出:

使用end="，引号中间填写希望中间隔开的东西，比如说一个空格

在下一行print()从而达到换行的目的

&nbsp;

输出列表内所有元素：

print(\*list) ##把列表中元素顺序输出

&nbsp;

保留小数的多种方式：

print("{:.2f}".format(3.146)) # 3.15

print(round(3.123456789,5)# 3.12346四舍六入五成双

#保留n位小数：print(f"{x:.nf}")

&nbsp;

不定行输入：套用try-except循环

Try except 无法使用break来跳出循环，如果已知结束的特定输入（比如说输入0代表结束），那么可以用以下代码：

while True:

try:

xxxxx

If input()=='0':

break

except EOFFError:

break

&nbsp;

**矩阵：**

1\. 基本方法：列表套列表，用i，j两个指针

2\. 将n\*n的矩阵用某一元素进行填充的格式：

e.g：a是列数，b是行数

matrix = \[\[1\]\*a for \_in range(b)\]

&nbsp;

其他

output = ','.join(my_list)

print(output)#把列表中的所有元素一串输出，条件是列表中的元素都是str类型

&nbsp;

mylist=\[1,2,3,4,5\]

print(mylist,sep=',')#把列表中所有元素之间用sep内部的东西分开，输出形式仍然是一个列表\[1, 2, 3, 4, 5\]

&nbsp;

ord（）#返回对应的ASCII表值

chr（）#返回ASCII值对应的字符

bin(),oct(),hex()#分别表示二进制，八进制，十六进制的转换

&nbsp;

\# 二进制转十进制

binary_str = "1010"

decimal_num = int(binary_str, 2) # 第一个参数是字符串类型的某进制数，第二个参数是他的进制，最终转化为整数

print(decimal_num) # 输出 10

&nbsp;

#Dp写不出来用递归，为了防止爆栈（re）：使用缓存

from functools import lru_cache

@lru_cache(maxsize=128)

#注意：使用时函数的参数需要是不能修改的，可以改用元组（）或者set

&nbsp;

#判断完全平方数

import math

def isPerfectSquare(num):

if num < 0:

return False

sqrt_num = math.isqrt(num)

return sqrt_num \* sqrt_num == num

print(isPerfectSquare(97)) # False

&nbsp;

#年份calendar

import calendar

print(calendar.isEmpty(2020)) # True，判断是否是闰年

&nbsp;

#字符串的连接

str=str1+str2

&nbsp;

#用同一个数据充整个列表

dp=\[\[0\]\*(i+1) for i in range(5)\]

#输出\[\[0\], \[0, 0\], \[0, 0, 0\], \[0, 0, 0, 0\], \[0, 0, 0, 0\]\]

&nbsp;

**#str相关**

str.lstrip() / str.rstrip(): 移除字符串左侧/右侧的空白字符。

str.find(sub): 返回子字符串 'sub' 在字符串中首次出现的索引，如果未找到，则返回-1。

str.replace(old, new): 将字符串中的 'old' 子字符串替换为 'new'。

str.isalpha() / str.isdigit() / str.isalnum(): 检查字符串是否全部由字母/数字/字母和数字组成。

str.title(): 每个单词首字母大写。

&nbsp;

#保留小数

#1.round函数

number = 3.14159

rounded_number = round(number, 1)

&nbsp;

print(rounded_number)

#输出3.1，保留一位小数

#2.format格式化

number = 3.14159

formatted_number = "\[:.1f\]".format(number)

print(formatted_number)

#保留一位小数，输出的类型为str

&nbsp;

#字符串的连接

''.join()

#eg: ','.join(\[2,3,4,5\])

#output:2,3,4,5

&nbsp;

#eval函数

#eval() 是 python 中功能非常强大的一个函数，将字符串当成有效的表达式来求值，并返回计算结果，就是实现 list、dict、tuple、与str 之间的转化

result = eval("1 + 1")

print(result) # 2

result = eval("'+' \* 5")

print(result) #+++++

\# 3. 将字符串转换成列表

a = "\[1, 2, 3, 4\]"

result = type(eval(a))

print(result) # &lt;class 'list'&gt;

&nbsp;

input_number = input("请输入一个加减乘除运算公式：")

print(eval(input_number))

\## 1\*2 +3

\## 5

&nbsp;

&nbsp;

for key.value in dict.items() #遍历字典的键值对。

for index.value in enumerate(list) #枚举列表，提供元素及其索引。

&nbsp;

dic.setdefault(key,\[\]) .append(value) #常用在字典中加入元素的方式

dict.get(key,default) #从字典中获取键对应的值，如果键不存在，则返回默认值\`default\`。

&nbsp;

list(zip(a,b)) #将两个列表元素一一配对，生成元组的列表。

&nbsp;

类的格式和使用

&nbsp;

#创建一个类

class person();

#类变量的创建

name='aa'

#类方法的创建

def who(self):

print(name)

&nbsp;

#类变量的访问：类名、变量名

p=person.name

print(p)

&nbsp;

#实例化类（类函数的使用）：类名、函数名

c=person()

c.who()

#输出：aa

&nbsp;

#类变量的修改: 实例化后只修改自己内部而不影响原始的类；若直接用类名修改则会影响所有的实例化

c=person()

c.name=0

print(c.name)

#0

a=person()

print(a.name)

#aa

person.name=1

#则后续所有都会改变

&nbsp;

#构造器：

class person();

#self 表示的就是类的实例

def \__init_\_(self,a)

#实例变量：依靠输入

self.name=a

#实例变量：默认值

self.age=10

&nbsp;

print(person(a).name)

#a

&nbsp;

#用类实现双端队列：

class deque:

def \__init_\_(self):

&nbsp;

\===== Page 7 =====

&nbsp;

self.queue=\[\]

&nbsp;

def push(self,a):#进队

self.queue.append(a)

&nbsp;

def post_out(self):

self.queue.pop()

&nbsp;

def pre_out(self):

self.queue.pop(0)

&nbsp;

def empty(self):

if self.queue==\[\]:

return False

else:

return True

&nbsp;

t=int(input())

for i in range(t):

p=deque()

n=int(input())

for j in range(n):

t,x=map(int,input().split())

if t==1:

p.push(x)

elif t==2:

if x==0:

p.pre_out()

elif x==1:

p.post_out()

if p.empty():

ans=\[\]

for z in p.queue:

ans.append(str(z))

print(' '.join(ans))

else:

print('NULL')

&nbsp;

算法相关

1\. 质数筛

\# 换页筛选输出素数列表

N=20

primes = \[\]

is_prime = \[True\]\*N

is_prime\[0\] = False; is_prime\[1\] = False

for i in range(1,N):

if is_prime\[i\]:

primes.append(i)

for k in range(2\*i,N,i): #用素数去筛掉它的倍数

is_prime\[k\] = False

print(primes)

\# \[2, 3, 5, 7, 11, 13, 17, 19\]

&nbsp;

\# 欧拉筛直接判断某个数是否是质数

prime = \[\]

n = c

is_prime=\[True\] \* (n+1) # 初始化为全是素数

is_prime\[0\]=is_prime\[1\]=False#把0和1标记为非素数

def euler_sieve():

for i in range(2, n // 2 + 1):

if is_prime\[i\]:

prime.append(i)

for j in prime: # 将所有质数的倍数标记为非素数

if i \* j > n:

break

is_prime\[j \* i\] = False

if i % j == 0:

break

\# 测试

euler_sieve()

if is_prime\[n\]:

return True

else:

return False

&nbsp;

\# 6k+1质数判断法即Miller-Rabin素性测试算法

import math

def is_prime(num):

if num <= 1:

return False

elif num <= 3:

return True

elif num % 2 == 0 or num % 3 == 0:

return False

&nbsp;

i = 5

while i \* i <= num:

if num % i == 0 or num % (i + 2) == 0:

return False

i += 6

return True

#其原理基于以下观察：除了2和3之外，所有的原数据都可以表示为 6k ± 1 的形式，其中 k 是一个整数

&nbsp;

**2.二分查找：**

&nbsp;

import bisect

sorted_list = \[1,3,5,7,9\] #\[(0)1, (1)3, (2)5, (3)7, (4)9\]

position = bisect.bisect_left(sorted_list, 6) #查找某一元素插入后的索引

print(position) # 输出: 3, 因为6应该插入到位置3, 才能保持列表的升序顺序

&nbsp;

bisect.insert_left(sorted_list, 6)#将某个元素插入原列表并不改变升序/降序

print(sorted_list) # 输出: \[1, 3, 5, 6, 7, 9\], 6被插入到适当的位置以保持升序顺序

&nbsp;

sorted_list=(1,3,5,7,7,7,9)

print(bisect.bisect_left(sorted_list,7))

print(bisect.bisect_right(sorted_list,7))

\# 输出: 3 6

#右侧插入，如果有相同元素，就输出最大的索引，左侧输入则相反

&nbsp;

**3.heap优先堆：**

特别地，使用了heap结构之后该列表只能用heap包里的函数，不能再用remove、append等python中堆默认是最小堆，如果需要最大堆可以把所有的元素都加负号即可

&nbsp;

import heapq # 优先队列可以实现以log复杂度拿出最小（大）元素

1st=\[1,2,3\]

heapq.heapify(lst) # 将1st优先队列化，获得最小堆，从小到大排序

heapq.heappop(lst) # 从队列中弹出树顶元素，实际上是从前往后弹（默认最小，相反数reverse一下1st）

heapq.heappush(lst,element) # 把元素压入堆中

top_value = heap\[0\]#查看最小值但不弹出

&nbsp;

import heapq

def dynamic_median(nums):

\# 维护小根和大根堆（对顶），保持中位数在大根堆的顶部

min_heap = \[\] # 存储较大的一半元素，使用最小堆

max_heap = \[\] # 存储较小的一半元素，使用最大堆

median = \[\]

for i, num in enumerate(nums):

\# 根据当前元素的大小将其插入到对应的堆中

if not max_heap or num <= -max_heap\[0\]:

heapq.heappush(max_heap, -num)

&nbsp;

else:

heapq.heappush(min_heap, num)

&nbsp;

\# 调整两个堆的大小差，使其不超过 1

if len(max_heap) - len(min_heap) > 1:

heapq.heappush(min_heap, -heapq.heappop(max_heap))

elif len(min_heap) > len(max_heap):

heapq.heappush(max_heap, -heapq.heappop(min_heap))

&nbsp;

if i % 2 == 0:

median.append(-max_heap\[0\])

&nbsp;

return median

&nbsp;

T = int(input())

for _ in range(T):

#M = int(input())

nums = list(map(int, input().split())

median = dynamic_median(nums)

print(len(median))

print(\*median)

&nbsp;

4.default_dict:

&nbsp;

defaultdict是Python中collections模块中的一种数据结构，它是一种特殊的字典，可以为字典的值提供默认值。当你使用一个不存在的键访问字典时，defaultdict会自动对该键创建一个默认值，而不会引发KeyError异常。

&nbsp;

from collections import defaultdict

\# 创建一个defaultdict，值的默认工厂函数为int，表示默认值为0

char_count = defaultdict(int)

\# 统计字符串出现次数

input_string = "hello"

for char in input_string:

char_count\[char\] += 1

print(char_count) # 输出 defaultdict&lt;<class 'int'&gt;，{'h': 1, 'e': 1, 'l': 2, 'o': 1}')

print(char_count\['h'\])

#输出：1

&nbsp;

dict.get(key,default=None)

\# 其中，my_dict是要操作的字典，key是要查找的键，default是可选参数，表示当前定的键不存在时要返回的默认值

&nbsp;

**5.栈**

&nbsp;

单调栈：可以找到第一个比当前节点高的节点的位置

&nbsp;

\# n=int(input())

a=list(map(int,input().split())

&nbsp;

def monotonic_stack(nums):

stack = \[\]

result = \[str(0)\] \* len(nums)

&nbsp;

for i in range(len(nums)):

\# 当栈非空且当前元素比较元素大时，出栈并更新结果

while stack and nums\[i\] > nums\[stack\[-1\]\]:

result\[stack.pop()\] = str(i+1)

&nbsp;

\# 将当前元素的索引入栈

stack.append(i)

&nbsp;

return result

print(' '.join(monotonic_stack(a)))

&nbsp;

波兰表达式（前缀表达式）

\# 原理：从后往前遍历，依次把数字放入栈中，遇到一个运算符就从栈顶弹出两个数字进行运算然后再将结果压入栈中。

a=input().split()

s=\[\]#存储运算符

n=\[\]#存储数字

for i in range(len(a)):

x=a.pop()

if x=='+" or x=='-" or x=='+" or x=='/':

s.append(x)

y = n.pop()

z = n.pop()

k = s.pop()

if k == '+':

n.append(y + z)

elif k == '-':

n.append(y-z)

elif k == '\*':

n.append(y \* z)

elif k == '/':

n.append(y/z)

&nbsp;

else:

n.append(float(x))

&nbsp;

ans=n\[0\]

print("{:.6f}".format(ans))

&nbsp;

中序表达式转后序表达式：shunting yard调度场算法

&nbsp;

def infix_to_postfix(expression):

precedence = {'+':1, '-':1, '\*':2,'/':2}

stack = \[\]

postfix = \[\]

number = ''

&nbsp;

for char in expression:

if char.isnumeric() or char == '.':

number += char

else:

if number:

num = float(number)

postfix.append(int(num) if num.is_integer() else num)

number = ''

if char in '+\*/':

while stack and stack\[-1\] in '+\*/' and precedence\[char\] <= precedence\[stack\[-1\]\]:postfix.append(stack.pop())#优先级大于等于当前运算符的全部出栈

stack.append(char)#最后再入栈

elif char == '(':

stack.append(char)

elif char == ')':

while stack and stack\[-1\] != '(':

postfix.append(stack.pop())

stack.pop()

&nbsp;

if number:

num = float(number)

postfix.append(int(num) if num.is_integer() else num)

&nbsp;

while stack:

postfix.append(stack.pop())

&nbsp;

return ''.join(str(x) for x in postfix)

&nbsp;

n = int(input())

for _ in range(n):

expression = input()

print(infix_to_postfix(expression))

&nbsp;

快速堆猪：辅助栈

\### 描述

小明有很多猪，他喜欢玩疊猪游戏，就是将猪一头头疊起来。猪疊上去后，还可以把顶上的猪拿下来。小知道每头猪的重量，而且他还随时想知道疊在那里的猪最轻的是多少斤。

&nbsp;

\### 输入

有三种输入 1)push n n是整数(0<=0 <=20000)，表示疊上一头重量是n斤的新猪 2)pop 表示将猪堆顶的猪赶走。如果猪堆没猪，就啥也不干 3)min 表示问现在猪堆里最轻的猪多重。如果猪堆没猪，就啥也不干

输入总数不超过100000条

&nbsp;

\### 输出

对每个min输入，输出答案。如果猪堆没猪，就啥也不干

\# pig1=\[\]

pig2=\[\]

while True: try: a=input().split() if a\[0\]=='pop': if pig1: pig1.pop() if pig2: pig2.pop()

elif a\[0\]=='min': if pig2: print(pig2\[-1\])

else: b=int(a\[1\]) pig1.append(b) if not pig2:

&nbsp;

pig2.append(b)

else:

min==min(pig2\[-1\],b)

pig2.append(minn)

except EOFError:

break

&nbsp;

**6\. 并查集：**

&nbsp;

class disj_set:

def \__init_\_(self,n): # n 表示并查集的初始大小

self.rank = \[1 for i in range(n)\]

\# 用于记录每个元素所在树的深度

self.parent = \[i for i in range(n)\]

\# 用于记录每个元素的父节点，初始时父节点都是自己

&nbsp;

def find(self,x): # 用于查找X所在的集合，即数据节点（根节点条件：parent=自己本身）

if self.parent\[x\] != x:

self.parent\[x\] = self.find(self.parent\[x\]) # 路径压缩；把父节点不停在根节点

找

return self.parent\[x\] # 返回最终的根节点

&nbsp;

def union(self,x,y): # 用于合并x，y所在的两个集合

x_root = self.find(x) # 分别找到两者的根节点

y_root = self.find(y)

&nbsp;

if x_root == y_root:

return

\# 哪颗树更深就把哪颗树设为主树，把另一棵树连到根节点

if self.rank\[x_root\] > self.rank\[y_root\]:

self.parent\[y_root\] = x_root

elif self.rank\[y_root\] < self.rank\[x_root\]:

self.parent\[x_root\] = y_root

else:

self.parent\[y_root\] = x_root

self.rank\[x_root\] += 1

&nbsp;

\# # 计算根节点个数

count = 0

for x in range(1,n+1):

if D.parent\[x-1\] == x - 1: # 如果parent就是本身，说明是根节点

count += 1

&nbsp;

**图：**

&nbsp;

判断无向图是否联通/有回路：

class Node:

def \__init_\_(self, v):

self.value = v

self.joint = set()

&nbsp;

def connected(x, visited, num):#判断是否联通

visited.add(x)

a1 = 1

q = \[x\]

while a1 != num and q:

x = q.pop(0)

for y in x.joint:

if y not in visited:

visited.add(y)

a1 += 1

q.append(y)

return a1 == num

&nbsp;

def loop(x, visited, parent):#判断是否有环

visited.add(x)

if x.joint:

for a in x.joint:

if a in visited and a != parent:

return True

elif a != parent and loop(a, visited, x):

return True

return False

&nbsp;

n, m = map(int, input().split())

&nbsp;

vertex = \[Node(i) for i in range(n)\]

for i in range(m):

a, b = map(int, input().split())

vertex\[a\].joint.add(vertex\[b\])

vertex\[b\].joint.add(vertex\[a\])

&nbsp;

if connected(vertex\[0\], set(), n):

print('connected:yes')

else:

print('connected:no')

x=0

for i in range(n):

if loop(vertex\[i\],set(),None):

print('loop:yes')

x=1

break

if x==0:

print('loop:no')

&nbsp;

判断有问题是否有环：拓扑排序

&nbsp;

原理：每次进入度为0的点，将该点放入output，并删除该点的出边，同时更新其他点的入度。

如果最后output的长度为n则说明无环

&nbsp;

class Node:

def \__init_\_(self, v):

self.val = v

self.to = \[\]

&nbsp;

from collections import deque

&nbsp;

t = int(input())

for _ in range(t):

n, m = map(int, input().split())

node = \[Node(i) for i in range(1, n + 1)\]

into = \[0 for _ in range(n)\] # 记录入度

for _ in range(m): # 构建图

x, y = map(int, input().split())

node\[x - 1\].to.append(node\[y - 1\])

into\[y - 1\] += 1#更新入度

&nbsp;

queue = deque(\[node\[i\] for i in range(n) if into\[i\] == 0\])

output = \[\]

&nbsp;

while queue:

a = queue.popleft()

output.append(a)#把a增加进输出列表中

for x in a.to:#对于a的指出去的边

num = x.val

into\[num - 1\] -= 1#删除a指出去的边，同时更新有向边缘点的入度

if into\[num - 1\] == 0:#如果更新后入度为0就入队

queue.append(x)

&nbsp;

if len(output) == n:#如果output的长度是n说明没有环

print('No')

else:#否则说明有环

print('Yes')

&nbsp;

DFS深度搜索

#例题：迷宫的所有路径

#骑士周游也是经典dfs，按照马走日的规则更改一下每次可移动的dx、dy即可

n,m=map(int,input().split())

ma=\[\]

&nbsp;

for _ in range(n):

ma.append(list(map(int,input().split())))

ans=0

def dfs(ma,i,j):

global ans#要在函数内部设置全局变量，方便更新ans的值

if i==n-1 and j==m-1:

ans+=1

#走到终点一次就增加一个ans

&nbsp;

elif ma\[i\]\[j\]==0:

dx=\[0,1,-1,0\]

dy=\[1,0,0,-1\]

for k in range(4):

if 0<=i+dx\[k\]<n and 0<=j+dy\[k\]<m:

ma\[i\]\[j\]=1

#修改为端，防止往回走

dfs(ma,i+dx\[k\],j+dy\[k\])

#往四面八方走

ma\[i\]\[j\]=0

#还原为初始值

dfs(ma,0,0)

print(ans)

&nbsp;

#八皇后

board=\[\[0\]\*8 for i in range(8)\]

solutions=\[\]

visited_y=set()#存储有皇后的列

visited_sum=set()#存储x+y，用于判断是否在左上-右下的斜线

visited_dff=set()#存储x-y，用于判断是否在右上-左下的斜线

def dfs(x,y,board,visited_y,visited_sum):

global solutions

if y not in visited_y and x+y not in visited_sum and x-y not in visited_dff:

board\[x\]\[y\]=1

visited_y.add(y)

visited_sum.add(x+y)

visited_dff.add(x-y)

&nbsp;

if x == 7:

output = \[\]

for i in range(8):

for j in range(8):

if board\[i\]\[j\] == 1:#把每一行的皇后对应的列加入output里

output.append(str(j + 1))

&nbsp;

ans = int(''.join(output))

solutions.append(ans)

&nbsp;

if x<?:

for i in range(8):

dfs(x+1,i,board,visited_y,visited_sum)

&nbsp;

board\[x\]\[y\] = 0

visited_y.discard(y)

visited_sum.discard(x + y)

visited_dff.discard(x - y)#在每一个皇后位置以后的所有皇后都访问完后，还原初始状态，

以便访问下一个皇后的位置

&nbsp;

for i in range(8):

dfs(0,i,board,visited_y,visited_sum)

&nbsp;

solutions.sort()

n=int(input())

for i in range(n):

a=int(input())

print(solutions\[a-1\])

&nbsp;

BFS广度优先搜索

核心：使用deque队列

&nbsp;

\# 最大连通域面积

#使用了bfs的思想遍历整个棋盘，在数过w后将其标记为'.',确保后续不会再重复数这个元素。同时，在周围没有w的情况下，因为队列无法弹出会自动终止循环，不需要额外添加一个参数来计算，这样子会使代码更加简洁。

t = int(input())

result = \[\]

for _ in range(t):

re = \[\]

ans = 0

N, M = map(int, input().split())

ma = \[\]

for _ in range(N):

list1 = list(input())

ma.append(list1)

&nbsp;

for i in range(N):

for j in range(M):

if ma\[i\]\[j\] == 'W':

ans += 1

ma\[i\]\[j\] = '.'

queue = \[{i, j}\]

while queue:

x, y = queue.pop()

for dx in \[-1, 0, 1\]:

for dy in \[-1, 0, 1\]:

nx, ny = x + dx, y + dy

&nbsp;

\===== Page 21 =====

&nbsp;

if 0 <= nx < N and 0 <= ny < M and ma\[nx\]\[ny\] == 'w':

ma\[nx\]\[ny\] = '.'

queue.append((nx, ny))

ans += 1

&nbsp;

if ans > 0:

re.append(ans)

ans = 0

&nbsp;

re.append(ans)

result.append(max(re))

&nbsp;

for z in result:

print(z)

&nbsp;

#数字操作：给定一个整数n，计算从I开始每次可以\*2或者+1，最少经历多少次才可以得到n

from collections import deque

&nbsp;

def minoperations(target):

queue = deque(\[(1, 0)\]) # (当前数字，操作次数)

&nbsp;

while queue:

num, operations = queue.popleft()

&nbsp;

if num == target: # 如果当前数字等于目标数字，返回操作次数

return operations

&nbsp;

\# 尝试加1和乘2两种操作

next_add = num + 1

next_mul = num \* 2

&nbsp;

\# 将加1和乘2得到的数字加入队列

queue.append((next_add, operations + 1))

queue.append((next_mul, operations + 1))

&nbsp;

return -1 # 如果无法得到目标数字，返回-1

&nbsp;

\# 读取输入并调用函数输出结果

target = int(input())

print(minoperations(target))

#最短迷宫路径

from collections import deque

n,m=map(int,input().split())

ma=\[\]

result=float('inf')

for i in range(n):

ma.append(list(map(int,input().split())))

def bfs(ma):

global result

queue = deque(\[(0, 0, 0)\])

visited = set() # 用集合记录已经访问过的位置

while queue:

i, j, k = queue.popleft() # 从左侧弹出队列中的第一个元素

if i == n - 1 and j == m - 1:

&nbsp;

\===== Page 22 =====

&nbsp;

result = min(result, k) # 更新最短路径长度

else:

dx = \[1, 0, 0, -1\]

dy = \[0, 1, -1, 0\]

if ma\[i\]\[j\] == 0:

for _ in range(4):

x, y = i + dx\[\_, j + dy\[\_\]

if 0 <= x < n and 0 <= y < m and (x, y) not in visited:

visited.add((x, y)) # 标记位置(x, y)为已访问，防止重复访问导致

&nbsp;

RE. TLE

queue.append((x, y, k + 1)) # 将符合条件的位置加入队列

&nbsp;

bfs(ma)

if result!=float('inf');

print(result)

else:

print(-1)

&nbsp;

bfs常用数据结构: deque, 类似列表, 但是更高效

&nbsp;

**deque相关操作和作用:**

from collections import deque

d = deque()# 创建一个空的deque对象

d.append(x)# 在deque的右端添加元素x

d.appendleft(x) # 在deque的左端添加元素x

&nbsp;

d.pop()# 从deque的右端删除并返回最右边的元素

d.popleft()# 从deque的左端删除并返回最左边的元素

len(d)# 返回deque中元素的数量

d.clear()# 清空deque中的所有元素

d = deque(maxlen=5) # 创建一个最大长度为5的deque, 当超出长度时, 自动弹出最左边元素

list(d)# 将deque转换为列表

&nbsp;

BFS中的Dijkstra算法: 带权重的最小路径

#经典bfs:

def bfs(x, y):

\# 定义方向的偏移量

directions = \[(0, -1), (0, 1), (1, 0), (-1, 0)\]

\# 初始化队列, 将起点加入队列

queue = \[ (x, y) \]

\# 初始化距离字典，将起点的距离设为0，其他节点设为无穷大

distances = {(x, y): 0}

&nbsp;

while queue:

\# 弹出队列中的节点

current_x, current_y = queue.pop(0)

&nbsp;

\# 遍历四个方向上的相邻节点

for dx, dy in directions:

new_x, new_y = current_x + dx, current_y + dy

&nbsp;

\# 判断新节点是否在合法范围内

if 0 <= new_x < m and 0 <= new_y < n:

\# 判断新节点是否为墙

if d\[new_x\]\[new_y\] != '#':

\# 计算新节点的距离

new_distance = distances\[(current_x, current_y)\] +

abs(int(d\[new_x\]\[new_y\]) - int(d\[current_x\]\[current_y\]))

\# 如果新节点的距离小于已记录的距离，则更新距离字典和队列

if (new_x, new_y) not in distances or new_distance <

distances\[(new_x, new_y)\]:

distances\[(new_x, new_y)\] = new_distance

queue.append((new_x, new_y))

&nbsp;

return distances

&nbsp;

\# 读取输入

m, n, p = map(int, input().split())

d = \[\]

for _ in range(m):

row = input().split()

d.append(row)

&nbsp;

for _ in range(p):

\# 读取起点和终点坐标

x1, y1, x2, y2 = map(int, input().split())

&nbsp;

\# 判断起点和终点是否为墙

if d\[x1\]\[y1\] == '#' or d\[x2\]\[y2\] == '#':

print('No')

continue

&nbsp;

\# 使用BFS计算最短距离

distances = bfs(x1, y1)

&nbsp;

\# 输出结果，如果终点距空字典中，则输出对应的最短距离，否则输出'NO'

if (x2, y2) in distances:

print(distances\[(x2, y2)\])

else:

print('No')

&nbsp;

\===== Page 24 =====

&nbsp;

#graph 应该是一个字典，其中键表示图中的节点，而值表示从每个节点到其相邻节点的距离或权重。

def dfs(start,end,graph): #初始位置、结束位置、邻接表

heap=\[(0,start,\[start\])\]

heapq.heapify(heap)

visited-set() #初始化已访问列表

while heap:

(length,start.path)=heapq.heappop(heap) #每次pop出来的一定是该点到其他相邻点距离最小的路径

if start in visited:

continue

visited.add(start)

if start==end: #意味着已经到达重点，返回路径

return path

for i in graph\[start\]: #在start的邻居节点中，如果尚未被访问

if i not in visited: #则更新到i的新距离，方法是将从起始节点到start的距离

(length) 和从start到i的距离（graph\[start\]\[i\]）相加

heapq.heappush(heap,(length+graph\[start\]\[i\],i.path-\[i\]))

&nbsp;

**\### DP动态规划**

|#斐波那契数列 -维数组 up-down类型 递归写法 |

| dp=\[-1 for i in range(200)\]#初始化一个数组 |

| dp\[0\]=0#设置好初始值 |

| dp\[2\]=1 |

| dp\[1\]=1 |

| n=int(input()) |

| def f(x): |

if dp\[x-1\]!=-1 and dp\[x-2\]!=-1:

dp\[x\]=dp\[x-1\]+dp\[x-2\]#如果数组里面已经有了，就直接加

else:

f(x-1)#如果没有，就需要递归

dp\[x\] = dp\[x - 1\] + dp\[x - 2\]

for i in range(n):

a=int(input())

if a>2:#注意边界情况，避免指针出现负值

f(a)

print(dp\[a\])

&nbsp;

| #数字三角形 bottom-up类型 |

| n=int(input()) |

| tri=\[\] |

| dp=\[\] |

| for i in range(n):

tri.append(list(map(int,input().split())))

dp.append(\[0\]\*(i+1))

for i in range(n):#先把最后一行更新为tri里面的

dp\[n-1\]\[i\]=tri\[n-1\]\[i\]

for z in range(n-2,-1,-1):

for k in range(z+1):#运用贪心策略，每次加底下两个中比较大的数，存储在上一行的相应位置

dp\[z\]\[k\]=max(dp\[z+1\]\[k\],dp\[z+1\]\[k+1\])+tri\[z\]\[k\]

print(dp\[0\]\[0\])#最后输出顶端的就是所求的最大数

&nbsp;

#最大连续子序列和 在dp库里找最大值即可

n = int(input())

a = list(map(int, input().split())

&nbsp;

dp = \[0\]\*n

dp\[0\] = a\[0\]

&nbsp;

for i in range(1, n):

dp\[i\] = max(dp\[i-1\]+a\[i\], a\[i\])#状态转移方程：只有两种可能，取较大的

&nbsp;

print(max(dp))

&nbsp;

#最长上升子序列的长度

n = int(input())

b = list(map(int, input().split())

&nbsp;

dp = \[1\]\*n

&nbsp;

for i in range(1, n):

for j in range(i):

if b\[j\] < b\[i\]:

dp\[i\] = max(dp\[i\], dp\[j\]+1)#dp对应索引存储的是以第i个数为结尾的上升子序列长度，对于i之前的数，如果小于这个，就可以更新dp\[i\]的值

&nbsp;

print(max(dp))

&nbsp;

#小偷背包

n,b=map(int, input().split())

price=\[0\]+\[int(i) for i in input().split()

weight=\[0\]+\[int(i) for i in input().split()

bag=\[\[0\]\*(b+1) for _ in range(n+1)\]

#bag\[i\]\[j\] 表示前 i 件物品放入容量为 j 的背包可以获得的最大价值。

#price\[i\] 表示第 i 件物品的价值。

#weight\[i\] 表示第 i 件物品的重量。

for i in range(1,n+1):

for j in range(1,b+1):

if weight\[i\]<=j:

bag\[i\]\[j\]=max(price\[i\]+bag\[i-1\]\[j-weight\[i\]\], bag\[i-1\]\[j\])

else:

bag\[i\]\[j\]=bag\[i-1\]\[j\]

&nbsp;

#状态转移方程的意义是在考虑第 i 件物品时，背包的容量为 j 时的最大价值取决于两种情况的较大值

&nbsp;

#1. 第 i 件物品放入背包，其价值为 price\[i\]，并且需要腾出 weight\[i\] 的空间，此时背包容量变为 j-weight\[i\]，因此最大价值为 price\[i\] + bag\[i-1\]\[j-weight\[i\]\]。

#2. 不放入第 i 件物品，背包容量为 j 时的最大价值为 bag\[i-1\]\[j\]，即前 i-1 件物品放入容量为 j 的背包的最大价值。

#通过状态转移方程，逐步计算出放入不同数量和重量的物品时，背包在不同容量下可以获得的最大价值，最终得到的结果就是整个问题的解。

print(bag\[-1\]\[-1\])

&nbsp;

#采药 类似小偷背包

\# 首先将草药按顺序存入列表，然后构造一个二维命表，i 表示第 i 个草药，j 表示此时剩余的时间数，如果下一个草药的时间比 j 小，那么就分两种情况，放入或者不放入该草药。如果下一个草药的时间比 t 大，那么就只能不放入这个草药。对 i 进行双循环遍历，最后到第 M 组的第 T 次即为所求

T, M = map(int, input().split()) # T 是总时间，M 是草药数目

herbal = \[\]

for _ in range(M):

t, v = map(int, input().split())

herbal.append(\[t, v\])

&nbsp;

dp = \[\[0\] \* (T + 1) for _ in range(M + 1)\]

&nbsp;

for a in range(1, M + 1):

for b in range(1, T + 1):

if herbal\[a - 1\]\[0\] <= b: # 如果草药采摘时间小于等于剩余时间

dp\[a\]\[b\] = max(dp\[a-1\]\[b\], dp\[a-1\]\[b-herbal\[a-1\]\[0\]\] + herbal\[a-1\]

&nbsp;

\[1\])

else:

dp\[a\]\[b\] = dp\[a-1\]\[b\]

&nbsp;

print(dp\[M\]\[T\])

&nbsp;

**约瑟夫问题:**

&nbsp;

while True:

n, p, m = map(int, input().split())

if {n,p,m} == {0':

break

monkey = \[i for i in range(1, n+1)\]

for _ in range(p-1):

tmp = monkey.pop(0)

monkey.append(temp)

\# print(monkey)

&nbsp;

index = 0

ans = \[\]

while len(monkey) != 1:

temp = monkey.pop(0)

index += 1

if index == m:

index = 0

ans.append(temp)

continue

monkey.append(temp)

&nbsp;

ans.extend(monkey)

&nbsp;

print(','.join(map(str, ans)))

&nbsp;

math库

\# 开头要写

import math

math.sqrt() #开方

math.ceil() #取浮点数上整数

math.floor() #取浮点数的下整数

math.gcd(a,b) #取两个数的最大公约数

math.pow(2,3) # 8.0 幂运算

math.inf#表示正无穷

math.log(100,10) # 2.0

#math.log(x.base) 以base为底，x的对数

math.comb(5,3) # 组合数，C53

math.factorial(5) # 51 阶乘

&nbsp;

\# 树相关知识点:

\# 用类建树：n为树的节点个数

class tree:

def \__init_\_(self):

self.left=None#左节点

self.right=None#右节点

n=int(input())

Tree=\[tree() for i in range(n)\]

&nbsp;

\# 树的高度（可能需要+1）

def tree_height(node):

if node is None:

return -1

left_height=true_height(node.left)

right_height=true_height(node.right)

return max(left_height.right_height)+1

&nbsp;

\# 如何寻找根节点

parent=\[False\]\*n#初始所有节点都没有parent

\# 一边接收子节点一边把子节点的parent改成True，最后一个为False的节点就是root

for i in range(n):

1,r=map(int,input().split())

if l!=-1:

tree\[i\].left=True\[l\]

parent\[l\]=True

if r!=-1:

tree\[i\].right=True\[r\]

parent\[r\]=True

&nbsp;

\# 括号嵌套树的解析方法：

&nbsp;

\===== Page 30 =====

&nbsp;

class tree:

def \__init_\_(self,v):

self.children=\[\]

self.value=v

&nbsp;

tr=input()

stack=\[\]

node=None#node指向的是当前的节点

for i in tr:

if i.isalpha():

node=tree(i)

if stack:#如果栈不为空，则该节点是栈顶节点的children

stack\[-1\].children.append(node)

&nbsp;

elif i=='(': #出现左括号表示当前节点可能有children

if node:#如果当前节点存在

stack.append(node)#将其压入栈中

node=None#把新节点初始化为none，准备读取新节点

elif i==')': #说明结束了一个子树

if stack:

node=stack.pop()#从栈中弹出父节点 便于初始化新树或者更换父节点

root=node#最后弹出的是根节点

&nbsp;

树:

&nbsp;

基础知识/名词:

&nbsp;

层级: 从根节点开始到达一个节点的路径，所包含的一边的数量==，称为这个节点的层级。

如图 D 的层级为 2，根节点的层级为 0。

&nbsp;

高度=深度-1 (空树深度为0，高度为-1)

&nbsp;

计算深度:

def depth(root):

if root is None: # 先判断是否为空树

return 0 # 若计算高度，则return -1

else:

left_depth = depth(root.left) # 递归

right_depth = depth(root.right)

return max(left_depth, right_depth)+1

&nbsp;

计算叶子节点数目

&nbsp;

def count_leaves(root):

if root is None: # 先判断是否为空树

return 0

if root.left is None and root.right is None:

return 1

return count_leaves(root.left)+count_leaves(root.right)

&nbsp;

\===== Page 31 =====

&nbsp;

树的遍历方法：

&nbsp;

#前序遍历

def preorder(node):

print(self.value)

if self.left:

preorder(self.left)

if self.right:

preorder(self.right)

&nbsp;

#后续遍历：

def postorder(node):

if self.left:

postorder(self.left)

if self.right:

postorder(self.right)

print(self.value)

&nbsp;

#按层次遍历：（队列表达式例题）

def level_order_traversal(root):

queue = \[root\]

traversal = \[\]

while queue:

node = queue.pop(0)

traversal.append(node.value)

if node.left:

queue.append(node.left)

if node.right:

queue.append(node.right)

return traversal

&nbsp;

#这段代码通过队列实现了层序遍历的逻辑，确保了按照每一层从左到右的顺序访问树的所有节点。

&nbsp;

#中序遍历：

def inorder(root):

result=\[\]

if root is not None:

result+=postorder(root.left)

&nbsp;

\===== Page 32 =====

&nbsp;

result+=\[root.val\]

result+=postorder(root.right)

return result

&nbsp;

树的三种遍历方式的原理：

&nbsp;

一：后序遍历

先递归遍历左子树（从下往上）

再递归遍历右子树（从下往上）

最后访问根节点

二：前序遍历

1\. 先访问根节点

2\. 递归遍历左子树

3\. 最后递归地遍历右子树。

三：中序遍历

1\. 先递归地遍历左子树。

2\. 访问根结点

3\. 最后递归地遍历右子树。

&nbsp;

二叉树不同遍历方式的互相转换：

#前序+中序=后序

#后序遍历=前序遍历先遍历右子树再进行一次reverse

class Node:

def \__init_\_(self,val):

self.left=None

self.right=None

self.value=val

&nbsp;

def build_tree(midtree,pretree,output):#递归函数

root=pretree\[0\]

output.append(root)

root_index=midtree.index(root)#将mid和post都切分为左子树和右子树

mid_left_tree=midtree\[0:root_index\]

mid_right_tree=midtree\[root_index+1:len(midtree)\]

pre_left_tree=pretree\[1:1-len(mid_left_tree)\]

pre_right_tree=pretree\[1:len(mid_left_tree):len(pretree)\]

if pre_right_tree:

build_tree(mid_right_tree,pre_right_tree,output)

&nbsp;

\===== Page 33 =====

&nbsp;

if pre_left_tree:#递归调用

build_tree(mid_left_tree,pre_left_tree,output)

return output

&nbsp;

while True:

try:

a,b=input().split()

pre,mid=\[\], \[\]

for i in range(len(a)):

pre.append(a\[i\])

mid.append(b\[i\])

&nbsp;

ans=build_tree(mid,pre,\[\])

ans.reverse()

&nbsp;

print(''.join(ans))

except EOFError:

break

&nbsp;

#中序+后序=前序

\# 通过后序遍历最后一位是根节点的结论，不断把树分割为左子树和右子树，然后递归调用建树的函数进行操作。

&nbsp;

class Tree:

def \__init_\_(self.value):

self.left=None

self.right=None

self.value=value

&nbsp;

def build_tree(midtree,posttree,output):#递归函数

root=posttree\[-1\]

output.append(root)

root.index=midtree.index(root)#将mid和post都切分为左子树和右子树

mid_left_tree=midtree\[0:root_index\]

mid_right_tree=midtree\[root_index+1:len(midtree)\]

post_left_tree=posttree\[0:len(mid_left_tree)\]

post_right_tree=posttree\[len(mid_left_tree):len(posttree)-1\]

if post_left_tree:#递归调用

build_tree(mid_left_tree,post_left_tree,output)

if post_right_tree:

build_tree(mid_right_tree,post_right_tree,output)

return output

&nbsp;

a=input()

mid=\[\]

for i in a:

mid.append(i)

b=input()

post=\[\]

&nbsp;

for i in b:

post.append(i)

&nbsp;

ans=build_tree(mid,post,\[\])

root=True(post\[-1\])

&nbsp;

\===== Page 34 =====

&nbsp;

print(''.join(ans))

&nbsp;

2.二叉搜索树的层次遍历

&nbsp;

输入一个数字列表，建立二叉搜索树并按层次遍历

#

class Tree:

def \__init_\_(self,v):

self.right=None

self.left=None

self.value=v

&nbsp;

def insert(root,node):

if not root:

return node

&nbsp;

if node.value>root.value:

root.right=insert(root.right,node)

&nbsp;

elif node.value<root.value:

root.left=insert(root.left,node)

&nbsp;

return root

&nbsp;

def level_traversal(root):

queue=\[root\]

output=\[\]

while queue:

node=queue.pop(0)

output.append(node.value)

if node.left:

queue.append(node.left)

if node.right:

queue.append(node.right)

return output

&nbsp;

n=list(map(int,input().split())

tree=\[\]

for i in n:

if i not in tree:

&nbsp;

\===== Page 36 =====

&nbsp;

tree.append(i)

root=Tree(tree.pop(0))

&nbsp;

while tree:

node=tree.pop(0)

node=Tree(node)

root=insert(root,node)

output=level_traversal(root)

print(' '.join(map(str,output)))

&nbsp;

树的转换：

&nbsp;

把一棵 普通树 转化为 二叉树

核心方法：左儿子右兄弟

例题：

&nbsp;

04081:树的转换

&nbsp;

总时间限制：5000ms 单个测试点时间限制：1000ms 内存限制：65536kB

&nbsp;

描述

&nbsp;

我们都知道用“左儿子右兄弟”的方法可以将一棵一般的树转换为二叉树，如：

现在请你将一些一般的树用这种方法转换为二叉树，并输出转换前和转换后树的高度。

&nbsp;

#

class Node:

def \__init_\_(self):

self.children=\[\]

self.parent=None

self.left=None

self.right=None

&nbsp;

def build_tree(node):

if node:

&nbsp;

\===== Page 37 =====

&nbsp;

x=Node()

x.parent=node

&nbsp;

node.children.append(x)

return x

&nbsp;

def initial_tree_height(root,ans):

global output1

if root.children:

for i in root.children:

initial_tree_height(i,ans+1)

else:

output1.append(ans)

&nbsp;

def binary_tree_height(node):

if node is None:

return -1

left_height=binary_tree_height(node.left)

right_height=binary_tree_height(node.right)

return max(left_height,right_height)+1

&nbsp;

def change_tree(root):

if not root:

return None

&nbsp;

if len(root.children) > 0:

left_child = change_tree(root.children\[0\])

root.left = left_child

left_child.parent = root

for i in range(1, len(root.children)):

right_child = change_tree(root.children\[i\])

left_child.right = right_child

right_child.parent = left_child

left_child = right_child

return root

&nbsp;

a=input()

#build initial tree

root=Node()

node=root

for i in range(len(a)):

if a\[i\]=='d':

node=build_tree(node)

else:

x=node

node=x.parent

&nbsp;

output1=\[\]

initial_tree_height(root,0)

initial_height=max(output1)#初始树高度

change_tree(root)

post_height=binary_tree_height(root)

print(initial_height,'=>',post_height)

&nbsp;

collection库

&nbsp;

#counter: 计数字典子类，适用于list, str

#可以生成一个字典，其中key是对应的元素，value是该元素的出现次数

from collections import Counter

\# 从可迭代对象创建 Counter

my_list = \[1, 2, 3, 1, 2, 3, 4, 5\]

my_counter = Counter(my_list)

print(my_counter)

\# 输出：Counter(\[1: 2, 2: 2, 3: 2, 4: 1, 5: 1\]

&nbsp;

#也可直接自定义通过关键字参数创建 Counter

my_counter_explicit = Counter(a=2, b=3, c=1)

print(my_counter_explicit)

\# 输出：Counter(\['b': 3, 'a': 2, 'c': 1\])

&nbsp;

#特别地，访问不存在的元素不会引发 KeyError，而会返回 0

count_of_6 = my_counter\[6\]

print(count_of_6)

\# 输出：0

&nbsp;

#常用的一些操作

\# 获取所有元素

elements = my_counter.elements()

print(list(elements))

\# 输出：\[1, 1, 2, 2, 3, 3, 4, 5\]

\# 获取最常见的 n 个元素及其计数，会返回一个列表，其中包含计数最多的前 n 个元素及其计数。每个元素都表示为一个元组，第一个元素是元素本身，第二个元素是它在 Counter 对象中的计数。

most_common = my_counter.most_common(2)

print(most_common)

\# 输出：\[(1, 2), (2, 2)\]

&nbsp;

\===== Page 41 =====

&nbsp;

\# 更新计数，即增加这些元素

my_counter.update(\[1, 2, 3, 4\])

print(my_counter)

\# 输出：Counter(\[1: 3, 2: 3, 3: 3, 4: 2, 5: 1\])

&nbsp;

其他捞分小tips

1\. 除去是否得到整数？ (4/2=2.0)

2\. 缩进错误

3\. 用于调试的print是否删去

4\. 非一般情况的边界条件

5\. 递归中的return的位置

6\. 贪心是否最优

7\. 正难则反

8\. 审题是否准确？是否漏掉输出？