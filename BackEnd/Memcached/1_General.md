# General

## Homepage
https://memcached.org/

## What is Memcached?
Distributed memory object caching system.

## What it Does?
With traditional cache, each host must have same data in each memory considering to keep the cache **consistent**.
But each host can only use 64MB memory (for example).

With Memcached, all of hosts are looking into the same virtural pool of memory which can combine each usable memory.

Of course, it's better to have dedicated hosts only built to be Memcached servers.
