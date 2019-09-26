# Receive Message
Link: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-receive-delete-message.html

Here is a simple code:
```java
final AmazonSQS client = AmazonSQSClientBuilder.defaultClient();

final String QUEUE_URL = "MyQueue";

final ReceiveMessageRequest request = new ReceiveMessageRequest();
request.setQueueUrl(QUEUE_URL);

final List<Message> messages = client.receiveMessage(request).getMessages();
for (final Message message : messages) {
    System.out.println("Current message body: " + message.getBody());
}

// Delete the first(index of 0) message received
final String messageReceiptHandle = messages.get(0).getReceiptHandle();
client.deleteMessage(QUEUE_URL, messageReceiptHandle);
```
