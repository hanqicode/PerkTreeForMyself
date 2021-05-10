# Java Util Function Package

## Intro
Four categories:
1. consumers: take a generic argument and return nothing;
2. suppiers: take no arguments and return a value;
3. predicates: take an argument and return a boolean;
4. functions: take a single argument and return a value;

## Consumers
One example is `forEach`:
```java
names.forEach(System.out::println); // method reference

names.forEach(new Consumer<String>() { // Anonymous inner class
    @Override
    public void accept(String s) {
        System.out.println(s);
    }
});
```

## Suppliers
To use Supplier interface, you need to implement `get()` method.

For example, `Math.random` which takes no arguments and returns a double.

## Predicates
To use Predicate interface, you need to implement `test(T t)` method.

Predicates are used primarily to filter streams.

```java
Arrays.stream(names).filter(s -> s.length() == 5).collect(Collectors.toList());
```

## Functions
To use Function interface to transform an input parameter into an output value.

```java
names.stream().map(s -> s.length()).collect(Collectors.toList());
```
