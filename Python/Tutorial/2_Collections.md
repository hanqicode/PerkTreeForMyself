# Collections

## List
list是一种有序的集合，可以随时添加和删除其中的元素。

Definition:
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

Operations:
```python
>>> classmates.append('Adam')
>>> classmates.insert(1, 'Jack')
>>> classmates.pop() # remove the last element
'Adam'
>>> classmates.pop(1)
'Jack'
>>> classmates[1] = 'Sarah' # set/replace element
```

Members:
```python
>>> L = ['Apple', 123, True] # can hold different types
```

## Tuple
tuple和list非常类似，但是tuple一旦初始化就不能修改.

Definition:
```python
>>> classmates = ('Michael', 'Bob', 'Tracy')
```

## Dict
Get:
```python
>>> d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
>>> d['Michael'] # may get Error when key is not exist
95
```

Insert:
```python
>>> d['Adam'] = 67
>>> d['Adam']
67
```

Check:
```python
>>> 'Thomas' in d
False
```

Safely Get:
```python
>>> d.get('Thomas') # return None
>>> d.get('Thomas', -1)
-1
```

Remove:
```python
>>> d.pop('Bob')
75
```

## Set
Creation:
```python
>>> s = {1, 2, 3}
>>> s
{1, 2, 3}
```

Add/Remove:
```python
>>> s.add(4)
>>> s.remove(4)
```

