# Flyweight Design Pattern

## What is Flyweight pattern?
It is used when we should not create more than one object like `manager`. We could reuse `manager` and no need to create
many of it.

For example: (This is not correct)
```java
public void enact(Message message) {
    Manager manager = new Manager();
    manager.process(message);
}
```

At least we could make it to:
```java
public class Activity {

    private Manager manager;

    public void enact(Message message) {
        manager.process(message);
    }
}
```

## Example
Say we have a `Message` class which is light-weight; and `Manager` here holds business logic which is a heavy to create and
occopies more memory.

```java
public class Message {

    @Getter
    @Setter
    private String payload;
}
```

```java
public class Manager {

    public void process(Message message) {
        // omit business logic here
    }
}
```

We should not create too many `Manager` inside our service but we could receive lots of `Message`.

## Notes
From my experience, we could make `Manager` to singleton.

Also, when there is multiple type of `Message` and multiple type of `Manager`, we could use:
1. switch case
2. factory pattern

to get corresponding `Manager` with input `Message`.
