# Python Basic

## Format and Indent
```python
# print absolute value of an integer:
a = 100
if a >= 0:
    print(a)
else:
    print(-a)
```
按照约定俗成的惯例，应该始终坚持使用**4个空格**的缩进。

## Data Types
Python 基本数据类型：
- Integer: `a = 1`
- Float: `a = 1.23`
- String: `a = "string"`, `'I\'m \"OK\"!'`
- Boolean: `True`, `False`, `True and/or/not False`
- None: `None`

## Variable
在Python中，等号`=`是赋值语句，可以把任意数据类型赋值给变量，同一个变量可以反复赋值，而且可以是不同类型的变量.

这种变量本身类型不固定的语言称之为**动态语言**，与之对应的是静态语言。静态语言在定义变量时必须指定变量类型，如果赋值的时候类型不匹配，就会报错。

```python
a = 'ABC'
```
1. 在内存中创建了一个'ABC'的字符串；
2. 在内存中创建了一个名为a的变量，并把它指向'ABC'。

## Constants
在Python中，通常用全部大写的变量名表示常量：
```python
PI = 3.14159265359
```

## Encoding
因为计算机只能处理数字，如果要处理文本，就必须先把文本转换为数字才能处理。

| Char      | ASCII | Unicode      | UTF-8 |
| ----------- | ----------- |----------- | ----------- |
| A      | 01000001       | 00000000 01000001      | 01000001       |
| 中   | x        |01001110 00101101   | 11100100 10111000 10101101        |

在计算机内存中，统一使用Unicode编码，
当需要保存到硬盘或者需要传输的时候，就转换为UTF-8编码。

E.g. 用记事本编辑的时候，从文件读取的UTF-8字符被转换为Unicode字符到内存里，编辑完成后，保存的时候再把Unicode转换为UTF-8保存到文件.

## String
在最新的Python 3版本中，字符串是以Unicode编码的，所以支持多种语言。
