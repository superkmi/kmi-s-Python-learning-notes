## 一、关于sys包
- sys包是与python解释器交互的一个接口。
- 提供与解释器紧密相关的变量和函数。
- 通常`import sys`导入sys包。
> **1）sys.abiflags**
> - 是POSIX系统中PEP3149定义的二进制应用程序结构标志。
>```
>>>> sys.abiflags
>'m'
>```
> **2）sys.addaudithook(<hook>)**
> - 为编译器运行时添加监听钩子。
> - <hook>是一个回调函数。
> - 可以用事件触发。
>```
>>>>def audit_hook(event,args):
>>>>  print(event)
>>>>sys.addaudithook(audit_hook)
>>>>print('test')
>exec
>test
>compile
>```
> **3）sys.audit(<event>, <\*args>)**
> - 可以触发某个监听事件<event>,并传入参数<args>。
> - 可以自定义事件并触发。
>```
>>>>def audit_hook(event,args):
>>>>  if event in ['test']:
>>>>    print('event:'+event)
>>>>sys.addaudithook(audit_hook)
>>>>sys.audit('test','Hello World!')
>event:test
>```
> **4）sys.argv**
> - 用于从程序外部获得参数。
> - 返回的是一个列表,其中包含了被传递给 Python 脚本的命令行参数。
> - argv[0] 为脚本的名称。
>```(python3.8) ubuntu@VM-0-4-ubuntu:~$ cat test.py
>#test.py文件
>>>>import sys
>>>>args = sys.argv
>>>>print(args)
>
># 终端
>>>>python test.py abc test 123
>['test.py', 'abc', 'test', '123']
>```
> **5）sys.base_exec_prefix**
> - 指向Python环境的安装路径。
> - 如果是虚拟环境，则指向虚拟环境的路径。
>```
>>>>sys.base_prefix
>'/home/ubuntu/anaconda3/envs/python3.8'
>```
> **6）sys.base_prefix**
> - 与sys.base_exec_prefix相同，指向Python环境的安装路径。
> - 如果是虚拟环境，则指向虚拟环境的路径。
>```
>>>>sys.base_prefix
>'/home/ubuntu/anaconda3/envs/python3.8'
>```
> **7）sys.byteorder**
> - 显示本地的字节顺序。
> - 返回big为大尾，litter为小尾。
> - [关于字节存放大尾和小尾的说明。](http://blog.sina.com.cn/s/blog_6277623c0102vntv.html)
>```
>>>>sys.byteorder
>'little'
>```
>**8）sys.builtin_module_names**
> - 一个元祖，包含所有被编译进编译器的模块。
>```
>>>>sys.builtin_module_names
>('_abc', '_ast', '_codecs', '_collections', '_functools', '_imp', '_io', '_locale', '_operator', '_signal', '_sre', '_stat', '_string', '_symtable', '_thread', '_tracemalloc', '_warnings', '_weakref', 'atexit', 'builtins', 'errno', 'faulthandler', 'gc', 'itertools', 'marshal', 'posix', 'pwd', 'sys')
>```
>**9）sys.call_tracing(<func>, <args>)**
> - 调用程序<func>(<args>)。
>```
>>>>def printArgs(*args): # 创建方法，收集参数。
>>>>  print(list(args))
>>>>sys.call_tracing(printArgs,(1,2,3,4))
>[1, 2, 3, 4]
>```
>**10）sys.copyright**
>  - 包含 Python 解释器有关的版权信息的字符串。
>```
>>>> sys.copyright
>'Copyright (c) 2001-2019 Python Software Foundation.\nAll Rights Reserved.\n\nCopyright (c) 2000 BeOpen.com.\nAll Rights Reserved.\n\nCopyright (c) 1995-2001 Corporation for National Research Initiatives.\nAll Rights Reserved.\n\nCopyright (c) 1991-1995 Stichting Mathematisch Centrum, Amsterdam.\nAll Rights Reserved.'
>```
>**11）sys._clear_type_cache()**
> - 清除内部的类型缓存。类型缓存是为了加速查找方法和属性的。
> - 在调试引用泄漏的时候调用这个函数 只会 清除不必要的引用。
> - 这个函数应该只在内部为了一些特定的目的使用。
>```
>>>> sys._clear_type_cache() 
>```
>**12）sys._current_frames()**
> - 返回函数调用时，每个线程标识符与该线程中处于活动状态的顶层堆栈帧的字典映射。
> - 这对于调试死锁是非常有用的：此函数不需要死锁线程的合作，而且只要它们保持死锁状态，调用堆栈都将被冻结。
> - 到调用代码检查帧时，非死锁线程返回的帧可能与该线程的当前活动没有关系。
>```
>>>>sys._current_frames()
>{140225429296896: <frame at 0x7f88c5ba56d0, file '<stdin>', line 1, code <module>>}
>```
>**13）sys.breakpointhook()**
> - 调用调试器。
>```
>>>>sys.breakpointhook()
>--Call--
> d:\python3.7\lib\site-packages\ipython\core\displayhook.py(252)__call__()
>-> def __call__(self, result=None):
>(Pdb) print('hello world!')
>hello world!
>```
>**14）sys._debugmallocstats()**
> - 打印CPython内存分配器状态的低级信息到stderr。
> - 此方法特定于CPython解释器使用。
> - CPython是特指C语言实现的Python,就是原汁原味的Python。
>```
>>>>sys._debugmallocstats()
>Small block threshold = 512, in 64 size classes.
>
>class   size   num pools   blocks in use  avail blocks
>-----   ----   ---------   -------------  ------------
>    0      8           1             159           347
>    1     16           1              10           243
>    2     24           1              22           146
>    3     32           4             410            94
>    4     40           5             429            76
>    5     48           4             299            37
>... ...
>```
>**15）sys.dllhandle**
> - 指定Python DLL句柄的整数。
> - 句柄是WONDOWS用来标识被应用程序所建立或使用的对象的唯一整数。
> - 只能在Windows下使用。
>```
>>>> sys.dllhandle
>140708584882176
>```
>**16）sys.displayhook(<value>)**
> - 将<value>输出到sys.stdout。
> - 预设内容会保存在sys.\_\_displayhook__。
>```
>>>> sys.displayhook('test')
>'test'
>```
>**17）sys.dont_write_bytecode**
> - 如果值为True，导入源模块时python将不会写入.pyc文件。
>```
>>>> sys.dont_write_bytecode # 查看目前的变量值
>False
>```
>**18）sys.pycache_prefix**
> - 报告缓存的位置。
> - None表示pycache子目录中的默认位置。
>```
>>>> print(sys.pycache_prefix)
>None
>```
>**19）sys.excepthook(<type>,<value>, <traceback>)**
> -  捕获异常，并将exception输出到sys.stderr。
> - 预设的exceptionhook会存放在sys.\_\_exceptionhook__。
>```
>>>> def new_excepthook(type,value,traceback): # 创建一个新的异常处置方法
>     print(type,'+',value,'+',traceback) 
>>>> sys.excepthook = new_excepthook # 用新的方法替代默认的方法
>>>> a # 故意触发一个异常
><class 'NameError'> + name 'a' is not defined + <traceback object at 0x7f9e4a22fb80>
>```
>**20）sys.exc_info()**
> - 此函数返回三个值的元组，这些值提供有关当前正在处理的异常的信息。
> - 如果在堆栈的任何地方都没有处理异常，则包含三个 None 返回值。
> - 否则，返回的值为 (type, value, traceback) 。
> -  type: 获取正在处理的异常的类型。
> -  value: 获取异常实例（异常类型的实例）。
> - traceback: 获取一个回溯对象。
>```
>>>> try:
>>>>     1/0 # 故意触发一个异常
>>>> except Exception as e:
>>>>     info = sys.exc_info() # 返回异常信息
>>>>     print(info)
>(<class 'ZeroDivisionError'>, ZeroDivisionError('division by zero'), <traceback object at 0x7f9098a58940>)
>```
>**21）sys.exec_prefix**
> - 系统Python文件的所在安装目录。
>```
>>>>sys.exec_prefix
>'/home/ubuntu/anaconda3'
>```
>**22）sys.executable**
> - Python解释器的所在路径。
>```
>>>> sys.executable
>'/home/ubuntu/anaconda3/bin/python'
>```
>**23）sys.exit(<arg>)**
> - 用于退出程序。
> - 一般用在主程序退出。
> - 当<arg>为0时是正常退出，否则会抛出SystemExit异常。
>```
>>>>try:
>>>>  sys.exit(101)
>>>>except SystemExit as e:
>>>>  print(repr(e))
>SystemExit(101)
>```
>**24）sys.flags**
> - 返回一个tuple,里面的值显示命令行标志的状态。
> - 这些属性是只读的。
> - 这些属性包括：
>
> 属性|flag
>:--:|:--:
>debug|-d
>inspect|-i
>interactive|-i
>isolated|-I
>optimize|-O or -OO
>dont_write_bytecode|-B
>no_user_site|-s
>no_side|-S
>ignore_environment|-E
>verbose|-v
>bytes_warning|-b
>quiet|-q
>hash_randomization|-R
>dev_mode|-X dev
>utf8_mode|-X utf8
>```
>>>>sys.flags
>sys.flags(debug=0, inspect=0, interactive=0, optimize=0, dont_write_bytecode=0, no_user_site=0, no_site=0, ignore_environment=0, verbose=0, bytes_warning=0, quiet=0, hash_randomization=1, isolated=0, dev_mode=False, utf8_mode=0)
>```
>**25）sys.float_info**
> - 有关浮动类型的信息。它包含关于精度和内部表示的低级信息。
> - 这些值对应于标准头文件中定义的各种浮点常量。
> - 属性包括：
>
>属性|浮点宏|解释
>:--:|:--:|:--
>epsilon|DBL_EPSILON|1和最小值之间的差异大于1，可表示为浮点
>dig|DBL_DIG|在一个浮点中可以如实表示的最大小数位数。
>mant_dig|DBL_MANT_DIG|浮点精度：基数- radix 浮点数的有效位
>max|DBL_MAX|最大可表示有限浮点数
>max_exp|DBL_MAX_EXP|最大整数e radix\*\*(e-1) 是可表示的有限浮点
>max_10_exp|DBL_MAX_10_EXP|最大整数e 10\*\*e 在可表示的有限浮点数范围内
>min|DBL_MIN|最小正归一化浮点数
>min_exp|DBL_MIN_EXP|最小整数e radix\*\*(e-1) 是规范化的浮点
>min_10_exp|DBL_MIN_10_EXP|最小整数e 10\*\*e 是规范化的浮点
>radix|FLT_RADIX|指数表示的基数
>rounds|FLT_ROUNDS|整数常量，表示用于算术运算的舍入模式。这反映了在解释器启动时系统flt_rounds宏的值。
>```
>>>>sys.float_info
>sys.float_info(max=1.7976931348623157e+308, max_exp=1024, max_10_exp=308, min=2.2250738585072014e-308, min_exp=-1021, min_10_exp=-307, dig=15, mant_dig=53, epsilon=2.220446049250313e-16, radix=2, rounds=1)
>```
>**26）sys.float_repr_style**
> - 一个字符串，指示repr()函数对浮点数x的行为方式。
> - 如果值为short，repr(x)生成短字符串。(python3.1后的通常模式）
> - 如果值为legacy, 采用python3.1之前的模式。
>```
>>>>sys.float_repr_style
>'short'
>```
>**27）sys.getallocatedblocks()**
> - 返回解释器当前分配的内存块数，而不考虑其大小。
> - 此函数主要用于跟踪和调试内存泄漏。
>```
>>>>sys.getallocatedblocks()
>21009
>```
>**28）sys.getandroidapilevel()**
> - 以整数形式返回Android编译时的API版本。
> - 只有在Android系统下使用。
>
>**29）sys.getcheckinterval()**
> - 返回解释器的“检查间隔”
>```
>>>> sys.getcheckinterval()
>100
>```
>**30）sys.getdefaultencoding()**
> - 返回当前Unicode使用的默认字符串编码。
>```
>>>> sys.getdefaultencoding()
>'utf-8'
>```
>**31）sys.getdlopenflags()**
> - 返回用于dlopen()调用的所有标签的当前值。
> - 只能在Unix系统下使用。
>```
>>>> sys.getdlopenflags()
>2
>```
>**32）sys.getfilesystemencoding()**
> - 返回用于在Unicode文件名和字节文件名之间转换的编码名称。
> - 编码通常是utf-8。
>```
>>>> sys.getfilesystemencoding()
>'utf-8'
>```
>**33）sys.getfilesystemencodeerrors()**
> - 返回用于在Unicode文件名和字节文件名之间转换的错误模式的名称。
>```
>>>>sys.getfilesystemencodeerrors()
>'surrogateescape'
>```
>**34）sys.getrefcount(<object>)**
> - 返回<object>的引用次数。
> - 引用次数会比期望值值多一个，因为它包含getrefcount()参数的临时引用。
>```
>>>> class Test():
>>>>     pass
>>>> t = Test()
>>>> sys.getrefcount(t) # t 本身是Test,所以被引用了一次。      
>2
>```
>**35）sys.getrecursionlimit()**
> - 返回当前递归的限制也就是Python解释器堆栈最大深度的值。
> - 该限制可防止无限递归导致C堆栈溢出和Python崩溃。它可以通过setrecursionlimit()设置。
>```
>>>> sys.getrecursionlimit()
>1000
>```
>**36）sys.getsizeof(<object>, <default>)**
> - 返回<object>的大小。
> - 以字节为单位。
>```
>>>> class Test():
>>>>     pass
>>>> t = Test()
>>>> sys.getsizeof(t)
>64
>```
>**37）sys.getswitchinterval()**
> - 返回解释器的“线程切换间隔。
>```
>>>> sys.getswitchinterval()
>0.005
>```
>**38）sys._getframe(<depth>)**
> - 从调用堆栈返回一个 frame 对象。
> - 如果给出可选的整型depth，返回栈顶以下相应数目的帧对象。
> - 下划线开头的成员属于“具体的实现细节”吧，这种不属于外部接口的东西，将来有可能被去除或者改换名字。
>```
>>>> sys._getframe(0)    
><frame at 0x7f7bd4cea3b0, file '<stdin>', line 1, code <module>>
>```
>**39）sys.getprofile()**
> - 获取由setprofile()设置的全局配置函数。
>```
>>>> def test(*args):
>     print("args="+str(list(args))) 
>>>> sys.setprofile(test)
>args=[<frame at 0x7fa45c975050, file '<stdin>', line 1, code <module>>, 'return', None]
>>>> sys.getprofile()
>args=[<frame at 0x7fa45c9bb6d0, file '<stdin>', line 1, code <module>>, 'call', None]
>args=[<frame at 0x7fa45c9bb6d0, file '<stdin>', line 1, code <module>>, 'c_call', <built-in function getprofile>]
>args=[<frame at 0x7fa45c9bb6d0, file '<stdin>', line 1, code <module>>, 'c_return', <built-in function getprofile>]
><function test at 0x7fa45c958440>
>args=[<frame at 0x7fa45c9bb6d0, file '<stdin>', line 1, code <module>>, 'return', None]
>```
>**40）sys.gettrace()**
> - 获取由settrace()设置的跟踪函数。
>```
>>>> def test(*args):                
>>>>     print('args='+str(args)) 
>>>> sys.settrace(test)          
>>>> sys.gettrace()              
>args=(<frame at 0x7fbf55fbf530, file '<stdin>', line 1, code <module>>, 'call', None)
><function test at 0x7fbf55f90560>
>```
>**41）sys.getwindowsversion()**
> - 返回一个已命名的元组，描述当前正在运行的 Windows 版本。
> - 已命名元素包括：major、minor、build、platform、 service_pack、 service_pack_minor、 service_pack_major、suite_mask和product_typr。
> - platform元素可以为下列值之一：
>
>常量|平台
>:--|:--
>0 （VER_PLATFORM_WIN32s）|	Win32s在Windows 3.1
>1 （VER_PLATFORM_WIN32_WINDOWS）	|Windows 95/98 / ME
>2 （VER_PLATFORM_WIN32_NT）|	Windows NT / 2000 / XP / x64
>3 （VER_PLATFORM_WIN32_CE）|	Windows CE
> - product_type可以是下列值之一:
>
>常量|含义
>:--|:--
>1 （VER_NT_WORKSTATION）|	系统是一个工作站。
>2 （VER_NT_DOMAIN_CONTROLLER）	|系统是一个域名控制器。
>3 （VER_NT_SERVER）|	系统是一个服务器，但不是域名控制器。
> - 只能在Windows系统下使用。
>```
>>>> sys.getwindowsversion()
>sys.getwindowsversion(major=10, minor=0, build=17763, platform=2, service_pack='')
>```
>**42）sys.get_asyncgen_hooks()**
> - 通常用于异步生成器处理。
> - 返回一个带有 firstiter 和 finalizer 字段的类似于类的结构。
> - firstiter：一个可调用的方法，当第一次迭代异步生成器时将调用它。
> - finalizer：一个可调用的方法，当异步生成器即将被 GC 时将被调用。
>```
>>>> import sys
>>>> def firstiter():
>>>>     print('from firstiter.') 
>>>> def finalizer():
>>>>     print('from finalizer.')
>>>> sys.set_asyncgen_hooks(firstiter,finalizer)
>>>> sys.get_asyncgen_hooks()
>asyncgen_hooks(firstiter=<function firstiter at 0x7ff4f39fa0e0>, finalizer=<function finalizer at 0x7ff4f39fa290>)
>```
>**43）sys.get_coroutine_origin_tracking_depth()**
> - 获得当前携程的默认跟踪深度。
>```
>>>> sys.get_coroutine_origin_tracking_depth()
>0
>```
>**44）sys.hash_info**
> - 一个包含哈希参数的元祖。
> - 返回的属性包含:
>
>属性|说明
>:--|:--
>width|用于哈希值的位宽度
>modulus|用于数字散列方案的素数模数P。
>inf|为正无穷大返回的哈希值
>nan|为nan返回的哈希值
>imag|用于复数虚部的乘数
>algorithm|字符串、字节和内存视图的哈希算法的名称
>hash_bits|哈希算法的内部输出大小。
>seed_bits|散列算法的种子密钥的大小
>```
>>>>sys.hash_info
>sys.hash_info(width=64, modulus=2305843009213693951, inf=314159, nan=0, imag=1000003, algorithm='siphash24', hash_bits=64, seed_bits=128, cutoff=0)
>```
>**45）sys.hexversion**
> - 获取Python解释程序的版本值。
>```
>>>> sys.hexversion
>50791152
>```
>**46）sys.implementation**
> - 有关当前正在运行的Python解释器的实现信息的对象。
> - 包含的属性如下：
>
>属性|说明
>:--|:--
>name | 实现的标识符，例如'cpython'。实际的字符串是由Python实现定义的，但它保证为小写。
>version|一个命名的元组，表示Python的implementation版本 。
>hexversion|十六进制格式的实现版本
>cache_tag|导入机制在缓存模块的文件名中使用的标记。
>```
>>>> sys.implementation
>namespace(cache_tag='cpython-37', hexversion=50791152, name='cpython', version=sys.version_info(major=3, minor=7, micro=2, releaselevel='final', serial=0))
>```
>**47）sys.int_info**
> - 有关Python的整数实现的信息。
>```
>>>> sys.int_info
>sys.int_info(bits_per_digit=30, sizeof_digit=4)
>```
>**48）sys.\_\_interactivehook\_\_**
> - 当此属性存在时，当解释器在互动模式中启动时，其值将自动调用。
>
>**49）sys.intern(<string>)**
> - 在“interned”字符串表中输入string，并返回intern字符串。
> - 本质是在set()中操作字符串。
> - 用于性能优化，节省内存。
>```
>>>> t1 = sys.intern('hello!')
>>>> print(t1)
>hello!
>>>> t2 = ('hello!') # intern字符串与string不同
>>>> t1 is t2
>False
>```
>**50）sys.is_finalizing()**
> - 如果Python解释器关闭，则返回True。
> - 否则返回False。
>```
>>>> sys.is_finalizing()
>False
>```
>**51）sys.last_type**
> - 用于在异常未被处理时，获取出错程序的异常信息中的异常类型。
> - 只有在异常发生后才会生效。
> - 其用途是允许交互式用户导入一个调试器模块并参与在事后调试无需重新执行导致错误的命令。
>```
>>>> try:
>>>>     type,value,tb = sys.exc_info()
>>>>     sys.last_type=type            
>>>>     i=1/0
>>>> finally:            
>>>>     pass
>ZeroDivisionError: division by zero
>>>> print(sys.last_type)
><class 'ZeroDivisionError'>
>```
>**52）sys.last_value**
> - 用于在异常未被处理时，获取出错程序的异常信息中的异常值。
> - 只有在异常发生后才会生效。
> - 其用途是允许交互式用户导入一个调试器模块并参与在事后调试无需重新执行导致错误的命令。
>```
>>>> try:
>>>>     type,value,tb = sys.exc_info()
>>>>     sys.last_value=value            
>>>>     i=1/0
>>>> finally:            
>>>>     pass
>ZeroDivisionError: division by zero
>>>> print(sys.last_value)
>division by zero
>```
>**53）sys.last_traceback**
> - 用于在异常未被处理时，获取出错程序的异常信息中的异常traceback对象。
> - 只有在异常发生后才会生效。
> - 其用途是允许交互式用户导入一个调试器模块并参与在事后调试无需重新执行导致错误的命令。
>```
>>>> try:
>>>>     type,value,tb = sys.exc_info()
>>>>     sys.last_value=value            
>>>>     i=1/0
>>>> finally:            
>>>>     pass
>ZeroDivisionError: division by zero
>>>> print(sys.last_traceback)
><traceback object at 0x7fe3fd233230>
>```
>**54）sys.maxsize**
> - 最大的Int值。
> - 32位平台是2**31 - 1。
> - 64位平台是2**63 - 1。
>```
>>>> sys.maxsize
>9223372036854775807
>```
>**55）sys.maxunicode**
> - sys.maxunicode
> - unicode字符的最大代码点。
>```
>>>> sys.maxunicode
>1114111
>```
>**56）sys.meta_path**
> - 保存了一系列 importer 对象的list。
> - 与sys.path_hooks是两种不同的hook。
> - 有以下三个 importer:
>
>importer|用途
>:--:|:--:
>class ‘_frozen_importlib.BuiltinImporter’|查找及导入build-in模块
>class ‘_frozen_importlib.FrozenImporter|查找及导入frozen模块(即已编译为Unix可执行文件的模块)
>class ‘_frozen_importlib.PathFinder’|查找及导入import path中的模块。
>```
>>>> sys.meta_path
>[<class '_frozen_importlib.BuiltinImporter'>, <class '_frozen_importlib.FrozenImporter'>, <class '_frozen_importlib_external.PathFinder'>]
>```
>**57）sys.modules**
> - 一个字典将模块名称映射到已加载的模块。
> - 它可以被修改来强制重新加载模块和其他技巧。
> - 然而，替换字典将不一定按预期工作，删除从字典中的必要项目可能会导致Python失败。
>```
>>>> import os
>>>> sys.modules['os']
><module 'os' from '/home/ubuntu/anaconda3/lib/python3.7/os.py'>
>```
>**58）sys.path**
> - 指定用于模块搜索路径的字符串列表。
> - 它根据环境变量PYTHONPATH进行初始化，再加上安装时的默认值。
>```
>>>> sys.path
>['', '/home/ubuntu/anaconda3/lib/python37.zip', '/home/ubuntu/anaconda3/lib/python3.7', '/home/ubuntu/anaconda3/lib/python3.7/lib-dynload', '/home/ubuntu/anaconda3/lib/python3.7/site-packages']
>```
>**59）sys.path_hooks**
> - 一个可调用对象的列表，它们以一个路径为参数并为该路径创建一个finder。
> - 与meta hook(sys.meta_path)是两种不同的hook。
>```
>>>> sys.path_hooks
>[<class 'zipimport.zipimporter'>, <function FileFinder.path_hook.<locals>.path_hook_for_FileFinder at 0x7f1d590c13b0>]
>```
>**60）sys.path_importer_cache**
> - 一个字典，作为finder对象的缓存。
> - 字典的键是传递给sys.path_hooks的路径，对应的值是找到的查找器。
>```
>>>> sys.path_importer_cache
>{'/home/ubuntu/anaconda3/lib/python37.zip': None, '/home/ubuntu/anaconda3/lib/python3.7': FileFinder('/home/ubuntu/anaconda3/lib/python3.7'), '/home/ubuntu/anaconda3/lib/python3.7/encodings': FileFinder('/home/ubuntu/anaconda3/lib/python3.7/encodings'), '/home/ubuntu/anaconda3/lib/python3.7/importlib': FileFinder('/home/ubuntu/anaconda3/lib/python3.7/importlib'), '/home/ubuntu/anaconda3/lib/python3.7/lib-dynload': FileFinder('/home/ubuntu/anaconda3/lib/python3.7/lib-dynload'), '/home/ubuntu/anaconda3/lib/python3.7/site-packages': FileFinder('/home/ubuntu/anaconda3/lib/python3.7/site-packages'), '/home/ubuntu': FileFinder('/home/ubuntu')}
>```
>**61）sys.platform**
> - 此字符串包含一个平台标识符。
> - 可用于平台相关的组件追加到sys.path。
> - 平台标识符对应：
>
>系统|平台值
>:--:|:--:
>AIX|'aix'
>Linux|'linux'
>Windows|'win32'
>Windows/Cygwin|'cygwin'
>macOS|'darwin'
>```
>>>> sys.platform
>'linux'
>```
>**62）sys.prefix**
> - python文件的安装路径。
>```
>>>> sys.prefix # Linux下
>'/home/ubuntu/anaconda3'
>
>>>> sys.prefix #Windows下
>'D:\\Python3.7' 
>```
>**63）sys.ps1和sys.ps2**
> - 解释器的主提示符和次提示符。
> - 它们只在解释器的交互模式中定义。
>- 它们的初始值是'>>> '和'... '。
>```
>>>> sys.ps1
>'>>> '
>>>> sys.ps2
>'... '
>```
>**64）sys.setdlopenflags(<n>)**
> - 设置解释器调用dlopen()的标志，例如解释器如何加载扩展模块。
> - 只能在Unix平台使用。
>```
>>>> sys.setdlopenflags(1)
>>>> sys.getdlopenflags() 
>1
>```
>**65）sys.setprofile(<profilefunc>)**
> - 设置系统配置函数,用于实现源代码配置程序
>```
>>>> def test(*args):
>     print("args="+str(list(args))) 
>>>> sys.setprofile(test)
>args=[<frame at 0x7fa45c975050, file '<stdin>', line 1, code <module>>, 'return', None]
>>>> sys.getprofile()
>```
>**66）sys.setrecursionlimit(<limit>)**
> - 设置Python解释器的堆栈最大深度为<limit>。
> - 该限制可防止无限递归导致C堆栈溢出和Python崩溃。
> - 最高可能的限制取决于平台。
>```
>>>> sys.setrecursionlimit(999)
>>>> sys.getrecursionlimit()
>999
>```
>**67）sys.setswitchinterval(<interval>)**
> - 设置解释器的线程切换间隔为<interval>
> - 以秒为单位。
>```
>>>> sys.getswitchinterval()
>0.005
>>>> sys.setswitchinterval(0.001)
>>>> sys.getswitchinterval()
>0.001
>```
>**68）sys.settrace(<tracefunc>)**
> - 设置全局跟踪调试函数，它允许你在Python中实现Python源代码调试器。
> - 跟踪函数应具有三个参数：frame、event 和arg。
> - frame 是当前的堆栈帧。
> - event 返回一个字符串，包含：
>
>字符串|含义
>:--|:--
>'call'|正在调用一个函数（或者进入其它代码块）。将调用全局跟踪函数；arg 为None；返回值表示局部跟踪函数。
>'line'|解释器将执行一行新的代码或者重新执行循环的条件。将调用局部跟踪函数；arg 为None；返回值表示新的局部跟踪函数。它是如何工作的详细解释请参阅Objects/lnotab_notes.txt。
>'return'|有个函数（或者代码块）即将返回。将调用局部跟踪函数；arg 是即将返回的值；如果事件是由正在引发的异常引起的则返回None。跟踪函数的返回值将被忽略。
>'exception'|出现了一个异常。将调用局部的跟踪函数；arg 为一个元组(exception, value, traceback)；返回值表示新的局部跟踪函数。
>'c_call'|一个C函数即将被调用。这可以是扩展函数或内建。arg 为该C函数对象。
>'c_return'|返回了C函数。arg 为该C函数对象。
>'c_exception'|C函数引发了异常。arg 为该C函数对象。
>```
>>>> def test(*args):
>>>>   print('args:'+str(args))
>>>> sys.settrace(test)
>>>> test() # 调用时触发trace
>args:(<frame at 0x7f358326f530, file '<stdin>', line 1, code <module>>, 'call', None)
>args:(<frame at 0x7f3583394e50, file '<stdin>', line 1, code test>, 'call', None)
>args:()
>```
>**69）sys.set_asyncgen_hooks(<firstiter>, <finalizer>)**
> - 设置一个异步生成器的对象。
> - <firstiter>：一个可调用的方法，当第一次迭代异步生成器时将调用它。
> - <finalizer>：一个可调用的方法，当异步生成器即将被 GC 时将被调用。
>```
>>>> import sys
>>>> def firstiter():
>>>>     print('from firstiter.') 
>>>> def finalizer():
>>>>     print('from finalizer.')
>>>> sys.set_asyncgen_hooks(firstiter,finalizer)
>>>> sys.get_asyncgen_hooks()
>asyncgen_hooks(firstiter=<function firstiter at 0x7ff4f39fa0e0>, finalizer=<function finalizer at 0x7ff4f39fa290>)
>```
>**70）sys.set_coroutine_origin_tracking_depth(depth)**
> - 允许启用或禁用协同程序源跟踪。
> - 启用后， cr_origin coroutine对象的属性将包含一个（文件名、行号、函数名）元组，描述创建coroutine对象的回溯，并首先调用最新的调用。
> - 禁用时， cr_origin 为空。
> - 此设置是线程特定的。
>
>**71）sys._enablelegacywindowsfsencoding()**
> - 将默认的文件系统编码和错误模式分别更改为“mbcs”和“replace”。
> - 这相当于定义 PYTHONLEGACYWINDOWSFSENCODING为启动python之前的环境变量。
> - 只能在Windows系统使用。
>```
>>>> sys._enablelegacywindowsfsencoding()
>>>> sys.getfilesystemencoding()
>'mbcs'
>>>> sys.getfilesystemencodeerrors()
>'replace'
>```
>**72）sys.stdin**
> - Python解释器的标准输入,一般指键盘输入到缓冲区里的东西。
> - 可以通过修改sys.stdin临时改变输入源。
>```
>>>>input = sys.stdin.readline()
>>>>Hello World!
>>>>input
>'Hello World!\n'
>```
>**73）sys.stdout**
> - Python解释器的标准输出。
> - 可以通过修改sys.stdout临时改变输出目标。
>```
>>>> output = sys.stdout.write
>>>> output('Hello World')
>Hello World11
>```
>**74）sys.stderr**
> - Python解释器的标准错误信息。
> - 可以通过修改sys.stdout临时改变错误信息输出目标。
>```
>>>> err = sys.stderr.write
>>>> err('WARNING: something bad occur!')
>29
>WARNING: something bad occur!
>```
>**75）\_\_sys.stdin__、\_\_sys.stdout__和\_\_sys.stderr__**
> - 包含了以上三个方法的初始值。
> - 即使以上三个方法被重新定向，也可以通过他们恢复。
>
>**76）sys.thread_info**
> - 包含线程的信息。
> - 信息包括：
>
>属性|说明
>:--|:--
>name|线程实现的名称：'nt': Windows 线程、'pthread': POSIX 线程、'solaris': Solaris 线程
>lock|锁实现的名称：'semaphore': 锁使用信号量、'mutex+cond': 锁使用互斥和条件变量、None 如果此信息未知
>version|线程库的名称和版本。它是一个字符串，如果此信息未知，则为 None 。
>```
>>>> sys.thread_info
>sys.thread_info(name='pthread', lock='semaphore', version='NPTL 2.23')
>```
>**77）sys.tracebacklimit**
> - 当此变量设置为整数值时，它将确定在发生未处理的异常时打印的跟踪信息的最大级别数。
> - 默认值为 1000 .当设置为 0 或者更少，抑制所有的回溯信息，只打印异常类型和值。
>```
>>>> 1/0
>Traceback (most recent call last):
>  File "<stdin>", line 1, in <module>
>ZeroDivisionError: division by zero
>
>>>> sys.tracebacklimit = 0 # tracebacklimit设置为0后
>>>> 1/0
>ZeroDivisionError: division by zero
>```
>**78）sys.unraisablehook(<unraisable>, /)**
> - 处理python没办法处理的异常。
> - <unraisable>参数具有以下属性：
> 
> 属性|含义
>:--:|:--:
>exc_type |异常类型。
>exc_value |异常值，可以是 None .
>exc_traceback |异常回溯，可以是 None .
>err_msg |错误消息，可以是 None .
>对象 |导致异常的对象，可以是 None .
>**79）sys.version**
> - 一个字符串，包含Python解释器的版本号以及有关内部版本号和所用编译器的其他信息。
>```
>>>> sys.version
>'3.8.0 (default, Nov  6 2019, 21:49:08) \n[GCC 7.3.0]'
>```
>**80）sys.api_version**
> - 此解释器的C API版本。
> - 在调试Python和扩展模块之间的版本冲突时很有用。
>```
>>>> sys.api_version
>1013
>```
>**81）sys.version_info**
> - 包含版本号的五个组件的元组。
> - 组件包括： major, minor, micro, releaselevel, 和 serial。
>```
>>>> sys.version_info
>sys.version_info(major=3, minor=8, micro=0, releaselevel='final', serial=0)
>```
>**82）sys.warnoptions**
> - Warning框架的实现细节。
> - 不要修改此值。
>```
>>>> sys.warnoptions
>[]
>```
>**83）sys.winver**
> - 用于在Windows平台上形成注册表项的版本号。
> - 只能在Windows系统使用。
>```
>>>> sys.winver
>'3.8'
>```
>**84）sys._xoptions**
> - 通过 -X 命令行选项传递的各种实现特定标志的字典。
> - 如果显式给定，则选项名要么映射到它们的值，要么映射到 True。
>```
>$ ./python -Xa=b -Xc
>Python 3.2a3+ (py3k, Oct 16 2010, 20:14:50)
>[GCC 4.4.3] on linux2
>Type "help", "copyright", "credits" or "license" for more information.
>>>> import sys
>>>> sys._xoptions
>{'a': 'b', 'c': True}
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
![梦幻微武侠](https://upload-images.jianshu.io/upload_images/19742364-0b165e9d9cf51f71.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
