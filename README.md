# python-learn
这次真的会学下去吗？工作压力也许会使学习效率更高...
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
    1.class 后面就是类的名字
