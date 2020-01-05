[大师兄的Python学习笔记(七）: 常用库之os包](https://www.jianshu.com/p/7f2139299669)
##一、语法错误和异常
####1.语法错误
 - 语法错误通常是因为人为导致的错误。
 - 语法错误可以通过人为避免。
 - 遇到语法错误时，编译器将不执行代码，而直接指出语法错误行。
```
>>>print( # 这里少了半个括号
  File "<ipython-input-10-424fbb3a34c5>", line 1
    print(
          ^
SyntaxError: unexpected EOF while parsing
```
####2.异常
- 异常是在语法正确的情况下出现的问题。
- 有些异常时无法避免的。
- 当异常发生时，如果没有处理，程序可能会在异常处终止,并将异常信息抛出到console中。
- 异常分为内置异常和自定义异常。
```
>>>print(1/0) # 从语法上来说是正确的，但是1/0在数学上是错误的
ZeroDivisionError                         Traceback (most recent call last)
<ipython-input-11-2fc232d1511a> in <module>
----> 1 print(1/0)

ZeroDivisionError: division by zero
```
####3.异常类
- 异常在Python中是类，可以用类的方法处理和使用。
- 既然是类，也具备实例化、继承等属性。
#####3.1 基类
- 这些异常类属于异常的基类。
- 异常类层级结构如下（在Python官方文档上添加了EnvironmentError）：
BaseException
&emsp; +-- SystemExit
&emsp;  +-- KeyboardInterrupt
&emsp;  +-- GeneratorExit
&emsp;  +-- Exception
&emsp; &emsp;       +-- StopIteration
&emsp; &emsp;       +-- StopAsyncIteration
&emsp; &emsp;       +-- ArithmeticError
&emsp; &emsp;       |  &emsp;   +-- FloatingPointError
&emsp; &emsp;       |  &emsp;   +-- OverflowError
&emsp; &emsp;       |  &emsp;   +-- ZeroDivisionError
&emsp; &emsp;       +-- AssertionError
&emsp; &emsp;       +-- AttributeError
&emsp; &emsp;       +-- BufferError
&emsp; &emsp;       +-- EOFError
&emsp; &emsp;       +-- ImportError
&emsp; &emsp;       |  &emsp;   +-- ModuleNotFoundError
&emsp; &emsp;       +-- LookupError
&emsp; &emsp;       |   &emsp;  +-- IndexError
&emsp; &emsp;       | &emsp;    +-- KeyError
&emsp; &emsp;       +-- MemoryError
&emsp; &emsp;       +-- NameError
&emsp; &emsp;       | &emsp;   +-- UnboundLocalError
&emsp; &emsp;       +-- OSError
 &emsp; &emsp;      |   &emsp;  +-- BlockingIOError
&emsp; &emsp;       |  &emsp;   +-- ChildProcessError
&emsp; &emsp;       |  &emsp;   +-- ConnectionError
 &emsp; &emsp;      |  &emsp;   |  &emsp;   +-- BrokenPipeError
&emsp; &emsp;       | &emsp;    |  &emsp;   +-- ConnectionAbortedError
&emsp; &emsp;       | &emsp;    |  &emsp;   +-- ConnectionRefusedError
 &emsp; &emsp;      |  &emsp;  | &emsp;    +-- ConnectionResetError
&emsp; &emsp;       |  &emsp;   +-- FileExistsError
&emsp; &emsp;       |  &emsp;   +-- FileNotFoundError
&emsp; &emsp;      | &emsp;    +-- InterruptedError
&emsp; &emsp;       |  &emsp;   +-- IsADirectoryError
 &emsp; &emsp;      |  &emsp;   +-- NotADirectoryError
 &emsp; &emsp;      | &emsp;    +-- PermissionError
&emsp; &emsp;       |  &emsp;   +-- ProcessLookupError
 &emsp; &emsp;      | &emsp;    +-- TimeoutError
&emsp; &emsp;       +-- ReferenceError
&emsp; &emsp;       +-- RuntimeError
&emsp; &emsp;       |  &emsp;  +-- NotImplementedError
&emsp; &emsp;       |   &emsp;  +-- RecursionError
&emsp; &emsp;       +-- SyntaxError
&emsp; &emsp;       |   &emsp;  +-- IndentationError
&emsp; &emsp;       |  &emsp;&emsp;         +-- TabError
&emsp; &emsp;       +-- SystemError
&emsp; &emsp;       +-- TypeError
&emsp; &emsp;       +-- ValueError
&emsp; &emsp;       |   &emsp;  +-- UnicodeError
&emsp; &emsp;       |  &emsp;&emsp;         +-- UnicodeDecodeError
&emsp; &emsp;       |   &emsp;&emsp;        +-- UnicodeEncodeError
&emsp; &emsp;       |  &emsp; &emsp;       +-- UnicodeTranslateError
&emsp;&emsp;       +-- EnvironmentError
&emsp; &emsp;       |  &emsp;&emsp;  IOError
&emsp; &emsp;       |  &emsp;&emsp;         +-- WindowsError
&emsp; &emsp;      +-- Warning
&emsp; &emsp; &emsp;            +-- DeprecationWarning
&emsp; &emsp; &emsp;            +-- PendingDeprecationWarning
&emsp; &emsp; &emsp;            +-- RuntimeWarning
&emsp; &emsp; &emsp;            +-- SyntaxWarning
&emsp; &emsp; &emsp;            +-- UserWarning
&emsp; &emsp; &emsp;            +-- FutureWarning
&emsp; &emsp; &emsp;            +-- ImportWarning
&emsp; &emsp; &emsp;            +-- UnicodeWarning
&emsp; &emsp; &emsp;            +-- BytesWarning
&emsp; &emsp; &emsp;            +-- ResourceWarning

>**1）BaseException**
> - 是以下所有内置异常的基类。
>```
>>>>try:
>>>>    raise ValueError('valueError occured') # 手动抛出了一个valueError异常
>>>>except BaseException as e: # 用BaseException成功拦截
>>>>    print(e)
>valueError occured
>```
>**2）Exception**
> - 是BaseException的子类。
> - 所有内置的非系统退出类异常都派生自此类。 
> - 所有用户自定义异常也应当派生自此类。
> - 是3），4），5）的父类。
>```
>>>>isinstance(Exception(),BaseException) # BaseException是Exception的父类
>True
>
>>>>try:
>>>>    print(1/0)
>>>>except Exception as e:
>>>>    print(e)
>division by zero
>```
>**3）ArithmeticError**
> - 所有算术类错误而引发的内置异常派生自此类。
>```
>>>>isinstance(ArithmeticError(),Exception)
>True
>
>>>>try:
>>>>    print(1/0)
>>>>except ArithmeticError as e:
>>>>    print(e)
>division by zero
>```
>**4）BufferError**
> - 所有缓冲区相关的异常派生自此类。
>```
>>>>isinstance(BufferError(),Exception)
>True
>
>>>>try:
>>>>    raise BufferError('BufferError occered!')
>>>>except BufferError as e:
>>>>    print(e)
>BufferError occered!
>```
>**5）LookupError**
> - 派生所有映射或序列所使用的键或索引无效时引发的异常。
>```
>>>>isinstance(LookupError(),Exception)
>True
>
>>>>l = [1,2,3]
>>>>try:
>>>>    print(l[4]) # l的索引只到2
>>>>except LookupError as e:
>>>>    print(e)
>>>>list index out of range
>```
#####3.2 常用异常
>**6）AssertionError**
> - Exception的子类。
> - assert语句失败时引发的异常。
>```
>>>>i = 1
>>>>assert i > 5 # 这里引发异常
>AssertionError                            Traceback (most recent call last)
><ipython-input-58-04180c239fb3> in <module>
>      1 i = 1
>----> 2 assert i > 5
>      3 
>
>AssertionError: 
>```
>**7）AttributeError**
> - Exception的子类。
> - 当属性引用或赋值失败时被引发。
>```
>>>>class test():
>>>>    pass
>>>>t = test()
>>>>print(t.a) # object t并没有属性a
>AttributeError                            Traceback (most recent call last)
><ipython-input-64-32249b4ea681> in <module>
>      2     pass
>      3 t = test()
>----> 4 print(t.a)
>
>AttributeError: 'test' object has no attribute 'a'
>```
>**8）EOFError**
> - 当 input() 函数未读取任何数据即达到文件结束条件 (EOF) 时引发。
> - 通常是在Linux系统下Ctrl+D引起的。
>```
>>>> input('请输入内容:\n') # 运行后输入Ctrl+D退出
>请输入内容:
>Traceback (most recent call last):
>  File "<stdin>", line 1, in <module>
>EOFError
>```
>**9）GeneratorExit**
> - 直接继承自BaseException。
> - 当一个迭代器或携程被关闭时引发。
> - 其实并不能算错一个错误。
> - 系统会自动处理。
>```
>>>>def mygen():
>>>>    try:
>>>>        yield 1
>>>>    except GeneratorExit:
>>>>        print ("GeneratorExit occured!")
>>>>gen = mygen()
>>>>del gen
>GeneratorExit occured!
>```
>**10）ImportError**
> - Exception的子类。
> - 加载模块出错时引发。
>```
>>>>from os import somethingnotexist
>ImportError                               Traceback (most recent call last)
><ipython-input-85-d2637e218b4a> in <module>
>----> 1 from os import somethingnotexist
>
>ImportError: cannot import name 'somethingnotexist' from 'os' (d:\python3.7\lib\os.py)
>```
>**11）ModuleNotFoundError**
> - ImportError的子类。
> - 当使用import一个模块，但无法被定位时引发。
>```
>>>>import somethingnotexist
>ModuleNotFoundError                       Traceback (most recent call last)
><ipython-input-1-bc82e8bf935f> in <module>
>----> 1 import somethingnotexist
>
>ModuleNotFoundError: No module named 'somethingnotexist'
>```
>**12）IndexError**
> - lookupError的子类。
> - 当序列抽取超出范围时将被引发。
>```
>>>>l = [1,2,3]
>>>>print(l[3]) # l索引最大到2
>IndexError                                Traceback (most recent call last)
><ipython-input-2-76a3a79e6b74> in <module>
>      1 l = [1,2,3]
>----> 2 print(l[3])
>
>IndexError: list index out of range
>```
>**13）KeyError**
> - lookupError的子类。
> - 字典中查找一个不存在的关键字时触发。
>```
>>>>d = dict() # 一个空字典
>>>>d['a']
>KeyError                                  Traceback (most recent call last)
><ipython-input-6-8074ed6d8e6e> in <module>
>      1 d = dict()
>----> 2 d['a']
>
>KeyError: 'a'
>```
>**14）KeyboardInterrupt**
> - BaseException的子类,不会被Exception捕获。
> - 当用户按下中断键时触发。（比如ctrl+C）
>```
>>>> try:
>>>>     input('wait...')          
>>>> except KeyboardInterrupt as e:
>>>>     print('KeyboardInterrupt!\n') 
>wait... #ctrl+c中断
>KeyboardInterrupt!
>```
>**15）MemoryError**
> - Exception的子类。
> - 当内存超出时引发。
>
>**16）NameError**
> - Exception的子类。
> - 当某个局部或全局名称未找到时将被引发。
>```
>>>>print(somethingnotexist)
>NameError                                 Traceback (most recent call last)
><ipython-input-10-9f8454c313fd> in <module>
>----> 1 print(somethingnotexist)
>
>NameError: name 'somethingnotexist' is not defined
>```
>**17）NotImplementedError**
> - RuntimeError的子类。
> - 当抽象类的方法没有被实现时触发。
>```
>>>>class Animal():
>>>>    def bart(self):
>>>>        raise NotImplementedError('我没有被实现！') # 方法没有被子类实现时抛出错误  
>>>>class Dog(Animal):
>>>>    pass
>>>>dog = Dog()
>>>>dog.bart()
>NotImplementedError                       Traceback (most recent call last)
><ipython-input-30-f77fee3d0182> in <module>
>      7 
>      8 dog = Dog()
>----> 9 dog.bart()
>
><ipython-input-30-f77fee3d0182> in bart(self)
>      1 class Animal():
>      2     def bart(self):
>----> 3         raise NotImplementedError('我没有被实现！')
>      4 
>      5 class Dog(Animal):
>
>NotImplementedError: 我没有被实现！
>```
>**18）OSError(<arg>)**
> - Exception的子类。
> - 当一个系统函数返回系统相关的错误时将被引发。
> - 通常返回的是OSError的子类。
>```
>>>>os.rmdir('somethingnotexist') # FileNotFoundError是OSError的子类
>FileNotFoundError                         Traceback (most recent call last)
><ipython-input-44-45f9a9469295> in <module>
>----> 1 os.rmdir('somethingnotexist')
>
>FileNotFoundError: [WinError 2] 系统找不到指定的文件。: 'somethingnotexist'
>```
>**19）OverflowError**
> - ArithmeticError的子类。
> - 当算术运算的结果大到无法表示时将被引发。
>
>**20）RecursionError**
> - RuntimeError的子类。
> - 递归超过最大深度时引发。
>```
>>>>def A(): # 一个无限的递归函数
>>>>    print('test')
>>>>    A()
>>>>A()
>...
>test
>test
>---------------------------------------------------------------------------
>RecursionError                            Traceback (most recent call last)
><ipython-input-9-6b72e429bc27> in <module>
>      2     print('test')
>      3     A()
>----> 4 A()
>
><ipython-input-9-6b72e429bc27> in A()
>      1 def A():
>      2     print('test')
>----> 3     A()
>      4 A()
>
>... last 1 frames repeated, from the frame below ...
>
><ipython-input-9-6b72e429bc27> in A()
>      1 def A():
>      2     print('test')
>----> 3     A()
>      4 A()
>
>RecursionError: maximum recursion depth exceeded while calling a Python object
>```
>**21）ReferenceError**
> - Exception的子类。
> - 使用weakref.proxy()函数创建的弱引用试图访问已经垃圾回收了的对象时触发。
>
>**22）RuntimeError**
> - Exception的子类。
> - 当检测到一个不属于任何其他类别的错误时将被引发。
>```
>>>>def countResult(n):
>>>>    if n>0:
>>>>        return 'result>0'
>>>>    elif n<0:
>>>>        return 'result<0'
>>>>    else:
>>>>        try:
>>>>            raise RuntimeError('no result!') # 抛出异常
>>>>        except Exception as e:
>>>>            return e
>>>>print(countResult(0))
>no result!
>```
>**23）StopIteration**
> - Exception的子类。
> - 当迭代器里没有更多值时触发。
>```
>>>>it = iter([1,2,3]) # 创建一个简单的迭代器
>>>>print(next(it))
>>>>print(next(it))
>>>>print(next(it))
>>>>print(next(it)) # it中只有3个元素
>1
>2
>3
>---------------------------------------------------------------------------
>StopIteration                             Traceback (most recent call last)
><ipython-input-33-bc72c5f43427> in <module>
>      3 print(next(it))
>      4 print(next(it))
>----> 5 print(next(it))
>
>StopIteration: 
>```
>**24）StopAsyncIteration**
> - Exception的子类。
> - 必须通过异步迭代器对象的\_\_anext__()方法引发以停止迭代
>```
># test()文件
>>>>import asyncio
>>>>async def genfunc():
>>>>    yield 1
>>>>    yield 2
>>>>gen = genfunc()
>>>>async def start():
>>>>    assert gen.__aiter__() is gen
>>>>    assert await gen.__anext__() == 1
>>>>    assert await gen.__anext__() == 2
>>>>    await gen.__anext__()  # This line will raise StopAsyncIteration.
>>>>if __name__ == '__main__':
>>>>   asyncio.run(start())
>
>>>>python test.py # 执行test文件
>Traceback (most recent call last):
>  File "G:/WeMud_new/test.py", line 15, in <module>
>    asyncio.run(start())
>  File "D:\Python3.7\lib\asyncio\runners.py", line 43, in run
>    return loop.run_until_complete(main)
>  File "D:\Python3.7\lib\asyncio\base_events.py", line 584, in run_until_complete
>    return future.result()
>  File "G:/WeMud_new/test.py", line 12, in start
>    await gen.__anext__()  # This line will raise StopAsyncIteration.
>StopAsyncIteration
>```
>**25）SyntaxError**
> - Exception的子类。
> - 语法错误引发。
>```
>>>>print( # 这里少了半个括号
>  File "<ipython-input-10-424fbb3a34c5>", line 1
>    print(
>          ^
>SyntaxError: unexpected EOF while parsing
>```
>**26）IndentationError**
> - SyntaxError的子类。
> - 缩进错误时触发。
>```
>>>>def func():
>>>>return # 这里没有按规范缩进
>  File "<ipython-input-66-7d5a616a14cd>", line 2
>    return
>         ^
>IndentationError: expected an indented block
>```
>**27）TabError**
> IndentationError的子类。
> - 当缩进制表符(tab)和空格混用时触发。(如果用开发工具比如pycharm可能会自动修复)
>```
>>>> def func():
>>>>  print(1) # 缩进一个空格
>>>>     return # 缩进一个tab
>  File "<stdin>", line 3
>    return
>         ^
>TabError: inconsistent use of tabs and spaces in indentation
>```
>**28）SystemError**
> - Exception的子类。
> - 当解释器发现内部错误，但情况看起来尚未严重到要放弃所有希望时将被引发。
>
>**29）SystemExit**
> - BaseException的子类。
> - 当调用sys.exit()时触发。
>```
>>>>import sys
>>>>try:
>>>>    sys.exit()
>>>>except SystemExit as e:
>>>>    print('SystemExit occured!')
>SystemExit occured!
>```
>**30）TypeError**
> - Exception的子类。
> - 当一个操作或函数被应用于类型不适当的对象时将被引发。
>```
>>>>s = 'Hello World!'
>>>>s += 1 # 字符串不能和数字相加
>TypeError                                 Traceback (most recent call last)
><ipython-input-79-c6917f6f88fa> in <module>
>      1 s = 'Hello World!'
>----> 2 s += 1
>
>TypeError: can only concatenate str (not "int") to str
>```
>**31）UnboundLocalError**
> - NameError的子类。
> - 当变量被调用，但未被赋值时触发。
>```
>>>>def test():
>>>>    a += 1
>>>>    return a
>>>>test()
>UnboundLocalError                         Traceback (most recent call last)
><ipython-input-100-33702ca80b3f> in <module>
>      3     return a
>      4 
>----> 5 test()
>
><ipython-input-100-33702ca80b3f> in test()
>      1 def test():
>----> 2     a += 1
>      3     return a
>      4 
>      5 test()
>
>UnboundLocalError: local variable 'a' referenced before assignment
>```
>**32）UnicodeError**
> - ValueError的子类。
> - 当发生与 Unicode 相关的编码或解码错误时将被引发。
>
>**33）UnicodeEncodeError**
> - UnicodeError的子类。
> - 当在编码过程中发生与 Unicode 相关的错误时将被引发。
>```
>>>>b = u'汉字'.encode('ascii')  #ascii无法解码unicode中文
>UnicodeEncodeError                        Traceback (most recent call last)
><ipython-input-36-16fbbd512a75> in <module>
>----> 1 b = u'汉字'.encode('ascii')
>
>UnicodeEncodeError: 'ascii' codec can't encode characters in position 0-1: ordinal not in range(128)
>```
>**34）UnicodeDecodeError**
> - UnicodeError的子类。
> - 当在解码过程中发生与 Unicode 相关的错误时将被引发。
>```
>>>>b = u'汉字'.encode('utf-8')
>>>>b.decode('ascii') # ascii编码无法解码汉字
>UnicodeDecodeError                        Traceback (most recent call last)
><ipython-input-18-4dec15c7db29> in <module>
>      1 b = u'汉字'.encode('utf-8')
>----> 2 b.decode('ascii')
>
>UnicodeDecodeError: 'ascii' codec can't decode byte 0xe6 in position 0: ordinal not in range(128)
>```
>**35）UnicodeTranslateError**
> - UnicodeError的子类。
> - 在转写过程中发生与 Unicode 相关的错误时将被引发。
>
>**36）ValueError**
> - Exception的子类。
> - 当操作或函数接收到具有正确类型但值不适合的参数，并且情况不能用更精确的异常。
>```
>>>>for k,v in 'Hello World': # 没有足够的值便利
>>>>    print(k)
>ValueError                                Traceback (most recent call last)
><ipython-input-44-7772db444362> in <module>
>----> 1 for k,v in 'Hello World':
>      2     print(k)
>
>ValueError: not enough values to unpack (expected 2, got 1)
>```
>**37）ZeroDivisionError**
> - ArithmeticError的子类。
> - 当除法或取余运算的第二个参数为零时将被引发。
>```
>>>>1/0
>ZeroDivisionError                         Traceback (most recent call last)
><ipython-input-45-9e1622b385b6> in <module>
>----> 1 1/0
>
>ZeroDivisionError: division by zero
>```
>**38）EnvironmentError**
> - Exception的子类。
> - 操作系统错误的基类。
>```
>>>>isinstance(EnvironmentError(),Exception)
>True
>```
>**39）IOError**
> - EnvironmentError的子类。
> - 输入/输出操作失败
>
>**40）WindowsError**
> - IOError的子类。
> - windows系统调用失败。
> - 只能在windows操作系统使用。
#####3.3 OS异常
- 均为OSError的子类。
> **41）BlockingIOError**
> - 当一个操作会被某个设置为非阻塞操作的对象（例如套接字）所阻塞时将被引发。
>```
>>>>import os,sys
>>>> while True:    # 一个不断进程分叉的死循环，最终资源不足导致BlockIOError
>>>>     pid = os.fork() # 进程分叉
>>>>     if pid==0:     # 父进程
>>>>       sys.exit()   
>>>>     elif pid>0: # 子进程
>>>>       pass
>>>>     else:
>>>>       sys.exit()
>Traceback (most recent call last):
>  File "<stdin>", line 2, in <module>
>BlockingIOError: [Errno 11] Resource temporarily unavailable
>```
> **42）ChildProcessError**
> - 当一个子进程的失败时被引发。
>
> **43）ConnectionError**
> - 连接相关异常的基类。
> - 由于网络的不确定性，在爬虫时常见。
> 
>**44）BrokenPipeError**
> - ConnectionError的子类。
> - 当试图写入另一端已被关闭的管道，或是试图写入已关闭写入的套接字时将被引发。
>```
># test.py文件
>>>>import sys
>>>>for line in sys.stdin: # 从标准输入导出标准输出
>>>>    print(line)
># linux控制台
>>ps -elf | python testexp.py | head -n 10
>Exception ignored in: <_io.TextIOWrapper name='<stdout>' mode='w' encoding='UTF-8'>
>BrokenPipeError: [Errno 32] Broken pipe
>```
>**45）ConnectionAbortedError**
> - ConnectionError的子类。
> - 当连接尝试被对端中止时将被引发。
>
>**46）ConnectionRefusedError**
> - ConnectionError的子类。
> - 当连接尝试被对端拒绝时将被引发。
>
>**47）ConnectionResetError**
> - ConnectionError的子类。
> - 当连接被对端重置时将被引发。
>
>**48）FileExistsError**
> - 当试图创建一个已存在的文件或目录时将被引发。
>```
>>>>os.makedirs(os.path.curdir) # 创建当前的目录...是不是很蠢
>FileExistsError                           Traceback (most recent call last)
><ipython-input-8-c5cb6237374b> in <module>
>----> 1 os.makedirs(os.path.curdir)
>```
>**49）FileNotFoundError**
> - 当所请求的文件或目录不存在时将被引发。 
>```
>>>>open('notexist.py') # notexist.py并不存在
>FileNotFoundError                         Traceback (most recent call last)
><ipython-input-9-7c67429085ae> in <module>
>      1 import os
>----> 2 open('notexist.py')
>
>FileNotFoundError: [Errno 2] No such file or directory: 'notexist.py'
>```
>**50）InterruptedError**
> - 系统调用被中断时触发。
>
>**51）IsADirectoryError**
> - 当请求对一个目录执行文件操作时触发。
>```
>>>> import os
>>>> os.mkdir('newdir') # 创建一个新路径
>>>> open('newdir','r') # 以打开文件的方式打开路径名
>Traceback (most recent call last):
>  File "<stdin>", line 1, in <module>
>IsADirectoryError: [Errno 21] Is a directory: 'newdir'
>```
>**52）NotADirectoryError**
> - 当请求对一个非目录对象执行目录操作时触发。
>```
>>>> import os
>>>> os.chdir('test.txt')
>Traceback (most recent call last):
>  File "<stdin>", line 1, in <module>
>NotADirectoryError: [Errno 20] Not a directory: 'test.txt'
>```
>**53）PermissionError**
> - 当在没有足够操作权限的情况下试图执行某个操作时将被引发 。
>```
>>>>with open('d:\wemud','r') as f: # 没有给予d盘权限的情况下
>>>>    print(f)
>PermissionError                           Traceback (most recent call last)
><ipython-input-17-621f4991ae7d> in <module>
>----> 1 with open('d:\wemud','r') as f:
>      2     print(f)
>
>PermissionError: [Errno 13] Permission denied: 'd:\\wemud'
>```
>**54）ProcessLookupError**
> - 当给定的进程不存在时将被引发。
>```
>>>> os.kill(123456,0) # 一个不存在的进程
>Traceback (most recent call last):
>  File "<stdin>", line 1, in <module>
>ProcessLookupError: [Errno 3] No such process
>```
>**55）TimeoutError**
> - 当一个系统函数发生系统级超时的情况下将被引发。
#####3.4 警告
- 警告会弹出异常信息，但不会停止程序。
- 警告可以用来自定义异常，提醒用户注意事项。
>**56）Warning**
> - Exception的子类。
> - 所有警告类别的基类
>```
>>>>isinstance(Warning(),Exception)
>True
>```
>**57）UserWarning**
> - Warning的子类。
> - 用户代码所产生警告的基类。
>```
>>>>isinstance(UserWarning(),Warning)
>True
>```
>**58）DeprecationWarning**
> - Warning的子类。
> - 通常用来警告特征已弃用。
>```
>>>>from openpyxl import Workbook
>>>>wb = Workbook()
>>>>wb.create_sheet("Mysheet") 
>>>>sheet = wb.get_sheet_by_name('Mysheet') # 这是一个过期的方法
>d:\ProgramData\Anaconda3\lib\site-packages\ipykernel_launcher.py:4: DeprecationWarning: Call to >deprecated function get_sheet_by_name (Use wb[sheetname]).
>  after removing the cwd from sys.path.
>```
>**59）PendingDeprecationWarning**
> - Warning的子类。
> - 对于已过时并预计在未来弃用，但目前尚未弃用的特性相关警告的基类。
> - 这个类很少用，推荐使用DeprecationWarning。
>
>**60）SyntaxWarning**
> - Warning的子类。
> - 与模糊的语法相关的警告的基类。
>
>**61）RuntimeWarning**
> - Warning的子类。
> - 与模糊的运行时行为相关的警告的基类。
>
>**62）FutureWarning**
> - Warning的子类。
> - 已弃用特性相关警告的基类。
>
>**63）ImportWarning**
> - Warning的子类。
> - 与在模块导入中可能的错误相关的警告的基类。
>
>**64）UnicodeWarning**
> - Warning的子类。
> - 与 Unicode 相关的警告的基类。
>
>**65）BytesWarning**
> - Warning的子类。
>- 与 bytes和bytearray相关的警告的基类。
>
>**66）ResourceWarning**
> - Warning的子类。
> - 与资源使用相关的警告的基类。 会被默认的警告过滤器忽略。
##二、异常处理
- 不能保证所有问题都被解决。
- 用于保证程序在最坏的情况下，问题被妥善处理。
- 异常处理可以让代码更健壮。
####4. 异常处理的语法
#####4.1 try .. except 语句
- 用于捕获并处理异常。
- 如果异常被捕获，则不会造成程序中断。
- 完整结构式:
try:
&emsp;<尝试某个操作,如果发生异常则进入except捕获流程>
except <异常1>:
&emsp;<捕获某个异常,并运行这里的内容>
except <异常2>:
&emsp;<捕获某个异常,并运行这里的内容>
else:
&emsp;<如果没有异常捕获，则运行这里的内容>
finally:
&emsp;<不管有没有异常捕获，都会运行这里的内容>
>**1）try .. except...**
> - try ... except...必须成对出现。
> - except可以有多个，如果发生多个异常将捕获第一个发生的异常。
> - except捕获的异常应该是子类在前，父类在后，否则子类有可能捕获不到。
> - except可以用```as语句```将异常类实例化。
>```
>>>>try:
>>>>    abc # NameError
>>>>    1/0 # ZeroDivisionError
>>>>    import notexist # importError
>>>>except NameError as e: # 捕获了第一个发生的异常，先捕获子类异常。
>>>>    print('NameError occured: {e}'.format(e=e))
>>>>except ZeroDivisionError as e: # 通过as语句将Exception实例化。
>>>>    print('ZeroDivisionError occured: {e}'.format(e=e))
>>>>except Exception as e: # 父类异常放在后面
>>>>    print('Exception occured: {e}'.format(e=e))
>NameError occured: name 'abc' is not defined
>```
>**2）try .. except...else...**
> - 如果没有异常被except捕获，并且try中的内容正常执行，则执行else中的内容。
> - else不是必选项。
>```
>>>>try:
>>>>    print('some strong code')
>>>>except NameError as e:
>>>>    print('NameError occured: {e}'.format(e=e))
>>>>except ZeroDivisionError as e:
>>>>    print('ZeroDivisionError occured: {e}'.format(e=e))
>>>>except Exception as e:
>>>>    print('Exception occured: {e}'.format(e=e))
>>>>else: # 没有异常发生，所以执行else中的内容
>>>>    print('flex muscle!')
>some strong code
>flex muscle!
>```
>**3）try .. except...finally...**
> - 不管有没有异常捕获，都会执行finally中的内容。
> - finally不是必选项。
>```
>>>>try:
>>>>    print('some code')
>>>>    1/0 # bug发生
>>>>except (NameError,ZeroDivisionError) as e: # 捕获异常
>>>>    print('ZeroDivisionError occured: {e}'.format(e=e))
>>>>except Exception as e:
>>>>    print('Exception occured: {e}'.format(e=e))
>>>>else: # 有bug所以不会运行else
>>>>    print('flex muscle!')
>>>>finally: # 不管怎样都会执行finally
>>>>    print('what so ever')
>some code
>ZeroDivisionError occured: division by zero
>what so ever
>```
#####4.2 raise 语句
- 可以手动抛出某个异常
- 语法是raise <异常>
```
>>>try:
>>>    raise DeprecationWarning('Python2快要停止维护啦！')
>>>except DeprecationWarning as e:
>>>    print(e)
Python2快要停止维护啦！
```
##三、自定义异常
- 自定义异常一般通过继承系统异常类的方式创建。
- 一般系统自带异常就够用了，除非有特殊需求。
- 如果是raise异常，推荐自定义异常。
```
>>>class QQWarning(RuntimeWarning): # 新的警告继承自RuntimeWarning
>>>    def __init__(self, *arg):
>>>        self.args = arg
>>>        self.bart()      
>>>    def bart(self):
>>>        print('嗷嗷嗷！')

>>>try:
>>>    raise QQWarning('QQ在警告你！')
>>>except QQWarning as e:
>>>    print(e)
嗷嗷嗷！
QQ在警告你！
```

##参考资料
---
- https://blog.csdn.net/u010138758/article/details/80152151  J-Ombudsman
- https://www.cnblogs.com/zhuluqing/p/8832205.html moisiet
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
