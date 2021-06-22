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
