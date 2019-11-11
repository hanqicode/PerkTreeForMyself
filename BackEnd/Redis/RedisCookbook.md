# Redis Cookbook
Also refer to [Redis Quick Start](https://redis.io/topics/quickstart)

## What is Redis?
It is a data structure server with an in-memory dataset for speed.

## When to use Redis?
It would be ideal if we use NoSQL databases, like DynamoDB.

## Start Server
```
$ redis-server

Port: 6379
PID: 73063
Server initialized
Ready to accept connections
```

## Test Ping
```
$ redis-cli ping                                                                                                                 
PONG
```

## Set/Get Value from CLI
```
$ redis-cli set myname hanqi                                                                                                  
OK

$ redis-cli get myname
"hanqi"
```

## Using Redis from Application
// Learn access with Java
