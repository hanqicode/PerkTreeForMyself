# Send Message
Link: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-send-message-with-attributes.html

Here is a simple code:
```java
final AmazonSQS client = AmazonSQSClientBuilder.defaultClient();

final String QUEUE_URL = "MyQueue' URL";
final String MESSAGE_BODY = "This is Qi's message";

final SendMessageRequest request = new SendMessageRequest();
request.setQueueUrl(QUEUE_URL);
request.setMessageBody(MESSAGE_BODY);

final SendMessageResult result = client.sendMessage(request);
System.out.println("SQS message ID: " + result.getMessageId());
```
