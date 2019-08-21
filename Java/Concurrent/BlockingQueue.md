# BlockingQueue General
Java API doc: https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/BlockingQueue.html

## Motivation
This is a very useful tool to solve concurrent producer-consumer problem.

For example, we want to process some elements asynchronously.
1. Save the elements into BlockingQueue and continue the main function.
2. Assign a daemon thread to poll the elements and process them.

## What is BlockingQueue?
A queue that supports operations:
1. wait for the queue to become non-empty when retrieving an element.
2. wait for the queue to have available space when storing an element.

## What are operations?
|         | Throws exception | Special value | Blocks | Times out            |
|---------|------------------|---------------|--------|----------------------|
| Insert  | add(e)           | offer(e)      | put(e) | offer(e, time, unit) |
| Remove  | remove()         | poll()        | take() | poll(time, unit)     |
| Examine | element()        | peek()        | N/A    | N/A                  |

## Notes
1. A BlockingQueue cannot accept `null`. Otherwise, it will throw `NullPointerException`.
2. A BlockingQueue can be capacity bounded or unbounded.
   If initiate without intrinsic capacity constraints, it will use `Integer.MAX_VALUE`.
3. BlockingQueue is thread-safe, which means it can safely be used with multiple producers and multiple consumers.

## Example
```java
 class Producer implements Runnable {
   private final BlockingQueue queue;
   Producer(BlockingQueue q) { queue = q; }
   public void run() {
     try {
       while (true) { queue.put(produce()); }
     } catch (InterruptedException ex) { ... handle ...}
   }
   Object produce() { ... }
 }

 class Consumer implements Runnable {
   private final BlockingQueue queue;
   Consumer(BlockingQueue q) { queue = q; }
   public void run() {
     try {
       while (true) { consume(queue.take()); }
     } catch (InterruptedException ex) { ... handle ...}
   }
   void consume(Object x) { ... }
 }

 class Setup {
   void main() {
     BlockingQueue q = new SomeQueueImplementation();
     Producer p = new Producer(q);
     Consumer c1 = new Consumer(q);
     Consumer c2 = new Consumer(q);
     new Thread(p).start();
     new Thread(c1).start();
     new Thread(c2).start();
   }
 }
```
