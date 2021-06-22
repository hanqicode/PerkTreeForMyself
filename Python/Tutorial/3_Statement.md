# Statement

## if/else
```python
# This is a sample Python script.
a = int(input())

if a > 10:
    print("a > 10")
elif a == 10:
    print("a == 10")
else:
    print("a < 10")

```

use `birth = int(s)` to convert string to int;

## For In Loop
```python
names = ['Michael', 'Bob', 'Tracy']
for name in names:
    print(name)
```

```python
# This is a sample Python script.
a = list(range(101))  # 101 is excluded
b = 0

for num in a:
    b += num

print("sum is", b)
```

## While Loop
```python
a = 0

while a < 100:
    print("a is < 100", a)
    a += 1

print("done")
```

## Break/Continue
Same as in Java.
