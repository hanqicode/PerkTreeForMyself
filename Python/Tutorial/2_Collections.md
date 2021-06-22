# Collections

## List
list是一种有序的集合，可以随时添加和删除其中的元素。

### Definition
```python
>>> classmates = ['Michael', 'Bob', 'Tracy']
>>> classmates
['Michael', 'Bob', 'Tracy']
>>> len(classmates)
3
>>> classmates[0]
'Michael'
>>> classmates[-1] # to get the last element
'Tracy'
```

### Operations
```python
>>> classmates.append('Adam')
>>> classmates.insert(1, 'Jack')
>>> classmates.pop() # remove the last element
'Adam'
>>> classmates.pop(1)
'Jack'
>>> classmates[1] = 'Sarah' # set/replace element
```

### Types
```python
>>> L = ['Apple', 123, True] # can hold different types
```

## Tuple
tuple和list非常类似，但是tuple一旦初始化就不能修改.

### Definition
```python
>>> classmates = ('Michael', 'Bob', 'Tracy')
```
