为保证高效率学习，太简单或者不常用，将不被笔记。笔记也会迭代版本更新。

*2023年夏季版*		-- 笔记大量摘自 www.runoob.com

# Python 基础

## 基本语法

### 关键字

关键字必须保留，我们不能把他们用作任何标识符名称。Python的标准库提供了一个keyword模块，可以输出当前版本所有的关键字

```python
>>> import keyword
>>> keyword kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

### 注释

单行注释以#开头，多行注释用`'''`或者`"""`包裹。

### 缩进

Python使用缩进来表示代码块，缩进的空格数可变，但是同一个代码块需要相同的缩进空格数。

### 多行语句

通常是一行写完一条语句，但如果语句很长，我们可以用反斜杠`\`来实现多行语句。在`[],{}或()`中的多行语句，不需要使用反斜杠。

```python
total = item_one + \
		item_two + \
		item_three

total = ['item_one', 'item_two', 'item_three',
         'item_four', 'item_five']
```

> 在同一行写多条语句，需要用`;`隔开。

## 数据类型

Pyhone允许同时给多个变量连续赋值，如：`a = b = c = 1` 或 `a, b, c = 1, 2, "hello"`

### Number 数字

Python3的数字类型只有**int, float, bool, complex(复数)**四种。

```python
# 使用函数type(var)查看变量类型
>>> a, b, c, d = 20, 5.5, True, 4+3j
>>> print(type(a), type(b), type(c), type(d))
<class 'int'> <class 'float'> <class 'bool'> <class 'complex'>
>>> isinstance(a, int)	# 也可以用isinstance()
True
>>> isinstance(c, int)	# bool类型是int子类
True					# isinstance认为子类也是父类类型
```

书写很大的数字时，可使用下划线将其中的数字分组，使其更清晰易读：

``` python
universe_age = 14_000_000_000
print(universe_age)		# 不会打印其中的下划线
```

``` sh
14000000000
```

#### 数学函数

| 函数           | 描述                                                    |
| -------------- | ------------------------------------------------------- |
| abs(x)         | 绝对值                                                  |
| ceil(x)        | 返回上入整数，如：ceil(4.1)返回5                        |
| exp(x)         | 返回e的x次幂(e^x^)，如exp(1)=e^1^ 返回2.718281828459045 |
| fabs(x)        | 以浮点数形式返回数字的绝对值                            |
| floor(x)       | 返回下舍整数，如：floor(-3.14)返回-4                    |
| log(x)         | 默认返回e为基数x的对数，log(e)=1 log(100,10)=2          |
| log10(x)       | 返回10为基数x的对数，log10(100)=2                       |
| max(x1,x2,...) | 返回最大值，参数可以为序列                              |
| min(x1,x2,...) | 返回最小值，参数可以为序列                              |
| modf(x)        | 以元组返回x的小数部分与整数部分，在元组中都以浮点型表示 |
| pow(x,y)       | 返回x的y次方，如：x^y^                                  |
| round(x[,n])   | 返回浮点数的四舍五入值，n为舍入到的小数点后位数         |
| sqrt(x)        | 返回x的平方根，如：$ \sqrt[2]{x}$                       |

#### 随机数函数

| 函数                           | 描述                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| choice(seq)                    | 从序列seq中随机挑选一个元素，如：random.choice(range(10))    |
| randrange([start,]stop[,step]) | 从指定范围内，按指定基数递增的集合中获取一个随机数，基数默认值为 1 |
| random()                       | 随机生成下一个实数，它在[0,1)范围内。                        |
| seed([x])                      | 改变随机数生成器的种子seed。如果你不了解其原理，你不必特别去设定seed，Python会帮你选择seed。 |
| shuffle(lst)                   | 将序列的所有元素随机排序                                     |
| uniform(x,y)                   | 随机生成下一个实数，它在[x,y]范围内。                        |

#### 三角函数

| 函数       | 描述                                          |
| ---------- | --------------------------------------------- |
| acos(x)    | 反余弦函数                                    |
| asin(x)    | 反正弦函数                                    |
| atan(x)    | 反正切函数                                    |
| atan2(y,x) | y/x的反正切值                                 |
| cos(x)     | 余弦函数                                      |
| hypot(x,y) | 欧几里得范数，如：  $\sqrt{x^2+y^2}$          |
| sin(x)     | 正弦函数                                      |
| tan(x)     | 正切函数                                      |
| degrees(x) | 弧度转换为角度，如：degrees(math.pi/2) = 90.0 |
| radians(x) | 角度转换为弧度                                |

### String 字符串

Python3之后，所有的字符串都是Unicode字符串。用引号（`'`或`"`）包裹。

#### 字符串运算

| 运算符     | 描述                     | 实例 |
| ---------- | ------------------------ | ---- |
| +          | 字符串连接               |      |
| *          | 字符串重复输出           |      |
| []         | 通过索引获取字符串中字符 |      |
| [:]        | 字符串切片               |      |
| in, not in | 成员运算符               |      |
| r/R        | 原始字符串               |      |
| %          | 格式字符串               |      |


#### 索引与切片

字符串的索引从左0开始往右递增，或者从右-1开始往左递减。也可以遵循**左闭右开**方式给字符串切片。

```python
str1 = 'abcdefg'	# str1[0]=str1[-7]='a'; str1[6]=str1[-1]='g'
str2 = "ABCDEFG"	# 下面切片
str2[2:4]	# CD
str2[:] 	# ABCDEFG
str2[1:-1]	# BDEF
str2[:-2]	# ABCDE
str2[2:]	# CDEFG
```

#### 格式字符串

| 符号   | 描述                         |
| ------ | ---------------------------- |
| %c     | 字符及其ASCII码              |
| %s     | 字符串                       |
| %d     | 整数                         |
| %u     | 无符号整数                   |
| %o     | 八进制数                     |
| %x[%X] | 十六进制数(大写)             |
| %f     | 浮点数，可指定小数点后的精度 |
| %e[%E] | 用科学计数法格式化浮点数     |
| %g[%G] | 浮点数的简写                 |
| %p     | 用十六进制数格式化变量的地址 |

```python
>>> name = 'world'
>>> 'Hello %s'%name
'Hello world'
>>> f'hello {name}'		# f-string是python3.6之后添加的字面量格式化字符串
'Hello world'
```

要在字符串中插入变量的值，可在前引号前加上字符`f`，再将要插入的变量放在花括号内。这样当Python显示字符串时，将把每个变量都替换为其值。

``` python
first_name = "ada"
last_name = "lovelace"
full_name = f"{first_name} {last_name}"
print(f"Hello, {full_name.title()}")
```

``` sh
Hello, Ada Lovelace
```

如果使用的是Python3.5或更早的版本，可以用`str.format()`增强字符串格式化的功能。

``` python
full_name = "{} {}".format(first_name, last_name)
```

#### 转义字符

在需要在字符中使用特殊字符时，python 用反斜杠`\` 转义字符。

```python
# 使用\r实现百分比进度
import time
for i in range(101):
    print("\r{:3}%".format(i),end=' ')
    time.sleep(0.05)
```

#### 字符串函数


| 函数                                           | 描述                                                         |
| ---------------------------------------------- | ------------------------------------------------------------ |
| capitalize()                                   | 将字符串的第一个字符转换为大写                               |
| center(width,fillchar)                         | 返回一个指定的宽度 width 居中的字符串，fillchar 为填充的字符，默认为空格。 |
| count(str,beg=0,end=len(string))               | 返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指定范围内 str 出现的次数 |
| bytes.decode(encoding="UTF-8",errors="strict") | Python3 中没有 decode 方法，但我们可以使用 bytes 对象的 decode() 方法来解码给定的 bytes 对象，这个 bytes 对象可以由 str.encode() 来编码返回。 |
| encode(encoding="UTF-8",errors="strict")       | 以 encoding 指定的编码格式编码字符串，如果出错默认报一个ValueError 的异常，除非 errors 指定的是'ignore'或者'replace' |
| endswith(suffix,beg=0,end=len(string))         | 检查字符串是否以 suffix 结束，如果 beg 或者 end 指定则检查指定的范围内是否以 suffix 结束，如果是，返回 True,否则返回 False。 |
| expandtabs(tabsize=8)                          | 把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8 。 |
| find(str, beg=0, end=len(string))              | 检测 str 是否包含在字符串中，如果指定范围 beg 和 end ，则检查是否包含在指定范围内，如果包含返回开始的索引值，否则返回-1 |
| index(str, beg=0, end=len(string))             | 跟find()方法一样，只不过如果str不在字符串中会报一个异常。    |
| isalnum()                                      | 如果字符串至少有一个字符并且所有字符都是字母或数字则返 回 True，否则返回 False |
| isalpha()                                      | 如果字符串至少有一个字符并且所有字符都是字母或中文字则返回 True, 否则返回 False |
| isdigit()                                      | 如果字符串只包含数字则返回 True 否则返回 False..             |
| islower()                                      | 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是小写，则返回 True，否则返回 False |
| isnumeric()                                    | 如果字符串中只包含数字字符，则返回 True，否则返回 False      |
| isspace()                                      | 如果字符串中只包含空白，则返回 True，否则返回 False.         |
| istitle()                                      | 如果字符串是标题化的(见 title())则返回 True，否则返回 False  |
| isupper()                                      | 如果字符串中包含至少一个区分大小写的字符，并且所有这些(区分大小写的)字符都是大写，则返回 True，否则返回 False |
| join(seq)                                      | 以指定字符串作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新的字符串 |
| len(string)                                    | 返回字符串长度                                               |
| ljust(width[,fillchar])                        | 返回一个原字符串左对齐,并使用 fillchar 填充至长度 width 的新字符串，fillchar 默认为空格。 |
| lower()                                        | 转换字符串中所有大写字符为小写.                              |
| lstrip()                                       | 截掉字符串左边的空格或指定字符。                             |
| maketrans()                                    | 创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。 |
| max(str)                                       | 返回字符串 str 中最大的字母。                                |
| min(str)                                       | 返回字符串 str 中最小的字母。                                |
| replace(old,new[,max])                         | 把 将字符串中的 old 替换成 new,如果 max 指定，则替换不超过 max 次。 |
| rfind(str,beg=0,end=len(string))               | 类似于 find()函数，不过是从右边开始查找.                     |
| rindex(str,beg=0,end=len(string))              | 类似于 index()，不过是从右边开始.                            |
| rjust(widt[,fillchar])                         | 返回一个原字符串右对齐,并使用fillchar(默认空格）填充至长度 width 的新字符串 |
| rstrip()                                       | 删除字符串末尾的空格或指定字符。                             |
| split(str="",num=string.count(str))            | 以 str 为分隔符截取字符串，如果 num 有指定值，则仅截取 num+1 个子字符串 |
| splitlines([keepends])                         | 按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。 |
| startswith(substr,beg=0,end=len(string))       | 检查字符串是否是以指定子字符串 substr 开头，是则返回 True，否则返回 False。如果beg 和 end 指定值，则在指定范围内检查。 |
| strip([chars])                                 | 在字符串上执行 lstrip()和 rstrip()                           |
| swapcase()                                     | 将字符串中大写转换为小写，小写转换为大写                     |
| title()                                        | 返回"标题化"的字符串,就是说所有单词都是以大写开始，其余字母均为小写(见 istitle()) |
| translate(table,deletechars="")                | 根据 table 给出的表(包含 256 个字符)转换 string 的字符, 要过滤掉的字符放到 deletechars 参数中 |
| upper()                                        | 转换字符串中的小写字母为大写                                 |
| zfill(width)                                   | 返回长度为 width 的字符串，原字符串右对齐，前面填充0         |
| isdecimal()                                    | 检查字符串是否只包含十进制字符，如果是返回 true，否则返回 false。 |

### Bool 布尔类型

### List 列表

只要把逗号分隔的不同数据项使用方括号包裹，就是列表了。列表允许不同数据项不同数据类型，拥有和string类型一样的索引与切片方式

```python
list1 = ['list', "string", 123, True]
list2 = [1, 2, 3, 4, 5]
list3 = ["a", "b", "c", "d"]
list4 = ['red', 'green', 'blue', 'yellow']
```

| 函数                              | 描述                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| len(list)                         | 列表元素个数                                                 |
| max(list)                         | 返回列表元素最大值                                           |
| min(list)                         | 返回列表元素最小值                                           |
| list(seq)                         | 将元组转换为列表                                             |
| list.append(obj)                  | 在列表末尾添加新的对象                                       |
| list.count(obj)                   | 统计某个元素在列表中出现的次数                               |
| list.extend(seq)                  | 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表） |
| list.index(obj)                   | 从列表中找出某个值第一个匹配项的索引位置                     |
| list.insert(index, obj)           | 将对象插入列表                                               |
| list.pop([index=-1])              | 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值 |
| list.remove(obj)                  | 移除列表中某个值的第一个匹配项                               |
| list.reverse()                    | 反向列表中元素                                               |
| list.sort(key=None,reverse=False) | 对原列表进行排序                                             |
| list.clear()                      | 清空列表                                                     |
| list.copy()                       | 复制列表                                                     |

### Tuple 元组

与列表相似，但是用小括号包裹，不能修改。

```python
tup1 = ('String', "tuple", 123, True)
tup2 = "a","b","c","d"	# 不需要括号也可以
tup3 = ("onlyOne",)		# 一个元素的元组，需要加个逗号
tup = tup1 + tup2		# 不能修改，但是可以拼接
tup4 = tuple(iterable)	# 将可迭代系列转换为元组。
```

### Set 集合

集合（set）是一个无序的不重复元素序列。

可以使用大括号 **{ }** 或者 **set()** 函数创建集合，注意：创建一个空集合必须用 **set()** 而不是 **{ }**，因为 **{ }** 是用来创建一个空字典。

| 函数                              | 描述                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| set.add()                         | 为集合添加元素                                               |
| set.clear()                       | 移除集合中的所有元素                                         |
| set.copy()                        | 拷贝一个集合                                                 |
| set.difference()                  | 返回多个集合的差集                                           |
| set.difference_update()           | 移除集合中的元素，该元素在指定的集合也存在。                 |
| set.discard()                     | 删除集合中指定的元素                                         |
| set.intersection()                | 返回集合的交集                                               |
| set.intersection_update()         | 返回集合的交集                                               |
| set.isdisjoint()                  | 判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False。 |
| set.issubset()                    | 判断指定集合是否为该方法参数集合的子集。                     |
| set.issuperset()                  | 判断该方法的参数集合是否为指定集合的子集                     |
| set.pop()                         | 随机移除元素                                                 |
| set.remove()                      | 移除指定元素                                                 |
| set.symmetric_difference()        | 返回两个集合中不重复的元素集合                               |
| set.symmetric_difference_update() | 移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。 |
| set.union()                       | 返回两个集合的并集                                           |
| set.update()                      | 给集合添加元素                                               |

### Dictionary 字典

字典是另一种可变容器模型，且可存储任意类型对象。

字典的每个键值 **key=>value** 对用冒号 **:** 分割，每个对之间用逗号(**,**)分割，整个字典包括在花括号 **{}** 中 。

| 函数                              | 描述                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| len(dict)                         | 计算字典元素个数，即键的总数。                               |
| str(dict)                         | 输出字典，可以打印的字符串表示。                             |
| type(variable)                    | 返回输入的变量类型，如果变量是字典就返回字典类型。           |
| dict.clear()                      | 删除字典内所有元素                                           |
| dict.copy()                       | 返回一个字典的浅复制                                         |
| dict.fromkeys()                   | 创建一个新字典，以序列seq中元素做字典的键，val为字典所有键对应的初始值 |
| dict.get(key,default=None)        | 返回指定键的值，如果键不在字典中返回 default 设置的默认值    |
| key in dict                       | 如果键在字典dict里返回true，否则返回false                    |
| dict.items()                      | 以列表返回一个视图对象                                       |
| dict.keys()                       | 返回一个视图对象                                             |
| dict.setdefault(key,default=None) | 和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default |
| dict.update(dict2)                | 把字典dict2的键/值对更新到dict里                             |
| dict.values()                     | 返回一个视图对象                                             |
| pop(key[,default])                | 删除字典 key（键）所对应的值，返回被删除的值。               |
| popitem()                         | 返回并删除字典中的最后一对键和值。                           |

## 运算符

| 类别         | 运算符              | 描述                           | 实例                |
| ------------ | ------------------- | ------------------------------ | ------------------- |
| **算术运算** | `+、-、*、/`        | 加减乘除                       | `21/10 = 2.1`       |
|              | %                   | 取模:除法的余数                | `7%3 = 1`           |
|              | **                  | 幂:x的y次幂                    | `3**4 = 81；2**3=8` |
|              | //                  | 整除:向下（往小的方向）取整    | `-5//2=-3；5//2=2`  |
| **比较运算** | ==、!=              | 等于、不等于                   |                     |
|              | >、>=、<、<=        | 大于、大于等于、小于、小于等于 |                     |
| **赋值运算** | =、+=、-=、*=、/=   | 简单的赋值运算                 | a+=b 等效 a=a+b     |
|              | %=、**=、//=        | 取模（幂、整除）赋值运算       | a%=b 等效 a=a%b     |
|              | :=                  | 海象运算符                     |                     |
| **位运算**   | &、\|、^、~、<<、>> |                                |                     |
| **逻辑运算** | and、or、not        |                                |                     |
| **身份运算** | is、is not          |                                |                     |

> 运算符有自己的优先级，记不清楚就多用括号

## 条件控制

### if 语句

```python
if condition_1:
    statement_block_1
elif condition_2:
    statement_block_2
else:
    statement_block_3
```

### match...case 语句

Python 3.10 增加了 **match...case** 的条件判断，不需要再使用一连串的 **if-else** 来判断了。

match 后的对象会依次与 case 后的内容进行匹配，如果匹配成功，则执行匹配到的表达式，否则直接跳过，**_** 可以匹配一切。

```python
match subject:
    case <pattern_1>:
        <action_1>
    case <pattern_2>:
        <action_2>
    case <pattern_3>:
        <action_3>
    case _:
        <action_wildcard>
```

### while 循环

```python
while 判断条件(condition)：
    执行语句(statements)……
```

### for 循环

```python
for <variable> in <sequence>:
    <statements>
else:
    <statements>		# 循环结束后执行的代码
```

### range 函数

如果你需要遍历数字序列，可以使用内置 range() 函数。它会生成数列，例如：

```python
>>>for i in range(5,9) :
    print(i)
5
6
7
8
>>>
```
``` python
>>>for i in range(0, 10, 3) :	# 有步长，步长可以是负数
    print(i)
0
3
6
9
>>>
```

* `break`   跳出循环体，结束循环。

* `continue`  跳过当前循环块剩余语句，进入下一轮循环。

* `pass`  不做任何事情的占位语句。

### enumerate 函数

enumerate参数为可遍历/可迭代的对象(如列表、字符串)
enumerate多用于在for循环中得到计数，利用它可以同时获得索引和值，即需要index和value值的时候可以使用enumerate，enumerate()返回的是一个enumerate对象

```python
s = [1,2,3,4,5]
for idx,val in enumerate(s,1):	# idx不是从0，而是从1开始
    print('%s, %s'%(idx,val))
1,1
2,2
3,3
4,4
5,5
```

## 函数

定义函数使用 def 关键字，一般格式如下：

```python
def 函数名(参数列表):
    函数体
```

### 参数传递

可更改(**mutable**)与不可更改(**immutable**)对象

在 python 中，strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象。

- **不可变类型：**变量赋值 **a=5** 后再赋值 **a=10**，这里实际是新生成一个 int 值对象 10，再让 a 指向它，而 5 被丢弃，不是改变 a 的值，相当于新生成了 a。
- **可变类型：**变量赋值 **la=[1,2,3,4]** 后再赋值 **la[2]=5** 则是将 list la 的第三个元素值更改，本身la没有动，只是其内部的一部分值被修改了。

python 函数的参数传递：

- **不可变类型：**类似 C++ 的值传递，如整数、字符串、元组。如 fun(a)，传递的只是 a 的值，没有影响 a 对象本身。如果在 fun(a) 内部修改 a 的值，则是新生成一个 a 的对象。
- **可变类型：**类似 C++ 的引用传递，如 列表，字典。如 fun(la)，则是将 la 真正的传过去，修改后 fun 外部的 la 也会受影响

```python
# ===不可变参数实例===
def change(a):
    print(id(a))   # 指向的是同一个对象
    a=10
    print(id(a))   # 一个新对象
    
a=1
print(id(a))
change(a)
```
```sh
4379369136
4379369136
4379369424
```
```python
# ===可写参数实例===
def changeme( mylist ):
   "修改传入的列表"
   mylist.append([1,2,3,4])
   print ("函数内取值: ", mylist)
   return

# 调用changeme函数
mylist = [10,20,30]
changeme( mylist )
print ("函数外取值: ", mylist)
```
```sh
函数内取值:  [10, 20, 30, [1, 2, 3, 4]]
函数外取值:  [10, 20, 30, [1, 2, 3, 4]]
```

> 函数还支持关键字参数使参数顺序调换，或者默认值参数（这个参数必须放在最后），以及不定长参数。

### 不定长参数

加了星号 ***** 的参数会以元组(tuple)的形式导入，存放所有未命名的变量参数。

``` python
# 可写函数说明
def printinfo( arg1, *vartuple ):
   "打印任何传入的参数"	# 函数内双引号内说明，可以用 函数名.__doc__ 显示，建议为每个函数添加
   print ("输出: ")
   print (arg1)
   print (vartuple)
 
# 调用printinfo 函数
printinfo(10)
printinfo(70, 60, 50)
```
```sh
输出：
10
()			# 输出了一个空元组
输出: 
70
(60, 50)
```

加了两个星号 ***\*** 的参数会以字典的形式导入。

``` python
# 可写函数说明
def printinfo( arg1, **vardict ):
   "打印任何传入的参数"
   print ("输出: ")
   print (arg1)
   print (vardict)
 
# 调用printinfo 函数
printinfo(1)
printinfo(1, a=2,b=3)
```
```sh
输出:
1
{}
输出: 
1
{'a': 2, 'b': 3}
```

### lambda 匿名函数

所谓匿名，意即不再使用 **def** 语句这样标准的形式定义一个函数。

- **lambda** 只是一个表达式，函数体比 **def** 简单很多。
- lambda 的主体是一个表达式，而不是一个代码块。仅仅能在 lambda 表达式中封装有限的逻辑进去。
- lambda 函数拥有自己的命名空间，且不能访问自己参数列表之外或全局命名空间里的参数。
- 虽然 lambda 函数看起来只能写一行，却不等同于 C 或 C++ 的内联函数，后者的目的是调用小函数时不占用栈内存从而增加运行效率。

原型：`lambda [arg1 [,arg2,.....argn]]:expression`

``` python
x = lambda a=0 : a + 10		# lambda也可以设置默认值
print(x(a=5))				# lambda也可以使用关键字参数
```
```sh
15
```
```python
sum = lambda arg1, arg2: arg1 + arg2
# 调用sum函数
print ("相加后的值为 : ", sum( 10, 20 ))
print ("相加后的值为 : ", sum( 20, 20 ))
```
```sh
30
40
```

### 强制位置参数

形参语法 **/** 用来指明函数前面形参必须使用指定位置参数，不能使用关键字参数的形式；*****用来指明函数后面形参必须使用关键字参数。

``` python
def f(a, b, /, c, d, *, e, f):
    print(a, b, c, d, e, f)
    
f(10, 20, 30, d=40, e=50, f=60)			# 正确
f(10, b=20, c=30, d=40, e=50, f=60)   	# b 不能使用关键字参数的形式
f(10, 20, 30, 40, 50, f=60)           	# e 必须使用关键字参数的形式
```

### return 语句

**return [表达式]** 语句用于退出函数，选择性地向调用方返回一个表达式。不带参数值的 return 语句返回 None。

python的return是可以以元组方式返回多个值的。

## 模块与包

把这些定义存放在文件中，为一些脚本或者交互式的解释器实例使用，这个文件被称为模块。

模块是一个包含所有你定义的函数和变量的文件，其后缀名也是.py。模块可以被别的程序引入，以使用该模块中的函数等功能。这也是使用 python 标准库的方法。

###  模块的使用

#### import 语句

原型：`import module1[, module2[,... moduleN]`

解释器遇到 import 语句，如果模块在当前的搜索路径就会被导入。

```python
>>> import sys
>>> sys.path	# 这里就是搜索路径了
['', '/usr/local/lib/python310.zip', '/usr/local/lib/python3.10', '/usr/local/lib/python3.10/lib-dynload', '/usr/local/lib/python3.10/site-packages']
```

``` python
# Filename: support.py 
def print_func( par ):
    print ("Hello : ", par)
    return
```
```python
# Filename: test.py 
import support					# 导入模块support 
support.print_func("World")	# 现在可以调用模块里包含的函数了
```
```sh
$python test.py
Hello : World
```

#### from...import 语句

from 语句让你从模块中导入一个指定的部分到当前命名空间中

原型：from modname import name1[, name2[, ... nameN]]``

#### \__name__ 属性

一个模块被另一个程序第一次引入时，其主程序将运行。如果我们想在模块被引入时，模块中的某一程序块不执行，我们可以用`__name__`属性来使该程序块仅在该模块自身运行时执行。

```python
# Filename: using_name.py

if __name__ == '__main__':
   print('程序自身在运行')
else:
   print('我来自另一模块')
```

```sh
$ python using_name.py
程序自身在运行
```

```sh
$ python
>>> import using_name
我来自另一模块
>>>
```

> 每个模块都有一个`__name__`属性，当其值是`__main__`时，表明该模块自身在运行，否则是被引入。

#### dir 函数

内置的函数 dir() 可以找到模块内定义的所有名称。以一个字符串列表的形式返回

``` python
>>>	import module
>>> dir(module)
['__builtins__', '__cached__', '__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__']
```

> 可以使用`help(moudle|function)`查看模块或函数使用帮助信息，或者`print(function.__doc__)`打印出来

### 标准模块

Python 标准库非常庞大，所提供的组件涉及范围十分广泛，使用标准库我们可以让您轻松地完成各种任务。

以下是一些 Python3 标准库中的模块：

- **os 模块：**os 模块提供了许多与操作系统交互的函数，例如创建、移动和删除文件和目录，以及访问环境变量等。
- **sys 模块：**sys 模块提供了与 Python 解释器和系统相关的功能，例如解释器的版本和路径，以及与 stdin、stdout 和 stderr 相关的信息。
- **time 模块：**time 模块提供了处理时间的函数，例如获取当前时间、格式化日期和时间、计时等。
- **datetime 模块：**datetime 模块提供了更高级的日期和时间处理函数，例如处理时区、计算时间差、计算日期差等。
- **random 模块：**random 模块提供了生成随机数的函数，例如生成随机整数、浮点数、序列等。
- **math 模块：**math 模块提供了数学函数，例如三角函数、对数函数、指数函数、常数等。
- **re 模块：**re 模块提供了正则表达式处理函数，可以用于文本搜索、替换、分割等。
- **json 模块：**json 模块提供了 JSON 编码和解码函数，可以将 Python 对象转换为 JSON 格式，并从 JSON 格式中解析出 Python 对象。
- **urllib 模块：**urllib 模块提供了访问网页和处理 URL 的功能，包括下载文件、发送 POST 请求、处理 cookies 等。

### 包

包是一种管理 Python 模块命名空间的形式，采用"点模块名称"。

比如一个模块的名称是 A.B， 那么他表示一个包 A中的子模块 B 。

就好像使用模块的时候，你不用担心不同模块之间的全局变量相互影响一样，采用点模块名称这种形式也不用担心不同库之间的模块重名的情况。

这样不同的作者都可以提供 NumPy 模块，或者是 Python 图形库。

不妨假设你想设计一套统一处理声音文件和数据的模块（或者称之为一个"包"）。

现存很多种不同的音频文件格式（基本上都是通过后缀名区分的，例如： .wav，:file:.aiff，:file:.au，），所以你需要有一组不断增加的模块，用来在不同的格式之间转换。

并且针对这些音频数据，还有很多不同的操作（比如混音，添加回声，增加均衡器功能，创建人造立体声效果），所以你还需要一组怎么也写不完的模块来处理这些操作。

这里给出了一种可能的包结构（在分层的文件系统中）:

```sh
sound/                          顶层包
      __init__.py               初始化 sound 包
      formats/                  文件格式转换子包
              __init__.py
              wavread.py
              wavwrite.py
              aiffread.py
              aiffwrite.py
              auread.py
              auwrite.py
              ...
      effects/                  声音效果子包
              __init__.py
              echo.py
              surround.py
              reverse.py
              ...
      filters/                  filters 子包
              __init__.py
              equalizer.py
              vocoder.py
              karaoke.py
              ...
```

在导入一个包的时候，Python 会根据 sys.path 中的目录来寻找这个包中包含的子目录。

目录只有包含一个叫做 `__init__.py` 的文件才会被认作是一个包，主要是为了避免一些滥俗的名字（比如叫做 string）不小心的影响搜索路径中的有效模块。

最简单的情况，放一个空的 `__init__.py`就可以了。当然这个文件中也可以包含一些初始化代码或者为（将在后面介绍的） `__all__`变量赋值。

用户可以每次只导入一个包里面的特定模块，比如:

```python
import sound.effects.echo		# 这样导入模块的
sound.effects.echo.echofilter(input, output, delay=0.7, atten=4) #全名访问

from sound.effects import echo	# 这样导入模块的(这也是推荐方法)
echo.echofilter(input, output, delay=0.7, atten=4) # 用echo.就可以了

from sound.effects.echo import echofilter	# 导入的是函数
echofilter(input, output, delay=0.7, atten=4)	# 直接使用
```

#### 从一个包中导入 *

如果包定义文件 **__init__.py** 存在一个叫做 **__all__** 的列表变量，那么在使用 `from package import *` 的时候就把这个列表中的所有名字作为包内容导入。

```python
file:sounds/effects/__init__.py
__all__ = ["echo", "surround", "reverse"]
```

这表示当你使用`from sound.effects import *`这种用法时，你只会导入包里面这三个子模块。

如果 `__all__`没有定义，那么使用`from sound.effects import *`这种语法的时候，就不会导入包 sound.effects 里的任何子模块。他只是把包sound.effects和它里面定义的所有内容导入进来（可能运行`__init__.py`里定义的初始化代码）。

## pip 包管理

### 安装

windows下安装python会默认安装pip，只要注意环境变量是否配置好，就可以顺利使用pip，在Linux下执行以下命令安装：

``` sh
# wget https://bootstrap.pypa.io/get-pip.py --no-check-certificate
# python get-pip.py
```

### 更改源

pip下载python包，有时速度非常慢，这是因为默认源可能在国外，而我们在国内访问会受到网络限制。因此，我们可以更改 pip 的源，以加快下载速度。以下命令可以更改 pip 的源为清华大学镜像源：

``` sh
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
```

如果是手动修改，它是在用户目录下(windows c:\Users\用户名；Linux /home/用户名)下的 `.config/pip/pip.conf`中，写入如下内容：

```json
[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple
```

> 你还以可以更改为国内的中科大镜像源，阿里云镜像源，华为云镜像源等，都可以。

### 使用

* **install：**安装包
* **download：**下载包
* **uninstall：**卸载包
* **freeze：**按着一定格式输出已安装包列表
* **list：**列出已安装包
* **show：**显示包详细信息
* **check：**检查包的依赖关系是否完整
* **config：**管理配置
* **search：**搜索包
* **wheel：**根据需要重建可重用的代码库（包）
* **hash：**计算包的hash值
* **completion：**自动完成 pip 命令的参数和选项
* **help：**帮助

``` python
pip install package_name			# 安装包
pip show --files package_name		# 查看某个已安装包
pip list --outdated					# 检查哪些包需要更新
pip install --upgrade package_name	# 升级包
pip uninstall package_name			# 卸载包
pip freeze > requirements.txt		# 按当前环境生成批量包目录
pip install -r requirements.txt		# 按生成的批量包目录批量安装包
```

## 虚拟环境

由于Python拥有众多的第三方开发者和高速的三方包迭代特性。由于越来越多的第三方库的安装使用，很可能由于版本的更新，使旧版本功能废弃或者不再支持，直接导致你辛苦开发的项目在同库不同版本中崩溃而无法使用，或者你开发的不同项目需要用到不同的库，甚至是相同的库但是版本不同。这时候使用虚拟环境的作用就体现出来，它的作用是隔离项目所需要的Python环境，以便不同的项目可以使用不同的Python版本和库，环境干净，准确且不会相互干扰。

### 安装与使用

``` sh
pip install virtualenv
virtualenv --version		# 如果不能看到版本，需要用ln命令添加软连接

virtualenv venv				# 创建venv目录下的虚拟环境
cd ./venv/bin				# 进入目录
source	activate			# 激活虚拟环境
pip install package_name	# 在当前虚拟环境下安装包
pip freeze > requirements.txt	# 当前虚拟环境下的包生成目录文件，以备恢复
pip install -r requirements.txt # 恢复虚拟环境
deactivate					# 退出虚拟环境
```

## Git的使用

### 安装

``` sh
$sudo apt install git-all
```

### 配置

``` sh
$git config --global user name "username"				# 初始化名称
$git config --global user.email username@example.com	# 初始化邮箱
```

### 忽略文件

有些文件并不需要Git跟踪，我们可以创建一个名为 **.gitignore** 的特殊文件，在里面添加需要忽略的目录和文件

``` sh
$cat .gitignore
__pycache__/
...
```

### 初始化仓库

我们一般会为项目创建一个目录，其中包含项目文件和一个 **.gitignore** 文件，现在可以初始化Git仓库了。

``` sh
$cd pro_dir
$git init
```

### 将文件加入仓库

``` sh
$git add .
$git status
```

### 执行提交

``` sh
$git commit -m "annotate"
```

### 查看提交历史

``` sh
$git log
```

### 撤销修改

``` sh
$git checkout .
$git checkout ee7641 # 或者撤销到指定ID（只用指出ID的前6位）
```

### 删除仓库

Git仓库就是 **.git** 目录下的文件，删除这个目录相当于删除了Git仓库

``` sh
$rm -rf .git
```

### 常用命令

``` shell
$git config --global user name "username"				# 初始化名称
$git config --global user.email username@example.com	# 初始化邮箱

$git clone https://github.com/torvalds/linux.git	# 下载一个项目

$git add <name>										# 加入跟踪，置缓存状态
$git rm <name>										# 移除各种状态
$git rm --cache <name>								# 移除跟踪，但保留文件
$git reset HEAD <name>								# 取消缓存状态
$git commit											# 提交缓存状态的修改
$git commit -m '提交描述'							 # 提交带描述
$git reset head~ --soft								# 取消这次提交
$git status											# 查看当前状态
$git diff											# 当前修改的内容
$git log											# 查看提交历史
$git log --pretty=oneline							# 有格式化效果的提交历史
$git log --pretty=format:"%h-%an,%ar:%s"			# 有格式化效果的提交历史
$git log --graph									# 图形化方式呈现提交历史

$git remote add orgin http://github.com/weige/a.git # 链接到远程仓库
$git remote											# 当前远程仓库
$git remote rename orgin origin						# 修改远程仓库名字
$git push origin master								# 推送到远程仓库master
$git branch --list									# 查看当前所属分支
$git branch feature1								# 创建feature1分支
$git checkout feature1								# 切换到feature1分支
$git merge feature1									# 合feature1并到master
$git fetch 											# 拉取分支

$git stash											# 储藏未完成的分支
$git stash apply									# 恢复存储的未完成分支
$git stash list										# 多次存储列表
$git stash apply stash@{2}							# 恢复到列表中{2}的存储
$git checkout --<file>								# 恢复file文件
$git stash pop										# 恢复到最近一次存储
$git stash drop stash@{2}							# 删除列表中{2}的存储

$git rebase A										# 把自己分支放到A分支后
```



# Python 进阶

## 面向对象

Python中的类提供了面向对象编程的所有基本功能：类的继承机制允许多个基类，派生类可以覆盖基类中的任何方法，方法中可以调用基类中的同名方法。

### 基本概念

- **类(Class):** 用来描述具有相同的属性和方法的对象的集合。它定义了该集合中每个对象所共有的属性和方法。对象是类的实例。
- **方法：**类中定义的函数。
- **类变量：**类变量在整个实例化的对象中是公用的。类变量定义在类中且在函数体之外。类变量通常不作为实例变量使用。
- **数据成员：**类变量或者实例变量用于处理类及其实例对象的相关的数据。
- **方法重写：**如果从父类继承的方法不能满足子类的需求，可以对其进行改写，这个过程叫方法的覆盖（override），也称为方法的重写。
- **局部变量：**定义在方法中的变量，只作用于当前实例的类。
- **实例变量：**在类的声明中，属性是用变量来表示的，这种变量就称为实例变量，实例变量就是一个用 self 修饰的变量。
- **继承：**即一个派生类（derived class）继承基类（base class）的字段和方法。继承也允许把一个派生类的对象作为一个基类对象对待。例如，有这样一个设计：一个Dog类型的对象派生自Animal类，这是模拟"是一个（is-a）"关系（例图，Dog是一个Animal）。
- **实例化：**创建一个类的实例，类的具体对象。
- **对象：**通过类定义的数据结构实例。对象包括两个数据成员（类变量和实例变量）和方法。

### 类对象

类实例化后，可以使用其属性与方法，如：

``` python
class MyClass:
    """一个简单的类实例"""
    i = 12345
    def f(self):
        return 'hello world'
 
# 实例化类
x = MyClass()
 
# 访问类的属性和方法
print("MyClass 类的属性 i 为：", x.i)
print("MyClass 类的方法 f 输出为：", x.f())
```

``` sh
MyClass 类的属性 i 为： 12345
MyClass 类的方法 f 输出为： hello world
```

类有一个名为`__init__()`的特殊方法（构造方法），该方法在类实例化时会自动调用，`__init__()`方法是可以有参数的，通过参数实例化类，如：

``` python
class Complex:
    def __init__(self, realpart, imagpart):		# self代表类的实例，而非类
        self.r = realpart
        self.i = imagpart
        
x = Complex(3.0, -4.5)
print(x.r, x.i)   # 输出结果：3.0 -4.5
```

**类的方法**与**普通函数**只有一个特别的区别，他们必须有一个额外的参数，按照惯例它的名字是：**self**（但是它并非关键字，换成其它也可以）。

``` python
class Test:
    def prt(self):
        print(self)
        print(self.__class__)
 
t = Test()
t.prt()
```

``` sh
<__main__.Test instance at 0x100771878>		# 从结果看出，self是类的实例，代表当前类的地址
__main__.Test
```

### 类的方法

在类的内部，使用 **def** 关键字来定义一个方法，与一般函数定义不同，类方法必须包含参数 self, 且为第一个参数，self 代表的是类的实例。

``` python
class people:
    name = ''					# 定义基本属性
    age = 0
    __weight = 0				# 定义私有属性,私有属性在类外部无法直接进行访问	
   
    def __init__(self,n,a,w):	# 定义构造方法
        self.name = n
        self.age = a
        self.__weight = w
        
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name,self.age))
 
# 实例化类
p = people('Han,meimei',10,30)
p.speak()
```

``` sh
Han,meimei 说: 我 10 岁。
```

### 继承

子类（派生类 DerivedClassName）会继承父类（基类 BaseClassName）的属性和方法。

BaseClassName（实例中的基类名）必须与派生类定义在一个作用域内。除了类，还可以用表达式，基类定义在另一个模块中时这一点非常有用，如：

``` python
class DerivedClassName(modname.BaseClassName):
```

``` python
class people:
    name = ''						# 定义基本属性
    age = 0 
    __weight = 0					# 定义私有属性,私有属性在类外部无法直接进行访问	
   
    def __init__(self,n,a,w):		# 定义构造方法
        self.name = n
        self.age = a
        self.__weight = w
        
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name,self.age))
 
class student(people):				# 单继承示例
    grade = ''
    def __init__(self,n,a,w,g):	
        people.__init__(self,n,a,w)	# 调用父类的构函
        self.grade = g
    
    def speak(self):				# 覆写父类的方法
        print("%s 说: 我 %d 岁了，我在读 %d 年级"%(self.name,self.age,self.grade))
 
s = student('Han,meimei',10,60,3)
s.speak()
```

``` sh
Han,meimei 说: 我 10 岁了，我在读 3 年级
```

### 多继承

Python有限的支持多继承形式。多继承的类定义，如：

``` python
class DerivedClassName(Base1, Base2, Base3):
```

> 圆括号中父类的顺序，若是父类中有相同的方法名，而在子类使用时未指定，python从左至右搜索 即方法在子类中未找到时，从左到右查找父类中是否包含方法。

``` python
class people:
    name = ''						# 定义基本属性
    age = 0  
    __weight = 0					# 定义私有属性,私有属性在类外部无法直接进行访问 
    
    def __init__(self,n,a,w):		# 定义构造方法
        self.name = n
        self.age = a
        self.__weight = w
        
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name,self.age))
 
class student(people):				# 单继承示例
    grade = ''
    
    def __init__(self,n,a,w,g):		# 调用父类的构函    
        people.__init__(self,n,a,w)
        self.grade = g
    
    def speak(self):				# 覆写父类的方法
        print("%s 说: 我 %d 岁了，我在读 %d 年级"%(self.name,self.age,self.grade))
 
class speaker():					# 另一个类，多重继承之前的准备
    topic = ''
    name = ''
    
    def __init__(self,n,t):
        self.name = n
        self.topic = t
        
    def speak(self):
        print("我叫 %s，我是一个演说家，我演讲的主题是 %s"%(self.name,self.topic))
 

class sample(speaker,student):		# 多重继承
    a =''
    def __init__(self,n,a,w,g,t):
        student.__init__(self,n,a,w,g)
        speaker.__init__(self,n,t)
 
test = sample("Han,meimei",25,80,4,"Python")
test.speak()   #方法名同，默认调用的是在括号中参数位置排前父类的方法
```

``` sh
我叫 Han,meimei，我是一个演说家，我演讲的主题是 Python
```

### 方法重写

如果父类方法的功能不能满足你的需求，你可以在子类重写你父类的方法，如：

``` python
class Parent:        		# 定义父类
   def myMethod(self):
      print ('调用父类方法')
 
class Child(Parent): 		# 定义子类
   def myMethod(self):
      print ('调用子类方法')
 
c = Child()          		# 子类实例
c.myMethod()         		# 子类调用重写方法
super(Child,c).myMethod()	# 用子类对象调用父类已被覆盖的方法
```

``` sh
调用子类方法
调用父类方法
```

> **super()**函数是用于调用父类（超类）的一个方法。

### 私有属性与方法

无论属性或方法，要私有就要以双下划线开头，如`__private_attrs`或`__private_method`；在类的内部使用`self.__private_attrs`或`self.__private_method`访问。

``` python
class Site:
    def __init__(self, name, url):
        self.name = name       # public
        self.__url = url   # private
 
    def who(self):
        print('name  : ', self.name)
        print('url : ', self.__url)
 
    def __foo(self):          # 私有方法
        print('这是私有方法')
 
    def foo(self):            # 公共方法
        print('这是公共方法')
        self.__foo()
 
x = Site('菜鸟教程', 'www.runoob.com')
x.who()        	# 正常输出
x.foo()        	# 正常输出
print(x.name)	# 正常访问共有属性
print(x.__url)	# 报错，不能访问私有属性
x.__foo()      	# 报错，不能访问私有方法
```

``` sh
name :  菜鸟教程
url :  www.runoob.com
这是公共方法
这是私有方法
菜鸟教程
Traceback (most recent call last):
  File "/home/xuwei/a01.py", line 21, in <module>
    print(x.__url)
AttributeError: 'Site' object has no attribute '__url'
```

### 类的专有方法

- **\__init__ :** 构造函数，在生成对象时调用
- **\__del__ :** 析构函数，释放对象时使用
- **\__repr__ :** 打印，转换
- **\__setitem__ :** 按照索引赋值
- **\__getitem__:** 按照索引获取值
- **\__len__:** 获得长度
- **\__cmp__:** 比较运算
- **\__call__:** 函数调用
- **\__add__:** 加运算
- **\__sub__:** 减运算
- **\__mul__:** 乘运算
- **\__truediv__:** 除运算
- **\__mod__:** 求余运算
- **\__pow__:** 乘方

### 运算符重载

``` python
class Vector:
   def __init__(self, a, b):
      self.a = a
      self.b = b
 
   def __str__(self):
      return 'Vector (%d, %d)' % (self.a, self.b)
   
   def __add__(self,other):
      return Vector(self.a + other.a, self.b + other.b)
 
v1 = Vector(2,10)
v2 = Vector(5,-2)
print (v1 + v2)
```

``` sh
Vector(7,8)
```

## 文件操作

Python 用`open()`打开文件，一定要保证用`close()`关闭文件，原型：

``` python
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```

参数说明：

- **file**: 必需，文件路径（相对或者绝对路径）。
- **mode**: 可选，文件打开模式
- **buffering**: 设置缓冲
- **encoding**: 一般使用utf8
- **errors**: 报错级别
- **newline**: 区分换行符
- **closefd**: 传入的file参数类型
- **opener**: 设置自定义开启器，开启器的返回值必须是一个打开的文件描述符。

| mode | 描述                                                         |
| ---- | ------------------------------------------------------------ |
| t    | 文本模式 (**默认**)。                                        |
| x    | 写模式，新建一个文件，如果该文件已存在则会报错。             |
| b    | 二进制模式。                                                 |
| +    | 打开一个文件进行更新(可读可写)。                             |
| U    | 通用换行模式（**Python 3 不支持**）。                        |
| r    | 以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。 |
| rb   | 以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。一般用于非文本文件如图片等。 |
| r+   | 打开一个文件用于读写。文件指针将会放在文件的开头。           |
| rb+  | 以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。一般用于非文本文件如图片等。 |
| w    | 打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。 |
| wb   | 以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。 |
| w+   | 打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。 |
| wb+  | 以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。 |
| a    | 打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 |
| ab   | 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。 |
| a+   | 打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。 |
| ab+  | 以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。 |

#### file 函数

| 函数                        | 描述                                                         |
| --------------------------- | ------------------------------------------------------------ |
| file.close()                | 关闭文件。关闭后文件不能再进行读写操作。                     |
| file.flush()                | 刷新文件内部缓冲，直接把内部缓冲区的数据立刻写入文件, 而不是被动的等待输出缓冲区写入。 |
| file.fileno()               | 返回一个整型的文件描述符(file descriptor FD 整型), 可以用在如os模块的read方法等一些底层操作上。 |
| file.isatty()               | 如果文件连接到一个终端设备返回 True，否则返回 False。        |
| file.next()                 | 返回文件下一行。（**Python3中的File对象不支持next()方法**）  |
| file.read([size])           | 从文件读取指定的字节数，如果未给定或为负则读取所有。         |
| file.readline([size])       | 读取整行，包括 "\n" 字符。                                   |
| file.readlines([sizeint])   | 读取所有行并返回列表，若给定sizeint>0，返回总和大约为sizeint字节的行, 实际读取值可能比 sizeint 较大, 因为需要填充缓冲区。 |
| file.seek(offset[, whence]) | 移动文件读取指针到指定位置。                                 |
| file.tell()                 | 返回文件当前位置。                                           |
| file.truncate([size])       | 从文件的首行首字符开始截断，截断文件为 size 个字符，无 size 表示从当前位置截断；截断之后后面的所有字符被删除，其中 windows 系统下的换行代表2个字符大小。 |
| file.write(str)             | 将字符串写入文件，返回的是写入的字符长度。                   |
| file.writelines(sequence)   | 向文件写入一个序列字符串列表，如果需要换行则要自己加入每行的换行符。 |

#### 文件清理

文件`open()`之后需要`close()`，关键词 `with` 语句就可以保证诸如文件之类的对象在使用完之后一定会正确的执行他的清理方法：

``` python
with open("myfile.txt") as f:
    for line in f:
        print(line, end="")
```

以上代码执行完毕，就算再处理过程中出现问题，文件**f**总是会关闭。

## 异常处理

Python有两种错误：语法错误（SyntaxError: invalid syntax）和异常（OtherError...）。

### 异常捕捉

我们用`try/except`语句捕捉异常，原型：

``` python
try:
    执行代码
except:
    发生异常时执行的代码
else:
    没有异常时执行的代码
finally:
    不管有没有异常都执行的代码
```

``` python
try:
    runoob()
except AssertionError as error:
    print(error)
else:
    try:
        with open('file.log') as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
finally:
    print('这句话，无论异常是否发生都会执行。')
```

### 抛出异常

Python使用raise语句抛出一个指定的异常，原型：

``` python
raise [Exception [, args [, traceback]]]
```

``` python
x = 10
if x > 5:
    raise Exception('x 不能大于 5。x 的值为: {}'.format(x))
```

以上代码会触发异常

``` sh
Traceback (most recent call last):
  File "test.py", line 3, in <module>
    raise Exception('x 不能大于 5。x 的值为: {}'.format(x))
Exception: x 不能大于 5。x 的值为: 10
```

raise 唯一的一个参数指定了要被抛出的异常。它必须是一个异常的实例或者是异常的类（Exception 的子类）。

如果你只想知道这是否抛出了一个异常，并不想去处理它，那么一个简单的 raise 语句就可以再次把它抛出。

``` python
try:
    raise NameError("HiThere")	# 模拟一个异常
except NameError:
    print("An exception flew by!")
    raise
```

``` sh
An exception flew by!
Traceback (most recent call last):
  File "/home/xuwei/a01.py", line 2, in <module>
    raise NameError("HiThere")
NameError: HiThere
```

### 自定义异常

你可以通过创建一个新的异常类来拥有自己的异常。异常类继承自 Exception 类，可以直接继承，或者间接继承，例如:

``` python
class MyError(Exception):
    def __init__(self, value):
        self.value = value
    def __str__(self):
        return repr(self.value)
    
try:
	raise MyError(2*2)
except MyError as e:
    print('My exception occurred, value:', e.value)

raise MyError('oops')
```

``` sh
My exception occurred, value: 4
Traceback (most recent call last):
  File "/home/xuwei/a01.py", line 12, in <module>
    raise MyError('oops')
__main__.MyError: 'oops'
```

在这个例子中，类 Exception 默认的 `__init__()` 被覆盖。

### assert 断言

Python `assert`（断言）用于判断一个表达式，在表达式条件为 false 的时候触发异常。断言可以在条件不满足程序运行的情况下直接返回错误，而不必等待程序运行后出现崩溃的情况，原型：

``` python
assert expression[, arguments]
#等价于
if not expression:
    raise AssertionError(arguments)
```

``` python
>>> assert True     # 条件为 true 正常执行
>>> assert False    # 条件为 false 触发异常
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AssertionError
>>> assert 1==1    # 条件为 true 正常执行
>>> assert 1==2    # 条件为 false 触发异常
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AssertionError

>>> assert 1==2, '1 不等于 2'		# 有参数
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AssertionError: 1 不等于 2
>>>
```

``` python
import sys
assert ('linux' in sys.platform), "该代码只能在 Linux 下执行"
```

## 单元测试与用例

unittest提供了代码测试工具。unittest模块中的常用断言：

* **assertEqual**(a, b)：a == b
* **assertNotEqua**(a, b)：a != b
* **assertTrue**(x)：x为True
* **assertFalse**(x)：x为False
* **assertIn**(item, list)：item在list中
* **assertNotIn**(item, list)：item不在list中

### 测试函数

``` python
# name_function.py
def get_formatted_name(first, last, middle = ''):
    """生成整洁的姓名"""
    if middle:
        full_name = f"{first} {middle} {last}"
    else:
        full_name = f"{first} {last}"
    
    return full_name.title()
```

``` python
# test_name_function.py
import unittest
from name_function import get_formatted_name

class NamesTestCase(unittest.TestCase):
    """测试 name_function.py"""
    def test_first_last_name(self):
        """能正确地处理像 Janis Joplin 这样的姓名吗？"""
        formatted_name = get_formatted_name("janis", "joplin")
        self.assertEqual(formatted_name, "Janis Joplin")
        
    def test_first_middle_last_name(self):
        """能正确地处理像 Wolfgang Amadeus Mozart 这样的姓名吗？"""
        formatted_name = get_formatted_name("wolfgang", "mozart", "amadeus")
        self.assertEqual(formatted_name, "Wolfgang Amadeus Mozart")   
        
if __name__ == "__main__":
    unittest.main()
```

``` sh
$ python test_name_function.py
..
----------------------------------------------------------------------
Ran 2 tests in 0.000s

OK
```

### 测试类

``` python
# survey.py
class AnonymousSurvey:
    """收集匿名调查问卷的答案。"""
    def __init__(self, question):
        """存储一个问题，并为存储答案做准备。"""
        self.question = question
        self.responses = []

    def show_question(self):
        """显示调查问卷。"""
        print(self.question)

    def store_response(self, new_response):
        """存储单份调查答案。"""
        self.responses.append(new_response)

    def show_results(self):
        """显示收集到的所有答案。"""
        print("Survey results：")
        for response in self.responses:
            print(f"- {response}")
```

``` python
# test_survey.py
import unittest
from survey import AnonymousSurvey

class TestAnonymousSurvey(unittest.TestCase):
    """针对 AnonymousSurvey 类的测试。"""
    def test_store_single_response(self):
        """测试单个答案会被妥善地存储。"""
        question = "What language did you first learn to speak?"
        my_survey = AnonymousSurvey(question)
        my_survey.store_response("English")
        self.assertIn("English", my_survey.responses)

if __name__ == "__main__":
    unittest.main()
```

``` sh
$ python test_survey.py
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK
```

### setUp方法

unittest.TestCase类包含的方法setUp()让我们只需创建这些对象一次，就能在每个测试方法中使用。Python将先运行它，再运行各个以`test_`开头的方法。这样，在你编写的每个测试方法中，都可使用在方法setUp()中创建对象。上面的test_survey.py改写为：

``` python
# test_survey.py
import unittest
from survey import AnonymousSurvey

class TestAnonymousSurvey(unittest.TestCase):
    """针对 AnonymousSurvey 类的测试。"""

    def setUp(self):
        """创建一个调查对象和一组答案，供使用的测试方法使用。"""
        question = "What language did you first learn to speak?"
        self.my_survey = AnonymousSurvey(question)
        self.responses = ["English", "Spanish", "Mandarin"]

    def test_store_single_response(self):
        """测试单个答案会被妥善地存储。"""
        self.my_survey.store_response(self.responses[0])
        self.assertIn(self.responses[0], self.my_survey.responses)

    def test_store_threee_responses(self):
        """测试三个答案会被妥善地存储。"""
        for response in self.responses:
            self.my_survey.store_response(response)
        for response in self.responses:
            self.assertIn(response, self.my_survey.responses)

if __name__ == "__main__":
     unittest.main()
```

## 推导式

Python 推导式是一种独特的数据处理方式，可以从一个数据序列构建另一个新的数据序列的结构体。

Python 支持各种数据结构的推导式：

### 列表推导式

``` python
[表达式 for 变量 in 列表] 
[out_exp_res for out_exp in input_list]
# 或者 
[表达式 for 变量 in 列表 if 条件]
[out_exp_res for out_exp in input_list if condition]
```

- out_exp_res：列表生成元素表达式，可以是有返回值的函数。
- for out_exp in input_list：迭代 input_list 将 out_exp 传入到 out_exp_res 表达式中。
- if condition：条件语句，可以过滤列表中不符合条件的值。

``` python
# 过滤掉长度小于或等于3的字符串列表，并将剩下的转换成大写字母
names = ['Bob','Tom','alice','Jerry','Wendy','Smith']
new_names = [name.upper() for name in names if len(name)>3]
print(new_names)
['ALICE', 'JERRY', 'WENDY', 'SMITH']	# 结果输出

# 计算 30 以内可以被 3 整除的整数
multiples = [i for i in range(30) if i%3==0]
print(multiples)
print(type(multiples))
[0, 3, 6, 9, 12, 15, 18, 21, 24, 27]	# 结果输出
<class 'list'>
```

### 字典推导式

``` python
{ key_expr: value_expr for value in collection }
# 或者
{ key_expr: value_expr for value in collection if condition }
```

``` python
# 将列表中各字符串值为键，各字符串的长度为值，组成键值对
listdemo = ['Bob','Tom','alice','Jerry','Wendy','Smith']
newdict = {key:len(key) for key in listdemo}	
print(newdict)
{'Bob': 3, 'Tom': 3, 'alice': 5, 'Jerry': 5, 'Wendy': 5, 'Smith': 5}	# 结果输出

# 提供三个数字，以三个数字为键，三个数字的平方为值来创建字典
dic = {x:x**2 for x in (2,4,6)}
print(dic)
print(type(dic))
{2: 4, 4: 16, 6: 36}	# 结果输出
<class 'dict'>
```

### 集合推导式

``` python
{ expression for item in Sequence }
# 或者
{ expression for item in Sequence if conditional }
```

``` python
# 计算数字 1,2,3 的平方数
setnew = {i**2 for i in (1,2,3)}
print(setnew)
{1, 4, 9}		# 结果输出

a = {x for x in 'abracadabra' if x not in 'abc'}
print(a)
print(type(a))
{'d', 'r'}		# 结果输出
<class 'set'>
```

### 元组推导式

``` python
(expression for item in Sequence )
# 或者
(expression for item in Sequence if conditional )
```

元组推导式和列表推导式的用法也完全相同，只是元组推导式是用 **()** 圆括号将各部分括起来，而列表推导式用的是中括号 **[]**，不同于列表，元组推导式返回的结果是一个**生成器对象**。

``` python
# 生成一个包含数字 1~9 的元组
a = (x for x in range(1,10))
print(a)
print(type(a))
<generator object <genexpr> at 0x7f60bb028190>		# 元组推导式返回的结果是一个生成器对象
<class 'generator'>
```

## 迭代器与生成器

### 迭代器

迭代器是一个可以记住遍历的位置的对象，是访问集合元素的一种方式。迭代器对象从集合的第一个元素开始访问，直到所有的元素被访问完结束。迭代器只能往前不会后退。

迭代器有两个基本的方法：**iter()** 和 **next()**。

``` python
# 字符串，列表或元组对象都可用于创建迭代器
list = [1,2,3,4]
it = iter(list)		# 创建迭代器对象
print(next(it))		# 输出迭代器的下一个元素 1
print(next(it))		# 2

# 迭代器对象可以使用常规for语句进行遍历
list = [1,2,3,4]
it = iter(list)
for x in it:
    print(x, end=" ")
1 2 3 4				# 输出结果

# 也可以使用next()函数
import sys
list = [1,2,3,4]
it = iter(list)
while True:
    try:
        print(next(it))
    except StopIteration:
        sys.ext()
1					# 输出结果
2
3
4
```

### 迭代器类

把一个类作为一个迭代器使用需要在类中实现两个方法 `__iter__()` 与 `__next__()` 。

* `__iter__()` 方法返回一个特殊的迭代器对象， 这个迭代器对象实现了 `__next__()` 方法并通过 StopIteration 异常标识迭代的完成。

* `__next__()` 方法（Python 2 里是 next()）会返回下一个迭代器对象。

``` python
# 创建一个返回数字的迭代器，初始值为 1，逐步递增 1
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self
 
  def __next__(self):
    x = self.a
    self.a += 1
    return x
 
myclass = MyNumbers()
myiter = iter(myclass)

print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
```

``` sh
1
2
3
4
5
```

### StopIteration 结束迭代

StopIteration 异常用于标识迭代的完成，防止出现无限循环的情况，在 __next__() 方法中我们可以设置在完成指定循环次数后触发 StopIteration 异常来结束迭代。

``` python
# 在 20 次迭代后停止执行
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self
 
  def __next__(self):
    if self.a <= 20:
      x = self.a
      self.a += 1
      return x
    else:
      raise StopIteration
 
myclass = MyNumbers()
myiter = iter(myclass)
 
for x in myiter:
  print(x)
```

### Generator 生成器

在 Python 中，使用了 **yield** 的函数被称为生成器（generator）。

跟普通函数不同的是，生成器是一个返回迭代器的函数，只能用于迭代操作，更简单点理解生成器就是一个迭代器。

在调用生成器运行的过程中，每次遇到 yield 时函数会暂停并保存当前所有的运行信息，返回 yield 的值, 并在下一次执行 next() 方法时从当前位置继续运行。

调用一个生成器函数，返回的是一个迭代器对象。

``` python
# 使用 yield 实现斐波那契数列
import sys
 
def fibonacci(n): 		# 生成器函数 - 斐波那契
    a, b, counter = 0, 1, 0
    while True:
        if (counter > n): 
            return
        yield a
        a, b = b, a + b
        counter += 1
f = fibonacci(10) 		# f 是一个迭代器，由生成器返回生成
 
while True:
    try:
        print (next(f), end=" ")
    except StopIteration:
        sys.exit()
```

```sh
0 1 1 2 3 5 8 13 21 34 55
```

## Decorators 装饰器

装饰器(Decorators)是 Python 的一个重要部分。简单地说：他们是修改其他函数的功能的函数。他们有助于让我们的代码更简洁。

``` python
# 首先来理解下 Python 中的函数
def hi(name="yasoob"):
    return "hi " + name
 
print(hi())
# output: 'hi yasoob'
 
# 我们甚至可以将一个函数赋值给一个变量，比如
greet = hi
# 我们这里没有在使用小括号，因为我们并不是在调用hi函数
# 而是在将它放在greet变量里头。我们尝试运行下这个
 
print(greet())
# output: 'hi yasoob'
 
# 如果我们删掉旧的hi函数，看看会发生什么！
del hi
print(hi())
#outputs: NameError
 
print(greet())
#outputs: 'hi yasoob'
```

### 在函数中定义函数

了解了基本函数之后，我们更近一步。在 Python 中我们可以在一个函数中定义另一个函数：

``` python
def hi(name="yasoob"):
    print("now you are inside the hi() function")
 
    def greet():
        return "now you are in the greet() function"
 
    def welcome():
        return "now you are in the welcome() function"
 
    print(greet())
    print(welcome())
    print("now you are back in the hi() function")
 
hi()		# 上面展示了无论何时你调用hi(), greet()和welcome()将会同时被调用
greet()		# 然后greet()和welcome()函数在hi()函数之外是不能访问的
```

``` sh
now you are inside the hi() function
now you are in the greet() function
now you are in the welcome() function
now you are back in the hi() function
Traceback (most recent call last):
  File "/home/xuwei/a01.py", line 15, in <module>
    greet()
NameError: name 'greet' is not defined
```

### 从函数中返回函数

我们也可以依条件将函数输出返回出来：

``` python
def hi(name="yasoob"):
    def greet():
        return "now you are in the greet() function"
 
    def welcome():
        return "now you are in the welcome() function"
 
    if name == "yasoob":
        return greet
    else:
        return welcome
 
a = hi()
print(a)		# 清晰地展示了`a`现在指向到hi()函数中的greet()函数
print(a())
```

``` sh
<function hi.<locals>.greet at 0x7f065f01ecb0>
now you are in the greet() function
```

> 这个代码。在 if/else 语句中我们返回 greet 和 welcome，而不是 greet() 和 welcome()。为什么那样？这是因为当你把一对小括号放在后面，这个函数就会执行。

### 函数作为函数参数

``` python
def hi():
    return "hi yasoob!"
 
def doSomethingBeforeHi(func):
    print("I am doing some boring work before executing hi()")
    print(func())
 
doSomethingBeforeHi(hi)
```

``` sh
I am doing some boring work before executing hi()
hi yasoob!
```

现在已经具备所有必需知识，来进一步学习装饰器真正是什么了。装饰器让你在一个函数的前后去执行代码。

### 装饰器

``` python
def a_new_decorator(a_func):	# 其实这就是一个装饰器
 
    def wrapTheFunction():
        print("I am doing some boring work before executing a_func()")
 
        a_func()
 
        print("I am doing some boring work after executing a_func()")
 
    return wrapTheFunction
 
def a_function_requiring_decoration():
    print("I am the function which needs some decoration to remove my foul smell")
 
a_function_requiring_decoration()
#outputs: "I am the function which needs some decoration to remove my foul smell"
 
a_function_requiring_decoration = a_new_decorator(a_function_requiring_decoration)
#now a_function_requiring_decoration is wrapped by wrapTheFunction()
 
a_function_requiring_decoration()
```

``` sh
I am the function which needs some decoration to remove my foul smell
I am doing some boring work before executing a_func()
I am the function which needs some decoration to remove my foul smell
I am doing some boring work after executing a_func()
```

> 这正是 python 中装饰器做的事情！它们封装一个函数，并且用这样或者那样的方式来修改它的行为。

我们在代码里并没有使用 **@** 符号。那只是一个简短的方式来生成一个被装饰的函数。这里是我们如何使用 **@** 来运行之前的代码：

``` python
def a_new_decorator(a_func):
 
    def wrapTheFunction():
        print("I am doing some boring work before executing a_func()")
        a_func()
        print("I am doing some boring work after executing a_func()")
 
    return wrapTheFunction

@a_new_decorator
def a_function_requiring_decoration():
    """Hey you! Decorate me!"""
    print("I am the function which needs some decoration to remove my foul smell")
 
a_function_requiring_decoration()

print(a_function_requiring_decoration.__name__)
```

``` sh
I am doing some boring work before executing a_func()
I am the function which needs some decoration to remove my foul smell
I am doing some boring work after executing a_func()
wrapTheFunction
```

这并不是我们想要的！Ouput输出应该是"a_function_requiring_decoration"。这里的函数被warpTheFunction替代了。它重写了我们函数的名字和注释文档(docstring)。幸运的是Python提供给我们一个简单的函数来解决这个问题，那就是functools.wraps。我们修改上一个例子来使用functools.wraps：

``` python
from functools import wraps
 
def a_new_decorator(a_func):
    @wraps(a_func)
    def wrapTheFunction():
        print("I am doing some boring work before executing a_func()")
        a_func()
        print("I am doing some boring work after executing a_func()")
    return wrapTheFunction
 
@a_new_decorator
def a_function_requiring_decoration():
    """Hey yo! Decorate me!"""
    print("I am the function which needs some decoration to "
          "remove my foul smell")
 
print(a_function_requiring_decoration.__name__)
# Output: a_function_requiring_decoration	现在输出的是正确的函数名了
```

### 装饰器规范

``` python
from functools import wraps
def decorator_name(f):
    @wraps(f)
    def decorated(*args, **kwargs):
        if not can_run:
            return "Function will not run"
        return f(*args, **kwargs)
    return decorated
 
@decorator_name
def func():
    return("Function is running")
 
can_run = True
print(func())
# Output: Function is running
 
can_run = False
print(func())
# Output: Function will not run
```

> **@wraps** 接受一个函数来进行装饰，并加入了复制函数名称、注释文档、参数列表等等的功能。这可以让我们在装饰器里面访问在装饰之前的函数的属性。

### 使用场景

#### Authorization 授权

装饰器能有助于检查某个人是否被授权去使用一个web应用的端点(endpoint)。它们被大量使用于Flask和Django web框架中。这里是一个例子来使用基于装饰器的授权：

``` python
from functools import wraps
 
def requires_auth(f):
    @wraps(f)
    def decorated(*args, **kwargs):
        auth = request.authorization
        if not auth or not check_auth(auth.username, auth.password):
            authenticate()
        return f(*args, **kwargs)
    return decorated
```

#### Logging 日志

``` python
from functools import wraps
 
def logit(func):
    @wraps(func)
    def with_logging(*args, **kwargs):
        print(func.__name__ + " was called")
        return func(*args, **kwargs)
    return with_logging
 
@logit
def addition_func(x):
   """Do some math."""
   return x + x
 
result = addition_func(4)
# Output: addition_func was called
```

### 装饰器的参数

@wraps不也是个装饰器吗？但是，它接收一个参数，就像任何普通的函数能做的那样。那么，为什么我们不也那样做呢？ 这是因为，当你使用@my_decorator语法时，你是在应用一个以单个函数作为参数的一个包裹函数。记住，Python 里每个东西都是一个对象，而且这包括函数！记住了这些，我们可以编写一下能返回一个包裹函数的函数。

### 函数中的装饰器

``` python
# 创建一个包裹函数，能让我们指定一个用于输出的日志文件
from functools import wraps
 
def logit(logfile='out.log'):
    def logging_decorator(func):
        @wraps(func)
        def wrapped_function(*args, **kwargs):
            log_string = func.__name__ + " was called"
            print(log_string)
            # 打开logfile，并写入内容
            with open(logfile, 'a') as opened_file:
                # 现在将日志打到指定的logfile
                opened_file.write(log_string + '\n')
            return func(*args, **kwargs)
        return wrapped_function
    return logging_decorator
 
@logit()
def myfunc1():
    pass
 
myfunc1()
# Output: myfunc1 was called
# 现在一个叫做 out.log 的文件出现了，里面的内容就是上面的字符串
 
@logit(logfile='func2.log')
def myfunc2():
    pass
 
myfunc2()
# Output: myfunc2 was called
# 现在一个叫做 func2.log 的文件出现了，里面的内容就是上面的字符串
```

### 装饰器类

有了能用于正式环境的logit装饰器，但当我们的应用的某些部分还比较脆弱时，异常也许是需要更紧急关注的事情。比方说有时你只想打日志到一个文件。而有时你想把引起你注意的问题发送到一个email，同时也保留日志，留个记录。这是一个使用继承的场景，但目前为止我们只看到过用来构建装饰器的函数。

幸运的是，类也可以用来构建装饰器。那我们现在以一个类而不是一个函数的方式，来重新构建logit。

``` python
from functools import wraps
 
class logit(object):
    def __init__(self, logfile='out.log'):
        self.logfile = logfile
 
    def __call__(self, func):
        @wraps(func)
        def wrapped_function(*args, **kwargs):
            log_string = func.__name__ + " was called"
            print(log_string)
            # 打开logfile并写入
            with open(self.logfile, 'a') as opened_file:
                # 现在将日志打到指定的文件
                opened_file.write(log_string + '\n')
            # 现在，发送一个通知
            self.notify()
            return func(*args, **kwargs)
        return wrapped_function
 
    def notify(self):
        # logit只打日志，不做别的
        pass
```

这个实现有一个附加优势，在于比嵌套函数的方式更加整洁，而且包裹一个函数还是使用跟以前一样的语法：

``` python
@logit()
def myfunc1():
    pass
```

现在，给 logit 创建子类，来添加某些功能：

``` python
class email_logit(logit):
    '''
    一个logit的实现版本，可以在函数调用时发送email给管理员
    '''
    def __init__(self, email='admin@myproject.com', *args, **kwargs):
        self.email = email
        super(email_logit, self).__init__(*args, **kwargs)
 
    def notify(self):
        # 发送一封email到self.email
        # 这里就不做实现了
        pass
```

## 正则表达式

正则表达式是一个特殊的字符序列，它能帮助你方便的检查一个字符串是否与某种模式匹配。

Python通过 **re** 模块提供Perl风格的正则表达式。

这里主要说明Python中常用的正则表达式处理函数，如果对正则表达式本身不了解，可以查看runoob提供的[正则表达式教程](https://www.runoob.com/regexp/regexp-tutorial.html "正则表达式教程")

### 正则表达式处理函数

#### match

re.match 尝试从字符串的起始位置匹配一个模式，原型：

``` python
re.match(pattern, string, flags=0)
```

参数：

* **pattern** 匹配的正则表达式
* **string** 要匹配的字符串
* **flags** 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参考[修饰符（可选标志）](#修饰符（可选标志）)

匹配成功re.match方法返回一个匹配的对象，否则返回None。

``` python
import re
print(re.match('www', 'www.runoob.com').span())  # 在起始位置匹配
print(re.match('com', 'www.runoob.com'))         # 不在起始位置匹配
```

``` sh
(0, 3)
None
```

我们可以使用group(num) 或 groups() 匹配对象函数来获取匹配表达式。

| 匹配对象方法 | 描述                                                         |
| ------------ | ------------------------------------------------------------ |
| group(num=0) | 匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。 |
| groups()     | 返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。     |

``` python
import re 
line = "Cats are smarter than dogs"
# .* 表示任意匹配除换行符（\n、\r）之外的任何单个或多个字符
# (.*?) 表示"非贪婪"模式，只保存第一个匹配到的子串
matchObj = re.match( r'(.*) are (.*?) .*', line, re.M|re.I)
 
if matchObj:
	print("matchObj.group() : ", matchObj.group())
	print("matchObj.group(1) : ", matchObj.group(1))
	print("matchObj.group(2) : ", matchObj.group(2))
    print("matchObj.groups() : ", matchObj.groups())
else:
   	print("No match!!")
```

``` sh
matchObj.group() :  Cats are smarter than dogs
matchObj.group(1) :  Cats
matchObj.group(2) :  smarter
matchObj.groups() :  ('Cats', 'smarter')
```

#### search

re.search扫描整个字符串并返回第一个成功的匹配，原型：

``` python
re.search(pattern, string, flags=0)
```

参数与上面`match()`完全一致；匹配成功re.search方法返回一个匹配的对象，否则返回None。

``` python
import re
print(re.search('www', 'www.runoob.com').span())  	# 在起始位置匹配
print(re.search('com', 'www.runoob.com').span())	# 不在起始位置匹配
```

``` sh
(0, 3)
(11, 14)
```

``` python
import re
line = "Cats are smarter than dogs";
 
searchObj = re.search( r'(.*) are (.*?) .*', line, re.M|re.I)
 
if searchObj:
   print("searchObj.group() : ", searchObj.group())
   print("searchObj.group(1) : ", searchObj.group(1))
   print("searchObj.group(2) : ", searchObj.group(2))
else:
   print("Nothing found!!")
```

``` sh
searchObj.group() :  Cats are smarter than dogs
searchObj.group(1) :  Cats
searchObj.group(2) :  smarter
```

#### 两者区别

re.match只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回None；而re.search匹配整个字符串，直到找到一个匹配。

``` python
import re
line = "Cats are smarter than dogs";
 
matchObj = re.match( r'dogs', line, re.M|re.I)
if matchObj:
   print "match --> matchObj.group() : ", matchObj.group()
else:
   print "No match!!"
 
matchObj = re.search( r'dogs', line, re.M|re.I)
if matchObj:
   print "search --> searchObj.group() : ", matchObj.group()
else:
   print "No match!!"
```

``` sh
No match!!
search --> searchObj.group() :  dogs
```

#### sub 检索和替换

re.sub用于替换字符串中的匹配项，原型：

``` python
re.sub(pattern, repl, string, count=0, flags=0)
```

参数：

- pattern : 正则中的模式字符串。
- repl : 替换的字符串，也可为一个函数。
- string : 要被查找替换的原始字符串。
- count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配。

``` python
import re
phone = "2004-959-559 # 这是一个国外电话号码"
 
# 删除字符串中的 Python注释 
num = re.sub(r'#.*$', "", phone)
print "电话号码是: ", num
 
# 删除非数字(-)的字符串 
num = re.sub(r'\D', "", phone)
print "电话号码是 : ", num
```

``` sh
电话号码是:  2004-959-559 
电话号码是 :  2004959559
```

##### repl 参数是一个函数

``` python
# 将字符串中的匹配的数字乘以 2
import re
# 将匹配的数字乘以 2
def double(matched):
    value = int(matched.group('value'))
    return str(value * 2)
 
s = 'A23G4HFD567'
print(re.sub('(?P<value>\d+)', double, s))
```

``` sh
A46G8HFD1134
```

#### compile

compile 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用，原型：

``` python
re.compile(pattern[, flags])
```

参数：

- **pattern** : 一个字符串形式的正则表达式。
- **flags** : 可选，表示匹配模式，比如忽略大小写，多行模式等。参考[修饰符（可选标志）](#修饰符（可选标志）)

``` python
import re
pattern = re.compile(r'\d+')					# 用于匹配至少一个数字
m = pattern.match('one12twothree34four')		# 查找头部，没有匹配
print(m)	# 输出: None

m = pattern.match('one12twothree34four', 2, 10) # 从'e'的位置开始匹配，没有匹配
print(m)	# 输出： None

m = pattern.match('one12twothree34four', 3, 10) # 从'1'的位置开始匹配，正好匹配
print(m)	# 输出：<_sre.SRE_Match object at 0x10a42aac0>
m.group(0)	# 输出：12
m.start(0)	# 输出：3
m.end(0)	# 输出：5
m.span(0)	# 输出：(3, 5)
```

在上面，当匹配成功时返回一个 Match 对象，其中：

- `group([group1, …])` 方法用于获得一个或多个分组匹配的字符串，当要获得整个匹配的子串时，可直接使用 `group()` 或 `group(0)`；
- `start([group])` 方法用于获取分组匹配的子串在整个字符串中的起始位置（子串第一个字符的索引），参数默认值为 0；
- `end([group])` 方法用于获取分组匹配的子串在整个字符串中的结束位置（子串最后一个字符的索引+1），参数默认值为 0；
- `span([group])` 方法返回 `(start(group), end(group))`。

``` python
import re
pattern = re.compile(r'([a-z]+)([a-z]+)', re.I)		# re.I 表示忽略大小写
m = pattern.match('Hello World Wide Web')
print(m)	# 输出：<_sre.SRE_Match object at 0x10bea83e8>
m.group(0)	# 输出: 'Hello World'
m.span(0)	# 输出：(0, 11)
m.group(1)	# 输出：'Hello'
m.span(1)	# 输出：(0, 5)
m.group(2)	# 输出：'World'
m.span(2)	# 输出：(6, 11)
m.groups()	# 输出：('Hello', 'World')		等价于 (m.group(1), m.group(2),...)
m.group(3)	# 输出：报错					   不存在第三个分组
```

#### findall

在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果有多个匹配模式，则返回元组列表，如果没有找到匹配的，则返回空列表，原型：

``` python
findall(string[, pos[, endpos]])
```

参数：

- **string** : 待匹配的字符串。
- **pos** : 可选参数，指定字符串的起始位置，默认为 0。
- **endpos** : 可选参数，指定字符串的结束位置，默认为字符串的长度。

``` python
# 查找字符串中的所有数字
import re
pattern = re.compile(r'\d+')   # 查找数字
result1 = pattern.findall('runoob 123 google 456')
result2 = pattern.findall('run88oob123google456', 0, 10)
 
print(result1)
print(result2)
```

``` sh
['123', '456']
['88', '12']
```

``` python
import re
result = re.findall(r'(\w+)=(\d+)', 'set width=20 and height=10')
print(result)
```

``` sh
[('width', '20'), ('height', '10')]
```

> match 和 search 是匹配一次 findall 匹配所有。

#### finditer

和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回，原型：

``` python
re.finditer(pattern, string, flags=0)
```

参数：

* **pattern** 匹配的正则表达式。
* **string** 要匹配的字符串。
* **flags** 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参考[修饰符（可选标志）](#修饰符（可选标志）)

``` python
import re
it = re.finditer(r"\d+","12a32bc43jf3") 
for match in it: 
    print (match.group() )
```

``` sh
12 
32 
43 
3
```

#### split

split 方法按照能够匹配的子串将字符串分割后返回列表，原型：

``` python
re.split(pattern, string[, maxsplit=0, flags=0])
```

参数：

* **pattern** 匹配的正则表达式。
* **string** 要匹配的字符串。
* **maxsplit** 分隔次数，maxsplit=1 分隔一次，默认为 0，不限制次数。
* **flags** 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参考[修饰符（可选标志）](#修饰符（可选标志）)

``` python
import re
re.split('\W+', 'Hello, Python, World。')
re.split('(\W+)', 'Hello, Python, World。')
re.split('\W+', ' Hello, Python, World。', 1)
re.split('a', 'hello world')	# 对于一个找不到匹配的字符串而言，split 不会对其作出分割
```

``` sh
['Hello', 'Python', 'World', '']
['Hello', ', ', 'Python', ', ', 'World', '。', '']
['', 'Hello, Python, World。']
['hello world']
```

### 正则表达式对象

`re.compile()` 返回 `RegexObject` 对象。

`group()` 返回被 RE 匹配的字符串。

- **start()** 返回匹配开始的位置。
- **end()** 返回匹配结束的位置。
- **span()** 返回一个元组包含匹配 (开始,结束) 的位置。

### 修饰符（可选标志）

正则表达式可以包含一些可选标志修饰符来控制匹配的模式。修饰符被指定为一个可选的标志。多个标志可以通过按位 OR(|) 它们来指定。如 re.I | re.M 被设置成 I 和 M 标志：

| 修饰符 | 描述                                                         |
| :----- | :----------------------------------------------------------- |
| re.I   | 使匹配对大小写不敏感                                         |
| re.L   | 做本地化识别（locale-aware）匹配                             |
| re.M   | 多行匹配，影响 ^ 和 $                                        |
| re.S   | 使 . 匹配包括换行在内的所有字符                              |
| re.U   | 根据Unicode字符集解析字符。这个标志影响 \w, \W, \b, \B.      |
| re.X   | 该标志通过给予你更灵活的格式以便你将正则表达式写得更易于理解。 |

### 正则表达式模式

模式字符串使用特殊的语法来表示一个正则表达式：

字母和数字表示他们自身。一个正则表达式模式中的字母和数字匹配同样的字符串。

多数字母和数字前加一个反斜杠时会拥有不同的含义。

标点符号只有被转义时才匹配自身，否则它们表示特殊的含义。

反斜杠本身需要使用反斜杠转义。

由于正则表达式通常都包含反斜杠，所以你最好使用原始字符串来表示它们。模式元素(如 r'\t'，等价于 '\\t')匹配相应的特殊字符。

下表列出了正则表达式模式语法中的特殊元素。如果你使用模式的同时提供了可选的标志参数，某些模式元素的含义会改变。

| 模式        | 描述                                                         |
| :---------- | :----------------------------------------------------------- |
| ^           | 匹配字符串的开头                                             |
| $           | 匹配字符串的末尾。                                           |
| .           | 匹配任意字符，除了换行符，当re.DOTALL标记被指定时，则可以匹配包括换行符的任意字符。 |
| [...]       | 用来表示一组字符,单独列出：[amk] 匹配 'a'，'m'或'k'          |
| [^...]      | 不在[]中的字符：\[^abc] 匹配除了a,b,c之外的字符。             |
| re*         | 匹配0个或多个的表达式。                                      |
| re+         | 匹配1个或多个的表达式。                                      |
| re?         | 匹配0个或1个由前面的正则表达式定义的片段，非贪婪方式         |
| re{n}      | 精确匹配 n 个前面表达式。例如，o{2} 不能匹配 "Bob" 中的 "o"，但是能匹配 "food" 中的两个 o。 |
| re{n,}     | 匹配 n 个前面表达式。例如， o{2,} 不能匹配"Bob"中的"o"，但能匹配 "foooood"中的所有 o。"o{1,}" 等价于 "o+"。"o{0,}" 则等价于 "o*"。 |
| re{n,m}   | 匹配 n 到 m 次由前面的正则表达式定义的片段，贪婪方式         |
| a\|b       | 匹配a或b                                                     |
| (re)        | 对正则表达式分组并记住匹配的文本                             |
| (?imx)      | 正则表达式包含三种可选标志：i, m, 或 x 。只影响括号中的区域。 |
| (?-imx)     | 正则表达式关闭 i, m, 或 x 可选标志。只影响括号中的区域。     |
| (?: re)     | 类似 (...), 但是不表示一个组                                 |
| (?imx:re)  | 在括号中使用i, m, 或 x 可选标志                              |
| (?-imx:re) | 在括号中不使用i, m, 或 x 可选标志                            |
| (?#...)     | 注释.                                                        |
| (?= re)     | 前向肯定界定符。如果所含正则表达式，以 ... 表示，在当前位置成功匹配时成功，否则失败。但一旦所含表达式已经尝试，匹配引擎根本没有提高；模式的剩余部分还要尝试界定符的右边。 |
| (?! re)     | 前向否定界定符。与肯定界定符相反；当所含表达式不能在字符串当前位置匹配时成功 |
| (?> re)     | 匹配的独立模式，省去回溯。                                   |
| \w          | 匹配字母数字及下划线                                         |
| \W          | 匹配非字母数字及下划线                                       |
| \s          | 匹配任意空白字符，等价于 **[ \t\n\r\f]**。                   |
| \S          | 匹配任意非空字符                                             |
| \d          | 匹配任意数字，等价于 [0-9].                                  |
| \D          | 匹配任意非数字                                               |
| \A          | 匹配字符串开始                                               |
| \Z          | 匹配字符串结束，如果是存在换行，只匹配到换行前的结束字符串。 |
| \z          | 匹配字符串结束                                               |
| \G          | 匹配最后匹配完成的位置。                                     |
| \b          | 匹配一个单词边界，也就是指单词和空格间的位置。例如， 'er\b' 可以匹配"never" 中的 'er'，但不能匹配 "verb" 中的 'er'。 |
| \B          | 匹配非单词边界。'er\B' 能匹配 "verb" 中的 'er'，但不能匹配 "never" 中的 'er'。 |
| \n, \t, 等. | 匹配一个换行符。匹配一个制表符。等                           |
| \1...\9     | 匹配第n个分组的内容。                                        |
| \10         | 匹配第n个分组的内容，如果它经匹配。否则指的是八进制字符码的表达式。 |

### 正则表达式实例

#### 字符

| 实例        | 描述                              |
| :---------- | :-------------------------------- |
| [Pp]ython   | 匹配 "Python" 或 "python"         |
| rub[ye]     | 匹配 "ruby" 或 "rube"             |
| [aeiou]     | 匹配中括号内的任意一个字母        |
| [0-9]       | 匹配任何数字。类似于 [0123456789] |
| [a-z]       | 匹配任何小写字母                  |
| [A-Z]       | 匹配任何大写字母                  |
| [a-zA-Z0-9] | 匹配任何字母及数字                |
| [^aeiou]    | 除了aeiou字母以外的所有字符       |
| [^0-9]      | 匹配除了数字外的字符              |

#### 特殊字符

| 实例 | 描述                                                         |
| :--- | :----------------------------------------------------------- |
| .    | 匹配除 "\n" 之外的任何单个字符。要匹配包括 '\n' 在内的任何字符，请使用象 '[.\n]' 的模式。 |
| \d   | 匹配一个数字字符。等价于 [0-9]。                             |
| \D   | 匹配一个非数字字符。等价于 \[^0-9]。                         |
| \s   | 匹配任何空白字符，包括空格、制表符、换页符等等。等价于 \[ \f\n\r\t\v]。 |
| \S   | 匹配任何非空白字符。等价于 \[^ \f\n\r\t\v]。                 |
| \w   | 匹配包括下划线的任何单词字符。等价于'[A-Za-z0-9_]'。         |
| \W   | 匹配任何非单词字符。等价于 '\[^A-Za-z0-9_]'。                |

## 多线程与多进程

多线程类似于同时执行多个不同程序，多线程运行有如下优点：

- 使用线程可以把占据长时间的程序中的任务放到后台去处理。
- 用户界面可以更加吸引人，比如用户点击了一个按钮去触发某些事件的处理，可以弹出一个进度条来显示处理的进度。
- 程序的运行速度可能加快。
- 在一些等待的任务实现上如用户输入、文件读写和网络收发数据等，线程就比较有用了。在这种情况下我们可以释放一些珍贵的资源如内存占用等等。

每个独立的线程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。

每个线程都有他自己的一组CPU寄存器，称为线程的上下文，该上下文反映了线程上次运行该线程的CPU寄存器的状态。

指令指针和堆栈指针寄存器是线程上下文中两个最重要的寄存器，线程总是在进程得到上下文中运行的，这些地址都用于标志拥有线程的进程地址空间中的内存。

- 线程可以被抢占（中断）。
- 在其他线程正在运行时，线程可以暂时搁置（也称为睡眠） -- 这就是线程的退让。

线程可以分为:

- **内核线程：**由操作系统内核创建和撤销。
- **用户线程：**不需要内核支持而在用户程序中实现的线程。

Python3 线程中常用的两个模块为：

- **_thread (废弃)**
- **threading (推荐使用)**

### 创建线程

我们可以通过直接从 threading.Thread 继承创建一个新的子类，并实例化后调用 start() 方法启动新线程，即它调用了线程的 run() 方法

``` python
import threading
import time

exitFlag = 0

class myThread (threading.Thread):
    def __init__(self, threadID, name, delay):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.delay = delay
    def run(self):
        print ("开始线程：" + self.name)
        print_time(self.name, self.delay, 5)
        print ("退出线程：" + self.name)

def print_time(threadName, delay, counter):
    while counter:
        if exitFlag:
            threadName.exit()
        time.sleep(delay)
        print ("%s: %s" % (threadName, time.ctime(time.time())))
        counter -= 1

# 创建新线程
thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

# 开启新线程
thread1.start()
thread2.start()
thread1.join()		# 在子线程thread1未完成之前，阻塞主线程
thread2.join()		# 在子线程thread2未完成之前，阻塞主线程
print ("退出主线程")
```

``` sh
开始线程：Thread-1
开始线程：Thread-2
Thread-1: Wed Jan  5 17:34:54 2022
Thread-2: Wed Jan  5 17:34:55 2022
Thread-1: Wed Jan  5 17:34:55 2022
Thread-1: Wed Jan  5 17:34:56 2022
Thread-2: Wed Jan  5 17:34:57 2022
Thread-1: Wed Jan  5 17:34:57 2022
Thread-1: Wed Jan  5 17:34:58 2022
退出线程：Thread-1
Thread-2: Wed Jan  5 17:34:59 2022
Thread-2: Wed Jan  5 17:35:01 2022
Thread-2: Wed Jan  5 17:35:03 2022
退出线程：Thread-2
退出主线程
```

### 线程同步

如果多个线程共同对某个数据修改，则可能出现不可预料的结果，为了保证数据的正确性，需要对多个线程进行同步。

使用 Thread 对象的 Lock 和 Rlock 可以实现简单的线程同步，这两个对象都有 acquire 方法和 release 方法，对于那些需要每次只允许一个线程操作的数据，可以将其操作放到 acquire 和 release 方法之间。如下：

多线程的优势在于可以同时运行多个任务（至少感觉起来是这样）。但是当线程需要共享数据时，可能存在数据不同步的问题。

考虑这样一种情况：一个列表里所有元素都是0，线程"set"从后向前把所有元素改成1，而线程"print"负责从前往后读取列表并打印。

那么，可能线程"set"开始改的时候，线程"print"便来打印列表了，输出就成了一半0一半1，这就是数据的不同步。为了避免这种情况，引入了锁的概念。

锁有两种状态——锁定和未锁定。每当一个线程比如"set"要访问共享数据时，必须先获得锁定；如果已经有别的线程比如"print"获得锁定了，那么就让线程"set"暂停，也就是同步阻塞；等到线程"print"访问完毕，释放锁以后，再让线程"set"继续。

经过这样的处理，打印列表时要么全部输出0，要么全部输出1，不会再出现一半0一半1的尴尬场面。

``` python
import threading
import time

class myThread (threading.Thread):
    def __init__(self, threadID, name, delay):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.delay = delay
    def run(self):
        print ("开启线程： " + self.name)
        threadLock.acquire()		# 获取锁，用于线程同步
        print_time(self.name, self.delay, 3)
        threadLock.release()		# 释放锁，开启下一个线程

def print_time(threadName, delay, counter):
    while counter:
        time.sleep(delay)
        print ("%s: %s" % (threadName, time.ctime(time.time())))
        counter -= 1

threadLock = threading.Lock()		# 创建锁
threads = []

# 创建新线程
thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

# 开启新线程
thread1.start()
thread2.start()

# 添加线程到线程列表
threads.append(thread1)
threads.append(thread2)

# 等待所有线程完成
for t in threads:
    t.join()
print ("退出主线程")
```

``` sh
开启线程： Thread-1
开启线程： Thread-2
Thread-1: Wed Jan  5 17:36:50 2022
Thread-1: Wed Jan  5 17:36:51 2022
Thread-1: Wed Jan  5 17:36:52 2022
Thread-2: Wed Jan  5 17:36:54 2022
Thread-2: Wed Jan  5 17:36:56 2022
Thread-2: Wed Jan  5 17:36:58 2022
退出主线程
```

### Queue 线程队列

Python 的 Queue 模块中提供了同步的、线程安全的队列类，包括FIFO（先入先出)队列Queue，LIFO（后入先出）队列LifoQueue，和优先级队列 PriorityQueue。

这些队列都实现了锁原语，能够在多线程中直接使用，可以使用队列来实现线程间的同步。

Queue 模块中的常用方法:

- Queue.qsize() 返回队列的大小
- Queue.empty() 如果队列为空，返回True,反之False
- Queue.full() 如果队列满了，返回True,反之False
- Queue.full 与 maxsize 大小对应
- Queue.get([block[, timeout]])获取队列，timeout等待时间
- Queue.get_nowait() 相当Queue.get(False)
- Queue.put(item) 写入队列，timeout等待时间
- Queue.put_nowait(item) 相当Queue.put(item, False)
- Queue.task_done() 在完成一项工作之后，Queue.task_done()函数向任务已经完成的队列发送一个信号
- Queue.join() 实际上意味着等到队列为空，再执行别的操作

``` python
import queue
import threading
import time

exitFlag = 0

class myThread (threading.Thread):
    def __init__(self, threadID, name, q):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.q = q
    def run(self):
        print ("开启线程：" + self.name)
        process_data(self.name, self.q)
        print ("退出线程：" + self.name)

def process_data(threadName, q):
    while not exitFlag:
        queueLock.acquire()
        if not workQueue.empty():
            data = q.get()
            queueLock.release()
            print ("%s processing %s" % (threadName, data))
        else:
            queueLock.release()
        time.sleep(1)

threadList = ["Thread-1", "Thread-2", "Thread-3"]
nameList = ["One", "Two", "Three", "Four", "Five"]
queueLock = threading.Lock()		# 创建锁
workQueue = queue.Queue(10)
threads = []
threadID = 1

# 创建新线程
for tName in threadList:
    thread = myThread(threadID, tName, workQueue)
    thread.start()
    threads.append(thread)
    threadID += 1

# 填充队列
queueLock.acquire()					# 锁定
for word in nameList:
    workQueue.put(word)
queueLock.release()					# 解锁

# 等待队列清空
while not workQueue.empty():
    pass

# 通知线程是时候退出
exitFlag = 1

# 等待所有线程完成
for t in threads:
    t.join()
print ("退出主线程")
```

``` sh
开启线程：Thread-1
开启线程：Thread-2
开启线程：Thread-3
Thread-3 processing One
Thread-1 processing Two
Thread-2 processing Three
Thread-3 processing Four
Thread-1 processing Five
退出线程：Thread-3
退出线程：Thread-2
退出线程：Thread-1
退出主线程
```

## 协程与异步编程

协程，又被称为微线程，在io密集型任务中，能起到很好的作用。

### async | await

在Python中，早期版本有过使用yield、asyncio装饰器等进行协程编写；但在python3.5之后，新增**async**与**await**关键字，也成为官方推荐的异步语法，我们此处只介绍这个。

### 异步方法定义

与常规方法不同的是，异步方法需要有async关键词，代码如下：

```python
async def asd():
    await asyncio.sleep(2)
    return 123
```

**async**是指该方法为一个异步方法，**await**后面跟随一切io操作。 什么叫一切io操作，所有耗费io的比如网络请求、task、future都是io操作，这些io操作全部需要手动执行await来挂起，否则无法执行异步。

> 在异步方法里，执行任何同步模块都会是程序变为同步。

### 异步方法调用

``` python
asyncio.run(asd())
```

run方法里默认创建事件循环。

### 比较异步效果

``` python
# 不使用异步
import time
def asd():
    time.sleep(2)
    print(123)

def asd2():
    time.sleep(2)
    print(456)

def main():
    asd()
    asd2()

start = time.time()
main()
print('程序运行时长：',time.time()-start)
```

``` sh
123
456
程序运行时长： 4.004298210144043
```

``` python
# 使用异步
import time, asyncio
async def asd():
    await asyncio.sleep(2)
    print(123)

async def asd2():
    await asyncio.sleep(2)
    print(456)

async def main():
    task_list = [asyncio.create_task(asd()), asyncio.create_task(asd2())]
    done,pending = await asyncio.wait(task_list)
    
start = time.time()
asyncio.run(main())
print('程序运行时长：',time.time()-start)
```

``` sh
123
456
程序运行时长： 2.002639055252075
```

### 异步的方式执行同步

异步的方法里不能使用同步的模块，否则全部按照同步执行，那么我们在生产中经常要用到不支持异步的模块，难道要放弃大好异步性能吗？答案显然不是的，下面写了一个print_的方法，没有任何逻辑，只是睡眠指定时间，然后打印，很明显是个同步方法，然后我们用手动创建事件循环，然后调用 run_in_executor这个方法即可成功注册为异步方式，第一个参数为执行的线程或进程，不启用多线程的话我们直接传None即可，然后方法名，方法参数。

``` python
# 同步调用
import time, asyncio

def print_(i, y):
    time.sleep(i)
    print('print_', i, y)
    
async def asd():
    await asyncio.sleep(2)
    print_(1, 2)
    
async def asd2():
    await asyncio.sleep(2)
    print_(3, 4)
    
async def main():
    task_list = [asyncio.create_task(asd()), asyncio.create_task(asd2())]
    done,pending = await asyncio.wait(task_list)
    
start = time.time()
asyncio.run(main())
print(time.time()-start)
```

``` sh
print_ 1 2
print_ 3 4
6.0070483684539795
```

可以看到，程序耗时八秒，不难理解，异步方法asd和asd2的sleep时间共享，同步模块print_共调用两次，每次耗时三秒，1+3+2=6。

``` python
# 异步调用
import time, asyncio

def print_(i, y):
    time.sleep(i)
    print('print_', i, y)
    
async def asd():
    await asyncio.sleep(2)
    l = asyncio.get_running_loop()
    future = l.run_in_executor(None, print_, 3, 4)
    await future
    return 123

async def asd2():
    await asyncio.sleep(2)
    l = asyncio.get_running_loop()
    future = l.run_in_executor(None, print_, 3, 5)
    await future
    return 456

async def main():
    task_list = [asyncio.create_task(asd()), asyncio.create_task(asd2())]
    done,pending = await asyncio.wait(task_list)
    
start = time.time()
asyncio.run(main())
print(time.time()-start)
```

``` python
print_ 3 4
print_ 3 5
5.008421421051025
```

耗时5秒，即print_的sleep时间也共享，3+2=5。

### 进程池

run_in_executor的第一个参数为executor，那么这个executor是哪来的呢，就是线程池。代码如下：

``` python
import time, asyncio, concurrent

def print_(i,y):
    time.sleep(i)
    print('print_', i,y)

async def asd():
    await asyncio.sleep(2)
    return 123

async def asd3():
    await asyncio.sleep(2)
    return 456

async def main():
    task_list = [asyncio.create_task(asd()), asyncio.create_task(asd3())]
    done,pending = await asyncio.wait(task_list)

    loop = asyncio.get_running_loop()
    with concurrent.futures.ThreadPoolExecutor() as pool:
        result = await loop.run_in_executor(pool, print_, 3, 4)

start = time.time()
asyncio.run(main())
print(time.time()-start)
```

``` sh
print_ 3 4
5.007253170013428
```

### aiohttp 爬虫异步库

``` python
async def company_detail(path):
    url = path
    proxy = await self.proxy()
    header = {'User-Agent': random.choice(self.user_agent_list),
              'Connection': 'close',
              }
    proxies = f'http://{proxies_user}:{proxies_pass}@{proxy["ip"]}:{proxy["port"]}'
    async with aiohttp.ClientSession(headers=header) as session:
        async with session.get(url=url, headers=header, proxies=proxies, timeout=20) as response:
            if response.status != 200:
                logger.error('返回状态码异常，程序异常退出')
                raise requests.exceptions.ConnectionError
            response_data = await response.text()		# 获取html requests
        data = list_get(re.findall('props = ({.*})', response_data))
        # print(data)
        return data
async def main()
    done = await company_detail()

asyncio.run(main())
```

* **获取html requests**：response.text **aiohttp** `response.text()`
* **获取二进制内容**：requests response.content() **aiohttp** `response.read()`
* **设置代理**：requests {‘http’: …,‘https’:…} **aiohttp** `http://ip:port`

## 数据库编程

Python 标准数据库接口为 Python DB-API，Python DB-API为开发人员提供了数据库应用编程接口。

Python 数据库接口支持非常多的数据库，你可以选择适合你项目的数据库：

- GadFly
- mSQL
- MySQL
- PostgreSQL
- Microsoft SQL Server 2000
- Informix
- Interbase
- Oracle
- Sybase
- ... 还在扩展

不同的数据库你需要下载不同的DB API模块，例如你需要访问Oracle数据库和Mysql数据，你需要下载Oracle和MySQL数据库模块。

DB-API 是一个规范. 它定义了一系列必须的对象和数据库存取方式, 以便为各种各样的底层数据库系统和多种多样的数据库接口程序提供一致的访问接口 。

Python的DB-API，为大多数的数据库实现了接口，使用它连接各数据库后，就可以用相同的方式操作各数据库。

Python DB-API使用流程：

1. 引入 API 模块。
2. 获取与数据库的连接。
3. 执行SQL语句和存储过程。
4. 关闭数据库连接。

### MySQL

MySQLdb 是用于Python链接Mysql数据库的接口，它实现了 Python 数据库 API 规范 V2.0，基于 MySQL C API 上建立的。

安装MySQLdb，请访问 http://sourceforge.net/projects/mysql-python ，(Linux平台可以访问：https://pypi.python.org/pypi/MySQL-python)从这里可选择适合您的平台的安装包，分为预编译的二进制文件和源代码安装包。

选择二进制文件发行版本，安装过程基本安装提示即可完成。如果从源代码进行安装的话，则需要切换到MySQLdb发行版本的顶级目录，并键入下列命令：

``` sh
$ gunzip MySQL-python-1.2.2.tar.gz
$ tar -xvf MySQL-python-1.2.2.tar
$ cd MySQL-python-1.2.2
$ python setup.py build
$ python setup.py install
```

### 数据库连接

连接数据库前，请先确认以下事项：

- 您已经创建了数据库 TESTDB.
- 在TESTDB数据库中您已经创建了表 EMPLOYEE
- EMPLOYEE表字段为 FIRST_NAME, LAST_NAME, AGE, SEX 和 INCOME。
- 连接数据库TESTDB使用的用户名为 "testuser" ，密码为 "test123",你可以可以自己设定或者直接使用root用户名及其密码，Mysql数据库用户授权请使用Grant命令。
- 在你的机子上已经安装了 Python MySQLdb 模块。
- 如果您对sql语句不熟悉，可以访问runoob的 [SQL基础教程](https://www.runoob.com/sql/sql-tutorial.html)

连接Mysql的TESTDB数据库：

``` python
import MySQLdb

# 打开数据库连接
db = MySQLdb.connect("localhost", "testuser", "test123", "TESTDB", charset='utf8' )

# 使用cursor()方法获取操作游标 
cursor = db.cursor()

# 使用execute方法执行SQL语句
cursor.execute("SELECT VERSION()")

# 使用 fetchone() 方法获取一条数据
data = cursor.fetchone()

print "Database version : %s " % data

# 关闭数据库连接
db.close()
```

``` sh
Database version : 5.0.45
```

### 创建数据库表

数据库连接存在我们可以使用execute()方法来为数据库创建表，如下所示创建表EMPLOYEE：

``` python
import MySQLdb

# 打开数据库连接
db = MySQLdb.connect("localhost", "testuser", "test123", "TESTDB", charset='utf8' )

# 使用cursor()方法获取操作游标 
cursor = db.cursor()

# 如果数据表已经存在使用 execute() 方法删除表。
cursor.execute("DROP TABLE IF EXISTS EMPLOYEE")

# 创建数据表SQL语句
sql = """CREATE TABLE EMPLOYEE (
         FIRST_NAME  CHAR(20) NOT NULL,
         LAST_NAME  CHAR(20),
         AGE INT,  
         SEX CHAR(1),
         INCOME FLOAT )"""

cursor.execute(sql)

# 关闭数据库连接
db.close()
```

### 数据库插入操作

``` python
import MySQLdb

# 打开数据库连接
db = MySQLdb.connect("localhost", "testuser", "test123", "TESTDB", charset='utf8' )

# 使用cursor()方法获取操作游标 
cursor = db.cursor()

# SQL 插入语句
sql = """INSERT INTO EMPLOYEE(FIRST_NAME,
         LAST_NAME, AGE, SEX, INCOME)
         VALUES ('Mac', 'Mohan', 20, 'M', 2000)"""
try:
   # 执行sql语句
   cursor.execute(sql)
   # 提交到数据库执行
   db.commit()
except:
   # Rollback in case there is any error
   db.rollback()

# 关闭数据库连接
db.close()
```

``` python
import MySQLdb

# 打开数据库连接
db = MySQLdb.connect("localhost", "testuser", "test123", "TESTDB", charset='utf8' )

# 使用cursor()方法获取操作游标 
cursor = db.cursor()

# SQL 插入语句
sql = "INSERT INTO EMPLOYEE(FIRST_NAME, \
       LAST_NAME, AGE, SEX, INCOME) \
       VALUES (%s, %s, %s, %s, %s )" % \
       ('Mac', 'Mohan', 20, 'M', 2000)
try:
   # 执行sql语句
   cursor.execute(sql)
   # 提交到数据库执行
   db.commit()
except:
   # 发生错误时回滚
   db.rollback()

# 关闭数据库连接
db.close()
```

### 数据库查询操作

Python查询Mysql使用 fetchone() 方法获取单条数据, 使用fetchall() 方法获取多条数据。

- **fetchone():** 该方法获取下一个查询结果集。结果集是一个对象
- **fetchall():**接收全部的返回结果行.
- **rowcount:** 这是一个只读属性，并返回执行execute()方法后影响的行数。

``` python
# 查询EMPLOYEE表中salary（工资）字段大于1000的所有数据
import MySQLdb

# 打开数据库连接
db = MySQLdb.connect("localhost", "testuser", "test123", "TESTDB", charset='utf8' )

# 使用cursor()方法获取操作游标 
cursor = db.cursor()

# SQL 查询语句
sql = "SELECT * FROM EMPLOYEE \
       WHERE INCOME > %s" % (1000)
try:
   # 执行SQL语句
   cursor.execute(sql)
   # 获取所有记录列表
   results = cursor.fetchall()
   for row in results:
      fname = row[0]
      lname = row[1]
      age = row[2]
      sex = row[3]
      income = row[4]
      # 打印结果
      print "fname=%s,lname=%s,age=%s,sex=%s,income=%s" % \
             (fname, lname, age, sex, income )
except:
   print "Error: unable to fetch data"

# 关闭数据库连接
db.close()
```

``` sh
fname=Mac, lname=Mohan, age=20, sex=M, income=2000
```

### 数据库更新操作

``` python
# 更新操作用于更新数据表的的数据，以下实例将 EMPLOYEE 表中的 SEX 字段为 'M' 的 AGE 字段递增 1

import MySQLdb

# 打开数据库连接
db = MySQLdb.connect("localhost", "testuser", "test123", "TESTDB", charset='utf8' )

# 使用cursor()方法获取操作游标 
cursor = db.cursor()

# SQL 更新语句
sql = "UPDATE EMPLOYEE SET AGE = AGE + 1 WHERE SEX = '%c'" % ('M')
try:
   # 执行SQL语句
   cursor.execute(sql)
   # 提交到数据库执行
   db.commit()
except:
   # 发生错误时回滚
   db.rollback()

# 关闭数据库连接
db.close()
```

### 数据库删除操作

``` python
# 删除操作用于删除数据表中的数据，以下实例演示了删除数据表 EMPLOYEE 中 AGE 大于 20 的所有数据
import MySQLdb

# 打开数据库连接
db = MySQLdb.connect("localhost", "testuser", "test123", "TESTDB", charset='utf8' )

# 使用cursor()方法获取操作游标 
cursor = db.cursor()

# SQL 删除语句
sql = "DELETE FROM EMPLOYEE WHERE AGE > %s" % (20)
try:
   # 执行SQL语句
   cursor.execute(sql)
   # 提交修改
   db.commit()
except:
   # 发生错误时回滚
   db.rollback()

# 关闭连接
db.close()
```

### 执行事务

事务机制可以确保数据一致性。

事务应该具有4个属性：原子性、一致性、隔离性、持久性。这四个属性通常称为ACID特性。

- 原子性（atomicity）。一个事务是一个不可分割的工作单位，事务中包括的诸操作要么都做，要么都不做。
- 一致性（consistency）。事务必须是使数据库从一个一致性状态变到另一个一致性状态。一致性与原子性是密切相关的。
- 隔离性（isolation）。一个事务的执行不能被其他事务干扰。即一个事务内部的操作及使用的数据对并发的其他事务是隔离的，并发执行的各个事务之间不能互相干扰。
- 持久性（durability）。持续性也称永久性（permanence），指一个事务一旦提交，它对数据库中数据的改变就应该是永久性的。接下来的其他操作或故障不应该对其有任何影响。

``` python
# SQL删除记录语句，事务提供了两个方法 commit 或 rollback
sql = "DELETE FROM EMPLOYEE WHERE AGE > %s" % (20)
try:
   # 执行SQL语句
   cursor.execute(sql)
   # 向数据库提交
   db.commit()
except:
   # 发生错误时回滚
   db.rollback()
```

对于支持事务的数据库， 在Python数据库编程中，当游标建立之时，就自动开始了一个隐形的数据库事务。

commit()方法游标的所有更新操作，rollback（）方法回滚当前游标的所有操作。每一个方法都开始了一个新的事务。

### 错误与异常

| 错误与异常        | 描述                                                         |
| :---------------- | :----------------------------------------------------------- |
| Warning           | 当有严重警告时触发，例如插入数据是被截断等等。必须是 StandardError 的子类。 |
| Error             | 警告以外所有其他错误类。必须是 StandardError 的子类。        |
| InterfaceError    | 当有数据库接口模块本身的错误（而不是数据库的错误）发生时触发。 必须是Error的子类。 |
| DatabaseError     | 和数据库有关的错误发生时触发。 必须是Error的子类。           |
| DataError         | 当有数据处理时的错误发生时触发，例如：除零错误，数据超范围等等。 必须是DatabaseError的子类。 |
| OperationalError  | 指非用户控制的，而是操作数据库时发生的错误。例如：连接意外断开、 数据库名未找到、事务处理失败、内存分配错误等等操作数据库是发生的错误。 必须是DatabaseError的子类。 |
| IntegrityError    | 完整性相关的错误，例如外键检查失败等。必须是DatabaseError子类。 |
| InternalError     | 数据库的内部错误，例如游标（cursor）失效了、事务同步失败等等。 必须是DatabaseError子类。 |
| ProgrammingError  | 程序错误，例如数据表（table）没找到或已存在、SQL语句语法错误、 参数数量错误等等。必须是DatabaseError的子类。 |
| NotSupportedError | 不支持错误，指使用了数据库不支持的函数或API等。例如在连接对象上 使用.rollback()函数，然而数据库并不支持事务或者事务已关闭。 必须是DatabaseError的子类。 |

# Python 高级

## Web开发

### Flask 和 Django

### HTML、CSS 和 JavaScript

### RESTful API 和 Websockets

### 数据库集成

### 部署和维护

## 数据分析与机器学习

### NumPy、Pandas 和 Matplotlib

一个范例（热力图）

``` python
import pandas as pd
# import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

plt.rcParams['font.family'] = 'monospace'
plt.rcParams['font.sans-serif'] = ['Tahoma']
plt.rcParams['font.size'] = 9
plt.rcParams['axes.unicode_minus'] = False
# plt.style.use('ggplot')
plt.yticks(fontsize=10)

# pstore = pd.read_csv("heatmapcsv.csv").transpose()	# 读取数据并翻转90°
pstore = pd.read_csv("heatmapcsv.csv", index_col = 0)

sns.heatmap(pstore, cmap="GnBu", annot=True, vmin=0, vmax=1 ,yticklabels=1)
plt.show()
```

### 数据清洗和数据分析

### 机器学习算法和模型

### TensorFlow 、Keras 和 Scikit-learn

### 自然语言处理

### 图像与人脸识别

## 爬虫

## 游戏开发

### Pygame

### 2D 游戏和 3D 游戏

### 物理引擎和碰撞检测
