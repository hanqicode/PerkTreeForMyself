# Redis Cookbook
Also refer to [Redis Quick Start](https://redis.io/topics/quickstart)

## What is Redis?
It is a data structure server with an in-memory dataset for speed.

## When to use Redis?
It would be ideal if we use NoSQL databases, like DynamoDB.

## Quick Start
### Start Server
```
$ redis-server

Port: 6379
PID: 73063
Server initialized
Ready to accept connections
```

### Test Ping
```
$ redis-cli ping                                                                                                                 
PONG
```

### Set/Get Value from CLI
```
$ redis-cli set myname hanqi                                                                                                  
OK

$ redis-cli get myname
"hanqi"
```

### Using Redis from Java Client
In order to access Redis, we need to use clients.

There are several clients in different programming languages. Here we take Java for example.
This is [all Java clients](https://redis.io/clients#java).

For example, we use `Jedis`.
```java
Jedis jedis = new Jedis("localhost");
jedis.set("myName", "hanqi");

String value = jedis.get("myName");
System.out.println(value);
```
