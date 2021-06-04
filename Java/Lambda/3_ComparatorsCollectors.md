# Comparators and Collectors

## Sorting
Originally, we sort the collection itself:
```java
Collections.sort(list);
```

**Note**: it will modify the collection and it does not follow the principles of Java 8 "immutability";

So we will use this way:
```java
List<Integer> result = list.stream().sorted().collect(Collectors.toList());
```

## Adding a Linear Collection to a Map
You want to add a collection of objects to a Map, where the key is one of the object fields and the value is the object itself.
```java
Map<Integer, Book> bookMap = books.stream()
  .collect(Collectors.toMap(Book::getId, Function.identity()));
```

## Partition and Group
```java
Map<Integer, List<String>> map = list.stream()
  .collect(Collectors.groupingBy(String::length));
```
