# Best Practice to Log

## Why Need Good Log?
Log is expensive: It likely requires argument processing, disk writes, and storage.

## Example

**Bad**
```java
log.warn("Missing sessionID.");
```

**OK**
```java
log.warn(String.format("Missing sessionID in order %s for customer %s", orderID, customerID));
```

**Good**
```java
log.warn("Missing sessionID in order {} for customer {}.", orderID, customerID);
```

**Great/Best**
```java
log.warn("SessionID missing in order and customer, respectively(Order: {}, Customer: {}), rejecting request; 
please follow-up with the client service", orderID, customerID);
```

## What is the Fastest way of Logging?
Link: https://www.slf4j.org/faq.html#logging_performance

To use parameterized logging which can significantly boost logging performance for **disabled** logging statement.

**Bad**

See this for example:
```java
log.debug("Entry number: " + i + " is missing.");
```
It has a cost of constructing the message, no matter the message will be logged or not.

**OK**

One possible way to avoid this is checking log level:
```java
if (log.isDebugEnabled()) {
    log.debug("Entry number: " + i + " is missing.");
}
```
But it has a cost of evaluating whether the log is enabled or not, **twice**: in `debugEnabled` and `debug`.
It is still not good.

**Good**

By using parameterized messages
```java
log.debug("Entry number is {}", i);
```
After evaluating and only if the decision is affirmative, will the logger implementation format the message and replace {} with string.
In other words, it will not have the cost of construction in case the log is disabled.

## Don't Lose Parent Stack Trace

**Bad**
```java
try {
    ...
} catch (final IllegalArgumentException e) {
    log.warn("Missing sessionID");
    throw e;
}
```

**Good**
```java
try {
    ...
} catch (final IllegalArgumentException e) {
    log.warn("Missing sessionID", e);
    throw e;
}
```
