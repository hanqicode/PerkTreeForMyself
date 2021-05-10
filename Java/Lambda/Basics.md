# Basics

## Method Reference
Using a lambda expression:
```java
Stream.of(3, 1, 4).forEach(x -> System.out.println(x));
```
Using a method reference:
```java
Stream.of(3, 1, 4).forEach(System.out::println);
```

The method reference provides a couple of advantages over the lambda syntax:
1. shorter
2. often includes the name of the class containing the method
3. be consistent when using static methods like `Math::random`

All make the code easier to read.

