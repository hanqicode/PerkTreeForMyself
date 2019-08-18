# General
Homepage: https://projectlombok.org/

## Motivation
It will make our code cleaner by using Lombok.
I will focus on Lombok **Stable** features here.

## Features

### @NonNull
[Detailed link](https://projectlombok.org/features/NonNull)

Add `@NonNull` on the parameters of:
1. a method
2. a constructor

to have lombok generate a null-check statement for us.

It will throw `NullPointerException` if it is null.

```java
public void doSomething(@NonNull final String name) {
	// omitted here
}
```

### @Getter, @Setter
[Detailed link](https://projectlombok.org/features/GetterSetter)

Add `@Getter` and `@Setter` to any field to let lombok generate the default getter/setter automatically.

The generated getter/setter method is `public` access level by default.

You can specify it with `AccessLevel`.

```java
public class GetterSetterExample {

    @Getter
    @Setter
    private int age = 30;

    @Setter(AccessLevel.PROTECTED)
    private String name;
}
```

### @NoArgsConstructor, @RequiredArgsConstructor, @AllArgsConstructor
[Detailed link](https://projectlombok.org/features/constructor)

Use these annotations to avoid boilerplate code.

`@NoArgsConstructor` generates a constructor with no parameters. It can be forced when not possible(becaues of final fields), but we need to double think.

`@RequiredArgsConstructor` generates a constructor with 1 parameter for each field that:
1. non-initialized `final` fields.
2. marked as `@NonNull`.

`@AllArgsConstructor` generates a constructor with 1 parameter for each field in the class.

Static fields are skipped by these annotations.

```java
@RequiredArgsConstructor(access = AccessLevel.PROTECTED)
public class ConstructorExample {

    @NonNull
    private String name;
}
```

### @Data
[Detailed link](https://projectlombok.org/features/Data)

`@Data` is a convenient shortcut annotation that bundles the feature of `@ToString`, `@EqualsAndHashCode`, `@Getter`, `@Setter` and `@RequiredArgsConstructor` together.

In other words, `@Data` generates all the boilerplate that is normally associated with simple POJO(Plain Old Java Objects) and beans.

```java
@Data
public class DataExample {
    private final String name;
    private final String title;
}
```

### @Value
[Detailed link](https://projectlombok.org/features/Value)

`@Value` is the **immutable** variant of `@Data`.

All fields are made `private` and `final` by default, and `setters` are not generated. The class itself is also made `final` by default.

```java
@Value
public class ValueExample {
    String name;
    double score;
}
```
