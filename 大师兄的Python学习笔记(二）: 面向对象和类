## 三、面向过程和面向对象的思维方式
##### 1.面向过程（Proceduce Oriented）
> - 如果想吃西红柿炒鸡蛋:
> **step1: 打鸡蛋**
> **step2: 切西红柿**
> **step3: 热锅**
> **step4: 炒鸡蛋**
> **step5: 炒西红柿**
> **step6: 放盐**
> **step7: 出锅**
>
> - 这种把任务切分成一系列子工作，自顶向下一步一步实现的方式叫做**面向过程**。
##### 2. 面向对象（Object Oriented）
> - 如果想吃西红柿炒鸡蛋：
> **step1: 设计一个饭馆的蓝图（类）**
> 饭馆包含食材：西红柿、鸡蛋
> 饭馆包含调料：盐
> 饭馆包含炊具：锅
> 饭馆包含功能：炒菜
> **step2: 根据蓝图建造一个饭馆（对象）**
> **step3: 点西红柿炒鸡蛋这道菜**
> - 这里我们实际上是将制作西红柿炒鸡蛋的过程封装到对象饭馆中。
> - 吃饭的人只需要对厨房下达命令，至于功能的实现方式则不用关心。
> - 这种将功能抽象封装的方式叫做**面向对象**。
##### 3.面向对象的优缺点
> **1）易复用**
> 建立厨房后，如果为一万人提供西红柿炒鸡蛋，我们只需要下达一万次命令即可，不用重复造轮子。
> **2）易维护**
> 如果想吃黄瓜炒鸡蛋，只需将食材中的西红柿替换成黄瓜，不用重新设计整个流程。
>  **3）易扩展**
> 如果想吃西红柿鸡蛋盖饭，只需要增加食材大米和蒸饭的功能，而并不需要重建一个厨房。
>  **4）缺点：性能低于面向过程**
> 如果只是一个人吃饭，盖饭馆就很浪费。
##### 4.总结
>  **1）面向过程适合简单、少量的任务。**
>  **2）面向对象适合复杂、大量的任务。**
>  **3）面向对象并不能取代面向过程，面向对象的最底层是面向过程。**
# 四、类和对象
##### 1.类
> - 类就是具备某些共同特征的实体的集合,它是一种抽象的数据类型,它是对所具有相同特征实体的抽象。
> - 比如：西红柿和鸡蛋都属于食材，食材是个抽象的概念，是一个类。
##### 2.对象
> - 对象是具体的事物，单个的个体。
> - 比如：西红柿和鸡蛋可以是对象、盐和锅可以是对象、西红柿炒鸡蛋可以是对象，厨房也可以是对象。
##### 3.类和对象的关系
> 类是对象的概括，对象是类的具体体现
# 五、在Python中实现类和对象
##### 1.类的声明
> - 用class关键字。
> - 类的成员只可以是属性或方法。
> - 属性可以看理解为类中的变量。
> - 方法可以看理解为类中的函数。
>```
>class <类名>():
>      <类的成员> # 这里必须有缩进
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  # 属性
>>>>    def cut():   # 方法
>>>>        print('我被切成片了！')    
>```
##### 2.类的实例化
> - 也就是将类实例化成为对象
>```
><变量> = <类名>()
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  # 属性
>>>>    def cut():   # 方法
>>>>        print('我被切成片了！')    
>>>>tomato = FoodMaterial() # 这里将类实例化后存储在变量中
>```
##### 3. 访问类和对象的成员
> **1）访问类的属性和调用方法**
>```
>方法一:
><类名>.<属性名> # 访问属性
><类名>.<方法名>() # 调用方法
>方法二：
>getattr(<类名>,"<属性名>")
>getattr(<类名>,"<方法名>")()
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  
>>>>    def cut():   
>>>>        print('我被切成片了！')    
>>>>print(FoodMaterial.price) # 访问属性
>>>>10
>>>>FoodMaterial.cut() # 调用方法
>>>>我被切成片了！
>```
>**2） 访问对象的属性和方法**
>```
>方法一:
><对象名>.<属性名> # 访问属性
><对象名>.<方法名>() # 调用方法
>方法二：
>getattr(<对象名>,"<属性名>")
>getattr(<对象名>,"<方法名>")()
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  
>>>>    def cut(self):   # self我们后面说
>>>>        print('我被切成片了！')    
>>>>tomato = FoodMaterial() 
>>>>print(tomato.price) # 访问属性
>>>>10
>>>>tomato.cut() # 调用方法
>>>>我被切成片了！
>```
##### 4. 修改类和对象的属性
> **1）修改类的属性**
>```
>方法一:<类名>.<属性名> = <值> # 修改类属性
>方法二:setattr(<类名>,"<属性名>",<值>)
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  
>>>>tomato = FoodMaterial()
>>>>FoodMaterial.price = 20
>>>>print(FoodMaterial.price)
>20
>>>>print(tomato.price) # 这时对象的属性也跟着改变了
>20
>```
> **2）修改对象的属性**
> - 如果对象的属性被修改过，就不会跟着类的属性同步了。
>```
>方法一:<对象名>.<属性名> = <值> # 修改对象属性
>方法二:setattr(<对象名>,"<属性名>",<值>)
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  
>>>>tomato = FoodMaterial()
>>>>tomato.price = 20
>>>>print(tomato.price)
>20
>>>>print(FoodMaterial.price) # 这时类的属性并没有改变
>10
>>>>FoodMaterial.price = 30 # 如果这时我们再修改类的属性
>>>>print(tomato.price) # 对象的属性不会再跟着改变
>20
>```
##### 5. 增加类和对象的属性
> **1）增加类的属性**
>```
>方法一:<类名>.<属性名> = <值> 
>方法二:setattr(<类名>,"<属性名>",<值>)
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  
>>>>tomato = FoodMaterial()
>>>>FoodMaterial.colour = 'red'
>>>>print(FoodMaterial.colour)
>red
>>>>print(tomato.colour) # 这时对象的属性也跟着增加了
>red
>```
> **2）增加对象的属性**
>```
>方法一:<对象名>.<属性名> = <值> # 增加对象属性
>方法二:setattr(<对象名>,"<属性名>",<值>)
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  
>>>>tomato = FoodMaterial()
>>>>tomato.colour = 20
>>>>print(tomato.colour)
>red
>>>>print(FoodMaterial.colour) # 这时类的属性并没有增加
>AttributeError: type object 'FoodMaterial' has no attribute 'colour'
>>>>FoodMaterial.colour = 'yellow' # 如果这时我们再修改类的属性
>>>>print(tomato.colour) # 对象的属性不会改变
>red
>```
##### 6. 删除类和对象的属性
> **1）删除类的属性**
>```
>方法一:del <类名>.<属性名>  # 删除类属性
>方法二:delattr(<类名>,"<属性名>")
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  
>>>>    colour = 'red'
>>>>tomato = FoodMaterial()
>>>>del FoodMaterial.price
>>>>print(FoodMaterial.price) # 删除属性
>AttributeError: type object 'FoodMaterial' has no attribute 'price'
>>>>print(tomato.colour) # 这时对象的属性也被删除了
>AttributeError: type object 'FoodMaterial' has no attribute 'price'
>```
> **2）删除对象的属性**
>- 从下面的例子就可以看出，对象的属性在没有单独定义的情况下，实际上是调用了类的属性
>- 如果单独为对象创建属性，在属性名相同的情况下，优先调用对象的属性
>```
>方法一:del <对象名>.<属性名> # 删除对象属性
>方法二:delattr(<对象名>,"<属性名>")
>```
>```
>>>>class FoodMaterial():
>>>>    price = 10  
>>>>    colour = 'red'
>>>>tomato = FoodMaterial()
>>>>del tomato.price # 这里会提示tomato并没有price属性，实际上是调用的FoodMaterial得price属性
>AttributeError: price
>
>>>>tomato.price = 20 # 为对象增加属性
>>>>print(tomato.price) # 覆盖了类的属性
>20
>>>>del tomato.price # 删除了对象的属性
>>>>print(tomato.price) # 这里又调用了类的属性
>10
>
>>>>del FoodMaterial.price # 如果这时我们将类的属性也删除掉
>>>>print(tomato.price) # 无法调用属性，所以报错了
>AttributeError: 'FoodMaterial' object has no attribute 'price'
>```

##### 7.关于self
> - self是类和对象中的特一个特殊的参数，代表类本身。
> - self只在类和对象中存在。
> - self不需要赋值。
> - self是类中默认的第一个参数。
> - 其实self并不是系统指定的关键字，他可以叫任何名字，只要他是类中的第一个参数就可以。
> **1）在类中使用self参数**
>- 很少直接使用类中的self参数
>```
>>>>class FoodMaterial():
>>>>    def cut(self) :
>>>>        print('我被切成片了！')
>>>>FoodMaterial.cut(FoodMaterial) # 这时需要将类自身作为参数返回，不然会报错。
>我被切成片了！
>```
>- 因为对象也属于类，所以可以用对象作为self参数。但是这种用法比较奇葩，不推荐使用。
>```
>>>>class FoodMaterial():
>>>>    def cut(self) :
>>>>        print('我被切成片了！')
>>>>tomato = FoodMaterial()
>>>>FoodMaterial.cut(tomato) # 这里将方法当做参数代表类本身，也可以正常运行
>我被切成片了！
>```
> - 如果不使用self名称，也没有任何区别，但不推荐这样使用。
>```
>>>>class FoodMaterial():
>>>>    def cut(somethingbutnotself) : # 证明self并不是关键字
>>>>        print('我被切成片了！')
>>>>FoodMaterial.cut(FoodMaterial) 
>我被切成片了！
>```
>**2）在对象中使用self参数**
>- 在调用对象方法时，会默认将自身作为第一个参数返回。所以如例(3.2)中，如果在没有为方法添加self参数，而直接用对象中的该方法会报错。
>```
>>>>class FoodMaterial():
>>>>    def cut() :
>>>>        print('我被切成片了！')
>>>>tomato = FoodMaterial()
>>>>tomato.cut() # 这里会提示传入了一个参数，但是cut()不需要传入参数
>TypeError: cut() takes 0 positional arguments but 1 was given
>
>>>># 正确的调用方式
>>>>class FoodMaterial():
>>>>    def cut(self) :
>>>>        print('我被切成片了！')
>>>>tomato = FoodMaterial()
>>>>tomato.cut() # tomato会默认将自身作为第一个参数传入方法
>我被切成片了！
>```
>- 在对象中self改变了变量和函数的作用域，成为对象内的全局变量。
>```
>>>>class FoodMaterial():
>>>>    def __init__(self): # __init__是魔法函数，这里可以先理解为一个在对象创建时自动执行的方法。
>>>>        self.price = 10 # 这里self.price成为对象内的全局变量
>>>>    def getPrice(self) :
>>>>        print('我的价格是:{price}'.format(price=self.price)) # 调用了方法内的变量self.price，证明其作用域是全局
>>>>tomato = FoodMaterial() 
>>>>tomato.getPrice()
>我的价格是:10
##### 8.Python中的构造函数
> - 构造函数是一种特殊的方法，用来在创建对象时为对象赋值。
> - Python中构造函数的方法是: ```def __init__(self,arg1,arg2)```
> - 构造函数只能调用一次，就是在创建类的时候调用
> - \_\_init\_\_ 其实是一个魔法函数，后面会介绍。
>```
>>>>class FoodMaterial():
>>>>    def __init__(self,price,colour): # 构造函数，参数在创建类时需要提供
>>>>          self.price = price 
>>>>          self.colour = colour
>>>>          self.show() # 在创建类时就要执行的方法
>>>>    def show(self):
>>>>          print(self.price)
>>>>          print(self.colour)
>>>>tomato = FoodMaterial(price=10,colour='red') # 这里并没有再专门调用show()，在创建时就自动执行了。
>10
>red
>
>>>>print(FoodMaterial.price) # 直接用类访问不到构造函数中的成员，因为构造函数只在创建对象时执行。
>AttributeError: type object 'FoodMaterial' has no attribute 'price'
>```

# 六、面向对象的三大特征
> - 封装
>- 继承
>- 多态
##### 1. 封装
> - 封装就是对对象的成员进行访问限制，是为了保护私隐，明确区分内外。
> - 封装的级别分为：**公开(public)、受保护的(protected)、私有的(private)**
> - 与Java不同，Python中没有public，private，protected的关键字
> - Python中的封装并不是严格的语法，更像是一种规范。
>
> **1）公开的(public)**
> 公共的封装实际对成员没有任何操作，任何地方都可以访问。
> **2）受保护的(protected)**
> - 受保护的成员名称前增加一个下划线_。
> - 受保护的封装在类中或者子类中都可以访问，但在外部不允许访问。
> - 我测试受保护的成员实际上是可以直接访问的，应该只是一种书写规范，希望有人可以指正我。
>```
> _<受保护的成员名>
>```
>```
>>>>class FoodMaterial():
>>>>    _price = 10 # 受保护的属性
>>>>    def _getPrice(self) : # 受保护的方法
>>>>        print('我的价格是:{price}'.format(price=self.price)) 
>```
> **3）私有的(private)**
> - 私有员名称前增加两个划线__。
> - 私有成员只能在当前类或对象中访问。
> - Python中的私有实现方式是一种被称为name mangling的障眼法。
>```
> __<私有的成员名>
>```
>```
>>>>class FoodMaterial():
>>>>    __price = 10 # 私有的属性
>>>>    def __getPrice(self) : # 私有的方法
>>>>        print('我的价格是:{price}'.format(price=self.__price)) 
>>>>tomato = FoodMaterial() # 实例化
>>>>print(tomato.__price) # 注意，这里的报错是：不存在这个值!。
>AttributeError: 'FoodMaterial' object has no attribute '__price'
>>>>tomato.__getPrice()
>AttributeError: 'FoodMaterial' object has no attribute '__getPrice'
>```
> - 用魔法函数```__dict__```查看类的全部成员，可以看出私有成员实际是被改名为：```_<类名>__<成员名> ```
>```
>>>>print(FoodMaterial.__dict__)
>>>>mappingproxy({'__module__': '__main__',
>>>>              '_FoodMaterial__price': 10, # 这里可以看到被改名了
>>>>              '_FoodMaterial__getPrice': <function __main__.FoodMaterial.__getPrice(self)>,
>>>>              '__dict__': <attribute '__dict__' of 'FoodMaterial' objects>,
>>>>              '__weakref__': <attribute '__weakref__' of 'FoodMaterial' objects>,
>>>>              '__doc__': None})
>
>>>>print(tomato._FoodMaterial__price) # 试着访问改名后的成员
>10
>>>>print(tomato._FoodMaterial__getPrice())
>我的价格是:10
>```
##### 2. 继承
> **1）继承的作用：**
> - 继承就是一个类可以获得另外一个类中的成员属性和成员方法。
> - 继承可以减少代码，增加代码的复用功。
> - 继承可以建立类与类直接的关系。
>
> **2）继承与被继承的概念：**
> - 被继承的类叫父类，也叫基类，也叫超类。
> - 用于继承的类，叫子类，也叫派生类。
> - 所有的类全都是object的子类，继承时如果不特别指定父类，将默认继承object类。
>
> **3）继承的语法**
>``` 
>class <子类名>(<父类名>):
>          <类的内容> 
>```
>```
>>>># 父类
>>>>class Dog(object): # 这里不写object也会默认继承object
>>>>    type = 'dog'
>>>>    legs = 4
>>>>    def bark(self):
>>>>         print('汪汪!')
>
>>>># 子类
>>>>class Schnauzer(Dog): # schnauzer继承了dog类
>>>>     sub_type = 'schnauzer'
>```
>**4）继承的特性**
>- 子类一旦继承父类，则可以使用父类中除私有成员外的所有内容。
>- 子类继承父类后并没有将父类成员完全赋值到子类中，而是通过引用关系访问调用。
>- 子类中可以定义独有的成员属性和方法。
>- 子类中定义的成员和父类成员如果相同，则优先使用子类成员。
>```
>>>># 父类
>>>>class Dog(object): # 这里不写object也会默认继承object
>>>>    type = 'dog'
>>>>    def bark(self):
>>>>         print('汪汪!')
>>>>    def __showLegs(self): # 私有成员不会被继承
>>>>         print(4)
>
>>>># 子类
>>>>class Schnauzer(Dog): # schnauzer继承了dog类
>>>>     sub_type = 'schnauzer'
>>>>     def bark(self): # 这里覆盖了父类的方法
>>>>          print('嗷嗷1')
>>>>qq = Schnauzer()
>
>>>>print(qq.type) # 继承了父类的属性
>'dog'
>
>>>>print(qq.bark()) # 同名时首先引用了自己的方法
>嗷嗷!
>
>>>>print(qq.sub_type) # 有了自己的属性
>'schnauzer'
>
>>>>print(qq.__showLegs()) # 私有变量不会被继承
>AttributeError: 'schnauzer' object has no attribute '__showLegs'
>```
>**5）super函数**
> - super()函数用于调用父类的一个方法。
> -  ```super().<父类方法名>() = <父类名>.<父类方法名>()```
>```
>self(<父类名>,self).<方法名>(参数) # 意思是将父类的方法转换为自己的方法。
>self().<方法名>(参数) # python3.0中可以省略self()中的内容，但多重继承中还是需要。
>```
>```
>>>># 父类
>>>>class Dog(): 
>>>>    def bark(self):
>>>>         print('汪汪!')
>
>>>># 子类
>>>>class Schnauzer(Dog): # schnauzer继承了dog类
>>>>    def barkTwice(self): 
>>>>         super().bark() # 这里调用了父类的方法
>>>>         print('嗷嗷!')
>>>>qq = Schnauzer()
>>>>qq.barkTwice()
>汪汪!
>嗷嗷!
>```
>**6）继承的顺序**
> - 优先查找自己的函数
> - 没有则查找父类
> - 如果父类没有则查找父类的父类
>```
>>>># 父类
>>>>class Dog(): 
>>>>    type = 'dog'
>
>>>># 子类
>>>>class Schnauzer(Dog): 
>>>>    pass
>
>>>># 孙类
>>>>class BabySchnauzer(Schnauzer): 
>>>>    pass
>
>>>>qq = BabySchnauzer()
>>>>print(qq.type) # 继承了祖父类的属性s
>'dog'
>```
>**7）继承构造函数**
> - 如果定义了构造函数，则实例化时使用构造函数。
> - 如果没定义，则自动查找父类构造函数。
> - 如果重写了构造函数，还要继承父类的构造方法，可以使用 super()方法。 
>```
>>>># 父类
>>>>class Dog(): 
>>>>    def __init__(self，legs):
>>>>        self.type = 'dog'
>>>>    def fatherType(self):
>>>>        print('father type is {type}'.format(type=self.type))
>
>>>># 子类
>>>>class Schnauzer(Dog): 
>>>>     def __init__(self,legs):
>>>>         super().__init__(self,legs) # 这里调用了父类的构造函数，将参数传入
>>>>     def sonType(self):
>>>>         print('son type is {type}'.format(type=self.type))
>
>>>>qq = Schnauzer(4)
>>>>qq.sonType()
>son type is dog
>>>>qq.fatherType() # 将参数传给父类的方法，并调用方法
>father type is dog
>```
>**8）多继承**
> - 多继承就是子类同时继承多个类,方法是：```def <子类名>(<父类一>,<父类二>):```
> - 如果两个父类的属性相同，则继承写在前面的父类。
> - 可以通过inspect.getmro(<类名>)查看类的MRO列表（继承顺序）
>```
>>>># 父类一·
>>>>class Human():
>>>>    type = 'human'
>>>>    def introHuman(self):
>>>>          print('i am human!')
>
>>>>class Fish():
>>>>    type = 'fish'
>>>>    def introFish(self):
>>>>          print('i am fish!')
>
>>>>class Fishman(human,fish): # 多个父类
>>>>    pass
>>>>f = Fishman()
>
>>>>print(f.introHuman()) # 同时继承了两个父类的方法
>i am human!
>>>>print(f.introFish())
>i am fish!
>
>>>>print(f.type) # 属性名相同则继承前面的父类
>human
>
>>>>import inspect # 导入inspect包
>>>>inspect.getmro(fishman) # 查看fishman类的mro
>(__main__.fishman, __main__.human, __main__.fish, object)
>```
> - 单继承和多继承的对比:
>
>  /|单继承 | 多继承
>  :--:|:--:|:--:
> 优点|传承有序逻辑清晰语法简单隐患少 | 类的功能扩展方便
> 缺点|功能扩展性受父类限制 |  继承关系混乱
> - **经典钻石继承问题：**当一个孙类同时继承多个父类，而这些父类又继承同一个祖父类时，如果孙类同时继承多个父类的构造函数，祖父类构造函数会被初始化多次。
>```
> # 祖父类
>>>>class Grandpa(object):
>>>>    def __init__(self):
>>>>        print('from grandpa')
> # 父类1
>>>>class Dad1(Grandpa):
>>>>    def __init__(self):
>>>>        grandpa.__init__(self)
>>>>        print('from dad1')
> # 父类2
>>>>class Dad2(Grandpa):
>>>>    def __init__(self):
>>>>        grandpa.__init__(self)
>>>>        print('from dad2')
> # 子类
>>>>class Son(Dad1, Dad2):
>>>>    def __init__(self):
>>>>        dad1.__init__(self) 
>>>>        dad2.__init__(self) # 同时调用两个父类的构造函数
>>>>        print('from son')
>
>>>>s = Son()
>from grandpa
>from dad1
>from grandpa
>from dad2
>from son
>```
> - 钻石继承问题解决方案：使用super()函数
>```
> # 祖父类
>>>>class Grandpa(object):
>>>>    def __init__(self):
>>>>        print('from grandpa')
> # 父类1
>>>>class Dad1(Grandpa):
>>>>    def __init__(self):
>>>>        super().__init__()
>>>>        print('from dad1')
> # 父类2
>>>>class Dad2(Grandpa):
>>>>    def __init__(self):
>>>>        super().__init__()
>>>>        print('from dad2')
> # 子类
>>>>class Son(dad1, dad2):
>>>>    def __init__(self):
>>>>        super().__init__() #这里同时继承了两个父类的构造函数
>>>>        print('from son')
>
>>>>s = Son() # 这里祖父类只调用了一次
>from grandpa
>from dad1
>from dad2
>from son
>```
##### 3. 多态
>**1）理解多态**
> - 首先要理解创建一个类就是创建了一种数据类型，和list,dict是一样的。
>```
>>>>a = list()
>>>>type(a) 
>list
>>>>isinstance(a,list) # a 属于list类型
>True
>
>>>>class Animal():
>>>>    pass
>>>>dog = Animal()
>>>>type(dog)
>__main__.Animal
>>>>isinstance(dog,Animal)  # dog是animal数据类型
>True
>```
> - 多态是指同一个对象在不同情况下有不同的状态出现。
> - 多态是一种思想，而不是一种语法。
> - 多态增加了程序的灵活性和扩展性。
>```
>>>>class Animal(): # 创造动物的数据类型
>>>>    pass
>
>>>>class Dog(Animal): # 狗属于动物
>>>>    pass
>
>>>>class Cat(Animal): # 猫也属于动物
>>>>    pass
>
>>>>qq = Dog()
>>>>isinstance(qq,Dog)
>True
>>>>isinstance(qq,Animal) # qq即属于狗，也属于动物
>True
>
>>>>mimi = Cat()
>>>>isinstance(mimi,Cat)
>True
>>>>isinstance(mimi,Animal) # mimi即属于猫，也属于动物
>True
>```
>**2）多态性**
>- 指具有不同功能的函数可以使用相同的函数名，这样就可以用一个函数名调用不同内容的函数。
>- 多态性是一钟调用方式，
>```
>>>>class Animal():
>>>>    def talk(self):
>>>>        pass
>
>>>>class Human():
>>>>    def talk(self):
>>>>        print('你好！')
>
>>>>class Dog():
>>>>    def talk(self):
>>>>        print('汪汪！')
>
>>>>class Cat():
>>>>    def talk(self):
>>>>        print('喵喵！')
>
>>>> ppl = Human()
>>>> pp = Dog()
>>>> mimi = Cat()
>
>>>> Human.talk()
>你好！
>>>> Dog.talk()
>汪汪！
>>>> Cat.talk()
>喵喵！
>```
>**3）mixin模式**
> - mixin模式通过多继承来实现，子类通过继承Mixin类获得一种功能。
> - Mixin类用```<类名 + Mixin>```的方式起名，但这不是语法，而是告诉后来读代码的人，这是一个Mixin类。
> - 一个Mixin类可以理解为一种功能，且只能是一种功能，如果有多个功能则创建多个Mixin类。
> - Mixin不能依赖于子类的实现
> - 子类及时没有继承这个Mixin类， 也能照样工作，只是缺少了某个功能
>```
>>>>class Animal():
>>>>    pass
>
>>>>class FlyMixin():  # Mixin类
>>>>    def fly(self):
>>>>        print('I can fly!')
>
>>>>class Bird(Animal,FlyMixin): # 鸟既是动物，也能飞
>>>>    pass
>
>>>>kiki = Bird() # kiki作为bird类，获得了fly能力
>>>>kiki.fly()
>I can fly!
>```
>**4）mixin模式的优点**
> - 使用Mixin可以在不对类进行任何修改的情况下，扩充功能
> - 可以方便的组织和维护不同功能组件的划分
> - 可以根据需要任意调整功能类的组合
> - 可以避免创建很多新的类，导致类的继承混乱
# 七.类的成员描述符
>(这里如果暂时看不懂请先看下一章魔法函数）
> - 类的成员描述符是为了在类中，对类的成员属性进行相关操作而创建的一种方式，大部分属于数据清洗。
> - 属性有三种操作：get获取属性值、set修改或添加属性、delete删除属性。
> - 实现成员描述符包括三种方法：**描述器、属性修饰符、property函数**。
##### 1. 描述器
> - 一个类只要实现了\_\_get\_\_，\__set\_\_，\_\_delete\_\_中任意一个方法，我们就可以叫它描述器
> - 如果仅仅实现了\_\_get\_\_.就是非数据描述器 non-data descriptor
> - 同时实现了\_\_get\_\_,\_\_set\_\_,就是数据描述器 data descriptor
>
> **1）\_\_get\_\_**
>不管是类还是实例去访问，默认都获得的是\_\_get\_\_的返回值，但是，如果中间有任何一次重新赋值，那么，这个实例获得的是新的值(对象)，已经和原来的描述器完全脱离了关系。
>```
>>>>class Tomato():
>>>>   def __get__(self,obj,cls):
>>>>       print('here inside __get__ !')
>
>>>>class MyClass():
>>>>    t = Tomato() #类或实例默认获得__get__的返回值
>>>>m = MyClass()
>>>>m.t # 调用了__get__
>here inside __get__ !
>```
> **2）\_\_set\_\_**
> 后期通过实例对描述器进行赋值，那么访问的是\_\_set\_\_，并且永远关联起来。但是如果通过修改类属性的方式复制，那么也会被重新获取新的值(对象)。
>```
>>>>class Tomato():
>>>>   def __set__(self,obj,cls):
>>>>       print('here inside __set__ !')
>
>>>>class MyClass():
>>>>    t = Tomato() #类或实例默认获得__get__的返回值
>>>>m = MyClass()
>>>>m.t = 'hello' # 赋值时调用__set__
>here inside __set__ !
>```
> **3）\_\_delete\_\_**
>采用del删除属性时,触发\_\_delete\_\_。
>```
>>>>class Tomato():
>>>>   def __delete__(self,obj):
>>>>       print('here inside __delete__ !')
>
>>>>class MyClass():
>>>>    t = Tomato()
>>>>m = MyClass()
>>>>del m.t # 用del删除属性时，触发__delete__
>here inside __delete__ !
>```
##### 2. 属性修饰符
> - 属性修饰符包括：\_\_getattribute\_\_()、\_\_getattr\_\_()、\_\_setattr\_\_()、\_\_delattr\_\_()
>
> **1）\_\_getattribute\_\_()**
>调用属性或方法时,会先强制调用 __getattribute__ 方法,然后再传回属性的值或者是 函数(方法)的引用。
>```
>>>>class Tomato():
>>>>    def __init__(self):
>>>>        name = 'tomato'
>>>>    def __getattribute__(self, item):
>>>>        print('inside __getattribute__!')
>>>>t = Tomato()
>>>>t.name # 调用属性时触发__getattribute__
>inside __getattribute__!
>```
> **2）\_\_getattr\_\_()**
>在实例以及对应的\_\_dict\_\_中查找属性失败，那么会调用\_\_getattr\_\_函数
>```
>>>>class Tomato():
>>>>    def __getattr__(self, item):
>>>>        print('inside __getattr__!')
>>>>t = Tomato()
>>>>t.name # 这里name并不存在，所以触发__getattr__
>inside __getattr__!
>```
> **3）\_\_setattr\_\_()**
>当为类属性赋值时，调用\_\_setattr\_\_()语句
>```
>>>>class Tomato():  
>>>>    def __setattr__(self, item,value):
>>>>        print('inside __setattr__!')
>>>>t = Tomato()
>>>>t.name = 'tomato' # 虽然和上个例子看起来相似，但其实这里时因为赋值触发__setattr__
>inside __setattr__!
>```
> **4）\_\_delattr\_\_()**
>只要使用del语句删除属性,就会调用这个方法
>```
>>>>class Tomato():
>>>>   def __init__(self):
>>>>        self.name = 'tomato'
>>>>   def __delattr__(self, item):
>>>>        print('inside __delattr__!')
>>>>t = Tomato()
>>>>del t.name # 用del删除元素时触发__delattr__
>inside __delattr__!
>```
##### 3. property函数
> - property() 函数的作用是在新式类中返回属性值。
> - 使用语法 ```property(<get方法>,<set方法>,<del方法>,<属性描述>)```。
> - get、set和del方法对应描述器的三个方法。
> - 三个方法的名字可以任意取，但是在property()中要按顺序一一对应。
>```
>>>>class Tomato():
>>>>    def __init__(self):
>>>>        self._name = 'tomato' # 创建protected属性
>>>>    def get_name(self): # 创建属性的get方法
>>>>        print('here inside get_name')
>>>>        return self._name
>>>>    def set_name(self, value): # 创建属性的set方法
>>>>        print('here inside set_name')
>>>>        self._name = value
>>>>    def del_name(self): # 创建属性的del方法
>>>>        print('here inside del_name')
>>>>        del self._name
>>>>    name = property(get_name, set_name, del_name, "I'm the 'name' property.") # 为name属性附加property
>>>>t = Tomato()
>
>>>>print(t.name) # 触发get_name()
>here inside get_name
>'tomato'
>
>>>>t.name = 'Tomato' # 触发set_name()
>here inside set_name
>
>>>>del t.name # 触发del_name()
>here inside del_name
>
>>>>help(t.name) # 触发描述
>here inside get_name
>```
> - 用装饰器实现property(如果对装饰器不熟悉可以先跳过）：
>```
>>>>class Tomato():
>>>>    def __init__(self):
>>>>        self._name = 'tomato' # 创建protected属性
>>>>    @property # 相当于get
>>>>    def name(self): # 创建属性的get方法
>>>>        print('here inside get_name')
>>>>        return self._name
>>>>    @name.setter # 相当于set
>>>>    def set_name(self, value): # 创建属性的set方法
>>>>        print('here inside set_name')
>>>>        self._name = value
>>>>    @name.deleter # 相当于del
>>>>    def del_name(self): # 创建属性的del方法
>>>>        print('here inside del_name')
>>>>        del self._name
>>>>t = Tomato()
>
>>>>print(t.name) # 触发get_name()
>here inside get_name
>'tomato'
>
>>>>t.name = 'Tomato' # 触发set_name()
>here inside set_name
>
>>>>del t.name # 触发del_name()
>here inside del_name
>
>>>>help(t.name) # 触发描述
>here inside get_name
>```
# 八.类的内置属性
> 类包含以下默认内置属性:
>**1）\_\_dict\_\_:以字典的方式显示类的成员组成**
>```
>>>>class FoodMaterial():
>>>>    def __init__(self):
>>>>        self._price = 10 # 受保护的属性
>>>>    def getPrice(self) : # 受保护的方法
>>>>        print('我的价格是:{price}'.format(price=self.price)) 
>>>>print(FoodMaterial.__dict__)
>{'__module__': '__main__', '__init__': <function FoodMaterial.__init__ at 0x000001A9534477B8>, 'getPrice': <function FoodMaterial.getPrice at 0x000001A953447840>, '__dict__': <attribute '__dict__' of 'FoodMaterial' objects>, '__weakref__': <attribute '__weakref__' of 'FoodMaterial' objects>, '__doc__': None}
>
>>>>tomato = FoodMaterial()
>>>>print(tomato.__dict__)
>{'_price': 10}
>```
>**2）\_\_doc\_\_: 获取类的文档信息**
>```
>>>>class FoodMaterial():
>>>>    '''This is class FoodMaterial'''
>>>>    pass
>>>>print(FoodMaterial.__doc__)
>This is class FoodMaterial
>
>>>>tomato = FoodMaterial()
>>>>print(tomato.__doc__)
>This is class FoodMaterial
>```
> **3）\_\_name\_\_:获取类的名称，如果在模块中使用，获取模块的名称**
>```
>>>>class FoodMaterial():
>>>>    pass
>>>>print(FoodMaterial.__name__)
>'FoodMaterial'
>```
> **4）\_\_bases\_\_: 获取某个类的所有父类，以元组的方式显示**
>```
>>>>class Animal():
>>>>    pass
>
>>>>class Baby():
>>>>    pass
>
>>>>class Dog(Animal):
>>>>    pass
>
>>>>class puppy(Dog,Baby):
>>>>    pass
>
>>>>print(puppy.__bases___)
>(__main__.Dog, __main__.Baby)
>```
# 九.魔法函数
> - 魔术方法就是不需要人为调用的方法，基本是在特定的时刻自动触发。
> - [魔法函数大全(没找到很好的中文教程，点击查看英文介绍)。](https://www.python-course.eu/python3_magic_methods.php)
> - 以下是一些常用的魔法函数:
>
>**1）\_\_init\_\_**
>见：构造函数 - 5.8
>**2）\_\_str\_\_**
>当类被打印时，将调用__str__方法的值。
>```
>>>>class Dog(object): # 如果不处理__str__方法
>>>>    pass
>>>>dog = Dog()
>>>>print(dog) 
><__main__.Dog object at 0x000001A953477240>
>
>>>>class Dog(object):
>>>>    def __str__(self):
>>>>        return 'It is a dog!'
>>>>dog = Dog()
>>>>print(dog) # 返回了__str__方法的值
>It is a dog!
>```
>**3）\_\_new\_\_**
> - 初始化对象，在\_\_init\_\_前执行
> - \_\_new\_\_方法包含一个参数，用于传入要实例化的对象
> - \_\_new\_\_方法必须返回一个值，是实例化后的对象
>```
>>>>class Dog(object):
>>>>    def __new__(cls):
>>>>        print(cls)
>>>>        return 1
>>>>dog = Dog() # 调用了print(cls)
><class '__main__.Dog'>
>
>>>>print(dog) # 由于返回值是1，所以Dog变成了1
>1
>>>>type(dog) # 类型也变成了整数
>int
>```
>**4）\_\_call\_\_**
>- 定义后可以将对象当作函数使用。
>```
>>>>class Dog(object):
>>>>    def __call__(self,name):
>>>>        print('{name} is running!'.format(name=name))
>>>>dog = Dog()
>>>>dog('qq') # 调用__call__
>qq is running!
>```
>**5）\_\_len\_\_**
> - 在用len()方法时，会调用\_\_len\_\_方法
>```
>>>>class Dog(object):
>>>>    def __len__(self):
>>>>        print('very very long!')
>>>>dog = Dog()
>>>>len(dog)
>very very long!
>---------------------------------------------------------------------------
>TypeError                                 Traceback (most recent call last)
><ipython-input-100-b3792c81c856> in <module>
>----> 1 len(dog)
>
>TypeError: 'NoneType' object cannot be interpreted as an integer
>```
>**6）\_\_repr\_\_**
>函数str() 用于将值转化为适于人阅读的形式，而repr() 转化为供解释器读取的形式，某对象没有适于人阅读的解释形式的话，str() 会返回与repr()，所以print展示的都是str的格式。
>```
>>>>class Dog(object):
>>>>    def __repr__(self):
>>>>        return 'It is a dog!'
>>>>dog = Dog()
>>>>print(dog) # 返回了__str__方法的值
>It is a dog!
>```
>**7）\_\_setattr\_\_**
>见：类的成员描述符 - 7
>**8）\_\_getattr\_\_**
>见：类的成员描述符 - 7
>**9）\_\_delattr\_\_**
>见：类的成员描述符 - 7
>**10）\_\_getattribute\_\_**
>见：类的成员描述符 - 7
>**11）\_\_del\_\_**
>见：类的成员描述符 - 7
>**12）\_\_getitem\_\_**
> 定义\_\_getitem\_\_方法，就可以用对象像字典一样取值:```key[value]```
>```
>>>>class Dog(object):
>>>>    def __init__(self):
>>>>        self.name = 'dog'
>>>>    def __getitem__(self,key):
>>>>        print('here in __getitem__')
>>>>        return self.name
>>>>dog = Dog()
>>>>print(dog['name']) # 调用了__getitem__方法
>here in __getitem__
>'dog'
>```
>**13）\_\_delitem\_\_**
> 定义\_\_delitem\_\_方法，就可以用对象像字典一样删除值:```del key[value]```
>```
>>>>class Dog(object):
>>>>    def __init__(self):
>>>>        self.name = 'dog'
>>>>    def __delitem__(self,key):
>>>>        print('here in __delitem__')
>>>>        del self.name
>>>>dog = Dog()
>>>>del dog['name'] # 调用了__delitem__方法
>here in __delitem__
>
>>>>print(dog.name)
>AttributeError: 'Dog' object has no attribute 'name'
>```
# 十.抽象类
> - 抽象类就是没有具体实现内容的方法成为抽象类
> - 抽象类的主要意义是规范了子类的行为和接口
> - 抽象类的使用需要借助abc模块
> - 抽象类不允许直接实例化
> - 必须继承才可以使用，且继承的子类必须实现所有继承来的抽象方法
> - 假定子类没有是现实所有继承的抽象方法，则子类也不能实例化
>```
>>>>import abc # 导入abc模块
>>>>class Animal(metaclass=abc.ABCMeta):
>>>>    type = animal
>>>>    @abc.abstractmethod # 定义抽象方法，无需实现功能
>>>>    def bart(self):
>>>>        pass
>>>>dog = Animal() # 抽象类不能被实例化
>TypeError: Can't instantiate abstract class animal with abstract methods bart
>
>>>>class Dog(animal):  # 通过继承实现抽象类
>>>>    def bart(self):
>>>>        print('嗷嗷!')
>>>>dog = Dog()
>>>>dog.bart()
>嗷嗷！
>```

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
