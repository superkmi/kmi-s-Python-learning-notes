[大师兄的Python学习笔记(六）: 常用库之os包](https://www.jianshu.com/p/5ef7183ade1b)

##一、关于re包和正则表达式
#####1.1 关于正则表达式
> - 正则表达式描述了一种字符串匹配的模式，可以理解成匹配特定字符串的公式。
> - 经常用于复杂或个性化的字符串处理。
> - 正则表达式在多种编程语言中是通用的。
> - 正则表达式相对独立于某种编程语言，是文字处理的常用工具。
>
#####1.2 关于re包
> - 提供了与 Perl 语言类似的正则表达式匹配操作。
> - re包在Python标准库中，所以不需要安装可以直接使用。
> - 被搜索的字符串既可以是 Unicode 字符串`str`，也可以是8位字节串`bytes`，但Unicode 字符串与8位字节串不能混用。
> - 本文所有内容默认已经`import re`。
##二、正则表达式的语法
>**1）. 匹配任意一个字符，除了\n(换行符）**
>```
>>>>pattern = re.compile(r'.')
>>>>m = pattern.match('any string')
>>>>print(m)
><re.Match object; span=(0, 1), match='a'>
>```
>**2）[] 匹配中括号中的字符集**
>```
>>>>pattern = re.compile(r'[abcded]')
>>>>m = pattern.findall('hello world')
>>>>print(m)
>['e', 'd']
>```
>**3）\d 匹配任意一个数字**
>```
>>>>pattern = re.compile(r'\d')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['1', '1', '1', '1']
>```
> **4）\D 匹配任意一个非数字**
>```
>>>>pattern = re.compile(r'\D')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['p', 'p', 'l', ' ', 's', 'p', 'e', 'n', 'd', ' ', 'h', 'u', 'g', 'e', ' ', 'm', 'o', 'n', 'e', 'y', ' ', 'o', 'n', ' ', '/', ' ']
>```
> **5）\s 匹配空格或tab键**
>```
>>>>pattern = re.compile(r'\s')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>[' ', ' ', ' ', ' ', ' ', ' ']
>```
> **6）\S 匹配非空格或非tab键**
>```
>>>>pattern = re.compile(r'\S')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['p', 'p', 'l', 's', 'p', 'e', 'n', 't', 'h', 'u', 'g', 'e', 'm', 'o', 'n', 'e', 'y', 'o', 'n', '1', '1', '/', '1', '1']
>```
> **7）\w 匹配一个单词字符**
> - 包括:a-z,A-Z,0-9
>```
>>>>pattern = re.compile(r'\w')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['p', 'p', 'l', 's', 'p', 'e', 'n', 't', 'h', 'u', 'g', 'e', 'm', 'o', 'n', 'e', 'y', 'o', 'n', '1', '1', '1', '1']
>```
> **8）\W 匹配一个非单词字符**
>```
>>>>pattern = re.compile(r'\W')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>[' ', ' ', ' ', ' ', ' ', '/', ' ']
>```
> **9）\* 匹配前面内容重复零次或者多次**
>```
>>>>pattern = re.compile(r'\w*')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['ppl', '', 'spent', '', 'huge', '', 'money', '', 'on', '', '11', '', '11', '', '']
>```
> **10）+ 匹配前面内容至少出现一次**
>```
>>>>pattern = re.compile(r'[spo]+')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['pp', 'sp', 'o', 'o']
>```
> **11）? 匹配前面内容出现零次或一次**
>```
>>>>pattern = re.compile(r'[spo]?')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['p', 'p', '', '', 's', 'p', '', '', '', '', '', '', '', '', '', '', 'o', '', '', '', '', 'o', '', '', '', '', '', '', '', '', '']
>```
> **12）{m,n} 匹配前面内容出现最少m次，最多n次**
> - n是可选项。
>```
>>>>pattern = re.compile(r'\w{4,5}')
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['spent', 'huge', 'money']
>```
> **13）^ 匹配字符串或行的开始部分**
>```
>>>>pattern = re.compile(r'^\w{2}') #至少两个连续的字符
>>>>m = pattern.findall('ppl spent huge money on 11/11 ')
>>>>print(m)
>['pp']
>```
> **14）$ 匹配字符串的结尾、字符串结尾的\n之前或行的结尾**
>```
>>>>pattern = re.compile(r'\d{2}$')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['11']
>```
> **15）\b 匹配单词的边界**
> - 也就是单词和空格间的位置。
> - 放在前面就是匹配前面的边界，放在后面就是匹配后面的边界。
>```
>>>>pattern = re.compile(r'\w{2}\b')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['pl', 'nt', 'ge', 'ey', 'on', '11', '11']
>
>>>>pattern = re.compile(r'\b\w{2}')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['pp', 'sp', 'hu', 'mo', 'on', '11', '11']
>```
>**16）\B 匹配非单词边界**
>```
>>>>pattern = re.compile(r'\w{2}\B')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['pp', 'sp', 'en', 'hu', 'mo', 'ne']
>```
> **17）() 对正则表达式进行分组，类似数学公式()的作用**
>```
>>>>pattern = re.compile(r'(\w{3}\s)+')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['ppl ', 'ent ', 'uge ', 'ney ']
>```
> **18）\A 只匹配字符串的开头部分**
>```
>>>>pattern = re.compile(r'\Appl\ss')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['ppl s']
>```
> **19）\Z 只匹配字符串的末尾部分**
>```
>>>>pattern = re.compile(r'\d*\W\d*\Z')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['11/11']
>```
>**20）\n 匹配一个换行符**
>```
>>>>pattern = re.compile(r'\n')
>>>>m = pattern.findall('''Ppl Spent Huge Money On 11\n11''')
>>>>print(m)
>['\n']
>```
>**21）\t 匹配一个制表符**
>```
>>>>pattern = re.compile(r'\t')
>>>>m = pattern.findall('''Ppl Spent Huge Money On 11\t11''')
>>>>print(m)
>['\t']
>```
> **22）<a>|<b> 匹配左右任意一个**
> - 可以理解为or
>```
>>>>pattern = re.compile(r'p\w|h\w')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['pp', 'pe', 'hu']
>```
>**23）(?P<name>) 分组并起一个别名<name>**
>```
>>>>pattern = re.compile(r'(?P<id>\w{4})')
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['spen', 'huge', 'mone']
>```
>**24）(?P=name) 引用分组<name>**
>```
>>>>pattern = re.compile(r'(?P<id>\w)(?P=id)') # 匹配连续连个相同的字符中的第一个
>>>>m = pattern.findall('ppl spent huge money on 11/11')
>>>>print(m)
>['p', '1', '1']
>```
>**25）(?imx:) 在括号中使用i, m, 或 x 可选标志**
> - 使匹配对大小写不敏感
> - 多行匹配，影响 ^ 和 $
> - 该标志通过给予你更灵活的格式以便你将正则表达式写得更易于理解。
>```
>>>>pattern = re.compile(r'(?imx:ppl)') # 忽略了大小写
>>>>m = pattern.findall('''Ppl Spent Huge Money On 11/11''')
>>>>print(m)
>['Ppl']
>```
>**26）(?#) 注释**
> - 给程序员看的，不会被计算机解析
>```
>>>>pattern = re.compile(r'(?#这里是注释)\w{4}')
>>>>m = pattern.findall('''Ppl Spent Huge Money On 11/11''')
>>>>print(m)
>['Spen', 'Huge', 'Mone']
>```
>**27）(?= re) 前向肯定界定符**
> - 如果匹配成功，则以 … 表示。
>```
>>>>pattern = re.compile(r'(?=\w{5})')
>>>>m = pattern.findall('''Ppl Spent Huge Money On 11/11''')
>>>>print(m)
>['', '']
>```
>**28）(?! re) 前向否定界定符**
> - 如果没有匹配成功，则以 … 表示。
>```
>>>>pattern = re.compile(r'(?!\w{5})')
>>>>m = pattern.findall('''Ppl Spent Huge Money On 11/11''')
>>>>print(m)
>['', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '', '']
>```
>**29）(?<=) 匹配字符串的当前位置**
> - 从匹配的位置开始往回看是否符合。
> - 样式必须是定长，比如abc 或 a|b 是允许的，但是 a* 和 a{3,4} 不可以。
>```
>>>>pattern = re.compile(r'(?<=\w{2})ent')
>>>>m = pattern.search('''Ppl Spent Huge Money On 11\t11''')
>>>>print(m)
><re.Match object; span=(6, 9), match='ent'>
>```
>**30）(?<!) 匹配当前位置之前不是**
> - 与(?<=)相反
>```
>>>>pattern = re.compile(r'(?<!\w)')
>>>>m = pattern.findall('''Ppl Spent Huge Money On 11\t11''')
>>>>print(m)
>['', '', '', '', '', '', '', '']
>```
>**31）\<n> 匹配第<n>个分组的子表达式。**
> - <n>是一个数据。
> - 只能用于匹配前面99个组合。
>```
>>>>pattern = re.compile(r'(\w)\1')
>>>>m = pattern.findall('''Ppl Spent Huge Money On 11\t11''')
>>>>print(m)
>['1', '1']
>```
>**32） 匹配汉字。**
> - 用unicode字符集[\u4E00-\u9FA5]匹配。
>```
>>>>pattern = re.compile(r'[\u4E00-\u9FA5]')
>>>>m = pattern.findall('Hello,我系渣渣辉，是兄弟就来砍我，4399') # 注意这里两个中文，没有被匹配
>>>>print(m)
>['我', '系', '渣', '渣', '辉', '是', '兄', '弟', '就', '来', '砍', '我']
>```
>**33） 匹配汉字及标点符号。**
> - 用unicode字符集'[\u3002\uff1b\uff0c\uff1a\u201c\u201d\uff08\uff09\u3001\uff1f\u300a\u300b\u4e00-\u9fa5]'匹配。
>```
>>>>pattern = re.compile(r'[\u3002\uff1b\uff0c\uff1a\u201c\u201d\uff08\uff09\u3001\uff1f\u300a\u300b\u4e00-\u9fa5]')
>>>>m = pattern.findall('Hello,我系渣渣辉，是兄弟就来砍我，4399')
>>>>print(m)
>['我', '系', '渣', '渣', '辉', '，', '是', '兄', '弟', '就', '来', '砍', '我', '，']
>```
##三、正则表达式的贪婪模式和非贪婪模式
- 贪婪或非贪婪模式，表示正则表达式趋向匹配最大长度或趋向最少的长度匹配。
#####3.1 贪婪模式
> - 贪婪模式中，正则表达式趋向最大的长度的匹配。
> - 贪婪模式为默认模式。
>```
>>>>pattern = re.compile(r'\w+')
>>>>m = pattern.findall('Hello World!')
>>>>print(m)
>['Hello', 'World']
>```
#####3.2 非贪婪模式
> - 非贪婪模式中，正则表达式趋向最少的长度匹配。
> - 在量词后加?启用贪婪模式。
>```
>>>>pattern = re.compile(r'\w+?')
>>>>m = pattern.findall('Hello World!')
>>>>print(m)
>['H', 'e', 'l', 'l', 'o', 'W', 'o', 'r', 'l', 'd']
>```

##四、re包的使用方法
 - re包的使用流程：

序号|流程|方法
:--:|:--|:--
1|导入re模块|import re
2a|生成正则表达式对象<pattern>|re.compile()
2b|直接使用表达式字符串|不需要编译，直接使用字符串
3a|调用正则表达式对象匹配文本|pattern.search()<br>pattern.match()<br>pattern.fullmatch()<br>pattern.split()<br>pattern.finall()<br>pattern.finditer()<br>pattern.sub()<br>pattern.subn()
3b|使用正则表达式字符串匹配文本(工厂模式）|re.search()<br>re.match()<br>re.fullmatch()<br>re.split()<br>re.finall()<br>re.finditer()<br>re.sub()<br>re.subn()
4|处理匹配结果(Match)|Match.group()<br>Match.groups()<br>Match.groupdict()<br>... ...
#####4.1 生成正则表达式对象
> **1）关于原生字符串**
> - 可以使用r"<str>"的方式生成原生字符串。
> - 原生字符串会忽略转义字符。
> - 关于转义字符请参考[大师兄的Python学习笔记(一)2.6.4](https://www.jianshu.com/p/8f06eacf6b5d)
>```
>>>>pattern = r"Hello\nWorld"
>>>>print(pattern) # 忽略转义字符\n被当做字符串使用
>>>>Hello\nWorld
>
>>>>pattern = "Hello\nWorld"
>>>>print(pattern) # \n被转义为换行符
>Hello
>World
>```
> **2）re.compile(<pattern>,<flags=0>)方法**
> - 将正则表达式的样式<pattern>(见前文正则表达式语法）编译为一个正则表达式对象。
> - <flags>表示匹配模式，可以使用以下参数:
>
>参数|意义
>:--:|:--
>re.A(re.ASCII)|让 \w, \W, \b, \B, \d, \D, \s 和 \S 只匹配ASCII，而不是Unicode。<br>这只对Unicode样式有效，会被byte样式忽略。<br>相当于前面语法中的内联标志 (?a) 。
>re.DEBUG|显示编译时的debug信息。
>re.I(re.IGNORECASE)| 忽略大小写 
>re.M(MULTILINE)|多行模式，改变’^’和’$’的行为 
>re.S(DOTALL)|点任意匹配模式，改变’.’的行为 
>re.L(LOCALE)| 使预定字符类 \w \W \b \B \s \S 取决于当前区域设定 
>re.U(UNICODE)| 使预定字符类 \w \W \b \B \s \S \d \D 取决于unicode定义的字符属性 
>re.X(VERBOSE)| 详细模式。这个模式下正则表达式可以是多行，忽略空白字符，并可以加入注释
>```
>>>>pattern = re.compile(r"^\w+@\w+\.com$",re.I) # 用于匹配邮箱地址的正则表达式
>>>>m = re.search(pattern,"xiaoransun@hotmail.com") 
>>>>print(m)
><re.Match object; span=(0, 22), match='xiaoransun@hotmail.com'>
>```
> **3）不使用re.compile()**
> - 在Python中，常用的正则表达式方法具备一定的compile功能。
> - 如果对正则表达式的查询性能要求不高，或不使用特定参数，可以不使用re.compile()方法。
>```
>>>>pattern = r"^\w+@\w+\.com$" # 用于匹配邮箱地址的正则表达式
>>>>m = re.search(pattern,"xiaoransun@hotmail.com") 
>>>>print(m)
><re.Match object; span=(0, 22), match='xiaoransun@hotmail.com'>
>```
> **4）re.escape(<pattern>)方法**
> - 将字符串中所有可能被解释为正则表达式的字符进行转义字符处理。
> - 返回处理后的字符串。
>```
>>>>pattern = "http:\\www.wemud.net.cn"
>>>>re.escape(pattern)
>'http:\\\\www\\.wemud\\.net\\.cn'
>```
#####4.2 调用re模块匹配文本
> - 相比对象匹配方法,工厂方法的好处是效率更高。
> **1）re.search(<pattern>,<string>,<flags=0>)方法**
> - <pattern>表示正则表达式。
> - <string>表示要匹配的字符串。
> - <flags> 同compile的参数。
> - 返回第一个匹配对象。
> - 如果匹配失败则返回None。
> - 返回对象<span>值表示匹配内容在原字符串的位置。
> - 返回对象<match>是匹配的字符串部分。
>```
>>>>pattern = r"^\w+" # 用于匹配邮箱地址的正则表达式
>>>>m = re.search(pattern,"Hello World!") 
>>>>print(m)
><re.Match object; span=(0, 5), match='Hello'>
>```
> **2）re.match(<pattern>,<string>,<flags=0>)方法**
> - 与re.search()相同，返回一个匹配的值。
> - 与re.search()不同，re.match只匹配字符串的开始。
> - 如果字符串开始不符合正则表达式，则匹配失败，函数返回None。
>```
>>>>pattern = r"^\w+" # 用于匹配邮箱地址的正则表达式
>>>>m = re.match(pattern,"Hello World!") 
>>>>print(m)
><re.Match object; span=(0, 5), match='Hello'>
>
>>>>pattern = r"^\w+" # 用于匹配邮箱地址的正则表达式
>>>>m = re.match(pattern,".Hello World!") # 如果在字符串开始部分没有匹配到则返回None
>>>>print(m)
>None
>```
> **3）re.fullmatch(<pattern>,<string>,<flags=0>)方法**
> - 如果整个<string>匹配到<pattern>则返回匹配对象。
> - 否则返回None。
>```
>>>>pattern = r"^.*" # 用于匹配邮箱地址的正则表达式
>>>>m = re.fullmatch(pattern,"Hello World!") 
>>>>print(m)
><re.Match object; span=(0, 12), match='Hello World!'>
>
>>>>pattern = r"^\w*" # 用于匹配邮箱地址的正则表达式
>>>>m = re.fullmatch(pattern,"Hello World!") 
>>>>print(m) # 必须整个string全部匹配
>None
>```
> **4）re.split(<pattern>, <string>, <maxsplit=0>, <flags=0>)方法**
> - 用<pattern>分开<string>。
> - 返回一个list()。
> - <maxsplit>表示最多进行的分割次数，如果为0则表示最大分割。
>```
>>>>pattern = r"\s" # 用空格分隔
>>>>m = re.split(pattern,"Hello World!") 
>>>>print(m)
>['Hello', 'World!']
>```
> **5）re.findall(<pattern>,<string>,<flags=0>)方法**
> - 返回所有的匹配结果，包括成功和不成功的内容。
> - 返回的是一个list()。
>```
>>>>pattern = r"\w*" # 用于匹配邮箱地址的正则表达式
>>>>m = re.split(pattern,"life is like a box of chocolate!") 
>>>>print(m)
>['life', '', 'is', '', 'like', '', 'a', '', 'box', '', 'of', '', 'chocolate', '', '']
>```
> **6）re.finditer(<pattern>,<string>,<flags=0>)方法**
> - 返回所有匹配结果的匹配对象。
> - 但是返回一个保存了匹配对象的迭代器（iterator)。
>```
>>>>pattern = r"\w*" # 匹配单词
>>>>m = re.finditer(pattern,"Hello World!") 
>>>>print(list(m))
>[<re.Match object; span=(0, 5), match='Hello'>, <re.Match object; span=(5, 5), match=''>, <re.Match object; span=(6, 11), match='World'>, <re.Match object; span=(11, 11), match=''>, <re.Match object; span=(12, 12), match=''>]
>```
> **7）re.sub(<pattern>, <repl>, <string>, <count=0>, <flags=0>)方法**
> - 将<string>中所有匹配<pattern>的部分用<repl>替换，并返回替换后的字符串。
> - <count>表示最大的替换次数，0为全部替换。
>```
>>>>pattern = r"e" # 用于匹配邮箱地址的正则表达式
>>>>m = re.sub(pattern,'%%%',"life is like a box of chocolate!")  # 将所有的e替换为%%%
>>>>print(m)
>lif%%% is lik%%% a box of chocolat%%%!
>```
> **8）re.subn(<pattern>, <repl>, <string>, <count=0>, <flags=0>)方法**
>- 与re.sub()相同。
> - 但是返回一个包含 字符串 和 更新次数 的元组。
>```
>>>>pattern = r"e" # 用于匹配邮箱地址的正则表达式
>>>>m = re.subn(pattern,'%%%',"life is like a box of chocolate!") 
>>>>print(m) # 被替换了3次
>('lif%%% is lik%%% a box of chocolat%%%!', 3)
>```
#####4.3 调用正则表达式对象匹配文本
- Pattern是经过compile()的正则表达式对象。
- 相比工厂方法,对象匹配方法的好处是同一个表达式对象可以多次使用。
> **1）Pattern.search(<string>, <pos>, <endpos>)方法**
> - <string>表示要匹配的字符串。
> - <pos>表示开始匹配的位置。
> - <endpos>表示结束匹配的位置。
> - 与re.search()相同，返回第一个匹配对象。
>```
>>>>pattern = re.compile(r"\w+")
>>>>m = pattern.search("Hello World!")
>>>>print(m)
><re.Match object; span=(0, 5), match='Hello'>
>```
> **2）Pattern.match(<string>, <pos>, <endpos>)方法**
> - 与re.match相同，从字符串的开始匹配，返回第一个匹配对象。
>```
>>>>pattern = re.compile(r"\w+")
>>>>m = pattern.match("Hello World!")
>>>>print(m)
><re.Match object; span=(0, 5), match='Hello'>
>```
> **3）Pattern.fullmatch(<string>, <pos>, <endpos>)方法**
> - 与re.fullmatch相同，返回完整匹配的字符串。
>```
>>>>pattern = re.compile("^.*") # 用于匹配邮箱地址的正则表达式
>>>>m = pattern.fullmatch(pattern,"Hello World!") 
>>>>print(m)
><re.Match object; span=(0, 12), match='Hello World!'>
>```
> **4）Pattern.split(<string>, <maxsplit=0>)方法**
> - 与re.split()相同，返回分割后的list()。
>```
>>>>import re
>>>>pattern = re.compile(r"\s")
>>>>m = pattern.split("Hello World!")
>>>>print(m)
>['Hello', 'World!']
>```
> **5）Pattern.findall(<string>, <pos>, <endpos>)方法**
> - 与re.findall()相同，返回所有的匹配结果。
>```
>>>>pattern = re.compile(r"\w*") # 用于匹配邮箱地址的正则表达式
>>>>m = pattern.findall("life is like a box of chocolate!") 
>>>>print(m)
>['life', '', 'is', '', 'like', '', 'a', '', 'box', '', 'of', '', 'chocolate', '', '']
>```
> **6）Pattern.finditer(<string>, <pos>, <endpos>)方法**
> - 与re.finditer()相同，返回一个保存了匹配对象的迭代器（iterator)。
>```
>>>>pattern = compile(r"\w*") # 匹配单词
>>>>m = pattern.finditer("Hello World!") 
>>>>print(list(m))
>[<re.Match object; span=(0, 5), match='Hello'>, <re.Match object; span=(5, 5), match=''>, <re.Match object; span=(6, 11), match='World'>, <re.Match object; span=(11, 11), match=''>, <re.Match object; span=(12, 12), match=''>]
>```
> **7）pattern.sub(<repl>, <string>, <count=0>)方法**
> - 与re.sub()相同，返回替换的字符串。
>```
>>>>pattern = compile(r"e") # 用于匹配邮箱地址的正则表达式
>>>>m = pattern.sub('%%%',"life is like a box of chocolate!")  # 将所有的e替换为%%%
>>>>print(m)
>lif%%% is lik%%% a box of chocolat%%%!
>```
> **8）pattern.subn( <repl>, <string>, <count=0>)方法**
>- 与re.subn相同，返回一个包含 字符串 和 更新次数 的元组。
>```
>>>>pattern = compile(r"e") # 用于匹配邮箱地址的正则表达式
>>>>m = pattern.subn('%%%',"life is like a box of chocolate!") 
>>>>print(m) # 被替换了3次
>('lif%%% is lik%%% a box of chocolat%%%!', 3)
>```
#####4.4 处理匹配结果
- 这块指的是对于匹配对象<match>的处理方法。
- 如果返回的是list或者string则无法使用。
> **1）Match.group(<group1>, ...)方法**
> - 如果只有一个参数，结果就是一个字符串，如果有多个参数，结果就是一个元组
>```
>>>>import re
>>>>pattern = re.compile(r"\w+")
>>>>m = pattern.search("life is like a box of chocolate!")
>>>>m.group(0)
>'life'
>```
> **2）Match.groups(<default=None>)方法**
> - 返回一个元组，包含所有匹配的子组。
>```
>>>>pattern = r"(\w*)\s(\w*)"
>>>>m = re.match(pattern,"Hello World!")
>>>>m.groups()
>('Hello', 'World')
>```
> **3）Match.groupdict(<default=None>)方法**
> - 返回一个字典，包含了所有的命名子组。
> - key为子组的名称。
>```
>>>>pattern = r"(?P<first>\w*)\s(?P<second>\w*)"
>>>>m = re.match(pattern,"Hello World!")
>>>>m.groupdict()
>{'first': 'Hello', 'second': 'World'}
>```
> **4）Match.expand(<template>)方法**
> - 将<match>中的转义符进行反斜杠转义替换并且返回。
>```
>>>>pattern = r"(\w*)\s(\w*)"
>>>>m = re.match(pattern,"Hello World!")
>>>>m.expand('\\2 \\1')
>'World Hello'
>```
> **5）Match.re**
> - 返回这个实例对应的正则表达式对象。
>```
>>>>pattern = r"(\w*)\s(\w*)"
>>>>m = re.match(pattern,"Hello World!")
>>>>m.re
>re.compile(r'(\w*)\s(\w*)', re.UNICODE)
>```
## 参考资料
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
