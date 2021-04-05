# Get Started

[Getting Started with Building a RESTful Web Service](https://spring.io/guides/gs/rest-service/)

## Action Items
1. Generate a new project with Spring Initializer with the required dependency (Spring Web, Lombok);
2. Create a Resource Representation Class: Greeting in POJO;
3. Create a Resource Controller;
4. Test the Service;

## Code Reference
1. Greeting class
```java
@Value
public class Greeting {
    int id;
    String content;
}
```
2. Controller
```java
@RestController
public class GreetingController {

    private static final String TEMPLATE = "Hello, %s!";

    @GetMapping("/greeting")
    public Greeting greeting(@RequestParam(value = "name", defaultValue = "world") String name) {
        return new Greeting(1, name);
    }
}
```

## Annotations
1. `@GetMapping`: ensures that HTTP GET requests to `/greeting` are mapped to the `greeting()` method;
2. `@RequestParam` binds the value of the query string parameter;
3. `@RestController` marks the class as a controller where every method returns a domain object instead of a view; It is shorthand for including both `@Controller` and `@ResponseBody`.
4. This web application is 100% pure Java and you did not have to deal with configuring any plumbing or infrastructure. No `web.xml` file!
