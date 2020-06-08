# Motivation

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
