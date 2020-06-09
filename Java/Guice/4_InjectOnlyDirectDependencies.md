# InjectOnlyDirectDependencies

Avoid injecting an object only as a means to get at another object. 
For example, don't inject a `Customer` as a means to get at an `Account`:

```java
public class ShowBudgets {

   private final Account account;

   @Inject
   ShowBudgets(Customer customer) {
       account = customer.getPurchasingAccount();
   }
}
```

Use this one:

```java
public class ShowBudgets {

   private final Account account;

   @Inject
   ShowBudgets(Account account) {
       this.account = account;
   }
}
```
