# Functions

[Website link](https://www.liaoxuefeng.com/wiki/1016959663602400/1017105145133280)

## Invocation
```python
a = abs(-10)
b = max(1, 0, 3, 0)
```

Convertion:
```python
>>> int('123')
123
>>> int(12.34)
12
>>> float('12.34')
12.34
>>> str(1.23)
'1.23'
>>> str(100)
'100'
>>> bool(1)
True
>>> bool('')
False
```

## Definition
```python
def get_sum(a, b):
    return a + b
```

Add type check:
```python
def get_sum(a, b):
    if not isinstance(a, int):
        raise TypeError("a and b must be Integer")
    return a + b
```
