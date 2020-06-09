# Minimize Mutability

Wherever possible, use constructor injection to create immutable objects.

Follow below pattern:
```java
public class RealPaymentService implements PaymentService {

   private final PaymentQueue paymentQueue;
   private final Notifier notifier;

   @Inject
   RealPaymentRequestService(PaymentQueue paymentQueue,
                             Notifier notifier) {
       this.paymentQueue = paymentQueue;
       this.notifier = notifier;
   }

   ...
}
```

We can see: class members have `final`.
