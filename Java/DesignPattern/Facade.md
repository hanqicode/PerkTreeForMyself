# Facade Design Pattern

## What is Facade Pattern?
It is not mystery and it is very easy to understand from encapsulation view.

Say one example:

In order to start a job, you need to:
1. Set initial metadata.
2. Configure job with metadata.
3. Set job attributes, like execution time, etc.
4. Start the job.

We could simplify the process to:
1. start the job.

Only expose the simpliest thing to client. Only let client have the least knowledge.

## Example
```java
JobScheduler scheduler = new JobScheduler();

scheduler.setInitMetadata();
scheduler.configWithMetadata();
scheduler.setOtherAttributes();
schduluer.startJob();
```

It can be simplified to:
```java
JobScheduler scheduler = new JobScheduler();

scheduler.startJob();
```

We can hide all details inside the `scheduler.startJob()`. 

Pros:
1. It makes code clean and clear.
1. It is easier and safer for clients to use.
