# Documentation

[Spring Boot Reference Documentation 2021.04.04](https://docs.spring.io/spring-boot/docs/2.4.4/reference/htmlsingle/#legal)

## Structuring Your Code
We generally recommend that you locate your main application class in a root package above other classes.;
```
com
 +- example
     +- myapplication
         +- Application.java
         |
         +- customer
         |   +- Customer.java
         |   +- CustomerController.java
         |   +- CustomerService.java
         |   +- CustomerRepository.java
         |
         +- order
             +- Order.java
             +- OrderController.java
             +- OrderService.java
             +- OrderRepository.java
```

The `Application.java` file would declare the main method, along with the basic `@SpringBootApplication`;

