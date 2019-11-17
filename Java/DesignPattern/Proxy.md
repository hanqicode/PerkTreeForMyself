# Proxy Design Pattern

## What is Proxy pattern?
> Another reason could be to act as a local representative for an object that lives in a different JVM. 

## Example
This is what we used in development.

Our service A depends on service B. What we used in our package should be service B client.  
But sometimes it may be not suitable to call B client's API directly. Like:
```java
public String method(final String contactId) {
    final String sessionId = createSessionIdFromContactId(contactId);
    return client.getTreatmentWithSessionId(sessionId);
}

private String createSessionIdFromContactId(final String contactId) {
    // omit here
}
```

So, here we can see we need to do data conversion first and then call API.  
It would be better to encapsulate data conversion inside the proxy instead of exposing this and let caller to handle.
