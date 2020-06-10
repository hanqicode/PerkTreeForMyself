# Guice with Lombok

It may be cumbersome to write constructor manually with following 
[Guice best practice](https://github.com/google/guice/wiki/Injections):

```java
public class ShowBudgets {

   private final Account account;

   @Inject
   ShowBudgets(Account account) {
       this.account = account;
   }
}
```

We could use Lombok to generate constructor for us:

```java
@AllArgsConstructor(onConstructor = @__({ @Inject }))
public class ShowBudgets {

   private final Account account;
}
```
