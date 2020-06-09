# Avoid Conditional Logic In Modules

It’s tempting to create modules that have moving parts and 
can be configured to operate differently for different environments:

```java
public class FooModule extends AbstractModule {

  private final String fooServer;

  public FooModule() {
    this(null);
  }

  public FooModule(@Nullable String fooServer) {
    this.fooServer = fooServer;
  }

  @Override 
  protected void configure() {
    if (fooServer != null) {
      bind(String.class).annotatedWith(named("fooServer")).toInstance(fooServer);
      bind(FooService.class).to(RemoteFooService.class);
    } else {
      bind(FooService.class).to(InMemoryFooService.class);
    }
  }
}
```

In this example, the author intends to use `InMemoryFooService` in development and `RemoteFooService` in production.
So it cannot be fully tested in development.
