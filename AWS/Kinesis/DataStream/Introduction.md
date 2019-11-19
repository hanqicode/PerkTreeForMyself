# Introduction

## What is Amazon Kinesis Data Stream?
[Introduction](https://docs.aws.amazon.com/streams/latest/dev/introduction.html)

### Data Stream
A Kinesis data stream is a set of shards.

Each shard has a sequence of data records.

A data record is the unit of data stored in a Kinesis data stream. 
Data records are composed of a sequence number, a partition key, and a data blob, which is an immutable sequence of bytes.

When an application puts data into a stream, it must specify a partition key.  
It uses the partition key that is associated with each data record to determine which shard a given data record belongs to.

Each data record has a sequence number that is unique per partition-key within its shard.  
Kinesis Data Streams assigns the sequence number after you write to the stream

### Producer
A producer puts data records into Amazon Kinesis data streams.

To put data into the stream, you must specify the name of the stream, a partition key, 
and the data blob to be added to the stream.

The partition key is used to determine which shard in the stream the data record is added to.  
The number of partition keys should typically be much greater than the number of shards. 
This is because the partition key is used to determine how to map a data record to a particular shard. 
If you have enough partition keys, the data can be evenly distributed across the shards in a stream.

### Consumer
A consumer, known as an Amazon Kinesis Data Streams application, 
is an application that you build to read and process data records from Kinesis data streams.

An Amazon Kinesis Data Streams application commonly runs on a fleet of EC2 instances.

### Kinesis Client Library
The Kinesis Client Library is compiled into your application to enable fault-tolerant consumption of data from the stream. 

### Limits
Like most AWS APIs, Kinesis Data Streams API operations are rate-limited.
If you encounter API throttling, we encourage you to request a 
[limit increase](https://docs.aws.amazon.com/streams/latest/dev/service-sizes-and-limits.html).

## Terminology and Concepts
[Concepts](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)

This is a high level overview of using Kinesis data stream:

<img src="https://github.com/hanqicode/PerkTreeForMyself/blob/master/AWS/Kinesis/DataStream/Pictures/HighLevel.png" alt="drawing" width="800"/>

## With Lambda
[Reference](https://docs.aws.amazon.com/lambda/latest/dg/with-kinesis.html)

## Difference with SQS
[See: when should I use Kinesis/SQS?](https://aws.amazon.com/kinesis/data-streams/faqs/)

From input view:
- If input is enough, then we can use Kinesis firehose to process data and push to other places.
- If input is not enough, then we need use Lambda to get data from other places to process.

From output view:
- If there is only one consumer, then SQS is enough;
- If there are multiple consumers, then Kinesis could provide a feature that all consumers can read data and won't delete data after reading.
- But SNS + multiple SQS can provide solution to multiple consumers.

From re-read view:
- Kinesis can be re-read.
- SQS cannot be re-read.

From scaling view:
- Kinesis cannot scale automatically.
- SQS can scale automatically. (Especially when we cannot estimate the peak TPS.)
> A single Kinesis shard can ingest up to 1 MiB of data per second (including partition keys) or 1,000 records per second for writes.  
> A megabyte(MB) is then 1,000,000 bytes. A mebibyte(MiB) is the actual 1,048,576 bytes that most intend.

From category view:
- Kinesis provides shards to category data from input.
- SQS doesn't have it.

From order view:
- Kinesis shard provide `sequence number` for ordering the data.
- SNS + SQS cannot use FIFO queue.
> Amazon SNS is NOT compatible with FIFO queues.
