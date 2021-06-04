# Issues

## Objects Not Null
```java
list.stream()
  .filter(Objects::nonNull)
  .collect(Collectors.toList());
```

## Lambda and Finals
Local variables are accessible but cannot be modified;
