# Basic Utilities

## Using and Avoiding Null
`null` is unpleasantly ambiguous. 

Map.get(key) can return `null`:
- its value is null
- doesn't contain the key

So, `null` can mean fail, success, or real value. Most critically, `null` gives no indication what a `null` value means.

## Preconditions
We strongly recommend importing these statically from `Preconditions` class.

### checkArgument
```java
checkArgument(i < j, "Expected i < j, but %s >= %s", i, j);
```

### checkNotNull
Checks that the value is not null. Returns the value directly, so you can use `checkNotNull(value)` inline.

## Objects

### equals
```java
Objects.equal("a", "a"); // returns true
Objects.equal(null, "a"); // returns false
Objects.equal("a", null); // returns false
Objects.equal(null, null); // returns true
```

