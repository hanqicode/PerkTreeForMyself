# Configuring messages arriving in SQS queue to trigger Lambda function
Link: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-configure-lambda-function-trigger.html

Lambda functions let you run code without provisioning or managing a server. 

## Note
1. FIFO queues do **NOT** support Lambda function triggers.
2. You can associate only one queue with one or more Lambda functions.
