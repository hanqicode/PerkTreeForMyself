# Observer Design Pattern

## What is Observer pattern?
Used for one-to-many situation. Like: many customers subsribe a single product update.

The key object in this pattern are: subject and observer. The another understanding is: Pub-Sub.

## Example
For subject:
```java
public interface Subject {
    public void subscribeObserver(Observer observer);
    public void unsubscribeObserver(Observer observer);
    public void notifyObservers(); 
}
```

For object:
```java
public interface Observer {
    public void update(Message message);
    public void subsribe();
    public void unsubsribe();
}
```

## Notes
There is a class `Observable` in Java and we could extend it to implement our business logic.

To me, this is a good pattern when we develop from nothing. But, we already have many mature tools that can help us to do
so and even better, like Amazon SNS.

Also, we should avoid to use inheritance to loose coupling.
