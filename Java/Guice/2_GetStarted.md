# Getting Started

## Core Guice Concepts

### @Inject Constructor
Guice will create constructors' arguments.

```java
class Foo {
    private final String message;
    private final int count;
    
    @Inject
    Foo(String message, int count) {
        this.message = message;
        this.count = count;
    }
}
```

### Guice Module
How does Guice know which `message` and `count` should it pass to `Foo` class? By Guice Module!

```java
class DemoModule extends Abstract Module {
    
    @Provides
    static Integer provideCount() {
        return 3;
    }
    
    @Provides
    static String provideMessage() {
        return "Hello world";
    }
}
```

### Guice Injectors
Then how does JVM know those Guice Modules and run them before real application? By Guice Injectors!

```java
public class WebServer {
    public static void main(String[] args) {
        Injector injector = Guice.createInjector(
            new AuthenticationModule();
            new UserModule();
            new EmailModule();
            // omit other modules here
        );
        
        injector.getInstance(WebServer.class).start();
    }
    
    public void start() {
        // run the service
    }
}
```
