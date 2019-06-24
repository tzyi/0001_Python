
# ch4_基本輸入輸出

> 1. print()格式化用法
> 2. 輸出資料到檔案
> 3. 輸入資料input()

## 1.print()格式化用法

## 1-1. print()基本介紹

print(value,sep=" ",end="\n",file=sys.stout,flush=False)

- value:要輸出的值
- sep:當書處多筆資料時，用什麼隔開
- end:輸出結束所插入的字元，預設是換行
- file:資料輸出位置，sys.stout就是螢幕
- flush:是否清除資料流的緩衝區，預設是不清除


```python
a='god'
b='damn'


print(a,b,sep=" &&& ")
```

    god &&& damn



```python
# 我们也可以输出到错误输出流，例如：
import sys
print('hello world!', file=sys.stderr)
```

    hello world!


## 1-2.格式化輸出

print("輸出格式區" % "變數區")

- %d:整數
- %f:浮點數
- %s:字串
<br><br>

- %o:8進位
- %x:16進位


```python
a=83.99

print("輸出整數:%d" % (a))
print("輸出浮點數:%f" % (a))
print("輸出字串:%s" % (a))

print('\n')

b=99
print("%o,%x" % (b,b))
#print("%x" % (b))
```

    輸出整數:83
    輸出浮點數:83.990000
    輸出字串:83.99
    
    
    143,63


## 1-3.精準控制格式化輸出

- %+/-nd:整數
- %+/-m.nf:浮點數
- %+/-ns:字串
    
    
對浮點數來說，m是保留多少格數供輸出(含小數點)，n則是小數點資料保留格數。

其他資料格式，m代表保留多少格數，若保留格數不足，則完整輸出，若保留格數太多，資料會向右對齊。


```python
x=99
print("/%6d/" % (x))

print("##############################################")

y=99.999
print("%6.0f" %(y))
print("%6.1f" %(y))
print("%6.2f" %(y))
print("%6.3f" %(y))
print("%6.4f" %(y))
print("%6.5f" %(y))

print('\n')

print("%4.0f" % (y))
print("%4.1f" % (y))
print("%4.2f" % (y))
print("%4.3f" % (y))
print("%4.4f" % (y))
print("%4.5f" % (y))
```

    /    99/
    ##############################################
       100
     100.0
    100.00
    99.999
    99.9990
    99.99900
    
    
     100
    100.0
    100.00
    99.999
    99.9990
    99.99900


## 1-4. format()

print("輸出格式區".format(變數1,變數2.....))


```python
score=99
student='吳披薩'

print("{}的分數是{}".format(student,score))
```

    吳披薩的分數是99


## 1-5. 無聊操作


```python
a='pizza'*100
print(a)
```

    pizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizzapizza


##################################################################################################

## 2.輸出資料到檔案

## 2-1.開啟一個檔案

open()可以開啟一個檔案供讀寫:
    
file_Obj = open(file,mode="r")
開啟檔案寫完後，記得要關閉物件file_Obj.close()才可到系統看到產生的檔案。

- file_Obj:檔案物件，可自行取名字
- file:用字串列出欲開啟的檔案
- mode:

| 模式 | 說明 |
|--|--|
| r | 預設，開啟檔案供讀取 |
| w | 開啟檔案供寫入，若原先檔案有內容會被覆蓋 |
| a | 開啟檔案供寫入，若原先檔案有內容會在後面附加 |
| x | 開啟檔案"一個新檔案"供寫入，若檔案已存在會報錯 |
| b | 開啟二進位檔案模式 |
| t | 開啟文字檔案模式，預設 |
| \+ | 開啟檔案供更新用 |


```python
# 將這段執行兩次，可看到差異
file_w1 = open("open_test.txt",mode="w")
print("pizza is my dog.",file=file_w1)
file_w1.close()

file_w2 = open("open_test2.txt",mode="a")  
print("pizza is my dog.",file=file_w2)
file_w2.close()
```

#######################################################################################################

## 3.輸入資料input()


```python
a = input("輸入一個國家:")
print(a)
```

    輸入一個國家:台灣
    台灣



