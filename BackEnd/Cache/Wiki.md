# Wikipedia about Cache(computing)

## Terminology
**Cache**: is a hardware/software that stores data so that future requests can be served faster,
the data stored in cache might be the result of an earlier computation or a copy of data stored in disk.

**Hit**: requested data can be found in a cache.

**Miss**: requested data cannot be found in a cache.

**Replacement Policy**: when there is a cache miss, some other previously existing cache entry is removed in order to
make room for the newly retrieved data. For example: least recently used (LRU).

## Motivation
There are two aspects:

### Latency
A larger resource incurs a significant latency for access.
1. It may take several layers to calcuate the result.
2. It may take much time to find the data in memory/disk.

### Throughput
The use of a cache allows for higher throughput.

## Examples

### CPU cache (hardware)
Small memories on or close to CPU can operate faster than main memory.

### Web cache (software)
Web browsers employ web caches to store previous responses from web servers, like web pages and images.
Web caches reduces the amount of information that needs to be transmitted across the network.

### Memorization (software)
A cache can store data that is computed on demand rather than retrieved from a backing store.
It allows subsequent calls to reuse the stored results and avoid repeated computation. 

It is related to the **dynamic programming** algorithm design methodology.
