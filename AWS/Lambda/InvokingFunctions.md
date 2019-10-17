# Invoking Functions
Link: https://docs.aws.amazon.com/lambda/latest/dg/lambda-invocation.html

## Synchronous Invocation
Lambda runs the function and waits for a response.

## Asynchronous Invocation
Lambda sends the event to a queue. A separate process reads events from the queue and runs your function.

When the event is added to the queue, Lambda returns a success response without additional information.

## Event Source Mapping
This is Lambda resource that reads from an event source and invokes a function.

Lambda can read events from:
1. Kinesis
2. DynamoDB
3. SQS

## Scaling
Lambda will create another instance when more events come in.

When requests come in faster than your function can scale, or when your function is at maximum concurrency,
additional requests fail with a throttling error (429 status code).
When you invoke your function directly, you should treat this as a retryable error.
