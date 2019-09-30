# Message

## Message Attributes
Link: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-message-attributes.html

They are user custom metadata.

## Message System Attributes
Link: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-message-system-attributes.html



## Delete message
If you receive a message more than once, each time you get it, you get a different Receipt Handle.

You must provide the most recently received Receipt Handle when you request to delete the message.
