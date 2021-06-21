# Transactions

## Multiuser Databases
If some of the users are adding and/or modifying data, however, the server must handle quite a bit more bookkeeping.

### Locking
Locks are the mechanism the database server uses to control simultaneous use of data resources.
Most database servers use one of two locking strategies:
1. Database writers must request and receive from the server a write lock to modify data, and database readers must request and receive from the server a read lock to query data. While multiple users can read data simultaneously, only one write lock is given out at a time for each table (or portion thereof), and read requests are blocked until the write lock is released.
2. Database writers must request and receive from the server a write lock to modify data, but readers do not need any type of lock to query data. Instead, the server ensures that a reader sees a consistent view of the data (the data seems the same even though other users may be making modifications) from the time her query begins until her query has finished. This approach is known as *versioning*.

The first approach can lead to long wait times if there are many concurrent read and write requests, 
and the second approach can be problematic if there are long-running queries while data is being modified.

### Lock Granularities
- Table locks
- Page locks
- Row locks

## What is a Transaction?
A device for grouping together multiple SQL statements such that either all or none of the statements succeed (a property known as **atomicity**).

### Starting a Transaction
//
