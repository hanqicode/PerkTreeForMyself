# Publish Message

Here is a simple code for how to publish SNS message.

```java
final AmazonSNS client = AmazonSNSClientBuilder.standard().build();

final String topicArn = "Topic Arn Here";
final String msg = "Message here";

final PublishRequest request = new PublishRequest();
request.setTopicArn(topicArn);
request.setMessage(msg);

final PublishResult result = client.publish(request);
System.out.println("Published: " + result.getMessageId());
```
