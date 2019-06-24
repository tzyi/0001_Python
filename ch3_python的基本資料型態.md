
# ch3_python的基本資料型態

> 1. 數值資料
> 2. 布林資料
> 3. 字串

## 1.數值資料

## 1-1.各種進位 二進位bin()、八進位oct()、十六進位hex()

python中凡是0b開頭的數字，代表這是一個二進位的整數。<br>
python中凡是0o開頭的數字，代表這是一個八進位的整數。<br>
python中凡是0x開頭的數字，代表這是一個十六進位的整數。<br>


```python
x = 13
print(bin(x))
print(oct(x))
print(hex(x))
```

    0b1101
    0o15
    0xd



```python
# 若是浮點數呢?

x = 34.5
print(bin(x))
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-4-526e710acd6b> in <module>
          2 
          3 x = 34.5
    ----> 4 print(bin(x))
    

    TypeError: 'float' object cannot be interpreted as an integer


## 1-2.數值運算常用的函數

abs():絕對值<br>
pow(x,y):返回x的y次方<br>
round():返回四捨五入<br>


```python
a=-15
print(abs(a))

b=2
print(pow(b,3))
```

    15
    8



```python
a=33.2
b=33.5
c=33.6
d=33.7

print(round(a))
print(round(b))
print(round(c))
print(round(d))
```

    33
    34
    34
    34


## 1-3.(TIPS)向上、下取整數

向上取整math.ceil(2.3)<br>
向下取整math.floor(2.3)


```python
import math

a=2.3

print(math.ceil(a))
print(math.floor(a))
```

    3
    2


##########################################################################################################

## 2.布林資料

## 2-1.認識布林值

布林值常用於流程控制中，特別是在條件運算式中id...else，程式可以根據布林值判斷如何執行工作。


```python
x = True
y = False

print(type(x),type(y))
print(x,y)
```

    <class 'bool'> <class 'bool'>
    True False


## 2-2.布林值換成整數

True=1
False=0


```python
x = True
y = False

print(int(x),int(y))
print(float(x),float(y))
```

    1 0
    1.0 0.0


###################################################################################################################

## 3.字串

## 3-1.處理多於一行的字串

用三個單引號包夾起來'''xxxxxx'''


```python
str1 = '''你在幹什麼??
我在玩狗!!!!!
'''

print(str1)
```

    你在幹什麼??
    我在玩狗!!!!!
    


## 3-2.逸出字元

![](https://images2.imgbox.com/98/bc/a2rzzsEn_o.jpeg)



## 3-3. 字元資料的轉換

如果一個字串含一個字元或一個文字時，我們可以利用以下執行資料轉換:

- chr(x):可以傳回x值的字元，x是ASCII碼值
- ord(x):可以傳回函數字元參數的Unicode碼值，如果是中文字也可以傳回Unicode碼值，如果是英文字，則ASCII和Unicode值一樣。



```python
a=99
b='d'
c='吳'


print(chr(a))
#print(chr(b))  #chr()參數必須是ASCII值
#print(chr(c))


print('\n')

d=chr(a)
print(ord(d))  # 輸出Unicode值


print('\n')


print(ord(b))
print(ord(c))
```

    c
    
    
    99
    
    
    100
    21555



