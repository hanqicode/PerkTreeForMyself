# Amazon SQS Short and Long Polling
Link: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-short-and-long-polling.html

By default, Amazon SQS uses short polling, querying only a subset of its servers to determine whether any messages are 
available for a response.

## Consuming Messages Using Short Polling
SQS only query a subset of its servers. So a particular `ReceiveMessage` request might not return all of your messages.

## Consuming Messages Using Long Polling
When the wait time for `ReceiveMessage` API action is greater than 0, long polling is in effect.

It will query all SQS servers.
