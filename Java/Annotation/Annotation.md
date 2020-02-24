# Annotation 

## What is Annotation?
It provides data about a program that is not part of the program itself.

1. To detect errors or supppress warnings.
2. To generate code, XML files.

## The Format of an Annotation
```java
@Override

@Author(name = "Owen")
```

## Where Annotations Can Be Used

> When used on a declaration, each annotation often appears, by convention, on its own line.

```java
@Getter
@Setter
private int age;
```

## Predefined Annotation Types

1. `@Deprecated`: The compiler generates a warning whenever a program uses a method, class, or field with the `@Deprecated` annotation.

2. `@Override`: informs the compiler that the element is meant to override an element declared in a superclass.

3. `@SuppressWarnings`: tells the compiler to suppress specific warnings that it would otherwise generate.

4. `@Retention`: specifies how the marked annotation is stored:
    1. RetentionPolicy.SOURCE - Retained only in the source level, but will be ignored by the compiler.
    2. RetentionPolicy.CLASS - Retained by the compiler, but will be ignored by JVM.
    3. RetentionPolicy.RUNTIME - Retained by the JVM so it can be used by the runtime environment.



