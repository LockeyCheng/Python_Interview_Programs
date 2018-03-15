### 1、用Python来进行查询和替换一个文本字符串

	>>> words.find('is') 
	>>> words.replace('tobereplace', 'Perl')  # replace()替换  

### 2、Python如何copy一个文件

    >>> import shutil  
    >>> shutil.copyfile('a.py', 'copy_a.py')

### 3、Python判断当前用户是否是root

    import os  
    if os.getuid() != 0:    # root账号的uid=0  
        print os.getuid()  
        print 'Should run as root account'  
    else:  
        print 'Hello, Root!'  

### 4、介绍一下Python中webbrowser的用法

    webbrowser模块提供了一个高级接口来显示基于Web的文档，大部分情况下只需要简单的调用open()方法。  
      
    webbrowser定义了如下的异常：exception webbrowser.Error, 当浏览器控件发生错误是会抛出这个异常  
      
    webbrowser有以下方法：  
      
    webbrowser.open(url[, new=0[, autoraise=1]])  
      
    这个方法是在默认的浏览器中显示url, 如果new = 0, 那么url会在同一个浏览器窗口下打开，如果new = 1, 会打开一个新的窗口，如果new = 2, 会打开一个新的tab, 如果autoraise ＝ true, 窗口会自动增长。  
      
    webbrowser.open_new(url)  
    在默认浏览器中打开一个新的窗口来显示url, 否则，在仅有的浏览器窗口中打开url  
      
    webbrowser.open_new_tab(url)  
    在默认浏览器中当开一个新的tab来显示url, 否则跟open_new()一样  
      
    webbrowser.get([name]) 根据name返回一个浏览器对象，如果name为空，则返回默认的浏览器  
      
    webbrowser.register(name, construtor[, instance])  
    注册一个名字为name的浏览器，如果这个浏览器类型被注册就可以用get()方法来获取。 

### 5、以下操作输出是什么？

    >>> t = set("Hello")

    答：
    >>> t  
    set(['H', 'e', 'l', 'o'])  

### 6、以下操作分别输出什么？

    >>> x = [4, 3, 6, 1, 2, 5]
    >>> x[10:]

    #[]
    >>> x[10]
    
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    IndexError: list index out of range