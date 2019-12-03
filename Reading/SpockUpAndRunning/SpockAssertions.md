# Spock Assertions

## Good diagnostics
If the assertion fails I should be able to see very easily in test report. Just tell me "something is wrong."

This has been summarized in *0_Introduction*. Like:
```
Condition not satisfied:

util.twoSum(a, b) == 1
|    |      |  |  |
|    3      1  2  false
```

## For loop

```groovy
then:
    for (post in user.posts) {
        post.postedBy == user
    }
```
This will not work. It is in the nested scope of the loop, it is not converted into an assertion.

We should use:
```groovy
then:
    user.posts.every {
        it.postedBy == user
    }
```

## Expecting Exceptions
It's an important consideration when writing tests to not test only the *happy path*.
```groovy
then:
    thrown(UnsupportedOperationException)
```

`thrown` must apprea in a `then:` block.
