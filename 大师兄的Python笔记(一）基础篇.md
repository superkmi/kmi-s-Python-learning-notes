## 一、在开始之前
##### 1. 一些常见问题
- 应该学习一种语言还是多种语言？
>在精通一种语言的基础上掌握得越多越好。

- 应该学习哪种编程语言？
>工具箱里有各种工具，每种工具都有各自的用途。

- 学习Python可以做什么？
>- Python就像工具箱里的瑞士军刀，基本什么都能做。
>- 目前Python在自动化运维、Web开发、爬虫、人工智能、机器学习和数据分析领域应用的比较多。

- Python的优点是什么？
>- 语言优雅、明确、简单。
>- 开发效率高: Python的第三方库超级强大，Github上有很多开源代码。
>- 高级语言：不用过多考虑底层细节
>- 可移植性：基本所有平台都可以使用，而且不会有太大的区别（还是有部分区别，比如fork()）
>- 可扩展性：存在许多使用 C 语言或 Fortran 编写扩展的方法。
>- 可嵌入型：可以把Python嵌入C/C++程序，从而向程序用户提供脚本功能。

- Python的缺点是什么？
>- 相比C语言和Java速度慢（对于计算机来说），除非要求极高，一般感觉不到。
>- 全局解释器锁GIL(Global Interpreter Lock)导致线程不能利用多CPU，有一些变通的解决方案。

- 应该学习Python2还是Python3?
>- Python2和Python3版本语法不兼容，创始人 Guido van Rossum表示Python2将更新至2020年。所以除非有特殊需求，学习最新版本肯定是没错的。
>- 截止本文发布，目前最新版本是Python3.8.0。

##### 2. 环境搭建
>Python是一门解释型语言，我们需要先把写完的代码编译成计算机能看懂的语言(字节码 bytes)，才能交给它执行,所以需要安装编译器(complier)。这里推荐两种方式二选一：
>- 方式一：直接安装python3: [Python下载](https://www.python.org/)、 [安装教程](https://www.runoob.com/python3/python3-install.html)
>- 方式二：安装Anaconda，Anaconda内置了Python编译器和很多工具: [下载Anaconda](https://www.anaconda.com/) 、[安装教程](https://blog.csdn.net/ITLearnHall/article/details/81708148)
##### 3. 开发工具推荐
> 我们需要用开发工具来编写代码，比较常用的开发工具包括:[Pycharm](http://www.jetbrains.com/pycharm/)、[Sublime](https://www.sublimetext.com/)、[Eclipse](https://www.eclipse.org/downloads/)等，个人推荐用Pycharm。另外，Jupyter Notebook也是一款非常好用的工具，推荐安装。
>- [Pycharm Community下载](http://www.jetbrains.com/pycharm/)、[安装教程](https://www.runoob.com/w3cnote/pycharm-windows-install.html)、[使用教程](https://blog.csdn.net/zhusongziye/article/details/79069233)
>- [Jupyter Notebook](https://jupyter.org/)、[安装教程](https://www.jianshu.com/p/87ed39c4e01b)
##### 4.  入门书籍推荐
>- [《Python学习手册》](http://product.dangdang.com/25576578.html)
>- [《Python编程 从入门到实践》](http://product.dangdang.com/24003310.html)
##### 5. 关于缩进
>- Python对缩进要求非常严格,相同逻辑层保持相同的缩进。
>- 在Pycharm中，可以使用TAB键进行缩进，用Shift+TAB键取消缩进。
>```
># 实例:
>a = 0 # 第一层
>def func():
>    b = 1 # 第二层
>    def printf():
>        print(b) # 第三层
>    printf()
>func()
>```
##### 6. 命名规范
###### 6.1 命名规范
>命名应当尽量使用全拼写的单词：
>- 包、文件名: 全小写，可以使用下划线 
>```例：my_file.py```
>- 类名: 大驼峰
>```例：MyClass```
>- 函数名: 小驼峰  
>```例：myFunction```
>- 变量：全小写，可以采用POSIX命名习惯
>```例: my_variable```
>- 常量: 全大写，可以采用POSIX命名习惯
>```例: MAX_LENGTH```

###### 6.2 关于名字中的下划线_
>- 名字前面一个_表示保护变量(protected) : 
>例：```_name```
>- 名字前面两个_表示内部使用(private):
>例：```__name```
>- 名字前后各两个_表示魔法函数/语法糖:
>例：```__init__```
>- 名字末尾一个_用来解决命名冲突
>例：```name_```
>- 单独一个_表示不重要或无意义变量
>例：```_```
###### 6.3 需要避免的命名 
>- **不要**用类型名称命名
>```例: name_list(错误用法!）```
>- **不要**用以下关键词命名:
>```
>False class  from                or
>None                continue            global              pass
>True                def                 if                  raise
>and                 del                 import              return
>as                  elif                in                  try
>assert              else                is                  while
>async               except              lambda              with
>await               finally             nonlocal            yield
>break               for                 not 
>```
##### 7. 一些马上要用到的函数
###### 7.1 print()函数
>- print()用于打印输出，是最常用的函数之一。
>- 语法：print(<对象>)
>###### 1）打印字符串
>```
>>>>print('Hello World!')
>Hello World!
>```
>###### 2）打印整数
>```
>>>>print(123456)
>123456
>```
>###### 3）打印多个字符串
>```
>>>>print('Hello''World')
>HelloWorld
>>>>print('Hello','World')
>Hello World
>```
>###### 4）打印间隔符
>```
>>>>print('www','baidu','com',sep='.')
>www.baidu.com
>```
###### 7.2 help()函数
> - help函数用于查看函数或模块用途的详细说明。
> - help是获得帮助最直接的方式，但内容为全英文。
>- 语法: help(<对象>）
>```
>>>>help(print)
>Help on built-in function print in module builtins:
>
>print(...)
>    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
>    
>    Prints the values to a stream, or to sys.stdout by default.
>    Optional keyword arguments:
>    file:  a file-like object (stream); defaults to the current sys.stdout.
>    sep:   string inserted between values, default a space.
>    end:   string appended after the last value, default a newline.
>    flush: whether to forcibly flush the stream.
>```
###### 7.3 type()函数
> - type()函数用于查看对象的类型。
>- 语法: type(<对象>)
>```
>>>>i = 1
>>>>print(type(help))
><class 'int'>
>```
##### 8. 关于注释
>注释是给自己和其他程序员看的内容。
###### 8.1 注释方法
>- \# 单行注释
>``` 
>#这里是单行注释
>```
>- ''' ''' 或 """ """ 多行注释
>```
>'''这里
>         是
>             多行
>                     注释'''
>```
###### 8.2 注释规则
>- 注释越少越好，简单的代码不要注释
>- 对于复杂的操作，应该在操作开始前写上若干行注释
>- 对于不是一目了然的代码，应在其行尾添加注释（为了提高可读性，注释应该至少离开代码 2 个空格）
>- 绝不要描述代码，假设阅读代码的人比你更懂 Python，他只是不知道你的代码要做什么
## 二、语法基础
##### 1. 变量
>- 变量用来存储值，通过访问变量可以访问值。
>- 变量是所有编程语言的基础，python变量属于弱类型，在创建变量时不需要声明变量类型。
>-  单“=” 在python中是赋值运算符。
> ###### 1）变量赋值语法如下:
>```
><变量名> = <变量值>
>```
>```
>>>>i = 1
>>>>print(i)
>1
>```
> ###### 2）为多个变量同时赋值：
>```
>>>>a,b = 1,2
>>>>print(a,b)
>1 2
>```
> ###### 3）两个变量交换值:
>```
>>>>a,b = 1,2
>>>>a,b = b,a
>>>>print(a,b)
>2 1
>```
###### 1.1 变量类型：数字
>###### 1) int 整形
>- int就是整数。
>- 可以是十进制、二进制、八进制、十六进制。
>- print(<int>)时，会自动换算到十进制。
>```
># 十进制数字
>>>>i = 1
>>>>print(i)
>1
>>>>print(type(i))
><class 'int'>
>```
>```
># 二进制数字
>>>>i = 0b1101 # 0b代表二进制
>>>>print(i) # print二进制数字时，会自动换算成十进制
>13
>>>>print(type(i))
><class 'int'>
>```
>```
> # 八进制数字  
> i = 0o427 # 0o代表八进制
>>>>print(i) # print八进制数字时，会自动换算成十进制
>279
>>>>print(type(i))
><class 'int'>
>```
>```
> # 十六进制数字  
> >>>i = 0xE1FF # 0x代表十六进制
>>>>print(i) # print十六进制数字时，会自动换算成十进制
>57855
>>>>print(type(i))
><class 'int'>
>```
>###### 2) float 浮点数
>```
>>>>f = 1.2
>>>>print(f)
>1.2
>>>>print(type(f)
><class 'float'>
>
> # 也可以用科学计数法表示
>>>>e = 2.4e2
>>>>print(e) 
>240
>>>>print(type(e)
><class 'float'>
>```
>###### 3) complex 复数
>```
>>>>x = 1 + 5j
>>>>print(x)
>(1+5j)
>>>>print(type(x))
><class 'complex'>
>```
>###### 4) bool 布尔值
>True与1等值，False与0等值

###### 1.2 变量类型：bool 布尔值
>- bool只有True和False两个值
>- True与1等值，False与0等值。
>```
>>>>a = True
>>>>print(type(a))
><class 'bool'>
>
>>>>print(a == 1) # 说明True和1相等
>True
>
>>>>b = 0
>>>>print(type(b))
><class 'int'>
>
>>>>print(b == False) # 说明False和0相等
>True
>```
###### 1.3 变量类型：string 字符串
> - 字符串就是文字类型
> - 字符串的形式:```'<str>'```
> - string可以切片
>```
>>>>str = 'Hello World!'
>>>>print(str)
>'Hello World!'
>>>>print(type(str))
><class 'str'>
>
>>>>str = '9'
>>>>print(str)
>'9'
>>>>print(type(str))
><class 'str'>
>```
###### 1.4 变量类型：列表 list
> - 列表是由一个或多个值组成的序列
> - 列表的形式:```[<l1>,<l2>,<l3>]```
> - 列表的值可以是任何类型
> - 列表有顺序，有序号
> - 列表可以嵌套
>```
>>>>l = [1,'hello',0.5]
>>>>print(l)
>[1, 'hello', 0.5]
>>>>print(type(l))
><class 'list'>
>```
###### 1.5 变量类型：元组 tuple 
>- 元组和list类似，区别是内容不可修改。
>- 元组的形式:```(<t1>,<t2>,<t3>)```
>```
>>>>tup = (1,'hello',0.5)
>>>>print(tup)
>(1,'hello',0.5)
>>>>print(type(tup))
><class 'tuple'>
>``` 
###### 1.6 字典 dict 
>- 字典是一种组合数据，包含一个或多个键(key)和值(value)的配对, key和value必须配对出现。
>- dict的key值必须是不可变的数据类型，而value值的数据类型可以是任意类型
>- 字典的形式：```{<key1>:<value1>,<key2>:<value2>}```
>- 字典没有顺序
>- 字典可以嵌套
>```
>>>>dict = {'name':'qq','age':1,'type':'雪纳瑞'}
>>>>print(dict)
>{'name': 'qq', 'age': 1, 'type': '雪纳瑞'}
>>>>print(type(dict))
><class 'dict'>
>```
###### 1.7 集合 set 
> - 集合是一组无序且不重复的值
> - 集合的形式:```{s1,s2,s3}```
> - 集合的值只能是可以hash的值，比如:str, int, float, tuple,冰冻集合等
>```
># set是内容的集合，内容不能重复
>>>>a = {'雪纳瑞','贵宾','柯基','拉布拉多'}
>>>>print(a)
>{'柯基', '贵宾', '拉布拉多', '雪纳瑞'}
>>>>print(type(a))
><class 'set'>
>```
###### 1.8 None
>None是一个空值，所以也是一个值。
>```
>>>>n = None
>>>>print(n)
>None
>>>>print(type(n))
><class 'NoneType'>
>```
##### 2. 运算符
###### 2.1 算数运算符
>- 进行算数运算的符号
>- 包括: +   -   *   /   %   **   //
>- Python没有自增自减运算符。
>```
>>>>a = 1 + 2 #加法
>>>>print(a)
>3
>
>>>>a = 2 - 1 #减法
>>>>print(a)
>1
> 
>>>>a = 2 * 2 #乘法
>>>>print(a)
>4
>
>>>>a = 9 / 3 # 除法
>>>>print(a)
>3
>
>>>>a = 9 // 4 #取商
>>>>print(a)
>2
>
>>>>a = 9 % 4 #取余
>>>>print(a)
>1
>
>>>>a = 10 ** 2 #幂运算
>>>>print(a)
>100
>``` 
###### 2.2 比较运算符
> - 对两个变量或值进行比较的运算符，包括: ==   !=   >   <   >=   <=
> - 比较的结果一定是布尔值: True / False
>```
>>>>a = 10 == 10 #相等
>>>>print(a)
>True
>
>>>>a = 10 != 10 #不相等
>>>>print(a)
>False
>
>>>>a = 1 > 2 #大于
>>>>print(a)
>False
>
>>>>a = 1 < 2 #大于
>>>>print(a)
>True
>
>>>>a = 1 >= 1 #大于等于
>>>>print(a)
>True
>
>>>>a = 1 <= 2 #小于等于
>>>>print(a)
>True
>```
###### 2.3 赋值运算符
>```
>>>>a = 'hello' #赋值
>>>>print(a)
>'hello'
>
>>>>a = 0
>>>>a += 1 # 是a = a + 1 的缩写,所有的数学运算符都有缩写形式
>>>>print(a)
>1
>>>>a += 1
>>>>print(a)
>2
>```
###### 2.4 位运算符
>- 二进制换位运算，包括：&   |   ^   ~   <<   >>
>- 涉及到二进制计算，初学者可以跳过。
>```
>>>>a = 0b01001101 # 二进制数字
>>>>b = 0b00100100
>
>>>>c = a & b #按位与运算符：参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0
>>>>print(bin(c)) #打印二进制数字
>0b100
>
>>>>c = a | b #按位或运算符：只要对应的二个二进位有一个为1时，结果位就为1。
>>>>print(bin(c))
>0b1101101
>
>>>>c = a ^ b #按位异或运算符：当两对应的二进位相异时，结果为1。
>>>>print(bin(c))
>0b1101001
>
>>>>c = ~ a #按位取反运算符：对数据的每个二进制位取反,即把1变为0,把0变为1。
>>>>print(bin(c))
>-0b1001110
>
>>>>c = a << 2 #左移动运算符：运算数的各二进位全部左移若干位，由 << 右边的数字指定了移动的位数，高位丢弃，低位补0。
>>>>print(bin(c))
>0b100110100
>
>>>>c = a >> 2 #右移动运算符：把">>"左边的运算数的各二进位全部右移若干位，>> 右边的数字指定了移动的位数
>>>>print(bin(c))
>0b10011
>```
###### 2.5 逻辑运算符
>- 对布尔值进行计算的符号
>- 包括：and(与，可以看作乘法）、or(或，可以看作加法）、not（非）
>- 比如: True and False = 1 * 0  = 0 = False
>```
>>>>a = True # 可以看做1
>>>>b = False # 可以看做0
>
>>>>c = a and b # 与，也可以看做乘法
>>>>print(c)
>False
>
>>>>c = a or b # 或，也可以看做加法
>>>>print(c)
>True
>
>>>>c = not a # 非
>>>>print(c)
>False
>```
###### 2.6 成员位运算符
>用来检测某一个变量是否是另一个变量的成员,包括:in（包含） 和 not in（不包含）
>```
>>>>a = [1,2,3,4,5] #列表
>>>>b = 2
>>>>c = 6
>
>>>>d = b in a # 是否包含
>>>>print(d)
>True
>
>>>>d = c not in a # 是否不包含
>>>>print(d)
>True
>```
###### 2.7 身份运算符
>- 用来检测两个变量的值是否相等
>- 包含:is 和 is not
>```
>>>>a = 1
>>>>b = 1
>
>>>>c = a is b # 判断是同一个变量
>>>>print(c)
>True
>
>>>>c = a is not b # 判断不是同一个变量
>>>>print(c)
>False
>```
###### 2.8 运算符的优先级
>标识|备注
>:--:|:--:
>( ) | 最高优先级
>** |指数
>\~ + -   |按位翻转, 一元加号和减号 (最后两个的方法名为 +@ 和 -@)
>\* / % //    |乘，除，取模和取整除
>\+ - |加法减法
>\>> <<   |右移，左移运算符
>&   |位 'AND'
>^ \| |位运算符
><= < > >=   |比较运算符
> \<> == !=    |等于运算符
>= %= /= //= -= += *= **=    |赋值运算符
>  is、is not   |身份运算符
>  in、not in  | 成员运算符
>  not、or、and  |逻辑运算符
##### 3. 程序结构
>Python程序包含三种结构: **顺序、分支和循环**
###### 3.1 顺序结构
>顺序结构是按照从上到下一行一行的顺序执行，是Python最基本的程序结构。
###### 3.2 分支结构
>分支结构根据条件判断选择一路执行。
>###### 1）单向分支: if 语句
>```
>if <条件表达式>:  #如果条件表达式为True则执行后面语句，条件表达式后面一定要有冒号
>    <语句> #这里一定要有缩进!
>
>if age > 18:
>    print('你已经是成年人了。') 
>```
>###### 2）双向分支：if ... else... 语句
>```
>if <条件表达式>:  #如果条件表达式为True则执行后面语句，条件表达式后面一定要有冒号
>    <语句1> #这里一定要有缩进!
>else: #如果条件表达式为False则执行else后面的语句
>    <语句2> #这里一定要有缩进！
>```
>```
>if age > 18:
>    print('你已经是成年人了。') 
>else:
>    print('你还没有成年。')
>```
>###### 3.3）多路分支: if ...elif ... else 语句
>```
>if <条件表达式>:  #如果条件表达式为True则执行后面语句，条件表达式后面一定要有冒号
>    <语句1> #这里一定要有缩进!
>elif <条件表达式>: #如果条件表达式为True则执行后面语句，elif可以有多个
>    <语句2>
>else: #如果前面的条件表达式全部为False则执行else后面的语句
>    <语句3> #这里一定要有缩进！
>```
>```
>if age > 18:
>    print('你是成年人了。') 
>elif age >= 15:
>    print('你已经超过15岁了。')
>elif age >= 10:
>    print('你已经超过10岁了。')
>else:
>    print('你还不到10岁。')
>```
##### 4. 循环结构
>重复执行某些固定动作或者处理基本固定的事物,包括:
>- for循环
>- while循环
###### 4.1 for循环
>- for循环有明确的循环次数。
>- range(start,stop,steps)函数表示一个范围的整数,例：```range(1,10,1)```表示从1-9。
>- steps表示步长。
>```
>for <变量> in <序列>:
>     <语句>    #这里必须有缩进
>```
>```
>>>>j = 0
>>>>for i in range(0,5):
>>>>  j += 1
>>>>print(j)
>4
>
>>>>for i in range(0,50,10):
>>>>  print(i)
>0
>10
>20
>30
>40
>
>>>>str = 'Hello'
>>>>for s in str:
>>>>  print(s)
>'H'
>'e'
>'l'
>'l'
>'o'
>
>>>>list = ['banana','apple','grape']
>>>>for l in list:
>>>>  print(l)
>'banana'
>'apple'
>'grape'
>
>>>>dict = {1:'雪纳瑞',2:'贵宾',3:'柯基'}
>>>>for k in dict:
>>>>  print(k,dict.get(k))
>1 '雪纳瑞'
>2 '贵宾'
>3 '柯基'
>
>>>>tp = ((1,2,3),(2,3,4),(5,6,7))
>>>>for a,b,c in tp:
>>>>  print(a,b,c)
>1 2 3
>2 3 4
>5 6 7
>```
###### 4.2 for...else...语句
>- for循环完成后会执行后面的else语句
>- 如果循环被中断，else就不会执行
>```
>>>>j = 0
>>>>for i in range(0,5):
>>>>  j += 1
>>>>else:
>>>>  print(j)
>4
>
>>>>j = 0
>>>>for i in range(0,5):
>>>>  j += 1
>>>>  break # 中断循环
>>>>else: 
>>>>  print(j) # 这里不会被执行
>```
###### 4.3 while 循环
>- while循环没有明确的循环次数，只要条件满足就会一直循环
>```
>while <条件表示式>:
>    <语句> #缩进
>```
>```
>>>>i = 1
>>>>while i < 5:
>>>>  print(i)
>>>>  i += 1
>1
>2
>3
>4
>
>>>>while True: # 这是个死循环
>>>>  print('Hello World!)
>```
###### 4.4 while...else...语句
>同for...else...语句
>```
>>>>i = 1
>>>>while i < 5:
>>>>  i += 1
>>>>else:
>>>>  print(i)
>5
>```
###### 4.5 break,continue和pass
>###### 1）break：跳出一层循环
>```
>>>>for i in range(0,10):
>>>>   print('Hello World!')
>>>>   if i == 2:
>>>>      break # 这里i到2就跳出循环，不会执行之后的循环
> 'Hello World!'
>'Hello World!'
>
># 如果要跳出多层循环，就需要多次break
>>>>a = 0
>>>>for i in range(0,10):
>>>>    for j in range(0,10):
>>>>         a += 1 
>>>>         if j == 5:
>>>>           break  # 这里跳出里面一层的循环，但是会继续执行外面的循环
>>>>    if i == 6:
>>>>        break  # 这里跳出外面一层的循环
>>>>print(a)
>42
>```
>###### 2）continue: 结束本次循环，并开始下一轮循环
>```
>>>>i = 0
>>>>while i < 5:
>>>>  if i == 3:
>>>>    continue # 当i为3时跳过一次循环
>>>>  print(i)
>0
>1
>2
>4
>```
>###### 3）pass: 占位符
>```
>>>>for i in range(1,5):
>>>>  pass   # 有占位符，即使循环内没有语句也可以执行
>
>>>>for i in range(1,2):
>>>>  pass
>>>>  print('Hello World!') # pass后面的内容会执行
>'Hello World!'
>'Hello World!'
>```
##### 5. 函数
>- 函数是一种代码的组织形式。
>- 一个函数通常完成一项功能。
>- 调用函数前需要先定义。
>- 函数可以嵌套。
>- 函数让代码可以重复使用，减少代码量。
>- 函数可以将编程工作分解，便于扩展和修改。
>- 函数让代码变得更具一致性。
###### 5.1 定义函数
>- 定义函数并不会调用执行
>- 调用函数使用def关键字
>- 请再看一下前面的命名规则
>- 可以定义参数
>- 函数内代码必须缩进
>```
>def <函数名>(<参数>): #参数可以为空
>    <代码>
>```
>```
>>>>def printInput(): 
>>>>  print('HelloWorld!')
>```
###### 5.2 调用函数
>- 用```<函数名>(<参数>)```调用函数
>- 调用函数后函数内的程序开始按执行。
>```
>>>>def printInput():
>>>>  print('Hello World!')
>>>>printInput() # 这里调用函数
>'Hello World!'
>```
###### 5.3 参数传递
>###### 1）普通参数
>- 用于传递必要的数据或信息给函数。
>- 调用时需要按顺序传入参数。
>```
>>>>def printInput(s1,s2): #定义函数时包含参数s
>>>>  print(s1,s2) #在代码中调用参数
>>>>printInput('Hello','World!') #调用时这里必须传入参数，不然会报错。
>'Hello World!'
>```
>###### 2）关键字参数
>- 调用时需要指定参数名。
>- 调用时可以忽略传入顺序。
>```
>>>>def printInput(s1,s2): #定义函数时包含参数s
>>>>  print(s1,s2) #在代码中调用参数
>>>>printInput(s2='Hey!',s1='You!) # 调用时不需要按照顺序传入参数
>'You! Hey!'
>```
>###### 3）默认参数
>- 给参数赋一个默认值。
>- 如果不传入参数，将用默认值代替参数。
>```
>>>>def printInput(s='Hey'): #定义函数时包含,定义了参数s的默认值
>>>>  print(s) #在代码中调用参数
>>>>printInput() # 如果不传入参数，将调用默认参数
>>>>printInput('Hello World!') # 如果传入参数，将替代默认参数
>'Hey'
>'Hello World!'
>```
>###### 4）收集参数
>- 参数前加*。
>- 把没有位置、不能和定义时的参数位置相对应的参数，放入一个特定的数据结构中。
>```
>>>>def printInput(*str): # 定义一个不定长参数。 
>>>>  for s in str:  #这里调用的参数是一个tuple
>>>>    print(s)
>>>>printInput('Hello','Python','World!') # 这里传入的是3个参数
>'Hello'
>'Python'
>'World!'
>```
>###### 5）关键字收集参数
>- 参数前加**。
>- 把关键字参数按字典格式存入收集参数。
>```
>>>def printInput(**str): # 定义一个不定长参数。 
>>>  for s in str:  #这里调用的参数是一个dict
>>>    print(str.get(s))
>>>printInput(var1='Hello',var2='Python',var3='World!') # 这里传入的是3个参数
>'Hello'
>'Python'
>'World!'
>```
>###### 6）匿名参数
>- 为lambda表达式传入参数
>-  lambda表达式可以以后再理解。
>```
>>>>str = lambda arg1,arg2: arg1+arg2 #这里定义了一个lambda表达式
>>>>print(str(‘Hello’,'World!')) #将参数传入了表达式
>Hello World!
>```
>###### 7）参数混合调用顺序
>- 收集参数，关键字参数，普通参数可以混合使用。
>- 参数顺序: 普通参数 > 关键字参数 > 收集参数 > 关键字收集参数
>```
>>>>def printInput(s1,*args,s2='None',**kargs):
>>>>    print('参数s1:',s1)
>>>>    print('参数s2:',s2)
>>>>    print('参数*args包括:',[x for x in args])
>>>>    print('参数**kargs包括:',{v : k for k,v in kargs.items() })
>>>>printInput('Hello','Python','I','love','Python',s2='World!',s3='Java',s4='C++',s5='JS')
>参数s1: Hello
>参数s2: World!
>参数*args包括: ['Python', 'I', 'love', 'Python']
>参数**kargs包括: {'Java': 's3', 'C++': 's4', 'JS': 's5'}
>```
###### 5.4 返回值
>- 为函数返回一个结果值
>- 使用return关键字
>- 如果没有return,默认在函数结尾 return None
>- 一旦执行return,则结束函数的执行
>```
>>>>def printInput():
>>>>  return "Hello World!" # 这里为函数返回结果
>>>>  x = 1  # 注意！这里不会被执行
>>>>print(printInput()) # 这里直接调用了函数的返回值
>"Hello World!"
>```
###### 5.5 局部变量和全局变量
>变量由作用范围限制，分为全局变量和局部变量。
>###### 1）全局变量
>- 在函数外部定义
>- 在全局范围可以使用
>- 在局部范围可以使用
>```
>>>>a = 1 # 创建全局变量
>>>>def func():
>>>>    print(a) # 在函数内调用全局变量
>>>>func() # 调用函数
>>>>print(a)
>1
>1
>```
>###### 2）局部变量
>- 在函数内部定义
>- 在全局范围无法使用
>- 在局部范围可以使用
>```
>>>>def func():
>>>>    a = 1 # 创建局部变量
>>>>    print(a)
>>>>func()
>>>>print(a) # 在函数外调用局部变量会报错
>1
>NameError: name 'q' is not defined
>```
>###### 3）提升局部变量为全局变量
>使用global
>```
>>>>def func():
>>>>    global a # 在函数内创建全局变量
>>>>    a = 1
>>>>    print(a)
>>>>func()
>>>>print(a) # 在函数外调用局部变量会报错
>1
>1
>```
>###### 4）LEGB原则
> 名称（由内到外）|内容 
>:--|:--
>- L（Local）|局部作用域
>- E（Enclosing function locale）|外部嵌套函数作用域
>- G（Global module）|函数定义所在模块作用域
>- B（Buildin）：| python内置魔法函数
>###### 5）globals和locals函数
>- 通过globals()显示所有局部变量
>- 通过locals()显示所有全局变量
>```
>>>>i = 1
>>>>str = 'Hello World!'
>>>>print('局部变量={0}'.format(locals()))
>>>>print('全局变量={0}'.format(globals())) #自己试试打印出来吧
>```
###### 5.6 函数嵌套
>- 嵌套函数即在函数内部定义函数并使用
>- 外部函数的变量可以被内部函数所使用，但不能被内部函数修改，若要修改需要添加关键字nonlocal
>```
>>>>def funcA():
>>>>    def funcB(): # 在函数内创建函数
>>>>        a = 1
>>>>        print(a)
>>>>    funcB() # 在函数内调用函数
>>>>funcA()
>1
>
>>>>def funcA():
>>>>    a = 1
>>>>    def funcB():
>>>>        nonlocal a # 改变外部函数需要用nonlocal关键字，不然会报错
>>>>        a += 1
>>>>    funcB()
>>>>    print(a)
>>>>funcA()
>2
>```
##### 6. 部分字符串处理及内建函数
###### 6.1 创建字符串
>###### 1）创建单行字符串
>```
>>>>str = 'Hello World!'
>>>>print(str)
>'Hello World!'
>```
>###### 2）创建跨行字符串:
>``` 
>>>>str = '''Hello
>>>>World!'''
>>>>print(str)
>Hello 
>World!
>```
###### 6.2 访问字符串
>- 可以用[序号]访问字符串
>```
>>>>str = 'Hello World!'
>>>>print(str[0]) # 访问字符串的第一个字符
>H
>
>>>>>str = 'Hello World!'
>>>>print(str[-2]) # 访问字符串的倒数第二个字符
>d
>```
>- 字符串切片,格式:```str[start,end,steps]```
>```
>>>>str1 = 'Hello World!'
>>>>str1 = str[2:5] # 访问字符串第3-5个字符
>>>>print(str1)
>llo
>
>>>>str2 = 'Hello World!'
>>>>str2 = str[:4] # 访问字符串第0-4个字符
>>>>print(str2)
>Hell
>
>>>>str3 = 'Hello World!'
>>>>str3 = str[0:8:2] # 访问字符串第0-6个字符,步长为2
>>>>print(str2)
>HloW
>
>>>>str4 = 'Hello World!'
>>>>str4 = str[-1:2:-2] # 从右向左切片
>>>>print(str2)
>!lo l
>```
###### 6.3 字符串连接
>```
>>>>str1 = 'Hello'
>>>>str2 = ' World'
>>>>str = str1 + str2 # 这里将两个字符串拼接在一起
>>>>print(str)
>Hello World
>```
###### 6.4 转义字符
>- 用一个特殊的方法表示出一系列不方便写出的内容，比如回车键，换行键，退格键
>- 借助反斜杠“\”字符，一旦字符串中出现反斜杠，则反斜杠后面一个火几个字符表示已经不是原来的意思了，进行了转义。
>###### 1）例：用\r\n转义 回车+换行
>- 在win系统下用\n，linux下需要\r\n
>- 这应该是唯一一个系统区分的转义案例
>``` 
>>>>str = 'Hello \r\nWorld' # 这里在字符串中增加了回车
>>>>print(str)
>Hello
>World
>```
>###### 2）例：一些常见应用
>```
>>>>print('c:\\folder\\file') # 用\\转义\
>c:\folder\file
>
>>>>print('I love \'Python!\'') # 用\'转义'
>i love 'Python!'
>
>>>>print('Hello \
>>>>World!') # 遇到过长的代码，可以用\换行继续编写
>Hello World!
>```
>###### 3）转义字符表
>转义字符|描述
>:--:|:--:
>\ |(在行尾时)续行符
>\\\ |反斜杠符号
>\’|单引号
>\”|双引号
>\a|响铃
>\b|退格(Backspace)
>\e|转义
>\000|空
>\n|换行
>\v|纵向制表符
>\t|横向制表符
>\r|回车
>\f|换页
>\oyy|八进制数yy代表的字符，例如：\o12代表换行
>\xyy|十进制数yy代表的字符，例如：\x0a代表换行
>\other|其它的字符以普通格式输出
###### 6.5 字符串运算符
>###### 1) + 字符串连接 
>```
>>>>str = 'Hello' + ' World'
>>>>print(str)
>Hello World
>```
>###### 2) * 重复字符串
>```
>>>>str = 'Hello World' * 2
>>>>print(str)
>Hello WorldHello World
>```
>###### 3) 通过索引获得字符
>```
>>>>str = 'Hello World' 
>>>>s = str[0]
>>>>print(s)
>H
>```
>###### 4) 截取一部分字符串
>```
>>>>str = 'Hello World' 
>>>>s = str[2:5]
>>>>print(s)
>llo
>```
>###### 5) 成员运算符 in 和 not in
>```
>>>>str = 'Hello World'
>>>>a = 'hello' in str # 这里返回True
>>>>b = 'Wrold' not in str # 这里返回False
>>>>print(a)
>>>>print(b)
>True
>False
>```
>###### 6) 原始字符串 r或R
>```
>>>>str = r'Hello /nWorld' # 这里会将/n当做字符串而不是转义字符处理
>>>>print(str)
>'Hello /nWorld'
>```
>###### 7) Unicode字符串 u
>Python3默认Unicode
>```
>>>>str = u'Hello World' # 这里字符串存储为16位unicode字符
>```
###### 6.6 字符串格式化的五种方式
>###### 1）老版占位符方式
>占位符必须和替换的内容匹配
> 常见占位符|含义
> :--:|:--:
>%d|整数
>%f|浮点数
>%s | 字符串
>%x |十六进制整数
>```
>>>>type = '雪纳瑞'
>>>>str = '我的小狗是, %s!'%type # 利用%s占位符
>>>>print(str)
>我的小狗是, 雪纳瑞!
>```
>###### 2）format方式
>```
>>>>type = '雪纳瑞'
>>>>str = '我的小狗是, {}!'.format(type)
>>>>print(str)
>我的小狗是, 雪纳瑞!
>
>>>>type = 'pp'
>>>>str = '我的小狗是,{name}!.format(name=type)'
>>>>print(str)
>我的小狗是, pp!
>```
>###### 3）format+解包方式
>利用**解包字典
>```
>>>>dict = {'name':'qq','age':1}
>>>>str = '我的小狗是{name},它今年{age}岁了'.format(**dict)
>>>>print(str)
>我的小狗是qq,它今年1岁了
>```
>###### 4）Template方式
>需要导入string.Template模块
>```
>>>>from string import Template
>>>>type = '雪纳瑞'
>>>>t = Template('我的小狗是,$type!')
>>>>t.substitute(type=type)
>'我的小狗是,雪纳瑞!'
>```
###### 6.7 全部string内建函数
>- 可以用help(string)查看全部内建函数。
>- 或者通过传送门看中文介绍: [内建函数资料](https://www.jianshu.com/p/523bd510901b)
##### 7. list、set、tuple和dict处理
###### 7.1 部分list处理及内建函数
>###### 1）定义列表
>```
>>>>li = list(('雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']))
>>>>print(li)
>['雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 19, ['Hello', 'World']]
>
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>print(li)
>['雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 19, ['Hello', 'World']]
>```
>###### 2）统计列表长度
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>print(len(li))
>6
>```
>###### 3）获取元素index
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>li_index = li.index('雪纳瑞') # 这里获取了序号
>>>>print(li_index)
>0
>```
>###### 4）修改列表内容
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>li[4] = 25 # 将li的第5个元素替换为25
>>>>print(li)
>['雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 25, ['Hello', 'World']]
>```
>###### 5）插入元素
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>li.append('金毛')
>>>>print(li)
>['雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 19, ['Hello', 'World'], '金毛']
>```
>###### 6）删除元素
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>li.remove('雪纳瑞')
>>>>print(li)
>['贵宾犬', '柯基', '阿拉斯加', 19, ['Hello', 'World']]
>```
>###### 7）列表pop和clear
>- pop()将列表的最后一个元素从列表中删除。
>- clear()将列表清除。
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>a = li.pop() # 将列表的最后一个元素 li[-1] 从列表中剔除，并赋值到变量a
>>>>print(a)
>>>>print(li)
>['Hello', 'World']
>['雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 19]
>
>>>>li.clear() # 清空整个列表
>>>>print(li)
>[]
>```
>###### 8）列表便利
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>for i in li:
>>>>  print(i)
>雪纳瑞
>贵宾犬
>柯基
>阿拉斯加
>19
>['Hello', 'World']
>
>>>>print([i for i in li]) # 表达式的方法
>雪纳瑞
>贵宾犬
>柯基
>阿拉斯加
>19
>['Hello', 'World']
>```
>###### 9）更多列表操作符
>- 列表重复
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>li = li*2 # 将内容重复两次
>>>>print(li)
>['雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 19, ['Hello', 'World'], '雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 19, ['Hello', 'World']]
>```
>- 列表连接
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>li1 = [1,2,3]
>>>>li = li + li1 # 两个列表组合
>>>print(li)
>['雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 19, ['Hello', 'World'], 1, 2, 3]
>```
> - 判断元素是否在列表中
>```
>>>>li = ['雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World']]
>>>>print('雪纳瑞' in li)
>True
>```
>###### 10）全部list内建函数
>- 可以用help(list)查看全部内建函数。 
>- 或者通过传送门看中文介绍: [内建函数资料](https://www.cnblogs.com/wangbin2188/p/6769514.html)
###### 7.2 部分set集合处理及内建函数
>- 集合set是一个无序的不重复元素序列, set中不会存在相同的元素
>###### 1）创建set
>```
>>>>a = {'雪纳瑞','贵宾犬','柯基','阿拉斯加',19}
>>>>b = set(('雪纳瑞','贵宾犬','柯基','阿拉斯加',19)) # 第二种方式
>>>>print(a)
>{'阿拉斯加', '柯基', '雪纳瑞', '贵宾犬', 19}
>```
>###### 2）集合运算
>运算符 | 备注
>:--:|:--:
>a - b|  集合a中包含而集合b中不包含的元素
>a \| b | 集合a和b中包含的所有元素，重复的元素只留一个
>a & b | 集合a和b中同时包含的元素
>a ^ b | 不同时包含于a和b的元素
>```
>>>>a = {'a','b','c'}
>>>>b = {'c','d','e'}
>
>>>>print(a-b) #集合a中包含而集合b中不包含的元素
>{'a', 'b'}
>
>>>>print(a|b) #集合a和b中包含的所有元素，重复的元素只留一个
>{'a', 'b', 'c', 'd', 'e'}
>
>>>>print(a&b) #集合a和b中同时包含的元素
>{'c'}
>
>>>>print(a^b) #不同时包含于a和b的元素
>{'a', 'b', 'd', 'e'}
>```
>###### 3）添加元素
>```
>>>>a = {'雪纳瑞','贵宾','柯基'}
>>>>a.add('金毛')
>>>>print(a)
>{'柯基', '金毛', '雪纳瑞', '贵宾'}
>
>>>>a.update('秋田犬','8岁') # 添加多个元素
>>>>print(set)
>{'8', '岁', '金毛', '秋', '田', '雪纳瑞', '犬', '贵宾', '柯基'}
>```
>###### 4）移除元素
>```
>>>>a = {'雪纳瑞','贵宾','柯基','贵宾犬'}
>>>>a.remove('贵宾犬')
>>>>print(a)
>{'柯基', '雪纳瑞', '贵宾'}
>
>>>>a.pop() #随机删除一个元素
>>>>print(a) #这里的结果是随机的
>{'雪纳瑞', '贵宾'}
>```
>###### 5）巧妙利用set为list去重
>```
>>>a = ['雪纳瑞','雪纳瑞','贵宾','柯基','贵宾犬','柯基']
>>>a = list(set(a)) #先转成set,再转回list
>>>print(a) #完成去重，但是位置也被随机改变了
>['柯基', '雪纳瑞', '贵宾犬', '贵宾']
>```
>###### 6）全部set内建函数
>- 可以用help(set)查看全部内建函数。
>- 或者通过传送门看中文介绍: [set内建函数](https://blog.csdn.net/weixin_44783160/article/details/100689430)
###### 7.3 部分tuple元组处理及内建函数
>- Python的元组与列表类似，不同之处在于元组的元素不能修改。
>###### 1）创建元组
>注意：如果元祖只包含一个值，需要在值后面加,
>```
>>>>tup1 = ('雪纳瑞',) # 如果只有一个元素，需要在元素后加,
>>>>print(tup1)
>('雪纳瑞',)
>
>>>>tup2 = ('雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World'])
>>>>print(tup2)
>('雪纳瑞', '贵宾犬', '柯基', '阿拉斯加', 19, ['Hello', 'World'])
>```
>###### 2）访问元组
>```
>>>>tup1 = ('雪纳瑞','贵宾犬','柯基','阿拉斯加',19,['Hello','World'])
>>>>print(tup1[0]) # 和list一样，访问第1个元素
>雪纳瑞
>
>>>>print(tup1[3:5])
>('阿拉斯加', 19)
>```
>###### 3） 拼接元组
>元组的内容不可以修改，但是可以拼接
>```
>>>>tup1 = ('雪纳瑞',)
>>>>tup2 = ('柯基','金毛','拉不拉多')
>>>>tup = tup1 + tup2
>>>>print(tup)
>('雪纳瑞', '柯基', '金毛', '拉不拉多')
>```
>###### 4） 删除元组
>将对象删除
>```
>>>>tup = ('柯基','金毛','拉不拉多')
>>>>del tup
>NameError: name 'tup' is not defined
>```
>###### 5）全部tuple内建函数
>- 可以用help(tuple)查看全部内建函数。
>- 或者通过传送门看中文介绍:[tuple内建函数](https://jingyan.baidu.com/article/4e5b3e199b2e49d1911e240b.html)
###### 7.4 部分dict字典处理及内建函数
>- 由于dict采用的是[hash](https://blog.csdn.net/xinshengdaxue000/article/details/80545146)算法，所以查找效率会比list快很多
>###### 1）创建字典
>- key只能是int或者string,且不能改变
>- value可以是任何值
>- 可以用setdefault创建一个默认值，如果key没有对应value，则用默认值替代。
>```
>>>>d1 = {'姓名':'pp','年龄':12,'性别':'男','品种':'雪纳瑞'}
>>>>print(d1)
>{'姓名': 'pp', '年龄': 12, '性别': '男', '品种': '雪纳瑞'}
>
>>>>d1.setdefault(‘爱吃','饼干') # 设定了一个默认值，如果字典中未定义该key或者value则用默认值代替
>>>>print(d1['爱吃'])
>饼干
>```
>###### 2）访问字典
>```
>>>>d1 = {'姓名':'pp','年龄':12,'性别':'男','品种':'雪纳瑞'}
>>>>print(d1['年龄'])
>12
>
>>>>print(d1.get('性别'))
>男
>```
>###### 3）修改字典元素
>```
>>>>d1 = {'姓名':'pp','年龄':12,'性别':'男','品种':'雪纳瑞'}
>>>>d1['姓名'] = 'qq' # 如果key不存在则添加元素
>>>>print(d1)
>{'姓名': 'qq', '年龄': 12, '性别': '男', '品种': '雪纳瑞'}
>```
>###### 4）删除字典元素
>```
>>>>d1 = {'姓名':'pp','年龄':12,'性别':'男','品种':'雪纳瑞'}
>>>>del d1['品种'] # 删除指定的key和value
>>>>print(d1)
>{'姓名': 'pp', '年龄': 12, '性别': '男'}
>
>>>>d1.clear() # 清空字典
>>>>print(d1)
>{}
>
>>>>del d1 # 删除字典
>NameError: name 'd1' is not defined
>```
>###### 5）全部dict内建函数
>- 可以用help(dict)查看全部内建函数。
>- 或者通过传送门看中文介绍:[dict内建函数](https://blog.csdn.net/abb1513/article/details/80340378)
##### 8 递归函数
>- 在函数内直接或间接调用其自身，叫做递归函数。
>- 递归函数必须要有一个终止递归的条件，否则会栈溢出。
>- 递归函数的运算速度相对较慢
>```
>>>># 下面案例通过递归函数实现了阶乘
>>>>def func(n):
>>>>   print(n)
>>>>   if n == 1: # 这里必须有一个终止递归的条件，否则会栈溢出
>>>>    return 1
>>>>   return n * func(n-1)
>>>>print(func(5))
>5
>4
>3
>2
>1
>1
>120

##参考资料
---
- https://www.runoob.com 菜鸟教程
- http://www.tulingxueyuan.com/ 北京图灵学院
- http://www.imooc.com/article/19184?block_id=tuijian_wz#child_5_1 两点水
- https://blog.csdn.net/weixin_44213550/article/details/91346411 python老菜鸟
- https://realpython.com/python-string-formatting/ Dan Bader
- https://www.liaoxuefeng.com/ 廖雪峰
- https://blog.csdn.net/Gnewocean/article/details/85319590 新海说
- 《Python学习手册》Mark Lutz
- 《Python编程 从入门到实践》Eric Matthes
---
本文作者：大师兄(superkmi)
![梦幻微武侠](https://upload-images.jianshu.io/upload_images/19742364-0b165e9d9cf51f71.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)







