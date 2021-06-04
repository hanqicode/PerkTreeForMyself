# Streams

Stream: a sequence of elements that does not save the elements or modify the original source.

Stream can only be used once.

## Creating Streams
Two ways:
1. use the static factory methods in the `Stream` interface;
2. use the `stream()` methods on `Iterable` or `Arrays`;

## Boxed Streams
Create a collection from a primitive stream:
```java
List<Integer> ints = IntStream.of(3, 1, 4, 5)
  .boxed() // convert int to Integer
  .collect(Collectors.toList());
```

## Reduce
You want to produce a single value from stream operations, like sum or average;
```java
list.stream().count();
list.stream().max(Integer::compareTo);
// min()
// sum()
// average()
```

## Summary Statistics
You want the count, max, min, sum, average of a stream of numerical values.
```java
DoubleSummaryStatistics stats = DoubleStream.generate(Math::random)
  .limit(100)
  .summaryStatistics();

stats.getCount();
stats.getMin();
stats.getMax();
stats.getSum();
stats.getAverage();
```

## Peek
forEach operation but can still generate a new stream:
```java
list.stream()
  .peek(n -> System.out.println(n))
  .sum();
```

## Finding the First Element
Find the first element in a stream that satisfies a particular condition.

Use `findFirst` or `findAny` method after applying a filter.
```java
Stream.of(3, 1, 5, 4)
  .filter(n -> n % 2 == 0)
  .findFirst();
```

## flatMap vs map
`flatMap` will "fattens" the resulting stream by removing each element from the individual streams and adding them to the output;

```java
Customer c1 = new Customer("xxx);
Customer c2
Customer c3

c1.addOrder("1");
c1.addOrder("2");
c1.addOrder("3");

c2.addOrder("4");
c2.addOrder("5");

customers.stream()
  .map(Customer::getOrder)
  .forEach(System.out::println);

// [Order1, Order2, Order3], [Order4, Order5], []

customers.steam()
  .flatMap(customer -> customer.getOrders().stream())
  .forEach(System.out::println);

// [Order1, Order2, Order3, Order4, Order5]
```
