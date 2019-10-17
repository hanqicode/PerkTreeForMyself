# Working With Java
Link: https://docs.aws.amazon.com/lambda/latest/dg/java-programming-model-handler-types.html

## Handler

The general syntax for the handler is as follows:
```java
outputType handler-name(inputType input, Context context) {
   ...
}
```

- InputType: can be event data or custom input.
- OutputType: 
  - Sync: can return using any of the supported data types.
  - Async: Should be `void`.
- InputType and OutputType can be:
  - Primitive Java types (String, int, etc.)
  - Predefined AWS event types (S3Event, KinesisEvent, etc.)
- Context:
  You can omit the `Context` object from the handler method signature if it isn't needed.
  
#### Leveraging Predefined Interfaces for Creating Handler
Link: https://docs.aws.amazon.com/lambda/latest/dg/java-handler-using-predefined-interfaces.html

It's provided by AWS Lambda Java Core Library.

## Context
Link: https://docs.aws.amazon.com/lambda/latest/dg/java-context-object.html

## Logging
Link: https://docs.aws.amazon.com/lambda/latest/dg/java-logging.html

1. System.out.println();
  - You can view the logs in CloudWatch.
2. Lambda Logger
  - Get it from `Context`. `LambdaLogger logger = context.getLogger();`
