# Reserved Concurrency
Link: https://docs.aws.amazon.com/lambda/latest/dg/per-function-concurrency.html

## What is Reserved Concurrency?
To guarantee a function can always reach a certain level of concurrency.

## Why need Reserved Concurrency?
1. **Other functions cannot prevent your function from scaling** - 
All of your account's functions in the same region without reserved concurrency share the pool of unreserved concurrency.
Other functions can use up all of the available concurrency.
2. **Your function won't scale out of control** - 
It will also limit your function from using concurrency from the unreserved pool.
