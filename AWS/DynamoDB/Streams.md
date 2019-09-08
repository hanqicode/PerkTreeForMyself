# Working with Streams
Link: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html

DynamoDB Streams captures a time-ordered sequence of item-level modifications in any DynamoDB table 
and stores this information in a log for up to 24 hours.

A DynamoDB stream is an ordered flow of information about changes to items in a DynamoDB table.
When you enable a stream on a table, DynamoDB captures information about every modification to data items in the table.

## Data Retention Limit for DynamoDB Streams
All data in DynamoDB Streams is subject to a 24-hour lifetime.

However, data that is older than 24 hours is susceptible to trimming (removal) at any moment.

## Using Kinesis Adapter to Process Stream Records
Using the Amazon Kinesis Adapter is the recommended way to consume streams from Amazon DynamoDB.

You can write applications for Kinesis Data Streams using the Kinesis Client Library (KCL).
The KCL simplifies coding by providing useful abstractions above the low-level Kinesis Data Streams API. 
