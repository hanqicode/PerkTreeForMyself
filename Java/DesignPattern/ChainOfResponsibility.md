# Chain of Responsibility Design Pattern

## What is Chain of Responsibility pattern?
In our service, there are a chain of handlers. A request coming in will be processed from beginning of the chain.  
If any of handler can process it, then return the result;  
Otherwise, pass the request to next handler.

## Example
Please recall the *CSContactAbuseService*, when a request coming in, it would check:  
1. IpWhitelistHandler
2. PhoneNumberWhitelistHandler
3. PhoneNumberBlacklistHandker
4. IpBlacklistHandler
5. etc.

So we can see how it works based on above example.

## Notes
Question: what is the difference of switch case and chain pattern?  
Answer: To me, if we can use switch case, we prefer to use it. At least, it is more clear and has less complexity.

Question: when should I use chain pattern?
Answer: To me, if we hava a list of handlers with **priority**, then we should consider it. *CSContactAbuseService* is really
a good example.
