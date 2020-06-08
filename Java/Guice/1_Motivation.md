# Motivation

## Normal Way
Normal way to use Dependency Injection with constructor:
```java
public class RealBillingService implements BillingService {

  private final CreditCardProcessor processor;

  public RealBillingService(CreditCardProcessor processor) {
    this.processor = processor;
  }

  public Receipt chargeOrder(PizzaOrder order, CreditCard creditCard) {
    try {
      ChargeResult result = processor.charge(creditCard, order.getAmount());

      return result.wasSuccessful()
          ? Receipt.forSuccessfulCharge(order.getAmount())
          : Receipt.forDeclinedCharge(result.getDeclineMessage());
     } catch (UnreachableException e) {
      return Receipt.forSystemFailure(e.getMessage());
    }
  }
}
```

In main function, we have to initialize `CreditCardProcessor` and pass it to `BillingService`:
```java
public static void main(String[] args) {
    CreditCardProcessor processor = new PaypalCreditCardProcessor();
    BillingService billingService = new RealBillingService(processor);
    ...
}
```

## With Guice
To use Guice, we first need to tell it how to map our interfaces to their implementations.
This is done in a Guice Module like below:

```java
public class BillingModule extends AbstractModule {
  @Override
  protected void configure() {
    bind(CreditCardProcessor.class).to(PaypalCreditCardProcessor.class);
    bind(BillingService.class).to(RealBillingService.class);
  }
}
```

Then for `RealBillingService`, we need to add `@Inject` to its constructor, which directs Guice to use it.
Guice will inspect annotated constructor and look up values for each parameter.

```java
public class RealBillingService implements BillingService {
  
  private final CreditCardProcessor processor;

  @Inject
  public RealBillingService(CreditCardProcessor processor) {
    this.processor = processor;
  }

  public Receipt chargeOrder(PizzaOrder order, CreditCard creditCard) {
    try {
      ChargeResult result = processor.charge(creditCard, order.getAmount());

      return result.wasSuccessful()
          ? Receipt.forSuccessfulCharge(order.getAmount())
          : Receipt.forDeclinedCharge(result.getDeclineMessage());
     } catch (UnreachableException e) {
      return Receipt.forSystemFailure(e.getMessage());
    }
  }
}
```

Finally, we need to register `BillingModule` in main function:
```java
public static void main(String[] args) {
    Injector injector = Guice.createInjector(new BillingModule());
    BillingService billingService = injector.getInstance(BillingService.class);
    ...
}
```

So if we have another class defined in `BillingModule`, we don't need to create a new instance in main function and we don't 
need to make any change. Because all of them are contained in `BillingModule`.
