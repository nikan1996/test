## Python编程规范

## 目录


* [Python编程规范](#python编程规范)
* [1 背景](#1-背景)
* [2 语言规范](#2-语言规范)
  * [2.1 代码检查工具](#21-代码检查工具)
  * [2.2 导入（Imports）](#22-导入imports)
  * [2.3 包（Packages）](#23-包packages)
  * [2.4 异常（Exceptions）](#24-异常exceptions)
  * [2.5 全局变量（Global variables）](#25-全局变量global-variables)
  * [2.6 嵌套、局部、内部类和函数(Nested/Local/Inner Classes and Functions)](#26-嵌套局部内部类和函数nestedlocalinner-classes-and-functions)
  * [2.7 推导式和生成器表达式（Comprehensions &amp; Generator Expressions）](#27-推导式和生成器表达式comprehensions--generator-expressions)
  * [2.8 默认迭代器和操作符（Default Iterators and Operators）](#28-默认迭代器和操作符default-iterators-and-operators)
  * [2.9 生成器（Generators）](#29-生成器generators)
  * [2.10 匿名函数（Lambda Functions）](#210-匿名函数lambda-functions)
  * [2.11 条件表达式（Conditional Expressions）](#211-条件表达式conditional-expressions)
  * [2.12 默认参数值（Default Argument Values）](#212-默认参数值default-argument-values)
  * [2.13 属性(Properties)](#213-属性properties)
  * [2.14 True/False的求值（True/False evaluations）](#214-truefalse的求值truefalse-evaluations)
  * [2.15 过时的语言特性(Deprecated Language Features)](#215-过时的语言特性deprecated-language-features)
  * [2.16 变量作用域(Lexical Scoping)](#216-变量作用域lexical-scoping)
  * [2.17 函数和方法装饰器(Function and Method Decorators)](#217-函数和方法装饰器function-and-method-decorators)
  * [2.18 线程(Threading)](#218-线程threading)
  * [2.19 强大的特性（Power Features）](#219-强大的特性power-features)
  * [2.20 现代化Python(Modern Python: Python 3 and from <strong>future</strong> imports)](#220-现代化pythonmodern-python-python-3-and-from-future-imports)
  * [2.21 代码类型注释(Type Annotated Code)](#221-代码类型注释type-annotated-code)
* [3 Python风格规范](#3-python风格规范)
  * [3.1 分号(Semicolons)](#31-分号semicolons)
  * [3.2 行长度（Line length）](#32-行长度line-length)
  * [3.3 括号（Parentheses）](#33-括号parentheses)
  * [3.4 缩进（Indentation）](#34-缩进indentation)
  * [3.5 空行（Blank Lines）](#35-空行blank-lines)
  * [3.6 空格（Whitespace）](#36-空格whitespace)
  * [3.7 SheBang行（Shebang Line）](#37-shebang行shebang-line)
  * [3.8 注释和文档字符串（Comments and Docstrings）](#38-注释和文档字符串comments-and-docstrings)
  * [3.8.1 文档字符串（Docstrings）](#381-文档字符串docstrings)
  * [3.8.2 模块（Modules）](#382-模块modules)
  * [3.8.3 函数和方法（Functions and Methods）](#383-函数和方法functions-and-methods)
  * [3.8.4 类（Classes）](#384-类classes)
  * [3.8.5 块注释和行注释（Block and Inline Comments）](#385-块注释和行注释block-and-inline-comments)
  * [3.8.6 标点符合、拼写和语法（Punctuation, Spelling and Grammar）](#386-标点符合拼写和语法punctuation-spelling-and-grammar)
  * [3.9 类（Classes）](#39-类classes)
  * [3.10 字符串（Strings）](#310-字符串strings)
  * [3.11 文件和sockets（Files and Sockets）](#311-文件和socketsfiles-and-sockets)
  * [3.12 TODO注释（TODO  Comments）](#312-todo注释todo--comments)
  * [3.13 导入格式化（Imports formatting）](#313-导入格式化imports-formatting)
  * [3.14 语句（Statements）](#314-语句statements)
  * [3.15 访问控制（Access Control）](#315-访问控制access-control)
  * [3.16 命名（Naming）](#316-命名naming)
  * [3.16.1应该避免的名称](#3161应该避免的名称)
  * [3.16.2 命名约定](#3162-命名约定)
  * [3.16.3 文件命名](#3163-文件命名)
  * [3.16.4 Guido van Rossum推荐的命名规范](#3164-guido-van-rossum推荐的命名规范)
  * [3.17 主函数（Main）](#317-主函数main)
  * [3.18 函数长度](#318-函数长度)
  * [3.19 类型注释](#319-类型注释)
* [4 临别赠言](#4-临别赠言)

## 1 背景

​        Python是一门动态语言。Python有着非常自由的语法和非常多的特性，开发者可以写出各种充满社会特色主义的代码。本规范的目的不是为了约束开发者的创造力和生产力，而是为了限制开发者的过度个性化，统一团队的代码风格，通过风格一致的代码来更好地进行团队成员之间的协作开发。本规范适用Python3.5以上的版本，部分规范在Python2.7不一定适用。本规范也不推荐开发者继续使用Python2.7开发，Python3会不断地加入新的特性，而Python2.7 到2020年1月1日后将停止被维护。本规范将辅助开发者写出简洁、优雅、高效和风格一致的代码，并且减少踩坑的概率，提升代码的质量，增强开发者的编程规范意识。

​        本规范主要遵循[google code style](https://github.com/google/styleguide/blob/gh-pages/pyguide.md)和 [PEP-8](https://www.python.org/dev/peps/pep-0008/)。

## 2 语言规范

### 2.1 代码检查工具

- flake8
- IDE自带代码检查工具

#### 2.1.1 解释

代码检查工具可以找出代码中存在的明显的bug和风格问题。

#### 2.1.2 优点

可以找出容易忽略的错误，比如单词拼写错误， 使用了未被赋值的变量等。

#### 2.1.3 缺点

代码检查工具不是万能的， 有些warning可能是不对的，在必要的时候可以忽略它们。

#### 2.1.4 推荐

确保你写的代码经过了代码检查工具的检查，并忽略不必要的warning。



### 2.2 导入（Imports）

使用`import`来导入。

####   2.2.1 解释

模块间的代码复用。

#### 2.2.2 优点

命名空间管理约定简单。`x.Obj`表示`Obj`对象在模块`x`中。

#### 2.2.3 缺点

绝对导入在嵌套和命名复杂的情况下， 导入代码会变得非常长。

#### 2.2.4 推荐
+ 使用`import x`来导入包和模块。

+ 使用`from x import y`当x是包名， y是模块名，模块名最好不要包含前缀。

+ 使用`from x import y as z`,如果y已经被导入了，为了避免重名，重命名为z。

+ 使用`from x.y import a, b, c` x是包名,y是模块名， a,b,c是类，方法或者变量名。

+ 使用`import y as z`，只有业界都这么做的时候才这么做。（比如import numpy as np， 是通用的一个做法）

+ 避免方法内的局部导入。（除非遇到循环引用的情况，这个时候需要检查是否必须只能循环引用，能不能拆分代码避免循环引用）

  ​


### 2.3 包（Packages）

使用模块的绝对路径名来导入每个模块。

#### 2.3.1 解释

包是按目录来组织模块的方法。

#### 2.3.2 优点

避免模块名冲突，查找模块更加容易。

#### 2.3.3 缺点

导入变得困难， 因为必须要带上整个包的路径。

#### 2.3.4 推荐

使用绝对导入，不推荐使用相对导入。

```Python
# Reference in code with complete name.
import absl.flags

# Reference in code with just module name (这种方法更好).
from absl import flags
```



### 2.4 异常（Exceptions）

异常需要小心使用。

#### 2.4.1 解释

异常是一种跳出代码块的正常控制流来处理错误或者其他异常情况的方式。

#### 2.4.2 优点

正常操作代码的控制流不会和处理错误的代码混合在一起。当某个特定异常发生的时候，控制流可以跳过。比如，返回，而不用继续执行错误的代码。

#### 2.4.3 缺点

控制流可能会让人懵逼。在调用库的时候容易错过一些错误的情况。

#### 2.4.4 推荐

+ 使用`raise MyError('Error message')` 或 `raise MyError()`

+ 充分利用内置的异常类。比如，如果你传递了一个负数，但是要求是一个正数，抛出一个`ValueError`。不要使用`assert`语句来验证公共API中参数的值。`assert`被用于确保内部的正确性，而不是为了强制正确的使用，也不是为了表明一些意外的事情发生。如果发生了意外，请使用`raise`语句。比如，

  ```python
  Yes:
    def ConnectToNextPort(self, minimum):
      """Connects to the next available port.  Returns the new minimum port."""
      if minimum <= 1024:
        raise ValueError('Minimum port must be greater than 1024.')
      port = self._FindNextOpenPort(minimum)
      if not port:
        raise ConnectionError('Could not connect to service on %d or higher.' % (minimum,))
      assert port >= minimum, 'Unexpected port %d when minimum was %d.' % (port, minimum)
      return port
  ```

  ```Python
  No:
    def ConnectToNextPort(self, minimum):
      """Connects to the next available port.  Returns the new minimum port."""
      assert minimum > 1024, 'Minimum port must be greater than 1024.'
      port = self._FindNextOpenPort(minimum)
      assert port is not None
      return port
  ```

+ 库和包可以定义它们自己的异常。如果要这么做， 必须继承一个已有的异常类。异常名需要以`Error`结尾，

+ 永远不要使用 `except:` 语句来捕获所有异常， 该语句将会捕获`SystemExit` 和`KeyboardInterrupt`异常，这样会很难通过Control-C中断程序， 并且会掩盖掉其它的异常。如果想要捕捉程序出错的异常，使用`except Exception as e:`。

+ 尽量减少`try/except`块内的代码量。`try`的内容越多， 期望外的异常就越容易被触发。在这种情况下`try/except`块将隐藏真正的错误。

+ 使用`finally`子句。无论有没有异常被抛出，`finally`子句内的代码都会被执行。对于需要执行清理操作的时候，这是非常有用的。比如，关闭一个文件。

+ 当捕获异常时，使用`as`而不要使用逗号（python3不支持逗号）。比如：

  ```python
  try:
      raise Error
  except Error as error:
      pass

  ```

  ​

### 2.5 全局变量（Global variables）

避免全局变量

#### 2.5.1 解释

`模块级的变量`或`类变量`

#### 2.5.2 优点

偶尔有用。

#### 2.5.3 缺点

导入时可能会改变模块行为，因为在首次导入模块时会对全局变量赋值。

#### 2.5.4 推荐

避免使用全局变量。

例外：

+ 模块级常量。比如，`MAX_HOLY_HANDGRENADE_COUNT = 3`。常量单词需要全部大写并且用下划线连接。具体请查看[命名规范]()。
+ 如果需要，全局变量仅在模块内部可用，并在名字前加一个`_`。外部访问必须通过公共模块级函数来完成。



### 2.6 嵌套、局部、内部类和函数(Nested/Local/Inner Classes and Functions)

当嵌套的局部方法或者类是允许的。

#### 2.6.1 解释

一个类可以在方法、函数或类中被定义。一个函数可以在方法或函数中被定义。嵌套方法拥有对闭包变量`只读`的权限。

#### 2.6.2 优点

允许写一点小的工具类和函数在局部（用于辅助一些操作），方便直接调用。

比如：

```python
import sys

def Foo():
    def e(s):
        sys.stderr.write('ERROR: ')
        sys.stderr.write(s)
        sys.stderr.write('\n')
    e('I regret to inform you')
    e('that a shameful thing has happened.')
    e('Thus, I must issue this desultory message')
    e('across numerous lines.')
Foo()
```

#### 2.6.3 缺点

嵌套和局部的类实例不能被序列化（pickled）。嵌套的方法和类不能被直接得测试。嵌套可能会让你的函数更长并减少可读性。

#### 2.6.4 推荐

推荐使用。



### 2.7 推导式和生成器表达式（Comprehensions & Generator Expressions）

适合在简单情况下使用。

#### 2.7.1 解释

列表，字典和集合推导式和生成器表达式提供了一种简洁高效的方式来创造容器类和迭代器，而不必借助于传统的循环， `map()`, `filter()`, 或者是`lambada`。

#### 2.7.2 优点

简单的推导式比其他`dict`, `list`或`set`的创建方法更加清晰简单。生成器表达式非常高效， 因为它们避免一次性创建整个列表。

#### 2.7.3 缺点

复杂的推导式或生成器表达式会导致阅读障碍。

#### 2.7.4 推荐

适合在简单情况下使用。 每个部分应该单独一行：映射（mapping）表达式， `for`语句， 过滤表达式。

**禁止**多重`for`语句或者过滤表达式。在复杂情况下，使用循环。


```python
Yes:
  result = []
  for x in range(10):
      for y in range(5):
          if x * y > 10:
              result.append((x, y))

  for x in xrange(5):
      for y in xrange(5):
          if x != y:
              for z in xrange(5):
                  if y != z:
                      yield (x, y, z)

  return ((x, complicated_transform(x))
          for x in long_generator_function(parameter)
          if x is not None)

  squares = [x * x for x in range(10)]

  eat(jelly_bean for jelly_bean in jelly_beans
      if jelly_bean.color == 'black')
```

```python
No:
  result = [(x, y) for x in range(10) for y in range(5) if x * y > 10]

  return ((x, y, z)
          for x in xrange(5)
          for y in xrange(5)
          if x != y
          for z in xrange(5)
          if y != z)
```



### 2.8 默认迭代器和操作符（Default Iterators and Operators）

如果类支持默认的迭代器和操作符，那么就使用它们，比如列表，字典和文件。

#### 2.8.1 解释

字典和容器类型，比如字典和列表，定义了默认的迭代器和成员关系操作符（`in`和`not in`）

#### 2.8.2 优点

默认迭代器和操作符简单高效。它们直接调用相关操作，不会因为额外的调用方法而产生开销。使用默认操作符的函数是通用的。任何类都可以去选择实现相关方法来支持这些操作。

#### 2.8.3 缺点

类似`in`和`not in` 无法直接判断该对象的类型，而如果使用 `has_key()`则意味着该对象是一个字典。

#### 2.8.4 推荐

如果默认的类支持默认的迭代器和操作符，比如列表，字典和文件。内建容器类型也定义了迭代器方法。优先考虑这些方法，而不是用另外的返回列表的方法。请注意，在迭代容器的时候，你是不能对它进行修改的。

```python
Yes:  for key in adict: ...
      if key not in adict: ...
      if obj in alist: ...
      for line in afile: ...
      for k, v in dict.iteritems(): ...
```

```python
No:   for key in adict.keys(): ...
      if not adict.has_key(key): ...
      for line in afile.readlines(): ...
```



### 2.9 生成器（Generators）

按需使用生成器。

#### 2.9.1 解释

一个生成器函数返回一个迭代器。每当它执行一次yield语句，它就会返回一个值。生成值后，生成器函数的运行状态被挂起直到需要生成下一个值。

#### 2.9.2 优点

简化代码， 因为每次调用时，局部变量和控制流的状态都会被保存。生成器仅会占用极少的内存，对于大内存对象的迭代，推荐使用生成器而不是列表。

#### 2.9.3 缺点

无。

#### 2.9.4 推荐

鼓励使用。



### 2.10 匿名函数（Lambda Functions）

适用于一行的表达式。

#### 2.10.1 解释

`Lambda`定义了以一个表达式作为匿名函数，经常用于回调和高阶函数比如`map()`，`filter()`。

#### 2.10.2 优点

方便。

#### 2.10.3 缺点

比本地函数更难阅读和调试。没有函数名意味着调用栈跟踪更加难以理解。由于python的lambda函数只能包含一个表达式，因此它的作用有限。

#### 2.10.4 推荐

对于简单的表达式，可以直接使用匿名函数而不用再单独写一个函数。如果匿名函数代码超过60-80个字符，最好还是定义成单独的函数。对于常见的操作符，比如乘法，使用`operator`模块中的函数代替`lambda`函数。比如， 推荐使用`operator.mul`， 而不是`lambda x,y: x*y`。



### 2.11 条件表达式（Conditional Expressions）

#### 2.11.1 解释

条件表达式（又被称为三元运算符）提供了比 `if`语句更短的语法。比如`x = 1 if cond else 2`。

#### 2.11.2 优点

比if语句更加简短和方便。

#### 2.11.3 缺点

比if语句读起来累，特别是一个表达式很长的时候。

#### 2.11.4 推荐

适用于简单的，一行能解决的情况。在需要多行语句才能解决的情况，推荐使用完整的if语句。



### 2.12 默认参数值（Default Argument Values）

适用于大部分情况。

#### 2.12.1 解释

函数的参数可以指定默认值。如`def foo(a, b=0):`。如果`foo`只传入一个参数，那么b的值就是0。如果传入两个参数，b的值就是第二个参数的值。

#### 2.12.2 优点

你经常会碰到一些使用大量默认值的函数， 但偶尔(比较少见)你想要覆盖这些默认值。默认参数值提供了一种简单的方法来完成这件事， 你不需要为这些罕见的例外定义大量函数。同时, Python也不支持重载方法和函数，默认参数是一种"仿造"重载行为的简单方式。

#### 2.12.3 缺点

默认参数只在模块加载时求值一次，如果参数是列表或字典之类的可变类型, 这可能会导致问题。如果在函数内部对该可变对象进行修改(比如向列表追加项`l.append('sth')`)，默认参数的值就被修改了。

#### 2.12.4 推荐

鼓励使用。不过有如下注意事项：

不要在函数或方法定义中使用可变对象作为默认值。

```python
Yes: def foo(a, b=None):
         if b is None:
             b = []
Yes: def foo(a, b: Optional[Sequence] = None):
         if b is None:
             b = []
```

```python
No:  def foo(a, b=[]):
         ...
No:  def foo(a, b=time.time()):  # The time the module was loaded???
         ...
No:  def foo(a, b=FLAGS.my_thing):  # sys.argv has not yet been parsed...
         ...
```



### 2.13 属性(Properties)

访问和设置数据成员时， 你通常会使用简单，轻量级的访问和设置函数。建议用属性（properties）来代替它们。

#### 2.13.1 解释

能够包装getter和setter。 当运算量不大, 它是获取和设置属性(attribute)的标准方式.

#### 2.13.2 优点

指定显式的属性get和set方法可以提高可读性。允许延迟计算（lazy calculation）。不需要对类的接口进行改动。

#### 2.13.3 缺点

在实例属性需要频繁访问的时候， 通过直接访问属性的速度会是通过该方式访问属性的3倍。在高性能编程下需要注意`@property`可能带来的性能问题。

#### 2.13.4 推荐

推荐使用`@property`装饰器的方式来获取或者设置属性，在获取属性需要通过简单的计算表达式得出结果时，这是非常适合的。比如：

```Python
Yes:
@property
def area(self):
    return math.pi * self.radius**2
```

```python
Yes: 
     import math

     class Square(object):
         """A square with two properties: a writable area and a read-only perimeter.

         To use:
         >>> sq = Square(3)
         >>> sq.area
         9
         >>> sq.perimeter
         12
         >>> sq.area = 16
         >>> sq.side
         4
         >>> sq.perimeter
         16
         """

         def __init__(self, side):
             self.side = side

         @property
         def area(self):
             """Gets or sets the area of the square."""
             return self._get_area()

         @area.setter
         def area(self, area):
             return self._set_area(area)

         def _get_area(self):
             """Indirect accessor to calculate the 'area' property."""
             return self.side ** 2

         def _set_area(self, area):
             """Indirect setter to set the 'area' property."""
             self.side = math.sqrt(area)

         @property
         def perimeter(self):
             return self.side * 4
```
避免太过简单的包装。
```python
No:
     @property
     def area(self):
     """Gets or sets the area of the square."""
         return self._area
```

避免通过`property`的方式设置getter和setter。使用`@property`和`@sth.setter`。

```Python
No:
area = property(___get_area, ___set_area,
                         doc="""Gets or sets the area of the square.""")
```



### 2.14 True/False的求值（True/False evaluations）

尽可能使用隐式false

#### 2.14.1 解释

Python在布尔上下文中会将某些值求值为`False`。 按简单的直觉来讲， 就是所有的"空"值都被认为是false。因此 `0, None, [], {}, ""`都被认为是false值。

#### 2.14.2 优点

使用Pythonic布尔值的条件语句更易读也更不易犯错。

#### 2.14.3 缺点

对于C/C++等其它语言开发人员来说，会感觉有点奇怪。

#### 2.14.4 推荐

尽可能使用隐式的false， 例如: 使用 `if foo:` 而不是 `if foo != []:` . 不过还是有一些注意事项需要你铭记在心:

+ 永远不要用==或者!=来比较某些单例， 比如None。 使用`is`或者is not。
+ 注意: 当你写下 `if x:` 时， 如果你其实表示的是 `if x is not None`，那么`if x:`是不对的。 例如: 当你要测试一个默认值是None的变量或参数是否被设为其它值。 这个值在布尔语义下可能是false！
+ 永远不要用==将一个布尔量与false相比较. 使用 `if not x:` 代替. 如果你需要区分false和None, 你应该用像 `if not x and x is not None:` 这样的语句。
+ 对于序列(字符串, 列表, 元组), 要注意空序列是false。因此 `if not seq:` 或者 `if seq:` 比 `if len(seq):` 或 `if not len(seq):` 要更好。
+ 处理整数时, 使用隐式false可能会得不偿失(即不小心将None当做0来处理). 你可以将一个已知是整型(且不是len()的返回结果)的值与0比较。

```python
   Yes: if not users:
            print('no users')

        if foo == 0:
            self.handle_zero()

        if i % 10 == 0:
            self.handle_multiple_of_ten()

        def f(x=None):
            if x is None:
                x = []
```

```python
No:  if len(users) == 0:
         print('no users')

     if foo is not None and not foo:
         self.handle_zero()

     if not i % 10:
         self.handle_multiple_of_ten()

     def f(x=None):
         x = x or []
```

+ 注意'0'(字符串)会被当做true。

  ​

### 2.15 过时的语言特性(Deprecated Language Features)

使用字符串方法代替字符串模块。使用列表推导式和`for`循环代替`filter`。在`map` 中少用复杂的lambda函数。使用`for`循环而不是`reduce`。

#### 2.15.1 解释

当前版本的Python提供了大家更喜欢的特性。

#### 2.15.2 推荐

我们不使用陈旧的Python版本，而是尽可能使用新的和稳定的Python版本。所以我们应该尝试、习惯并探索更好的特性。

```Python
Yes: words = foo.split(':')

     [x[1] for x in my_list if x[2] == 5]

     map(math.sqrt, data)    # Ok. No inlined lambda expression.

     fn(*args, **kwargs)
```



```Python
No:  words = string.split(foo, ':')

     map(lambda x: x[1], filter(lambda x: x[2] == 5, my_list))

     apply(fn, args, kwargs)
```



### 2.16 变量作用域(Lexical Scoping)

不要使用会让人误解的局部变量和全局变量，不同的变量作用域不同。

#### 2.16.1 解释

嵌套的Python函数可以引用外层函数中定义的变量，但是不能够对它们赋值。变量绑定的解析是使用词法作用域, 也就是基于静态的程序文本。对一个块中的某个名称的任何赋值都会导致Python将对该名称的全部引用当做局部变量， 甚至是赋值前的处理。 如果碰到global声明，该变量就会被视作全局变量。

一个使用闭包的例子：

```Python
def get_adder(summand1):
    """Returns a function that adds numbers to a given number."""
    def adder(summand2):
        return summand1 + summand2

    return adder
```

调用方式`sum = get_adder(summand1)(summand2)`

#### 2.16.2 优点

结果更加清晰，对Lisp和Scheme(Haskell，ML等)程序员友好

#### 2.16.3 缺点

可能会产生令人费解的bug。

例如这个依据 [PEP 0227](http://www.python.org/dev/peps/pep-0227/) 的例子:

```Python
i = 4
def foo(x):
    def bar():
        print(i, end='')
    # ...
    # A bunch of code here
    # ...
    for i in x:  # Ah, i *is* local to foo, so this is what bar sees
        print(i, end='')
    bar()
```

因此 `foo([1, 2, 3])` 会打印 `1 2 3 3` ，不是 `1 2 3 4` 。

因为foo函数中的i被隐式赋值为3， 而不是使用全局的4。

#### 2.16.4 推荐

**非常熟悉该特性的开发者可以使用。否则慎用。**

闭包会有一些问题比如：

```python
No:
def count():
    fs = []
    for i in range(1, 4):
        def f():
             return i*i
        fs.append(f)
    return fs

f1, f2, f3 = count()
```

你可能认为调用`f1()`，`f2()`和`f3()`结果应该是`1`，`4`，`9`，但实际结果是：

```python
>>> f1()
9
>>> f2()
9
>>> f3()
9
```

解释：返回函数引用变量`i`，但是它并不是立即执行的，而是延迟执行。等到3个函数都返回时，它们所引用的变量`i`已经变成了`3`，因此最终结果为`9`。

如果一定要引用循环变量怎么办？方法是再创建一个函数立即执行，用该函数的参数绑定循环变量当前的值，无论该循环变量后续如何更改，已绑定到函数参数的值不变：

```Python
Yes:
def count():
    def f(j):
        def g():
            return j*j
        return g
    fs = []
    for i in range(1, 4):
        fs.append(f(i)) # f(i)立刻被执行，因此i的当前值被传入f()
    return fs
```

```python
>>> f1, f2, f3 = count()
>>> f1()
1
>>> f2()
4
>>> f3()
9
```

`返回闭包时牢记：返回函数不要引用任何循环变量，或者后续会发生变化的变量。`



### 2.17 函数和方法装饰器(Function and Method Decorators)

使用装饰器。避免使用`@staticmethod`以及限制使用`@classmethod`

#### 2.17.1 解释

[用于函数及方法的装饰器](https://docs.python.org/release/2.4.3/whatsnew/node6.html) （也就是@标记）。一个流行的装饰器是`@property`用于把普通的方法转化成属性。装饰器也允许由用户自定义。比如`my_decorator`：

```python
class C:
    @my_decorator
    def method(self):
        # method body ...
```

等同于

```
class C:
    def Methodmethod(self):
        # method body ...
    Methodmethod = MyDecoratormy_decorator(Methodmethod)
```



#### 2.17.2 优点

优雅地定义了，减少重复的代码，从纵向上减少代码的耦合程度。具有面向切面编程的优点。

#### 2.17.3 缺点

装饰器会修改函数的参数或者返回值，这些操作都是隐式的。另外装饰器在导入时（import time）与函数绑定生效。装饰器中产生的错误会更加难追查。

#### 2.17.4 推荐

如果有非常明显的优点（代码复用，面向切面编程），那么就可以使用它。装饰器需要遵守和函数一样的导入和命名规则。装饰器的文档需要说明这是一个装饰器。为装饰器编写健壮的单元测试。

避免装饰器对外部的依赖（比如不要依赖文件，socket，数据库连接等）。要保证装饰器的有效调用在任何情况下都是成功的。

装饰器是一种特殊的“顶层代码”(top level code)。

少用`@staticmethod`。大多数情况下，直接使用模块级的函数更加适合而不是跟类耦合在一起。少部分情况下，在函数只被该类使用的情况下，可以使用`@staticmethod`。

仅在写构造函数时使用`@classmethod`。如果要修改类变量的值，也需要使用`@classmethod`。



### 2.18 线程(Threading)

不要依赖内建类型（`built-in`）的原子性。

#### 2.18.1 推荐

虽然Python的内建类型比如字典的操作看上去都是原子的，但是在某些情况下它们仍然不是原子的（如果`__hash__`或`__eq__`以Python代码实现），因此他们的原子性是不可靠的。

使用`Queue`作为线程间的数据通信方式。其它情况，使用`threading`模块和锁原语（locking primitives）。学习`condition`的适用场景，你可以使用`threading.Condition`来取代低级别的`Lock`。



### 2.19 强大的特性（Power Features）

强大不等于好用， 相反强大的特性正式因为它能做的事情过于强大，容易让初中级程序员翻船。

#### 2.19.1 解释

Python是非常灵活的语言， 它为你提供了很多花哨的特性，诸如元类（metaclasses），字节码（bytecode）访问, 任意编译（on-the-fly compilation），动态继承（dynamic inheritance），对象父类重定义（object reparenting），导入黑客（import hacks）, 反射，系统内修改（modification of system internals）等等。

#### 2.19.2 优点

强大的语言特性，可以让你的代码更加简洁紧凑。

#### 2.19.3 缺点

奇淫技巧的代码会变得难以阅读和调试。刚开始写下这些代码时还能理解，但是当后续回顾这些代码时，理解起来还不如一些虽然写得比较长还是表达意思很直接的代码。

#### 2.19.4 推荐

除非你对你将要使用的特性理解非常深入（你能够理解为什么要这么做，以及懂得怎么正确地去做）， 否则不要使用这些奇淫技巧。

有些特性经过封装后，我们认为它是相对安全并且容易理解的。

部分使用了这些特性的标准库的模块和类是允许使用的（比如`abc.ABCMeta`，`collections.namedtuple`和`enum`）。



### 2.20 现代化Python(Modern Python: Python 3 and from __future__ imports)

Python3即将开启新的时代！ 但是某些项目还不支持Python3， 因此那些项目需要进行迁移或是兼容。

#### 2.20.1 解释

Python3是Python的一个重要的改变。但是Python2的代码仍然存在，这时候需要利用future模块来进行兼容，而不需要做太大的改动。

#### 2.20.2 优点

Python3的语法更加优雅。

#### 2.20.3 缺点

future模块可能有些丑。没错，毕竟future是为了兼容所做的妥协。

#### 2.20.4 推荐

```Python
from __future__ import absolute_import
from __future__ import division
from __future__ import print_function
```

如果你对这些兼容为什么要这么做不太了解，你可以阅读 [absolute imports](https://www.python.org/dev/peps/pep-0328/), [new `/` division behavior](https://www.python.org/dev/peps/pep-0238/), and [the print function](https://www.python.org/dev/peps/pep-3105/)。

future, six模块可以帮助你进行Python2和3的兼容。

如果没有兼容Python2的必要，请选择Python3.5+的版本进行编程。

仔细阅读[Python2到3迁移](https://docs.python.org/3/howto/pyporting.html)，并对自己的项目进行改造。:smile:

在100%的情况下不建议再使用Python2进行编程。



### 2.21 代码类型注释(Type Annotated Code)

非常好的特性， 你可以对Python3.5+的代码进行注释，参考 [PEP-484](https://www.python.org/dev/peps/pep-0484/)。从python3.6开始还增加了变量注释，参考[PEP-0526](https://www.python.org/dev/peps/pep-0526/)。

#### 2.21.1 解释

类型注释`type annotations`（或者说类型提示`type hints`）是对函数参数和返回值进行注释。

类型注释：

```python
def func(a: int) -> List[int]:
```

变量注释：

`some_number: int           `

` valuesome_list: List[int] = []`

#### 2.21.2 优点

类型注释提高了你代码的可读性和可维护性。类型检查器可以根据类型注释把可能在运行时发生的错误提前检查出来。提高了项目的工程强度。

#### 2.21.3 缺点

+ Python3.5+支持。你需要不停更新这些类型声明。但是这会让你对你的代码非常熟悉，其实也算是一个优点。
+ 可能会限制开发者使用一些Python奇淫技巧的能力。

#### 2.21.4 推荐

如果你的项目复杂到你必须进行类型注释，那么这一定是一个值得一试的特性。

把代码变成类似静态语言的风格并不是在开倒车，在一个大型项目下这是必须要做的事情。



## 3 Python风格规范

#### 3.1 分号(Semicolons)

不要在行尾添加分号，也不要用分号将两条命令放在同一行

```python
Yes:
import a
import b
```

```Python
No:
import a;import b;
```



#### 3.2 行长度（Line length）

每行不超过120个字符。

例外：

+ 很长的导入语句。
+ URL，路径名，或者注释中非常长的flag。

不要使用反斜杠换行。

Python会把`(),[],{}`中的行自动隐式地连接到一起， 可以利用这个特性连接行。

```python
Yes: foo_bar(self, width, height, color='black', design=None, x='foo',
             emphasis=None, highlight=0)

     if (width == 0 and height == 0 and
         color == 'red' and emphasis == 'strong'):
```

如果一个字符串在一行放不下， 使用圆括号来进行隐式的连接：

```Python
x = ('This will build a very long long '
     'long long long long long long string')
```

在注释中，可以把长的URL放在一行上。

```Python
Yes:  # See details at
      # http://www.example.com/us/developer/documentation/api/content/v2.0/csv_file_name_extension_full_specification.html
```

```
No:  # See details at
     # http://www.example.com/us/developer/documentation/api/content/\
     # v2.0/csv_file_name_extension_full_specification.html
```

在使用`with`语句时， 三个以上的表达式可以被反斜杠分为多行。对于两行表达式，使用嵌套`with`。

```Python
Yes:  with very_long_first_expression_function() as spam, \
           very_long_second_expression_function() as beans, \
           third_thing() as eggs:
          place_order(eggs, beans, spam, beans)
```

```python
No:  with VeryLongFirstExpressionFunction() as spam, \
          VeryLongSecondExpressionFunction() as beans:
       PlaceOrder(eggs, beans, spam, beans)
```

```Python
Yes:  with very_long_first_expression_function() as spam:
          with very_long_second_expression_function() as beans:
              place_order(beans, spam)
```



### 3.3 括号（Parentheses）

少用括号。

除非是为了实现行与行之间的连接，否则不要在返回语句或条件语句中使用括号。在元祖两边使用括号是必要的。



```python
Yes: if foo:
         bar()
     while x:
         x = bar()
     if x and y:
         bar()
     if not x:
         bar()
     # 对于只包含一项的元祖，比起onesie = foo来说, 加上括号更加明显
     onesie = (foo,)
     return foo
     return spam, beans
     return (spam, beans)
     for (x, y) in dict.items(): ...
```

```Python
No:  if (x):
         bar()
     if not(x):
         bar()
     return (foo)
```



### 3.4 缩进（Indentation）

使用4个空格缩进代码。

不要使用tab！对于行链接的情况，使用垂直对齐

```python
Yes:   # Aligned with opening delimiter
       foo = long_function_name(var_one, var_two,
                                var_three, var_four)
       meal = (spam,
               beans)

       # Aligned with opening delimiter in a dictionary
       foo = {
           long_dictionary_key: value1 +
                                value2,
           ...
       }

       # 4-space hanging indent; nothing on first line
       foo = long_function_name(
           var_one, var_two, var_three,
           var_four)
       meal = (
           spam,
           beans)

       # 4-space hanging indent in a dictionary
       foo = {
           long_dictionary_key:
               long_dictionary_value,
           ...
       }
```

```python
No:    # Stuff on first line forbidden
       foo = long_function_name(var_one, var_two,
           var_three, var_four)
       meal = (spam,
           beans)

       # 2-space hanging indent forbidden
       foo = long_function_name(
         var_one, var_two, var_three,
         var_four)

       # No hanging indent in a dictionary
       foo = {
           long_dictionary_key:
           long_dictionary_value,
           ...
       }
```



### 3.5 空行（Blank Lines）

顶层的定义之间空两行， 方法定义之间空一行。

顶层定义之间空两行, 比如函数或者类定义。方法定义，类定义与第一个方法之间，都应该空一行。函数或方法中, 某些地方要是你觉得合适, 就空一行。



### 3.6 空格（Whitespace）

按照标准的排版规范使用标点两边的空格。

括号内不要有空格。

```python
Yes: spam(ham[1], {eggs: 2}, [])
No:  spam( ham[ 1 ], { eggs: 2 }, [ ] )
```

不要在逗号，分号，冒号前面加空格，在他们后面加。行尾不用加空格。

```python
Yes: if x == 4:
         print(x, y)
     x, y = y, x
```

```python
No:  if x == 4 :
         print(x , y)
     x , y = y , x
```
参数列表，索引或切片的左括号前不应该加空格。
```python
Yes: spam(1)
No:  spam (1)
Yes: dict['key'] = list[index]
No:  dict ['key'] = list [index]
```
在切片中，应该添加适当的空格。

```python
Yes:
ham[1:9], ham[1:9:3], ham[:9:3], ham[1::3], ham[1:9:]
ham[lower:upper], ham[lower:upper:], ham[lower::step]
ham[lower+offset : upper+offset]
ham[: upper_fn(x) : step_fn(x)], ham[:: step_fn(x)]
ham[lower + offset : upper + offset]
```

```python
No:
ham[lower + offset:upper + offset]
ham[1: 9], ham[1 :9], ham[1:9 :3]
ham[lower : : upper]
ham[ : upper]
```

在二元操作符两边都加上一个空格, 比如赋值(`=`)， 比较(`==, <, >, !=, <>, <=, >=, in, not in, is, is not`), 布尔(`and, or, not`)。

```python
Yes: x == 1
No:  x<1
```


当`=`用于指示关键字参数或默认参数值时，不要在其两侧使用空格。但是在进行类型注释的时候，允许使用空格。
```python
Yes: def complex(real, imag=0.0): return Magic(r=real, i=imag)
Yes: def complex(real, imag: float = 0.0): return Magic(r=real, i=imag)

No:  def complex(real, imag = 0.0): return Magic(r = real, i = imag)
No:  def complex(real, imag: float=0.0): return Magic(r = real, i = imag)
```
不要用空格来垂直对齐多行间的标记, 因为这会成为维护的负担(适用于`:`，`#`，`=`等)，保持左对齐就可以：

```python
Yes:
  foo = 1000  # comment
  long_name = 2  # comment that should not be aligned

  dictionary = {
      'foo': 1,
      'long_name': 2,
  }
```
```python
No:
  foo       = 1000  # comment
  long_name = 2     # comment that should not be aligned

  dictionary = {
      'foo'      : 1,
      'long_name': 2,
  }
```



### 3.7 SheBang行（Shebang Line）

在计算领域中，Shebang（也称为 Hashbang ）是一个由井号和叹号构成的字符序列 #! ，其出现在文本文件的第一行的前两个字符。 在文件中存在 Shebang 的情况下，类 Unix 操作系统的程序载入器会分析 Shebang 后的内容，将这些内容作为解释器指令，并调用该指令，并将载有 Shebang 的文件路径作为该解释器的参数。

大部分.py文件不必以#!作为文件的开头。 根据 [PEP-394](http://www.python.org/dev/peps/pep-0394/) ，程序的main文件应该以 #!/usr/bin/python2或者 #!/usr/bin/python3开始。



### 3.8 注释和文档字符串（Comments and Docstrings）

确保正确使用模块、函数、方法的文档字符串和行内注释。

#### 3.8.1 文档字符串（Docstrings）

> Python有一种独一无二的的注释方式：使用文档字符串。文档字符串是包，模块，类或函数里的第一个语句。这些字符串可以通过对象的__doc__成员被自动提取，并且被pydoc所用。 (你可以在你的模块上运行pydoc试一把， 看看它长什么样)。 我们对文档字符串的惯例是使用三重双引号"""( [PEP-257](http://www.python.org/dev/peps/pep-0257/) )。 一个文档字符串应该这样组织：首先是一行以句号，问号或感叹号结尾的概述(或者该文档字符串单纯只有一行)。接着是一个空行。接着是文档字符串剩下的部分，它应该与文档字符串的第一行的第一个引号对齐。下面有更多文档字符串的格式化规范。

#### 3.8.2 模块（Modules）

> 每个文件应该包含一个许可证。根据项目使用的许可（例如：Apache 2.0，BSD，LGPL，GPL），选择合适的许可证。

#### 3.8.3 函数和方法（Functions and Methods）

> 下文所指的函数，包括函数、方法以及生成器。
>
> 一个函数必须要有文档字符串，除非它满足以下条件：
>
> 1. 外部不可见
> 2. 非常短小
> 3. 简单明了
>
> 文档字符串应该包含函数做什么，以及输入和输出的详细描述。通常，不应该描述"怎么做"，除非是一些复杂的算法。文档字符串应该提供足够的信息，当别人编写代码调用该函数时，他不需要看一行代码，只要看文档字符串就可以了。对于复杂的代码，在代码旁边加注释会比使用文档字符串更有意义。
>
> 关于函数的几个方面应该在特定的小节中进行描述记录，这几个方面如下文所述。每节应该以一个标题行开始。标题行以冒号结尾。除标题行外，节的其他内容应被缩进2个空格。
>
> - Args:
>
>   列出每个参数的名字并在名字后使用一个冒号和一个空格，分隔对该参数的描述。如果描述太长超过了单行120字符，使用2或者4个空格的悬挂缩进(与文件其他部分保持一致)。描述应该包括所需的类型和含义。如果一个函数接受*foo(可变长度参数列表)或者**bar (任意关键字参数), 应该详细列出*foo和**bar。
>
> - Returns: (或者 Yields: 用于生成器)
>
>   描述返回值的类型和语义。如果函数返回None，这一部分可以省略。
>
> - Raises:
>
>   列出与接口有关的所有异常。
>
> ```
> def fetch_bigtable_rows(big_table, keys, other_silly_variable=None):
>     """Fetches rows from a Bigtable.
>
>     Retrieves rows pertaining to the given keys from the Table instance
>     represented by big_table.  Silly things may happen if
>     other_silly_variable is not None.
>
>     Args:
>         big_table: An open Bigtable Table instance.
>         keys: A sequence of strings representing the key of each table row
>             to fetch.
>         other_silly_variable: Another optional variable, that has a much
>             longer name than the other args, and which does nothing.
>
>     Returns:
>         A dict mapping keys to the corresponding table row data
>         fetched. Each row is represented as a tuple of strings. For
>         example:
>
>         {'Serak': ('Rigel VII', 'Preparer'),
>          'Zim': ('Irk', 'Invader'),
>          'Lrrr': ('Omicron Persei 8', 'Emperor')}
>
>         If a key from the keys argument is missing from the dictionary,
>         then that row was not found in the table.
>
>     Raises:
>         IOError: An error occurred accessing the bigtable.Table object.
>     """
>     pass
> ```

#### 3.8.4 类（Classes）

> 类应该在其定义下有一个用于描述该类的文档字符串。如果你的类有公共属性(Attributes)，那么文档中应该有一个属性(Attributes)段。并且应该遵守和函数参数相同的格式。
>
> ```
> class SampleClass(object):
>     """Summary of class here.
>
>     Longer class information....
>     Longer class information....
>
>     Attributes:
>         likes_spam: A boolean indicating if we like SPAM or not.
>         eggs: An integer count of the eggs we have laid.
>     """
>
>     def __init__(self, likes_spam=False):
>         """Inits SampleClass with blah."""
>         self.likes_spam = likes_spam
>         self.eggs = 0
>
>     def public_method(self):
>         """Performs operation blah."""
> ```

#### 3.8.5 块注释和行注释（Block and Inline Comments）

> 最需要写注释的是代码中那些技巧性的部分。如果你在下次 [代码审查](http://en.wikipedia.org/wiki/Code_review) 的时候必须解释一下，那么你应该现在就给它写注释。对于复杂的操作，应该在其操作开始前写上若干行注释。对于不是一目了然的代码，应在其行尾添加注释。
>
> ```
> # We use a weighted dictionary search to find out where i is in
> # the array.  We extrapolate position based on the largest num
> # in the array and the array size and then do binary search to
> # get the exact number.
>
> if i & (i-1) == 0:        # true iff i is a power of 2
> ```
>
> 为了提高可读性，注释应该至少离开代码2个空格。
>
> 另一方面，绝不要描述代码。 假设阅读代码的人比你更懂Python， 他只是不知道你的代码要做什么。
>
> ```
> # BAD COMMENT: Now go through the b array and make sure whenever i occurs
> # the next element is i+1
> ```

#### 3.8.6 标点符合、拼写和语法（Punctuation, Spelling and Grammar）

大家都喜欢读一份写得很优雅的注释，而不是杂乱没有头绪的注释。注释应该是一段通顺的语句。完整的句子比一个片段可读性更强。

源代码保持高度的清晰度和可读性是非常重要的。适当的标点符号、词汇选择和语法是必要的。



### 3.9 类（Classes）

Python3起，默认的类都继承自`object`，不用再显式继承`object`。

```python
Yes: class SampleClass:
        pass


    class OuterClass:

        class InnerClass:
            pass
```



### 3.10 字符串（Strings）

使用%操作符或者格式化方法`format`格式化字符串。Python3.6提供了f-string ，参考[PEP-498](https://www.python.org/dev/peps/pep-0498/)。简单的情况使用`+`。

```python
Yes: x = a + b
     x = '%s, %s!' % (imperative, expletive)
     x = '{}, {}'.format(first, second)
     x = 'name: %s; score: %d' % (name, n)
     x = 'name: {}; score: {}'.format(name, n)
     x = f'name: {name}; score: {n}'  # Python 3.6+
```

```python
No: x = '%s%s' % (a, b)  # use + in this case
    x = '{}{}'.format(a, b)  # use + in this case
    x = first + ', ' + second
    x = 'name: ' + name + '; score: ' + str(n)
```



避免在循环中用`+`和`+=`操作符来累加字符串。 由于字符串是不可变的，这样做会创建不必要的临时对象，并且导致二次方而不是线性的运行时间。作为替代方案，你可以将每个子串加入列表，然后在循环结束后用 `.join` 连接列表。 (也可以将每个子串写入一个 `cStringIO.StringIO` 缓存中。)

虽然Cpython对`+`和`+=`进行了优化，速度比`join`还快，但是不建议依赖特定的解释器进行编程。

```python
Yes: items = ['<table>']
     for last_name, first_name in employee_list:
         items.append('<tr><td>%s, %s</td></tr>' % (last_name, first_name))
     items.append('</table>')
     employee_table = ''.join(items)
```

```python
No: employee_table = '<table>'
    for last_name, first_name in employee_list:
        employee_table += '<tr><td>%s, %s</td></tr>' % (last_name, first_name)
    employee_table += '</table>'
```

在同一个文件中， 保持使用字符串引号的一致性。要么都是双引号，要么都是单引号， 在遇见字符串中有引号时，使用另一种引号。

```python
Yes:
     Python('Why are you hiding your eyes?')
     Gollum("I'm scared of lint errors.")
     Narrator('"Good!" thought a happy Python reviewer.')
```

```python
No:
     Python("Why are you hiding your eyes?")
     Gollum('The lint. It burns. It burns us.')
     Gollum("Always the great lint. Watching. Watching.")
```

为多行字符串使用三重双引号"""而非三重单引号'''。多行字符串与程序其他部分的缩进方式不一致， 使用隐式行链接来替代。

```python
  Yes:
  print("This is much nicer.\n"
        "Do it this way.\n")
```

```Python
  No:
    print("""This is pretty ugly.
Don't do this.
""")
```



### 3.11 文件和sockets（Files and Sockets）

在文件和sockets结束时，显式的关闭它。

除文件外，sockets或其他类似文件的对象在没有必要的情况下打开，会有许多副作用，例如：

1. 它们可能会消耗有限的系统资源，如文件描述符。如果这些资源在使用后没有及时归还系统，那么用于处理这些对象的代码会将资源消耗殆尽。
2. 持有文件将会阻止对于文件的其他诸如移动、删除之类的操作。
3. 仅仅是从逻辑上关闭文件和sockets，那么它们仍然可能会被其共享的程序在无意中进行读或者写操作。 只有当它们真正被关闭后，对于它们尝试进行读或者写操作将会抛出异常，并使得问题快速显现出来。

而且，对文件对象析构时，文件和sockets会自动关闭。

1. 不同的Python解释器实现了不同的gc。
2. 对于文件意外的引用,会导致对于文件的持有时间超出预期(比如对于异常的跟踪, 包含有全局变量等).

推荐使用`with`管理文件：

```python
with open("hello.txt") as hello_file:
    for line in hello_file:
        print line
```

对于不支持`with`的类文件对象，使用`contextlib.closing()`：

```python
import contextlib

with contextlib.closing(urllib.urlopen("http://www.python.org/")) as front_page:
    for line in front_page:
        print(line)
```



### 3.12 TODO注释（TODO  Comments）

为临时代码使用TODO注释，它是一种短期解决方案。

TODO注释应该在所有开头处包含"TODO"字符串，紧跟着是用括号括起来的你的名字、email地址或其它标识符。然后是一个可选的冒号，接着必须有一行注释， 解释要做什么。

主要目的是为了有一个统一的TODO格式， 这样添加注释的人就可以搜索到他的注释。

写了TODO注释并不保证写的人会亲自解决问题。当你写了一个TODO，请注上你的名字。

```python
# TODO(kl@gmail.com): Use a "*" here for string repetition.
# TODO(Zeke) Change this to use relations.
```



### 3.13 导入格式化（Imports formatting）

导入需要独占一行。

```python
Yes: import os
     import sys
```

```python
No:  import os, sys
```

导入总应该放在文件顶部，位于模块注释和文档字符串之后，模块全局变量和常量之前。导入应该按照以下顺序分组:

1. 标准库导入，比如：`import sys`

2. 第三方库导入，比如：`import tensorflow as tf`

3. 应用程序指定导入，比如：`from otherproject.ai import mind`




导入的每一部分需要按字典序排序，忽略大小写。

```python
import collections
import Queue
import sys

import argcomplete
import BeautifulSoup
import cryptography
import tensorflow as tf

from otherproject.ai import body
from otherproject.ai import mind
from otherproject.ai import soul

from myproject.backend.hgwells import time_machine
from myproject.backend.state_machine import main_loop
```



### 3.14 语句（Statements）

通常每个语句独占一行。

不过， 如果仅仅只有if语句，可以把整个语句放在一行。 如果为了测试，临时这么做也是可以的。

```python
Yes:

  if foo: bar(foo)
  import pdb; pdb.set_trace()
```

```python
No:

  if foo: bar(foo)
  else:   baz(foo)

  try:               bar(foo)
  except ValueError: baz(foo)

  try:
      bar(foo)
  except ValueError: baz(foo)
```



#### 3.15 访问控制（Access Control）



#### 3.16 命名（Naming）

Python命名分为许多种类：

`module_name`, `package_name`, `ClassName`, `method_name`, `ExceptionName`, `function_name`, `GLOBAL_CONSTANT_NAME`,`global_var_name`, `instance_var_name`, `function_parameter_name`, `local_var_name`。



#### 3.16.1应该避免的名称

> 1. 单字符名称， 除了计数器和迭代器。
> 2. 包/模块名中的连字符(-)。
> 3. 双下划线开头并结尾的名称(除了Python保留的例如__init__)。

#### 3.16.2 命名约定

> 1. 所谓"内部(Internal)"表示仅模块内可用，或者, 在类内是保护或私有的。
> 2. 用单下划线(_)开头表示模块变量或函数是protected的(使用import * from时不会包含)。
> 3. 用双下划线(__)开头的实例变量或方法表示类内私有。
> 4. 将相关的类和顶层函数放在同一个模块里。不像Java, 没必要限制一个类一个模块。
> 5. 对类名使用大写字母开头的单词(如CapWords, 即Pascal风格)，但是模块名应该用小写加下划线的方式(如lower_with_under.py)。尽管已经有很多现存的模块使用类似于CapWords.py这样的命名，但现在已经不鼓励这样做，因为如果模块名碰巧和类名一致，这会让人困扰。

#### 3.16.3 文件命名

Python文件名必须是`.py`的扩展名，不能包含连字符(`-`)。因此这些文件可以被导入和单元测试。如果你想要一个没有扩展名的可执行文件，使用软链接或者是一个bash来包装 `exec "$0.py" "$@"`。

#### 3.16.4 Guido van Rossum推荐的命名规范

| 类型（Type）                   | 公共（Public）           | 内部（Internal）                      |
| -------------------------- | -------------------- | --------------------------------- |
| Packages                   | `lower_with_under`   |                                   |
| Modules                    | `lower_with_under`   | `_lower_with_under`               |
| Classes                    | `CapWords`           | `_CapWords`                       |
| Exceptions                 | `CapWords`           |                                   |
| Functions                  | `lower_with_under()` | `_lower_with_under()`             |
| Global/Class Constants     | `CAPS_WITH_UNDER`    | `_CAPS_WITH_UNDER`                |
| Global/Class Variables     | `lower_with_under`   | `_lower_with_under`               |
| Instance Variables         | `lower_with_under`   | `_lower_with_under` (protected)   |
| Method Names               | `lower_with_under()` | `_lower_with_under()` (protected) |
| Function/Method Parameters | `lower_with_under`   |                                   |
| Local Variables            | `lower_with_under`   |                                   |

Python 通过双下划线命名来支持私有变量。但是最好使用单下划线来作为内部变量访问。



### 3.17 主函数（Main）

每一个可执行脚本都应该能被导入，并且导入不会执行这个脚本的主要功能部分。 主要功能部分应该被放在主函数中。

代码在执行主程序前应该检查`if __name__ == '__main__'`，这样当模块被导入时，这部分代码就不会被执行。

```python
def main():
    ...

if __name__ == '__main__':
    main()
```

所有的顶层代码在模块导入时都会被执行。因此要小心在全局中调用函数，创建对象的操作，需要测试的代码写在`if __name__ == '__main__'`下面。



### 3.18 函数长度

推荐使用小而精的函数。

有时候一段比较长的函数是比较合适的，所以这里不会过多地限制函数的长度。如果一个函数超过40行，那么要考虑一下它是否能被合理地拆分。一个很长的函数可能在这个需求下是适用的，并且没有bug，但是如果新增了需求需要对它进行改动，在多次改动后可能会导致难以找到的bug。函数应该是简洁明了，易于他人维护的。

如果你正好遇到一个函数代码量非常地长并且复杂，那么最好先把它拆分为多个函数易于管理。不要觉得拆分是一件很困难的事情，为了你的长远考虑，我建议你这么做。



### 3.19 类型注释



## 4 临别赠言

`务必保持代码的一致性`

如果你正在编辑代码，花几分钟看一下周边代码，然后决定风格。如果它们在所有的算术操作符两边都使用空格，那么你也应该这样做，如果它们的注释都用标记包围起来，那么你的注释也要这样。

制定风格指南的目的在于让代码有规可循，这样人们就可以专注于"你在说什么"，而不是"你在怎么说"。我们在这里给出的是全局的规范，但是本地的规范同样重要。如果你加到一个文件里的代码和原有代码大相径庭，它会让读者不知所措，请避免这种情况。



| 版本号   | 制订人（团队） | 更新日期       | 备注   |
| ----- | ------- | ---------- | ---- |
| 1.0.0 | 艾耕工程架构部 | 2018年7月30日 | 初版发布 |
|       |         |            |      |

