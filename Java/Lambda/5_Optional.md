# Optional

`java.util.Optional<T>`

## Motivation
While many developers assume that the goal of `Optional` is to remove `NullPointerException` from your code, that's not its real purpose.
Instead, `Optional` is designed to communicate to the user when a returned value may legitimately be null.

When will this(can return null) happen?
A stream does filter operation and leave no elements remaining!
- reduce
- min
- max
- findFirst
- findAny

## State
Two states:
1. **present**: a reference to an instance of type T
2. **empty**: empty

## Create
```java
Optional.ofNullable(value);
// same effect
return value == null ? Optional.empty() : Optional.of(value);
```

## Retrieve
`optional.get()` to retrieve the value;
```java
if (value == null) {
  throw new NoSuchElementException("No value present");
}
return value;
```

`optional.orElse(T t)` to prevent the exception;
