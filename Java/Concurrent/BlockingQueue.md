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

Note: Row title means what will happen if the attempted operation is not possible immediately; 

## Notes
1. A BlockingQueue cannot accept `null`. Otherwise, it will throw `NullPointerException`.
2. A BlockingQueue can be capacity bounded or unbounded.
   If initiate without intrinsic capacity constraints, it will use `Integer.MAX_VALUE`.
3. BlockingQueue is thread-safe, which means it can safely be used with multiple producers and multiple consumers.

## Example
```java
 public class Demo {

    public static void main(String[] args) throws Exception {
        BlockingQueue<Integer> blockingQueue = new ArrayBlockingQueue<Integer>(1000);

        Producer producer = new Producer(blockingQueue);
        Consumer consumer = new Consumer(blockingQueue);

        new Thread(consumer).start();

        for (int i = 0; i < 100; i++) {
            producer.produce(i);
            Thread.sleep(1000L);
        }

        System.out.println("-- End --");
    }
}

@RequiredArgsConstructor
public class Producer{

    @NonNull
    private BlockingQueue<Integer> blockingQueue;

    public void produce(Integer i) {
        try {
            blockingQueue.put(i);
        } catch (InterruptedException e) {
            System.out.println("Exception when putting a new element. " + e);
        }
    }
}

@RequiredArgsConstructor
public class Consumer implements Runnable {

    @NonNull
    private BlockingQueue<Integer> blockingQueue;

    @Override
    public void run() {
        while (true) {
            if (!blockingQueue.isEmpty()) {
                consume();
            }
        }
    }

    private void consume() {
        System.out.println("[Queue] current queue size: " + blockingQueue.size());

        try {
            Integer i = blockingQueue.take();
            System.out.println("Now processing: " + i);
        } catch (InterruptedException e) {
            System.out.println("Exception when taking a new element. " + e);
        }
    }
}
```
