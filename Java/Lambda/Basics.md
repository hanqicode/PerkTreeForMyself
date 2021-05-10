# Basics

## Method Reference
```java
Stream.of(3, 1, 4).forEach(x -> System.out.println(x)); // using a lambda expression

Stream.of(3, 1, 4).forEach(System.out::println); // using a method reference
```

The method reference provides a couple of advantages over the lambda syntax:
1. shorter
2. often includes the name of the class containing the method
3. be consistent when using static methods like `Math::random`

All make the code easier to read.

## Constructor Reference
```java
List<String> names = Arrays.asList("Qi", "Owen");

List<Person> people = names.stream().map(name -> new Person(name)).collect(Collectors.toList()); // using a lambda expression

List<Person> people = names.stream().map(Person::new).collect(Collectors.toList()); // using a constructor reference
```