```python
dir()
```




    ['In',
     'Out',
     '_',
     '_39',
     '_40',
     '__',
     '___',
     '__builtin__',
     '__builtins__',
     '__doc__',
     '__loader__',
     '__name__',
     '__package__',
     '__spec__',
     '_dh',
     '_i',
     '_i1',
     '_i10',
     '_i11',
     '_i12',
     '_i13',
     '_i14',
     '_i15',
     '_i16',
     '_i17',
     '_i18',
     '_i19',
     '_i2',
     '_i20',
     '_i21',
     '_i22',
     '_i23',
     '_i24',
     '_i25',
     '_i26',
     '_i27',
     '_i28',
     '_i29',
     '_i3',
     '_i30',
     '_i31',
     '_i32',
     '_i33',
     '_i34',
     '_i35',
     '_i36',
     '_i37',
     '_i38',
     '_i39',
     '_i4',
     '_i40',
     '_i41',
     '_i5',
     '_i6',
     '_i7',
     '_i8',
     '_i9',
     '_ih',
     '_ii',
     '_iii',
     '_oh',
     'a',
     'b',
     'exit',
     'file_w1',
     'file_w2',
     'file_write1',
     'get_ipython',
     'quit',
     'score',
     'str1',
     'student',
     'sys',
     'x',
     'y']




```python
# 列出python內建函數
dir(__builtins__)
```




    ['ArithmeticError',
     'AssertionError',
     'AttributeError',
     'BaseException',
     'BlockingIOError',
     'BrokenPipeError',
     'BufferError',
     'BytesWarning',
     'ChildProcessError',
     'ConnectionAbortedError',
     'ConnectionError',
     'ConnectionRefusedError',
     'ConnectionResetError',
     'DeprecationWarning',
     'EOFError',
     'Ellipsis',
     'EnvironmentError',
     'Exception',
     'False',
     'FileExistsError',
     'FileNotFoundError',
     'FloatingPointError',
     'FutureWarning',
     'GeneratorExit',
     'IOError',
     'ImportError',
     'ImportWarning',
     'IndentationError',
     'IndexError',
     'InterruptedError',
     'IsADirectoryError',
     'KeyError',
     'KeyboardInterrupt',
     'LookupError',
     'MemoryError',
     'ModuleNotFoundError',
     'NameError',
     'None',
     'NotADirectoryError',
     'NotImplemented',
     'NotImplementedError',
     'OSError',
     'OverflowError',
     'PendingDeprecationWarning',
     'PermissionError',
     'ProcessLookupError',
     'RecursionError',
     'ReferenceError',
     'ResourceWarning',
     'RuntimeError',
     'RuntimeWarning',
     'StopAsyncIteration',
     'StopIteration',
     'SyntaxError',
     'SyntaxWarning',
     'SystemError',
     'SystemExit',
     'TabError',
     'TimeoutError',
     'True',
     'TypeError',
     'UnboundLocalError',
     'UnicodeDecodeError',
     'UnicodeEncodeError',
     'UnicodeError',
     'UnicodeTranslateError',
     'UnicodeWarning',
     'UserWarning',
     'ValueError',
     'Warning',
     'ZeroDivisionError',
     '__IPYTHON__',
     '__build_class__',
     '__debug__',
     '__doc__',
     '__import__',
     '__loader__',
     '__name__',
     '__package__',
     '__spec__',
     'abs',
     'all',
     'any',
     'ascii',
     'bin',
     'bool',
     'bytearray',
     'bytes',
     'callable',
     'chr',
     'classmethod',
     'compile',
     'complex',
     'copyright',
     'credits',
     'delattr',
     'dict',
     'dir',
     'display',
     'divmod',
     'enumerate',
     'eval',
     'exec',
     'filter',
     'float',
     'format',
     'frozenset',
     'get_ipython',
     'getattr',
     'globals',
     'hasattr',
     'hash',
     'help',
     'hex',
     'id',
     'input',
     'int',
     'isinstance',
     'issubclass',
     'iter',
     'len',
     'license',
     'list',
     'locals',
     'map',
     'max',
     'memoryview',
     'min',
     'next',
     'object',
     'oct',
     'open',
     'ord',
     'pow',
     'print',
     'property',
     'range',
     'repr',
     'reversed',
     'round',
     'set',
     'setattr',
     'slice',
     'sorted',
     'staticmethod',
     'str',
     'sum',
     'super',
     'tuple',
     'type',
     'vars',
     'zip']




```python
help(round)
```

    Help on built-in function round in module builtins:
    
    round(...)
        round(number[, ndigits]) -> number
        
        Round a number to a given precision in decimal digits (default 0 digits).
        This returns an int when called with one argument, otherwise the
        same type as the number. ndigits may be negative.
    



```python

```
