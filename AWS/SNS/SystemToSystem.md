# System-to-System Messaging
Link: https://docs.aws.amazon.com/sns/latest/dg/sns-system-to-system-messaging.html

There are several other services integrated SNS well.

## AWS Lambda
When a message is published to an SNS topic that has a Lambda function subscribed to it, 
the Lambda function is invoked with the payload of the published message.
 
The Lambda function receives the message payload as an input parameter and can manipulate the information in the message, 
publish the message to other SNS topics, or send the message to other AWS services.
 
## AWS SQS
Link: https://docs.aws.amazon.com/sns/latest/dg/sns-sqs-as-subscriber.html

### Why we often use `SNS -> SQS` pattern?
It is related to their use cases:
- SNS: Fanout - Means allowing same message to be processed in multiple ways.
- SQS: Decoupling two applications and allowing parallel asynchronous processing.

So we can use SNS to push message to many SQS queues and decouple with dependencies.

Also, it allows clients to be offline, tolerant to network and host failures, which achieves guaranteed delivery.

## HTTP/S Endpoint
Link: https://docs.aws.amazon.com/sns/latest/dg/sns-http-https-endpoint-as-subscriber.html
