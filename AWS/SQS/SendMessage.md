# Send Message
Link: https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-send-message-with-attributes.html

## Send Message Body
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
## Send Message Attributes
You can include structured metadata (such as timestamps, geospatial data, signatures, and identifiers) 
with messages using message attributes.

Here is a simple code:
```java
final AmazonSQS client = AmazonSQSClientBuilder.defaultClient();

final String QUEUE_URL = "MyQueue's URL";
final String MESSAGE_BODY = "This is Qi's second message";
final Map<String, MessageAttributeValue> messageAttributes = new HashMap<>();
messageAttributes.put("Name", new MessageAttributeValue()
                .withDataType("String").withStringValue("Qi")
);

final SendMessageRequest request = new SendMessageRequest();
request.setQueueUrl(QUEUE_URL);
request.setMessageBody(MESSAGE_BODY);
request.setMessageAttributes(messageAttributes);

final SendMessageResult result = client.sendMessage(request);
System.out.println("SQS message ID: " + result.getMessageId());
```
