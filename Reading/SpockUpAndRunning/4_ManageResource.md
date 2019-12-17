# Managing Resources

## Testing a Persistence Layer
`DataStore` is an object to wrap a database connection.

A **database connection** is a classic example of a managed resource that needs to be acquired and disposed of correctly.

## Test Leakage
A very important feature of any unit test is that it should be idempotent.

That is to say, the test should produce the same result regardless of whether it is run alone or with other tests in a suite and regardless of the order in which the tests in that suite are run.

When side effects from a test affect subsequent tests in the suite, we can describe that test as leaking.

## Annotations
`@Subject`: claim the target to be tested. This annotation has only informational purposes.

`@Shared`: Instead of being reinitialized before each feature method is run they are initialized only once. -  when the specification is created, before the first feature method is run. 
