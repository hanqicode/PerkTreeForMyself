# Singleton Design Pattern

## What is Singleton pattern?
Sometimes it's important for some classes to have exactly one instance.

## Example
The simplest code but not correct enough looks like:
```java
public class SingletonClass {
    public static SingletonClass sc = new SingletonClass();
}
```

Due to several considerations, we need to revise it to this one:
```java
public class SingletonLazyMultiThreaded {

    private static SingletonLazyMultiThreaded sc = null;

    private SingletonLazyMultiThreaded() {}

    public static synchronized SingletonLazyMultiThreaded getInstance() {
        if (sc == null) {
            sc = new SingletonLazyMultiThreaded();
        }

        return sc;
    }
}
```
