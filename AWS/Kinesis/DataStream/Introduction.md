# Introduction

## What is Amazon Kinesis Data Stream?
[Introduction](https://docs.aws.amazon.com/streams/latest/dev/introduction.html)

### Data Stream
Amazon Kinesis Data Streams ingests a large amount of data in real time, durably stores the data,
and makes the data available for consumption.

The unit of data stored by Kinesis Data Streams is a *data record*. 
A *data stream* represents a group of data records. 
The data records in a data stream are distributed into *shards*.

A shard has a sequence of data records in a stream.

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

### Limits
Like most AWS APIs, Kinesis Data Streams API operations are rate-limited.
If you encounter API throttling, we encourage you to request a 
[limit increase](https://docs.aws.amazon.com/streams/latest/dev/service-sizes-and-limits.html).

## Terminology and Concepts
[Concepts](https://docs.aws.amazon.com/streams/latest/dev/key-concepts.html)

This is a high level overview of using Kinesis data stream:

<img src="https://github.com/hanqicode/PerkTreeForMyself/blob/master/AWS/Kinesis/DataStream/Pictures/HighLevel.png" alt="drawing" width="800"/>
