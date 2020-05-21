# Overview

## Link
https://github.com/memcached/memcached/wiki/Overview

## What's mechanism on Client and Server?

### For Client
1. It has a list of available Memcached serviers.
2. A client-based hashing algorithm, which choose a server based on the "key".

### For Server
1. Stores values with their keys into an internal HashTable.
2. Uses LRU to evict stale data.
3. Servers are unaware of each other. There is no crosstalk, no syncronization, no replication.
