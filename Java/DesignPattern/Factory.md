# Factory Design Pattern

## What is Factory pattern?
We can depend on the factory class only and let factory to provide appropriate handler for us.
So we can make code cleaner and replace switch case code.

## Example
Say we have a API class:
```java
public class API {
    private VideoHandler videoHandler;
    private TextHandler textHandler;
    private SoundHandler soundHandler;

    public void enact(Request request) {
        switch (request.getType()) {
            case "Video":
                videoHandler.process(request);
                break;
            case "Text":
                textHandler.process(request);
                break;
            case "Sound":
                soundHandler.process(request);
                break;
            default:
                break;
        }
    }
}
```

If we use Factory pattern here:
```java
public class API {
    private HandlerFactory handlerFactory;

    public void enact(Request request) {
        Handler handler = handlerFactory.getHandlerBasedOnType(request.getType());
        handler.process(request);
    }
}
```

See?
