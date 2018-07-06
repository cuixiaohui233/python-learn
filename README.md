# python-learn
## 模块
### 日志打印模块

logging：

    使用： 
    import logging
    # 通过下面的方式进行简单配置输出方式与日志级别
    logging.basicConfig(filename='logger.log', level=logging.INFO)

    logging.debug('debug message')
    logging.info('info message')
    logging.warn('warn message')
    logging.error('error message')
    logging.critical('critical message')
[更多关于 logging 的教程](https://www.jianshu.com/p/feb86c06c4f4)

    构造函数:
    1.轮询函数语法：TimedRotatingFileHandler:
        定义如下：
        TimedRotatingFileHandler(filename [,when [,interval [,backupCount]]])
            filename 是输出日志文件名的前缀

            when 是一个字符串的定义如下：

            “S”: Seconds
            “M”: Minutes
            “H”: Hours
            “D”: Days
            “W”: Week day (0=Monday)
            “midnight”: Roll over at midnight
            interval 是指等待多少个单位when的时间后，Logger会自动重建文件，当然，这个文件的创建取决于filename+suffix，若这个文件跟之前的文件
            有重名，则会自动覆盖掉以前的文件，所以有些情况suffix要定义的不能因为when而重复。

            backupCount 是保留日志个数。默认的0是不会自动删除掉日志。若设10，则在文件的创建过程中库会判断是否有超过这个10，若超过，则会从最先创
            建的开始删除。
    2.DatagramHandler 输出远程日志到 UDP sockets
    
    [更多](https://blog.csdn.net/yypsober/article/details/51800120)
### 正则模块
re:

    python 的正则：
    re.compile 函数，函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用。
    语法格式为：
    re.compile(pattern[, flags])
    参数：
    pattern : 一个字符串形式的正则表达式
    flags : 可选，表示匹配模式，比如忽略大小写，多行模式等，具体参数为：
        re.I 忽略大小写
        re.L 表示特殊字符集 \w, \W, \b, \B, \s, \S 依赖于当前环境
        re.M 多行模式
        re.S 即为 . 并且包括换行符在内的任意字符（. 不包括换行符）
        re.U 表示特殊字符集 \w, \W, \b, \B, \d, \D, \s, \S 依赖于 Unicode 字符属性数据库
        re.X 为了增加可读性，忽略空格和 # 后面的注释
### 日期和时间模块

    time:
    time.sleep(secs)
    推迟调用线程的运行，secs指秒数
    
### 进程通信模块

    socket：
    socket.gethostname() 获取本地主机名
## 面向对象

### 类
    class:
    类相当于一个抽象的模板，提供方法
    
### 实例
    instance：
    根据实例创建出来的具体的对象，方法相同，但是数据不同
    
### 举例：
    class student(object):
        pass
    xiaoming = Student();
    1.class 后面就是类的名字，通常首字母大写;
    2.紧接着是(object)，表示该类是从哪个类继承下来的;
    3.通过 类名+()去创建一个实例：bart = Student();
    4.给实例变量绑定属性，比如给 bart 绑定 age : bart.age = 18;
    
    由于类 class 可以起到模板的作用，所以在创建的时候可以给定默认值，默认方法，如:
    
        class Student(object):

            def __init__(self, name, score):
                self.name = name
                self.score = score
     注意到__init__方法的第一个参数永远是self，表示创建的实例本身，因此，在__init__方法内部，就可以把各种属性绑定到self，因为self就指向创建的实
     例本身。

    有了__init__方法，在创建实例的时候，就不能传入空的参数了，必须传入与__init__方法匹配的参数，但self不需要传，Python解释器自己会把实例变量传
    进去：

    >>> bart = Student('Bart Simpson', 59)
    >>> bart.name
    'Bart Simpson'
    >>> bart.score
        59
## 关键字

    global:
    全局变量 
    
### Python 中 __init__.py 的作用

    __init__.py 文件的作用是，将一个文件夹变成一个 Python 模块，Python 中的每个模块都有 __init__.py 文件
### Python 中的 * 和 ** 的区别

    * 代表tuple(('red','blue','green'))或者list(['red','blue','green'])
    ** 代表mapping({'red','blue','green'})或者dic（字典）({'color': 'red', 'color': 'blue'})
    
### if else 语句

    a = req['a'] if req.get('a') and req['a'] < 20 else 20
    这句话的意思是：如果 req.get('a') 存在，并且 req['a'] < 20 那么 a 就等于 req['a'] 否则 a 就等于 20
### 理解 Python 中的 if __name__ == '__main__'
    if __name__ == '__main__'的意思是：当.py文件被直接运行时，if __name__ == '__main__'之下的代码块将被运行；当.py文件以模块形式被导入
    时，if __name__ == '__main__'之下的代码块不被运行。
